1.call<br>

call的模拟实现主要分为三步<br>

1.1： 设置传入的参数是带有修改this指向的函数<br>

1.2：执行该函数<br>

1.3：修改该函数<br>

具体代码：<br>

Function.prototype.call2=function(context){<br>

 //判断是否传参，没有传参使用window作为this<br>

  var context=context||window;<br>

//获取调用当前call方法的函数<br>

  context.fn=this;<br>

  var arr=[];<br>

  for(var i=1;i++;i<arguments.length){<br>

//<br>

   arr.push(`arguments[${i}]`)<br>

  };<br>

//执行当前方法<br>

  var result=context.fn(...arr);<br>

//删除属性<br>

  delete context.fn;<br>

return result<br>

}<br>

2.apply方法类似





