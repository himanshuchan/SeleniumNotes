 - A java program can contain many java classes but it can atmost contain only one public class. Either one or zero public class is allowed.
- If the program does not have any public class then its name can be anything. But if it has a public class then it is compulsory to name it the same.
- If a class is not public then it is default i.e it is accessible to all within the package. Below all classess are acessible to each other.
- Once the below code is compiled like javac xyz.java four .class file will be generated. A.class , B.class,C.class,D.class .

class A  
{public static void main(){  
System.out.println("Inside class A main");  
}}  
class B  
{public static void main(){  
System.out.println("Inside class B main");  
}}  
class C  
{public static void main(){  
System.out.println("Inside class C main");  
}}  
class D  
{public static void main(){  
System.out.println("Inside class D main");  
}}

- import java.util.ArrayList;// Explicit import- this is more preferred because it increases readibility
- import java.util.*;//Implicit import