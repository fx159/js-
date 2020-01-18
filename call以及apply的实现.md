1.call

call的模拟实现主要分为三步

1.1： 设置传入的参数是带有修改this指向的函数

1.2：执行该函数

1.3：修改该函数

具体代码：

Function.prototype.call2=function(context){

 //判断是否传参，没有传参使用window作为this

  var context=context||window;

//获取调用当前call方法的函数

  context.fn=this;

  var arr=[];

  for(var i=1;i++;i<arguments.length){

//

   arr.push(`arguments[${i}]`)

  };

//执行当前方法

  var result=context.fn(...arr);

//删除属性

  delete context.fn;

return result

}

2.apply方法类似





