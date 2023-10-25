# Java-Code-Convention
This repository will contains Java Code Convention technique. The idea is taken from oracle official website.

# <center> Chapter - 1: Why are Code Conventions necessary?</center>

When a programmer builds a software, it is not guaranteed that this software will be maintained by that programmer for life time. Other programmers may need to update this software or maintain the software. At that time the important fact arises is to understand the code. So, it is necessary to do the coding in such a way so that another programmer can understand. Besides, 80% of the lifetime cost of a piece of software goes to maintenance. So, we can understand that the maximum cost goes on maintenance. That’s why it  is necessary to follow a standard way for that so that another one can understand. This standard way is known as Code Conventions.

Code Conventions improve the readability of the software. It allows engineers to understand new code more quickly and thoroughly.

# Chapter - 2: File Names
    1. Java source code is generally saved with the .java suffix.
    2. Java bytecode is generally saved with the .class suffix.
    3. For makefiles, gnumake is used to build software.
    4. README consists of text which summarises the contents of a particular directory.



# Chapter - 3: Indentation
Four spaces should be used as the unit of indentation. So, indentation will take place in 4 spaces, 8 spaces etc. It means multiple of 4. But the exact construction of the indentation is unspecified.

Previously I have discussed that in a file the maximum line should be 2000. Not more than that. Then a question arises, what should be the length of a line? The answer is, if the line is the part of coding then the line should not have more than 80 characters but if the line is the part of documentation then the line should not have more than 70 characters.

Another question arises when we will break a line? It means we know the length of the line but what is the standard way for breaking a line to get into a new line. The answer is,

- We can break after a comma
- We can break before an operator
- Prefer higher level breaks to lower level breaks.
- When we break an expression, we must align the new line with the beginning of the expression at the same level on the previous line.
- For the previous four rules, if the rules lead to confusing code, at that time we will indent 8 spaces to the right. For example, if we do indentation like below, this may lead to confusion.

        var = someMethod1(longExpression1,
              someMethod2(longExpression2,
              longExpression3));

  Instead of this we can do the following,
        var = someMethod1(longExpression1,
                    someMethod2(longExpression2,
                            longExpression3));

  We can take another example for a method,

        someMethod(int anArg, Object anotherArg, String yetAnotherArg, Object andStillAnother) {
        	Implementation of the method
        }

  This convention is okay. But if we think that it may make us confused at that time we can use 8 spaces indentation for the second line and more 8 spaces indentation for the third line. And obviously 
  indentation will take place to the right.

        someMethod(int anArg, Object anotherArg, String   
        yetAnotherArg, Object andStillAnother) { 
        ...
        }




