---
title: "Pass by Reference vs Pass by Value"
seoTitle: "Pass By Reference vs Pass By Value in Java"
datePublished: Sat Apr 01 2023 17:36:49 GMT+0000 (Coordinated Universal Time)
cuid: clfy99wsi00000ald5unphmw6
slug: pass-by-reference-vs-pass-by-value
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1680370257815/4baae04b-f15f-4a85-88a1-2aca25a41132.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1680370532198/776f5042-3708-4f38-a76a-142df4b33c02.png
tags: java, hashnode, wemakedevs, pass-by-refernce-pass-by-value-in-java

---

# Introduction

Have you ever faced a situation where you compared two strings using the "==" operator in Java, but it returned false even though the strings were equal? This can be a frustrating experience for Java coders. I made this mistake myself when I was learning Java. In this blog, we'll explore why the "==" operator behaves in this way and discuss the proper way to compare strings.

## Classes and Objects

Before discussing pass-by-reference and pass-by-value we need to have a solid understanding of classes and objects. So I'll provide some basic details about classes and objects.

Let's consider a Human being - a complex entity with various attributes and behaviors. We can represent a human using the class Human with class variables like name, age, height, weight, gender, talent etc. It can have methods like eat(), talk(), sleep(), work() and we can also define variables like the number of eyes, number of ears and mouth.

```java
public class Human {
    private String name;
    private int age;
    private String gender;
    private float height;
    private float weight;
    private int numEyes = 2; // the number of eyes a human has
    private int numEars = 2;
    private int mouth = 1;

    public Human(String name, int age, String gender, float height, float weight) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.height = height;
        this.weight = weight;
    }

    public void walk() {
        // code for walking
    }

    public void talk() {
        // code for talking
    }

    public void eat() {
        // code for eating
    }

    public void sleep() {
        // code for sleeping
    }

    public void see() {
        // code for perceiving visual stimuli through the eyes
    }
}
```

Above code defines the attributes of a human. We can create objects for the classes i.e) with this template we can create as many humans as we want and every human object (human) is unique and it has individual memory addresses.

```java
public class Main {
    public static void main(String[] args) {
        // Creating a human named John 
        Human john = new Human("John", 30, "Male", 1.8, 75);
        Human wayne = new Human("Wayne", 25, "Male", 1.4, 64);
        // Calling some methods on the john object
        john.walk();
        john.talk();
        john.eat();
        john.sleep();
        john.see();
        // Calling some methods on the john object
        wayne.walk();
        wayne.talk();
        wayne.eat();
        wayne.sleep();
        wayne.see();
    }
}
```

We've created two human objects with several humans with their associated object variables and called some functions on those objects. I hope this will give a concise idea of how classes and objects work. Theoretically, Classes are just templates to create objects.

## Pass by Value

When we pass a primitive datatype such as "int"," char", or "float" into a function in java, a copy of a variable's value is passed into a function. When we alter or change the variables inside the function it will not affect the variable outside the function. For instance, consider the code snippet given below

```java
public class Main {
    public static void main(String[] args) {
        int x = 10;
        System.out.println("Before calling the function : "+x);
        //10
        changeValue(x);
        System.out.println("After calling the function : "+x);
        //10
    }
    public static void changeValue(int num) {
        num = 20;
    }
}
```

The output will remain as 10 even though we have changed the value inside the function. This is called the pass-by-value.

## Pass by Reference

Pass-by-reference is the inverse of pass-by-value, here the original value will be modified because rather than passing a copy of that value we are passing the object itself. In the below code instead of creating a primitive integer, we are creating an Integer object

```java
public class Main {
    public static void main(String[] args) {
        int[] x = {0,1,2,3,4};
        System.out.println("Before calling the function : "+x[0]);
        //10
        changeValue(x);
        System.out.println("After calling the function : "+x[0]);
        //20
    }
    public static void changeValue(int[] x) {
        x[0] = 20;
    }
}
```

## "==" vs .equals()

When we compare two strings using "==" it will return false because when we compare those strings we are comparing the two string objects, not the values. As I mentioned in the previous example all human objects are unique John cannot be Wayne. The same applies here; each string objects are unique hence it returns false when we compare two string objects. We can solve this problem using the .equals() method. The code sample is given below:

```java
public class StringComparison {
    public static void main(String[] args) {
        String str1 = "hello";
        String str2 = "hello";
        String str3 = new String("hello");

        System.out.println(str1 == str2);        // true
        System.out.println(str1 == str3);        // false
        System.out.println(str1.equals(str2));   // true
        System.out.println(str1.equals(str3));   // true
    }
}
```

# Conclusion

In conclusion, understanding pass-by-reference and pass-by-value helps in writing bug-free code. Pass-by-value involves making a copy of data whereas pass-by-reference helps us work with the original data directly. Ultimately the choice using the pass-by-value and pass-by-reference depends on the user and the task at hand.

HAPPY CODING !!!

# Connect With Me

[Github](https://github.com/iamvbenz49)

[LinkedIn](https://www.linkedin.com/in/sham-vijay-v-a568a7238/)

[Twitter](https://twitter.com/iamvbenz)