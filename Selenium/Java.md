- ![Highlevel for humans level lan9ua9e computers sour...](Exported%20image%2020250822043428-0.png) - ![what is JDK JRE JVM a JDK JDK Java Development Kit...](Exported%20image%2020250822043430-1.png)
- JDK-Tools for developing Java application
- JRE- Need to run Java application
- JVM- Runs the java code on your device. We cannot install JVM alone.
- If we want to use all features of selenium we need jdk 11.
- Class should be in camel case and always start with capital letter.
- IDE- Integrated development environment.-Software that helps us write the code. IDE provide a interface to write code.
- Variable should always start in small letter.
- Escape sequence- "\n"-new line ,..."\t"-Tab space
- Inputs in Java- these are from scanner class. Scanner is a part of java.util
    - string name=sc.nextLine(); // Reads a string
    - int num=sc.nextInt(); // Reads an integer
    - double num=sc.nextDouble(); // Reads a double
    - char ch=sc.next().charAt(0); // Reads a single character
- If i want to use a method in class A in class B then i can do that in two ways
    1. By making the method as static and the using it by classname.method name.
    2. By making object of the class and then using objectname.methodname.
- Print and println are different. Println prints the output in next line.
- If I am defining a variable mousepad then it will be defined as "mousePad".
- Objects are the instance or referances of the class.
- Data Structures - It is a way to organize data. After organizing the data it becomes easy to process it.
- We use breakpoint in java for debugging.
- \t is used for giving space.
- Array- Container which store multiple values of same data type.
- int a[] = new int[5] // Declares an array and allocates memory for the variable￼new is used to create a new array object in the memory.
- Whether class contains main() method or not and whether main() method is declared according to requirement or not these things won't be checked by compiler. At runtime, JVM is responsible to check these things.
- At runtime if JVM is unable to find required main() method then we will get runtime exception syaing NoSUchMethodError:main.
- Why JVM searches for public static void main() ?￼Because that is how it is configured inside the JVM code. If we want to change main to hemu_main then we have to change inside JVM code as well.
- Why main method is public?￼To call by JVM from anywhere main method should be public
- Why main method is static?￼When a variable or a method is defined outside of the main function its object needs to be created or that variable or function can be termed as static so it can be used without an object within the class. Without existing object JVM has to call the main method and main method is no way related to any object.
- Why main method is void?￼The main method is not expected to return a value. Its purpose is to execute the propgram.Main method won't return anything to JVm.
- What is meaning of String[] args?￼String[] args allows the program to accept **command-line arguments**, which are passed as an array of strings, enabling interaction with the program at runtime.
- ![Exported image](Exported%20image%2020250822043432-2.png) - ![Highlevel language for humans mom ode java file ex...](Exported%20image%2020250822043434-3.png)
- How Java is platform independent?￼Jo source code likhenge usko compiler byte code mein convert kar dega eg hello.java ko hello.class mein. Jo byte code hoga wo platform independent hoga. Jis bhi machine mein JVM hoga wo use run kr sktin hai.The JVM is the key to Java's platform independence. Each operating system or platform has its own version of the JVM.When you run a Java program, the bytecode is executed by the JVM, which interprets or compiles it into **machine-specific code** at runtime.
- No executable code or variable can exist outside of class. Only package,import and comments can exist outside class.

class HelloWorld {  
int i=2; //this variable is defined outside main function. It can either be used by using static keyword or by making a object of the class.  
String str;   public static void main(String[] args) {  
HelloWorld obj = new HelloWorld();//object of the class created  
//int i=1;  
obj.add(1,3);  
System.out.println(obj.i);//by creating object of the class we can use anything from the class  
System.out.println("Hello WOrld");  
System.out.println("Try programiz.pro");  
int c=add(1,2);  
System.out.println(c);   }  
//below static is used before add function to make it available inside main function. We can also make object of the class and use this function.  
public static int add(int a,int b)  
{  
return a+b;  
}  
}

- Data Types
    - Primitive data types- only single value can be stored
        - Bytes,short,int,long-Number without decimal
        - Float,double- Decimal number
        - Char- single character(single quote)
        - Boolean-true/false
    - Non Primitive data types- multiple values can be stored
        - String
        - Array list
        - Hashmap
        - Hashset etc etc
- No methods are allowed inside the main block. They should be written outside the main function and called inside main function.
- We use length() to get the size of an array and we use size() method to get the size of an array list.
- What is platform independent?
    - When you write java program java compiler converts your program into byte code.
    - If I am running the java prgram in windows and java compiler convert it to byte code. This byte code can be run on any OS.
- What is JDK and JRE?
    - JDK(Java development kit)￼JDK has JRE,Java docs and debugging tools.
    - JRE(java runtime environment)￼This is responsible for running your java program. Sufficient for running plain java code.
- What is public static void main ?
    - Public-main method needs to be public because it is called by the java runtime environment which is outside of the class.
    - Static
    - Void
    - Main
- If I define a method as static then it can be called inside any class just by mentioning any classname.methodname or else first you have to make an object of the class first and then use the method.
- For each loop- makes loop more readable and less error prone. But you don't have the access to index.
- Sorting
    - Selection sort- Run time complexicity -O(n^2)--that means larger the data set more it becomes inefficient.
    - Bubble sort- Run time complexicity -O(n^2)--that means larger the data set more it becomes inefficient.￼
    - ![OnA2 data OnA2 quadratic insertion sort selection ...](Exported%20image%2020250822043441-4.png)
    - Merge Sort￼
    - ![merge50rt On log n OnA2 data n log n quasilinear t...](Exported%20image%2020250822043442-5.png)
      
    - Why strings are immutable in java?￼Immutable means it cannot be altered or changed.￼String str ="Hello";￼str.concat("World");￼System.out.prinltn(str);// Output should have been "Hello World" but it will still be hello because string is immutable and no change in the original value is possible.￼String c = str.conact("World");//this will work as we are creating a new string but changes to the original one is not possible.￼In java strings are immutable because of below reasons￼1.Security-