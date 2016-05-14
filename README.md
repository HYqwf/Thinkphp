# Thinkphp
对于Thinkphp中U方法的使用：
    U方法用于完成对URL地址的组装，特点在于可以自动根据当前的URL模式和设置生成对应的URL地址，格式为：
    U('地址','参数','伪静态',...);
U使用实例：
    U('User/checked') //User模块下的checked操作
    U('Admin/User/add') // 生成Admin分组的User模块的add操作地址
    
    除了分组、模块和操作名之外，我们也可以传入一些参数：
    U('Blog/edit?id=1') // 生成Blog模块的edit操作 并且id为1的URL地址
    
    U方法的第二个参数支持传入参数，支持数组和字符串两种定义方式，如果只是字符串方式的参数可以在第一个参数中定义，下面几种方式都是等效的：
    U('Blog/cate',array('cate_id'=>1,'status'=>1))
    U('Blog/cate','cate_id=1&status=1')
    U('Blog/cate?cate_id=1&status=1')


为啥使用U方法：在模板中使用U方法而不是固定写死URL地址的好处在于，一旦你的环境变化或者参数设置改变，你不需要更改模板中的任何代码。

U方法使用注意事项：
    U方法传参时，是使用get的方式，所以接收参数时不能用$_POST、I方法，可以使用$_REQUEST，只是$_REQUEST接收速度慢。
    在与form表单一块使用时，更要注意method是什么方式。
