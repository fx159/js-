function createnew(){
    const obj=Object.create(null);//创建一个空对象
    con=[].shift.call(arguments);//取出arguments的第一个元素，即传入的构造函数
    const Fun=function(){};//创建一个构建函数
    Fun.prototype=con.prototype;
    obj=new Fun();//让obj指向构造函数，这样就能访问传入的构造函数原型的属性
    con.apply(obj,arguments);//使用apply使obj的this指向构造函数，这样就能访问构造函数的属性
    return obj;//     返 回要创建的对象

}