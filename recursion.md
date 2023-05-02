# Recursion

## Prerequisite

- Function
- Memory Management

## Basics

- Recursion is a Function calling itself.
- Remember that in Java every program start from `main` method and ends with `main` method. (excluding statics, constructor)

### Write function to print message five times.

1. Method 1

```java
public class Main(){
    public static void main(String[] args){
      message();
      message();
      message();
      message();
      message();
    }
    static void message(){
      System.out.println("Hello World!");
    }
}
```

2. Method 2 (in main function call only one method and print five times)

```java
    public static void main(String[] args){
      message1();
    }
    static void message1(){
      System.out.println("Hello world!");
      message2();
    }

    static void message2(){
      System.out.println("Hello world!");
      message3();
    }

    static void message3(){
      System.out.println("Hello world!");
      message4();
    }

    static void message4(){
      System.out.println("Hello world!");
      message5();
    }

    static void message5(){
      System.out.println("Hello world!");
    }

```

```output
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
```

Now here what happeing is--

**First** of all _main_ function is call and then it that `message1();` calling method is present.
So `message1()` method is called. Here `main()` method is still remain in stack memory, because it is not completed yet.

Now `message1()` method is called and it goes inside and print _Hello world!_ and then another method is present.
so it called `message2()`. Here Notice that there are 2 method are still in executing progress. 1<sup>st</sup> is _main_ method and
2<sup>nd</sup> is `message1();`.

And still goes on upto `message5()` method. After printing `message4()` method. It returns void and came back and removed from stack memory. And it goes on upto `main` method. Picture is attched below
[!image](https://)

### Write a function that takes a number and prints it

```java
public class Example1 {
	public static void main(String[] args) {
		//write a function that takes a number and prints it
		//print first 3 numbers:  1 2 3

		print1(1);
	}
	static void print1(int number){
		System.out.println(number);
		print2(2);
	}
	static void print2(int number){
		System.out.println(number);
		print3(3);
	}
	static void print3(int number){
		System.out.println(number);
	}
}
```

### Base condition

Here more generalized code in Recursion method

```java
public class Example1 {
	public static void main(String[] args) {
		//write a function that takes a number and prints it
		//print first 5 numbers:  1 2 3

		print1(1);
	}
	static void print1(int number){

		System.out.println(number);
		print1(number + 1);
	}
}
```

The above gives Stackoverflow error. It means code flow continuously. Because it doesn't have Base case(break condition).

```java
public class Example1 {
	public static void main(String[] args) {
		//write a function that takes a number and prints it
		//print first 5 numbers:  1 2 3
		print1(1);
	}

	static void print1(int number){
		if(number == 5){
      return;
    }
		System.out.println(number);
		print1(number + 1);
	}
}
```

Here this is the Break condtion, to stop making calls

```java
if(number == 5){
      return;
    }
```

**NOTE: If break condition is not present, the function will keep happening and Stack will filled again and again**

### Why recursion?

- It helps us in solving bigger/complex problems in a simple way.
- You can convert recursion solution into iteration and vice versa.
- space complexity is NOT constant due to more recursive calls.

### Recursice Tree

[Image](https://)

### Find n<sup>th</sup> fibonacci number

0<sup>th</sup> 1<sup>st</sup> 2<sup>nd</sup> 3<sup>rd</sup> 4<sup>th</sup> 5<sup>th</sup> 6<sup>th</sup> 7<sup>th</sup> &nbsp;8<sup>th</sup>

0&nbsp;&nbsp;&nbsp; 1&nbsp;&nbsp; 1&nbsp;&nbsp;&nbsp; 2&nbsp;&nbsp;&nbsp; 3&nbsp;&nbsp;&nbsp; 5&nbsp;&nbsp;&nbsp; 8&nbsp;&nbsp; 13&nbsp;&nbsp;&nbsp; 27

> fibo(N) = fibo(N-1) + fibo(N-2)

[RECURSIVEIMAGE](https://)

```java
public class Main {
	public static void main(String[] args) {
		int ans = fib(7);
    System.out.println(ans);
	}

	static int print1(int number){
		if(number < 2){
      return n;
    }
		return fib(number - 1) + fib(number - 2);
	}
}
```
