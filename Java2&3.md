# 练习题  
## 手机类  
```java
class MyPhone1{
	/* 
    手机事物： 
     属性：品牌，价格，颜色 
     行为：打电话、发短信、玩游戏 
    手机类： 
     成员变量：品牌、价格、颜色 
     成员方法：打电话、发短息、完游戏 
   */ 
		String brand;
		int price;
		String color;
		public static void call(String name){
			System.out.println("今晚必须约"+name+"出来谈一谈。");
		}
		public static void message(int phoneNumber){
			System.out.println("发信息给"+phoneNumber);
		}
		public static void game(){
			System.out.println("玩游戏");
		}	
}
class MyPhone{
	public static void main(String[] args){
		MyPhone1 mp = new MyPhone1();
		System.out.println(mp.brand);
		System.out.println(mp.color);
		System.out.println(mp.price);
		mp.call("劳森");
		mp.message(10086);
		mp.game();
	}
}
```
##　学生类　　
```java
class Student{ 
  //定义变量 
  //姓名 
  String name; 
  //年龄 
  int age; 
  //地址 
  String address; 
 
  //定义方法 
  public void study(){ 
   System.out.println("学生爱学习 "); 
  } 
  //吃饭的方法 
  public void eat(){ 
   System.out.println("学生饿了，要吃饭 "); 
  } 
  //睡觉的方法 
  public void sleep(){ 
   System.out.println("学生累了，要睡觉 "); 
  } 
} 
class StudentDemo{
	public static void main(String[] args){
		Student stu = new Student();
		System.out.println("姓名："+stu.name);
		System.out.println("年龄："+stu.age);
		System.out.println("地址："+stu.address);
		stu.study();
		stu.eat();
		stu.sleep();
	}
}
```
## 手机类2
```java
/*定义手机类
成员变量： brand,price,color
构造方法：无参构造
成员方法： getXxx()/setXxx()
 */
class MyPhonet{
	private String brand;
	private int price;
	private String color;
	MyPhonet(){}
	public String getBrand(){
		return brand;
	}
	public int getPrice(){
		return price;
	}
	public String getColor(){
		return color;
	}
	public void setBrand(String brand){
		this.brand = brand;
	}
	public void setPrice(int price){
		this.price = price;
	}
	public void setColor(String color){
		this.color = color;
	}

}
public class MyPhoneSecond {

	public static void main(String[] args){
		MyPhonet m3 = new MyPhonet();
		m3.setBrand("华为");
		m3.setColor("黑色");
		m3.setPrice(4999);
		System.out.println("品牌是："+m3.getBrand()+"  机型颜色："+m3.getColor()+"  专柜价："+m3.getPrice());
	}

}

```
## 长方形
```java
/*练习题：定义一个长方形的类，求周长和面积
长方形的类：
	成员变量：
	成员方法：
		求周长： (长+宽)*2
		求面积： (长*宽)
*/
import java.util.Scanner;
class rectangleTest{
	private static int length;
	private static int width;
	
	public int getWidth(){
		return width;
	}
	public void setWidth(int width){
		this.width = width;
	}
	public int getLength(){
		return length;
	}
	public void setLength(int length){
		this.length = length;
	}
	public int area(){
		return length*width;
	}
	public int perimeter(){
		return 2*(length+width);
	}
	public rectangleTest(){
		System.out.println("长方形测试类开始啦");
	}
}
class Rectangle{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.print("请输入长方形的长：");
		int L = sc.nextInt();
		System.out.print("请输入长方形的宽：");
		int W = sc.nextInt();
		rectangleTest rt = new rectangleTest();
		rt.setLength(L);
		rt.setWidth(W);
		System.out.println("面积："+rt.area()+"周长："+rt.perimeter());
	}
}
```
## 员工类
```java
import java.util.Scanner;
/*练习题：定义一个员工类，自己分析出几个成员然后给出成员变量，
构造方法， getXxx()/setXxx()方法以及一个显示所有成员信息的方法，并测试。
分析：
	员工
	成员变量：
		员工编号、姓名、年龄
	构造方法：
		无参构造方法
		成员方法：
			getXxx()/setXxx()方法
			show();
*/
class EmployeeTest{
	private int number;
	private String name;
	private int age;
	public EmployeeTest(){}
	public int getNumber(){
		return number;
	}
	public String getName(){
		return name;
	}
	public int getAge(){
		return age;
	}
	public void setNumber(int number){
		this.number = number;
	}
	public void setName(String name){
		this.name = name;
	}
	public void setAge(int age){
		this.age = age;
	}
	public void show(){
		System.out.println("该员工的编号："+number+"、名字："+name+"、年龄："+age+"。");
	}
}
class Employee{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.print("请输入员工编号：");
		int sNumber = sc.nextInt();
		System.out.print("请输入员工姓名：");
		String sName = sc.next();
		System.out.print("请输入员工年龄：");
		int sAge = sc.nextInt();
		EmployeeTest et = new EmployeeTest();
		et.setNumber(sNumber);
		et.setName(sName);
		et.setAge(sAge);
		et.show();
	}
}
```
## 数学类
```java
package sen;
import java.util.Scanner;
/*练习题：定义一个My Math类，提供基本的加减乘除功能，然后进行测试  */ 
class count{
	private int a;
	private String b;
	private int c;
	count(){}
	public void result(String str){
		int x = 0;
		for(int i = 0;i<str.length();i++){
			if(str.substring(i,i+1).equals("+")){	
				b="+";x = i;
			}else if(str.substring(i,i+1).equals("-")){	
				b="-";x = i;
			}else if(str.substring(i,i+1).equals("*")){	
				b="*";x = i;
			}else if(str.substring(i,i+1).equals("/")){	
				b="/";x = i;
			}
		}
		a = Integer.parseInt(str.substring(0,x));
		c = Integer.parseInt(str.substring(x+1,str.length()));
		if(b.equals("+")){	
			System.out.println("结果为："+(a+c));
		}else if(b.equals("-")){	
			System.out.println("结果为："+(a-c));
		}else if(b.equals("*")){	
			System.out.println("结果为："+(a*c));
		}else if(b.equals("/")){	
			System.out.println("结果为："+(a/c));
		}else{
			System.out.print("输入格式有误！");
		}
	}
}
public class MyMath {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入待计算等式，如‘1+1’：");
		String a = sc.next();
		count c = new count();
		c.result(a);

	}

}

```
## 数字游戏
```java
import java.util.Scanner;
/* 
猜数字小游戏（数据在1-200之间） 

分析： 
 A：程序产生一个随机数(被猜的)
 B：键盘录入数据（你猜的） 
 C：把你猜的和被猜的进行比较 
  a:大了 
  b:小了 
  c:猜中了 
  D：给出多次猜的机会，猜中就结束 
  while()循环，猜中就break 
*/ 

public class HowMuch {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int number = (int) (Math.random()*200+1);
		while(true){
			int pr = sc.nextInt();
			if(pr>number){
				System.out.println("a");
			}else if(pr<number){
				System.out.println("b");
			}else if(pr==number){
				System.out.println("c");
			}
		}
	}
}

```
