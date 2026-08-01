project module package class
main方法是执行入口，
//*变量： 数据类型 变量名称 = 数量； int age = 18；
给变量开辟一块内存，并且赋值，
数据在计算机最小储存单元，字节b 一个字节8个b，1kb=1024b，1mb=1024kb，1g=1024mb，1t=1024gb
char ch ='A';八进制以0开头，16进制以ox开头 2进制以ob开头
byte 1个字节，kb mb gb  tb 1024
整型byte short int（默认） long 浮点数（小数) float double(默认） 字符型char 布尔型boolean true false
keywords：关键字  标识符：字母数字下划线美元
*/
变量名：首字母小写， 类名首字母大写 驼峰模式。
 ＋符号在Java中的特殊用法，做连接符，结果是字符串，能算就算，不能算就连接在一起，两个整数除法，结果一定是整数，最高类型是整数 %这个是取余数的
自增：++ 放在某个变量前面或者后面，对变量自身值加一
自减：-- 放在某个变量前面或者后面，对变量自身值减一
int a =10;
int rs =++a;
在变量前面，先对变量自增或者自减，再使用变量。在变量后面，在变量后面，变量先赋值，在进行自增或者自减
赋值运算符：="从右往左看 
+- a+=b 加后赋值 a=（a的类型）（a＋b）
关系运算符：>< >=等等 ==相等 =赋值 ！=不等于 布尔类型返回值是true false
三元运算符：条件表达式？值1：值2；
与 两者都要成立 或 二选一成立 两者都是假才是假 非 取反成立 异或 两者是相同条件就是假 两者一真一假就是真
短路与＆＆ 2》10 ＆＆3》2 判断结果和＆一样，左边为false，右边不执行 短路或11 2》1 判断结果与1一样，左边为true 右边不执行
switch分支结构是比较值是否相等，来界定执行那条分支
switch（表达式）{
case1：
执行代码；
break；
case2；
执行代码....;
break;
default:
执行代码；
}
switch表达式类型只能是byte、short、int、char、string、不支持double、float、long 
case的值只能用字面量不能用变量，正常写switch要加break，否则就会出现穿透现象
当存在多个case分支代码一样的时候，可以把代码写到一个case，其他case通过穿透case块，可以简化代码
for循环（初始化语句；循环条件；迭代语句；）{
循环体语句；
}目标：减少代码的重复填写，灵活控制程序执行。 
while循环写法：初始化语句；while（循环条件）{
循环体；
迭代语句
}
package com.itheima.loop;

        public class WhileTest5 {
            public static void main(String[] args) {
                System.out.println("需要的年数："+cale());

            }
            public  static int cale(){
                double money = 100000;
        double rate = 0.017;
        int year =0;
        while(money < 200000 ){
            year ++;
            money =money*(1+rate);
        }
        return  year;
    }
}
do——while循环
初始化语句；
do{
循环体语句；
迭代语句；
} while（循环条件）；
死循环就是一直循环下去，不停
循环嵌套 外部循环每循环一次，内部循环就要跑一把
System.out.print("x")	打印内容后不换行	连续输出同一行（如矩阵行）
System.out.println("x")	打印内容后自动换行	输出完整一行后换行
break：跳出并结束当前循环的执行，continue是用于跳出当前循环的当此执行，直接进入循环下一个
math回返回（0，1）的小数


生成随机数验证码：定义一个for循环，循环5次；随机生成012的数据，依次代表当前生成的字符是数字、大写字母、小写字母。；把012交给switch生成对应类型的随机字符；在循环外定义一个string类型变量用来连接生成随机字符；循环结束以后返回string类型即生成的验证码
package com.itheima.demo;

public class Test3 {
    public static void main(String[] args) {
        //目标：开发验证码
        System.out.println(getCode(4));



    }
    public static String getCode(int n) {
        String code = "";
        for (int i = 0; i < n; i++) {
            int number = (int)(Math.random()*3);
            switch (number){
                case 0:
                int number1 = (int)(Math.random()*10);
                code += number1;
                 break;
                case 1:
                int number2 = (int)(Math.random()*26);
                char ch= (char)(65+number2);
                code += ch;
                 break;
                case 2:
                 int number3 = (int)(Math.random()*26);
                 char ch2= (char)(97+number3);
                 code += ch2;
                 break;


            }

        }
        return code;

    }


}
