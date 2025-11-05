==1. Code to print number reverse pyramid==  
1234  
567  
89  
10
 
public static void main(String[] args) {  
int count1=1;  
for(int i=0;i\<4;i++)  
{  
for(int j=0;j\<4-i;j++)  
{  
System.out.print(count1);  
System.out.print("\t");  
count1++;  
}   System.out.println("");  
}  
}  
==2.Code to print number pyramid==  
1  
23  
456  
78910  
public static void main(String[] args) {  
int count1=1;  
for(int i=0;i\<4;i++)  
{  
for(int j=0;j\<=i;j++)  
{  
System.out.print(count1);  
System.out.print("\t");  
count1++;  
}   System.out.println("");  
}  
}  
==3. Program to print below pattern==  
1  
12  
123  
1234  
public static void main(String[] args) {  
for(int i=1;i\<=4;i++)  
{  
for(int j=1;j\<=i;j++)  
{  
System.out.print(j);  
}  
System.out.println();  
}  
}  
==4. Program to print below pattern==  
3  
6 9  
12 15 18  
21 24 27 30  
public static void main(String[] args) {  
int count=0;  
for(int i=1;i\<=4;i++)  
{  
for(int j=1;j\<=i;j++)  
{count++;  
System.out.print(3*count);  
System.out.print("\t");  
}  
System.out.println();  
}  
}  
**5. Program to take input from the user** 
import java.util.Scanner;  
class HelloWorld {  
public static void main(String[] args) {   Scanner scan = new Scanner(System.in);  
System.out.println("Enter your name");  
String name=scan.nextLine();  
System.out.println("Enter your age");  
int age=scan.nextInt();  
System.out.println("Your name is:"+name);  
System.out.println("Your age is:"+age);  
}  
}  
==6.Write a program to Reverse a string==  
public class reverse_of_string
 
{public static void main(String[] args) {  
String str = "Hello World";  
String ostr="";  
for(int i=str.length()-1;i\>=0;i--) //-1 because string indexing in Java is zero-based. If length is 11 then i will be between 0 to 10.  
{  
ostr=ostr+str.charAt(i);  
}  
System.out.println(ostr);  
}  
}  
==7.Write a program to swap the numbers without using extra variable==  
public static void main(String[] args) {   Scanner scan = new Scanner(System.in);   int x=scan.nextInt();//10  
int y=scan.nextInt();//5  
System.out.println("Number before swap x="+x+"y ="+y);  
x=x+y;//15  
y=x-y;//15-5=10  
x=x-y;//15-10=5  
System.out.println("Number after swap will be x:"+x +" y:"+y);  
}

1. ==Write a program to find the highest number from a given input array==

import java.util.Scanner;  
public class testing {  
int[] arr = new int[5];  
//int max;  
for(int i=0;i\<5;i++)  
{  
arr[i]=scan.nextInt();  
}  
int max=arr[0];  
for(int j=0;j\<arr.length;j++)  
{   if(max\<arr[j])  
{  
max=arr[j];  
}  
}  
}

3. ==Program to add two number using function==￼

class HelloWorld {  
public static int add(int a,int b)  
{  
return a+b;  
}  
public static void main(String[] args) {  
System.out.println(add(1,3));   }  
}

5. ==Program to find minimum number in a matrix==

public static void main(String[] args) {  
System.out.println("Given matrice: ");  
{7,4,3},  
{8,7,9}  
};  
for(int i=0;i\<3;i++)  
{  
for(int j=0;j\<3;j++)  
{  
System.out.print(arr[i][j]+"\t");  
//System.out.print()  
}  
System.out.println();  
}  
int min=arr[0][0];  
for(int i=0;i\<3;i++)  
{  
for(int j=0;j\<3;j++)  
{  
if(min\>arr[i][j])  
{  
min=arr[i][j];  
}  
}  
}  
System.out.println("Minimum number is: "+min);   }

7. ==Program to sort numbers in an array==￼

public class Main {  
public static void sorting(int arr[]) {  
int temp;  
for (int i = 0; i \< arr.length - 1; i++) { // Loop until the second-to-last element  
for (int j = i + 1; j \< arr.length; j++) {  
if (arr[i] \> arr[j]) {  
// Swap arr[i] and arr[j]  
temp = arr[i];  
arr[i] = arr[j];  
arr[j] = temp;  
}  
}  
}  
}
 
public static void main(String[] args) {  
int a[] = {7, 2, 5, 3, 4, 1};  
sorting(a);  
for (int i = 0; i \< a.length; i++) {  
System.out.print(a[i] + " "); // Print sorted array  
}  
}  
}

11. ==Program to showcase different functions of string class.==￼

public class Main {  
public static void main(String[] args) {  
String greeting = "Hello, World!";   ==// Length of the string==  
System.out.println("Length: " + greeting.length());//we use length() function in case of string and length keyword in case of an array.   ==// Concatenation==  
String name = "Alice";  
String message = greeting + " My name is " + name;  
System.out.println(message);   ==// Substring==  
String sub = greeting.substring(7, 12);//prints number between 7th and 12th index  
System.out.println("Substring: " + sub);  
System.out.println(greeting.substring(5));//prints string from 5th index to the last index.   ==// Character at index==  
char ch = greeting.charAt(0);  
System.out.println("Character at index 0: " + ch);  
==//Index of==System.out.println(greeting.indexOf("x"));//it will search index of character e and in this case it will return -1 as there is no character "x" in greeting string.  
==// Convert to upper case==  
String upper = greeting.toUpperCase();  
System.out.println("Uppercase: " + upper);   ==// Replace==  
String replaced = greeting.replace("World", "Java");//replaces word "World" with "Java"  
System.out.println("Replaced: " + replaced);   ==// Split==  
String csv = "apple,banana,cherry";  
String[] fruits = csv.split(",");//Splits the string on the basis of ",".  
System.out.println("Fruits: " + String.join(", ", fruits));  
==//Trim==System.out.println(greeting.trim());// this will removes white spaces from the string.  
}  
}
 
public static void main(String[] args) {
  Scanner scan = new Scanner(System.in);  
System.out.println(max);  
}  
int arr[][]={  
{3,4,6},