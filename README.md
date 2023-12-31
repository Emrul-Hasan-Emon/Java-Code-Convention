# Java-Code-Convention
This repository will contains Java Code Convention technique. The idea is taken from oracle official website.

# <center> Chapter - 1: Why are Code Conventions necessary?</center>

When a programmer builds a software, it is not guaranteed that this software will be maintained by that programmer for life time. Other programmers may need to update this software or maintain the software. At that time the important fact arises is to understand the code. So, it is necessary to do the coding in such a way so that another programmer can understand. Besides, 80% of the lifetime cost of a piece of software goes to maintenance. So, we can understand that the maximum cost goes on maintenance. That’s why it  is necessary to follow a standard way for that so that another one can understand. This standard way is known as Code Conventions.

Code Conventions improve the readability of the software. It allows engineers to understand new code more quickly and thoroughly.

<br>
<br>

# Chapter - 2: File Names
    1. Java source code is generally saved with the .java suffix.
    2. Java bytecode is generally saved with the **.class** suffix.
    3. For makefiles, gnumake is used to build software.
    4. README consists of text which summarises the contents of a particular directory.



<br>
<br>

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
- Never do the line breaking inside a parenthesis. For example,
  
        longName1 = longName2 * (longName3 + longName4
        - longName5) + 4 * longname6
  
    Try to avoid this. Instead do the line breaking outside the parentheses. It will make the code readable.
- There are three ways to format ternary expressions.

        1. alpha = (aLongBooleanExpression) ? beta : gamma;
        2. alpha = (aLongBooleanExpression) ? beta
                 : gamma;
        3. alpha = (aLongBooleanExpression)
                 ? beta
                 : gamma;



<br>
<br>

# Chapter - 4: Comments
Comments should be used to give overviews of code and provide some information about code which are not present in the code. Comments should be written in such a way that a programmer can understand. Comments should contain only information which is relevant to reading and understanding the program. For example, if a comment is made which describes how a portion works, it is not a good practice. Comment will not show how a specific portion of code works, instead it will show what is doing. Also frequency of comments is a matter. Comments should not include special characters such as form-feed and backspace. There are two types of comments present in Java.

- **Implementation Comment** <br>
       It means commenting out of code or the comments about a particular implementation which is a part of a method or class. Actually there may be some comments which don't give an overview as whole 
       but give overview for a specific portion. That’s why these comments are placed inside the class or the method. THa  They are delimited by `/*......*/`. <br><br>
  **Implementation comment is of four types.**
  - **Block Comments** <br>
     Specifically block comments are used to provide descriptions of files, methods, data structure and algorithms. Block comments may be used at the beginning of each file and before each method. Block comments also be used within methods and when they are used within a method they should be indented at the same level as the code.
  - **Single Line Comments** <br>
  Short comments can be done on a single line indented the level of the following. If short comments go out more than one line, at that time block comments should be used instead of single line comments.

          if (condition) {/* Handle the condition. */
          ...
          }
  - **Trailing Comments** <br>
   Very short comments can be used in the same line as the code. Note that the comments should be very short. If they become long, at that time it will be considered as single line comments. If more 
   than. one short comment appears in a chunk of code, they should all be indented to the same tab settings.

        if (a == 2) {return TRUE;            /* special case */
        } else {
            return isPrime(a);      /* works only for odd a */
        }
  - **End-Of-Line Comments.** <br>
   For this type of comments the used delimiter is //. This is done while commenting out a complete line. It means we have done coding. Now we want to uncomment a line. At that time we will use End- 
   Of_Line commenting. But if we want to use it for text it will not be appropriate. But if we want to use it for commenting multiple lines which are part of the code at that time we can do it.

        //if (bar > 1) {
        //
        //    // Do a triple-flip.
        //    ...
        //}
        //else {
        //    return false;
        //}
- **Documentation Comment** <br>
It is also known as doc comment also. Doc comments are meant to describe the specification of the code, from an implementation-free perspective. Doc comments describe the whole overview of a class or a method or a constructor. That’s why these types of comments are placed before the class declaration, before the method declaration, before the constructor declaration. It describes Java classes, interfaces, methods, constructors and fields.
They are delimited by `/**.....*/`.

        /**
        
         * The Example class provides ...
         */
        public class Example { ...
  
  The first line of doc comment /** for classes and interfaces is not indented but subsequent doc comment lines each have 1 space of indentation. And generally members of a class or a interface have 4 spaces indentation.So, doc comment for 
  members including constructors have spaces for the first doc comment which is /** and 1 space more, total 5 spaces thereafter. <br>
  **Note:** Doc comment should not be done inside a method or a constructor definition block.

<br>
<br>

# Chapter - 5: File Organization

A file consists of several lines. But the good way is to keep the number of lines in a file within 2000. <br>
  ## Java Source File <br>
  Each of the java source files is ended with .java suffix. Each of the java source files contains a single public class or interface. But if there are private classes and interfaces are present which are associated with a public, we can put them 
  in the same source file where the public class is present. At that time public class should appear at the top. Same thing can happen for an interface. There may be classes or interfaces which are associated with a public interface. Then we can 
  put them in the same source file where the public interface is present. At that time the public interface should appear at the top. <br>
  
