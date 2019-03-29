# douban-demo1
豆瓣获取图片有限制，报错403，添加下列标签解决
<meta name="referrer" content="never"> /*  豆瓣API访问图片403的解决方案 */


获取豆瓣api接口
 $.ajax({
          url:'http://api.douban.com/v2/movie/top250',
          type:'GET',
          data:{
            start:index,
            count:20
          },
          dataType:'jsonp'
        }).done(function(ret){
          console.log(ret)
          setData(ret)
          index+=20
        }).fail(function(){
          console.log('error...')
        })


滚动更新监听，当鼠标滚动到离main底部还有10px时更新加载，好处是可以提前加载，速度更快，当然在没有滚动的情况下不加载更新，可以省力。
 $('main').scroll(function(){ 
          if($('section').eq(0).height()-10 <= 
          $('main').scrollTop() + $('main').height()){
        start()
      }
      })
      
      main 高度设置，及手机端的弹性滚动效果设置
       main{
        height:calc(100vh - 50px);
        overflow: scroll;
        -webkit-overflow-scrolling: touch; /* ios5+ 弹性滚动 */
      }
      
