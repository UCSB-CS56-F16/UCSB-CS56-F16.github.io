---
layout: examHandout
num: e01c
ready: true
desc: "Handout for Practice Exam 'e01c'"
exam_date: 2016-10-17 12:30:00.00-7
---

<h2>CODE FOR QUESTION 1</h2>


{% highlight java linenos %}
public class Dog {

    private static Dog dogOfTheWeek = null;
    private String name;

    public void setAsDogOfTheWeek() {
        dogOfTheWeek = this;
    }

    public static Dog getDogOfTheWeek() {
        return dogOfTheWeek;
    }

    public Dog(String name) { this.name = name;}

    public static void main(String [] args) {

        Dog d1 = new Dog("Fido");
        Dog d2 = new Dog("Rover");
        Dog d3 = new Dog("Princess");
        Dog d4 = new Dog("Spot");
        Dog d5 = new Dog("Snoopy");

        d1.setAsDogOfTheWeek();    
        d1 = d2;                   
        Dog d6 = d3;               
        Dog temp = d4;             
        d4 = d3;                                      
        d3 = temp;                 
        d2 = getDogOfTheWeek();    
        d4.setAsDogOfTheWeek();    
        d5 = null;                 
        d4 = null;                 
        d3 = null;                 
        d2 = null;                 
        d1 = null;                 
        temp = null;               
    }                              
}
{% endhighlight %}



<h2 class="page-break-before">Code for Question 2</h2>

Note: Line numbers are not part of the code. They are only there for reference.

<div style="font-size:80%;">

## Product.java
```java
1	/** something that can be sold */
2	public abstract class Product {
3
4	/** get the price (in cents) */
5	public abstract int getPrice();
6
7	}
```

## Shippable.java

```java
1	/** something that can be shipped */
2	public interface Shippable {
3
4	/** get the shipping weight in pounds */
5	public double getWeight();
6	}
```

## Book.java

```java
1	/** A Book */
2	public class Book extends Product implements Shippable {
3
4	private int price;
5	private double weight;
6	private String author;
7	private String title;
8
9	public Book(String author, String title, int price,
10	double weight) {
11	  this.author = author;
12	  this.title = title;
13	  this.price = price;
14	  this.weight = weight;
15	}
16
17	public int getPrice() {return this.price;}
18	public String getTitle() {return this.title;}
19	public String getAuthor() {return this.author;}
20	public double getWeight() {return this.weight;}
21
22	}
```

## Song.java

```java
1	/** A downloadable Song */
2	public class Song extends Product {
3
4	private int price;
5	private String artist;
6	private String title;
7
8	public Song(String artist, String title, int price) {
9	  this.artist = artist;
10	  this.title = title;
11	  this.price = price;
12	}
13
14	public Song(String artist, String title) {
15	  this(artist,title,99);
16	}
17
18	public int getPrice() {return this.price;}
19	public String getTitle() {return this.title;}
20	public String getArtist() {return this.artist;}
21
22	}
```

</div>
