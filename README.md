# Rational Numbers:  Operators as Methods
 

## Summary 
Ruby provides us with different classes for representing numbers.  `Integer` and `Float`, for example.  In this challenge, we're going to build our own class to represent [rational numbers][wikipedia rational numbers].  To do so, we'll need to understand how to add, subtract, etc. rational numbers.  But, in doing so, we're also going to learn how to implement operators like `+`, `-`, and `==` in our custom classes.


### Rational Numbers
A rational number is any number which can be expressed as a fraction with integers for the numerator and denominator.  For example, `3` is a rational number because it can be expressed as `3/1`, and `1.25` is rational because it can be expressed as `5/4`.  [Maths is Fun][maths is fun rational numbers] and [Khan Academy][khan academy rational numbers] each provide an introduction to rational numbers.  The wikipedia article on rational numbers will provide a description of [how to perform arithmetic with rational numbers][wikipedia rational numbers arithmetic].


### Syntactic Sugar
Ruby is designed to be programmer friendly.  It provides *syntactic sugar* to improve the experience of writing code.  In other words, Ruby sometimes provides programmer-friendly alternative syntax for writing code.  The friendlier syntax might feel more natural or read better.  We've been taking advantage of Ruby's syntactic sugar, but perhaps we haven't recognized it.  Figure 1 shows some examples where we commonly see this; the syntactic sugar provides an alternative way of calling the methods `Person#first_name=`, `Array#<<`, and `Hash#[]=`.


```ruby
# Syntactic Sugar                #  Standard Ruby Syntax
                                 #
person = Person.new              #
person.first_name = "Connie"     #  person.first_name=("Connie")
                                 #
numbers = [43, 99, 17]           #
numbers << 25                     #  numbers.<<(25)
                                 #
menu_prices = Hash.new           #
menu_prices[:hamburger] = 3.49   #  menu_prices.[]=(:hamburger, 3.49) 
```
*Figure 1*.  Examples of Ruby's syntactic sugar: a setter method, array indexing, and key-value hash assigning.


### Operators as Methods
We see the same pattern with many of Ruby's operators:  `+`, `-`, `>`, `==`.  When we use Ruby's operators, the syntax often hides the fact that [many of them are actually methods][programming ruby operator expressions].  When we work with integers we rarely use the standard Ruby method-calling syntax; the sugary syntax is friendlier (see Figure 2).

```ruby
# Syntactic Sugar                #  Standard Ruby Syntax
                                 #
1 + 2                            #  1.+(2)
2 ** 3                           #  2.**(3)
4 == 4                           #  4.==(4)
```
*Figure 2*.  Using operator methods with integers.


And, because these operators are methods, each class can define its own operators.  For example, the classes `Fixnum`, `String`, `Array`, and others implement their own versions these operators (see Figure 3).  We can define these operator methods in our own custom classes, too, which is what we'll be doing in this challenge.

```ruby
# Syntactic Sugar                #  Standard Ruby Syntax
                                 #
1 + 2                            #  1.+(2)
"add " + "strings"               #  "add ".+("strings")
[:a, :b] + [:c, :d]              #  [:a, :b].+([:c, :d])
                                 #
1 == 2                           #  1.==(2)
"compare" == "strings"           #  "compare".==("strings")
[:a, :b] == [:c, :d]             #  [:a, :b].==([:c, :d])
```
*Figure 3*.  Calling operator methods with the same name on different types of object.


## Releases
### Release 0: Write Down the Rules of Rational Arithmetic
We're going to develop a `RationalNumber` class with behaviors like addition (`+`), subtraction (`-`), etc.  A couple behaviors have been written and tested for us (e.g., calculating a reciprocal.).  Empty method definitions have been written for the methods we need to develop. 

We're going to implement the following operations:

1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Equality
6. Exponentiation
7. Inversion / negation
8. Reciprocation (*completed*)

Read the Wikipedia page on the [arithmetic of rational numbers][wikipedia rational numbers arithmetic]; some additional information is provided as comments in the file `rational_number.rb`.  Ensure that we understand how to make each of the calculations.  Use pen and paper to demonstrate that we can make each of them (e.g., add two rational numbers).  Then translate the calculations to pseudocode.


### Release 1: Fill in the RationalNumber class

You've been provided with a skeleton `RationalNumber` class with methods to fill in.  Assume the input is always another `RationalNumber` instance.  Ruby has a built-in `Rational` class; don't use it!  Do, on the other hand, write tests to check your output.  If you need help on any of the math, just ask!

The point of this challenge is to see how something like Ruby's `Rational` might be implemented on the inside, and also to see how object-oriented design can implement concrete and abstract systems alike.
 

<!-- ##Optimize Your Learning  -->

##Resources

* [arithmetic of the Rationals](http://en.wikipedia.org/wiki/Rational_number#Arithmetic)

[khan academy rational numbers]: https://www.khanacademy.org/math/pre-algebra/order-of-operations/rational-irrational-numbers/v/introduction-to-rational-and-irrational-numbers
[maths is fun rational numbers]: http://www.mathsisfun.com/rational-numbers.html
[programming ruby operator expressions]: http://phrogz.net/ProgrammingRuby/frameset.html?content=http%3A//phrogz.net/ProgrammingRuby/language.html%23operatorexpressions
[wikipedia rational numbers]: http://en.wikipedia.org/wiki/Rational_number
[wikipedia rational numbers arithmetic]: https://en.wikipedia.org/wiki/Rational_number#Arithmetic

