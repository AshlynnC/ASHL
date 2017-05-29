#第一题  
```java
/* 
  需求：实例公司年销售额求和某公司按照季度和月份统计的数据如下：单位（万元） 
   第一季度：22,66,44 
   第二季度：77,33,88 
   第三季度：25,45,65 
   第四季度：11,66,99 
  分析： 
   A：把题目的数据用二维数组表示： 
    int[][] arr={{22,66,44},{77,33,88},{25,45,65},{11,66,99}}; 
   B：如何求和呢？ 
    求和其实就是获得到每一个元素，然后累加即可。 
   C：定义一个求和变量sum,初始值为0； 
   D：通过遍历就可以得到每一个二维数组的元素。 
   E：把元素累加即可。 
   F：最后输出sum,即可。 
*/ 
public class sum{
	public static void main(String[] args){
		int[][] arr={{22,66,44},{77,33,88},{25,45,65},{11,66,99}}; 
		int sum = 0;
		for(int i = 0;i<arr.length;i++){
			for(int j = 0;j<arr[i].length;j++){
				sum+=arr[i][j];
			}
		}
	System.out.println(sum);
	}
}
```
#第二题
```java
/* 
  需求：实例打印杨辉三角形（行数可以键盘输入） 
   1 
   1 1 
   1 2 1 
   1 3 3 1  
   1 4 6 4 1 
   1 5 10 10 5 1 
  分析：看这种图像的规律 
   A：任何一行的第一列和最后一列都是1. 
   B：从第三行开始，每一个数据是它上一行的前一列和它上一行的本行之和。最后一列除外 
  步骤： 
     A：定义一个二维数组。行数如果是n,把列数也定义为n.这个n的数据来自键盘录入。 
     B：给这个二维数组任何一行的第一列和最后一列都是1. 
     C；按照规律给其他元素赋值从第三行开始，每一个数据是它上一行的前一列和它上一行的本行之和。最后一列除外 
     D:遍历这个二维数组 
*/ 
import java.util.Scanner;
public static class triangle{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		int len = sc.nextInt();
		int[][] arr=new int[len][len];
		assignment(arr,len);
		printArr(arr);
	}
	public static void assignment(int[][] arr,int x){
		int y = 1;
		for(int i = 0;i<x;i++){
			for(int j = 0;j<y;j++){
				if(i<1||j<1){
					arr[i][j]=1;
				}else if(i==j){
					arr[i][j] = 1;
				}else{
					arr[i][j] = arr[i-1][j-1]+arr[i-1][j];
				}
			}
			y+=1;
		}
	}
	public static void printArr(int[][] arr){
		for(int i = 0;i<arr.length;i++){
			for(int j = 0;j<=i;j++){
				System.out.print(arr[i][j]+"\t");
			}
			System.out.println();
		}
	}
}
```
#思考题2
```java
import java.util.Scanner;
public class encryption{
	public static void main(String[] args){
		System.out.println("请输入一串小于8位数的数字");
		Scanner sc = new Scanner(System.in);
		String s = sc.nextLine();
		int[] arr = new int[s.length()];
		arr[0] = (Integer.parseInt(s.substring(0,1))+5)%10;
		arr[s.length()-1] = (Integer.parseInt(s.substring(s.length()-1,s.length()))+5)%10;
		for(int i = 1;i<s.length()-1;i++){
			arr[i] = (Integer.parseInt(s.substring(s.length()-1-i,s.length()-i))+5)%10;
		}
		System.out.println("加密后的结果为：");
		for(int i = 0;i<arr.length;i++)
			System.out.print(arr[i]+"");
	}
}
```
![]:(http://a2.qpic.cn/psb?/V14Jweno0VJwc8/Xf72l.eZ*ng46D6HojMEoAyTr5N7RoGwGNwzqAPyPlo!/b/dGwBAAAAAAAA&bo=BQPKAQAAAAADB.8!&rf=viewer_4)
