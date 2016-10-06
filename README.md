# onlineTests
Collection of online tests 

1.	
Which three statements are true?
1.Assertion checking is typically enabled when a program is deployed.
2.It is never appropriate to write code to handle failure of an assert statement.
3.Assertion checking is typically enabled during program development and testing.
4.Assertion checking can be selectively enabled or disabled on a per-package basis, but not on a per-class basis.
5.Assertion checking can be selectively enabled or disabled on both a per-package basis and a per-class basis.
Your Answer: Option C

Correct Answer: Option B

Explanation:

(1) is wrong. It's just not true.

(2) is correct. You're never supposed to handle an assertion failure.

(3) is correct. Assertions let you test your assumptions during development, but the assertion code鈥攊n effect鈥攅vaporates when the program is deployed, leaving behind no overhead or debugging code to track down and remove.

(4) is wrong. See the explanation for (5) below.

(5) is correct. Assertion checking can be selectively enabled or disabled on a per-package basis. Note that the package default assertion status determines the assertion status for classes initialized in the future that belong to the named package or any of its "subpackages".

The assertion status can be set for a named top-level class and any nested classes contained therein. This setting takes precedence over the class loader's default assertion status, and over any applicable per-package default. If the named class is not a top-level class, the change of status will have no effect on the actual assertion status of any class.


2.	
What will be the output of the program?
public class CommandArgs 
{
    public static void main(String [] args) 
    {
        String s1 = args[1];
        String s2 = args[2];
        String s3 = args[3];
        String s4 = args[4];
        System.out.print(" args[2] = " + s2);
    }
}
and the command-line invocation is
> java CommandArgs 1 2 3 4
	A.	
args[2] = 2
	B.	
args[2] = 3
	C.	
args[2] = null
	D.	
An exception is thrown at runtime.

An exception is thrown because in the code String s4 = args[4];, the array index (the fifth element) is out of bounds. The exception thrown is the cleverly named ArrayIndexOutOfBoundsException.


3.	
What will be the output of the program?
public class CommandArgsTwo 
{
    public static void main(String [] argh) 
    {
        int x;
        x = argh.length;
        for (int y = 1; y <= x; y++) 
        {
            System.out.print(" " + argh[y]);
        }
    }
}
and the command-line invocation is
> java CommandArgsTwo 1 2 3
	A.	
0 1 2
	B.	
1 2 3
	C.	
0 0 0
	D.	
An exception is thrown at runtime

Correct Answer: Option D

Explanation:

An exception is thrown because at some point in (System.out.print(" " + argh[y]);), the value of x will be equal to y, resulting in an attempt to access an index out of bounds for the array. Remember that you can access only as far as length - 1, so loop logical tests should use x < someArray.length as opposed to x < = someArray.length.

4.	
What will be the output of the program?
class Tree { } 
class Pine extends Tree { } 
class Oak extends Tree { } 
public class Forest1 
{ 
    public static void main (String [] args)
    { 
        Tree tree = new Pine(); 
        if( tree instanceof Pine ) 
            System.out.println ("Pine"); 
        else if( tree instanceof Tree ) 
            System.out.println ("Tree"); 
        else if( tree instanceof Oak ) 
            System.out.println ( "Oak" ); 
        else 
            System.out.println ("Oops "); 
    } 
}
	A.	
Pine
	B.	
Tree
	C.	
Forest
	D.	
Oops

Correct Answer: Option A

Explanation:

The program prints "Pine".

5.	
What will be the output of the program?
interface Foo141 
{ 
    int k = 0; /* Line 3 */
} 
public class Test141 implements Foo141 
{
    public static void main(String args[]) 
    {
        int i; 
        Test141 test141 = new Test141(); 
        i = test141.k; /* Line 11 */
        i = Test141.k; 
        i = Foo141.k; 
    } 
}
	A.	
Compilation fails.
	B.	
Compiles and runs ok.
	C.	
Compiles but throws an Exception at runtime.
	D.	
Compiles but throws a RuntimeException at runtime.

Correct Answer: Option B

Explanation:

The variable k on line 3 is an interface constant, it is implicitly public, static, and final. Static variables can be referenced in two ways:

Via a reference to any instance of the class (line 11)

Via the class name (line 12).

6.	
Which statement is true given the following?
Double d = Math.random();
	A.	
0.0 < d <= 1.0
	B.	
0.0 <= d < 1.0
	C.	
Compilation fail
	D.	
Cannot say.

Your Answer: Option D

Correct Answer: Option B

Explanation:

The Math.random() method returns a double value with a positive sign, greater than or equal to 0.0 and less than 1.0


7.	
What will be the output of the program?
public class Test 
{  
    public static void main(String[] args) 
    { 
        int x = 0;  
        assert (x > 0) ? "assertion failed" : "assertion passed" ; 
        System.out.println("finished");  
    } 
}
	A.	
finished
	B.	
Compiliation fails.
	C.	
An AssertionError is thrown and finished is output.
	D.	
An AssertionError is thrown with the message "assertion failed."

Your Answer: Option D

Correct Answer: Option B

Explanation:

Compilation Fails. You can't use the Assert statement in a similar way to the ternary operator. Don't confuse.

8.	
What two statements are true about properly overridden hashCode() and equals() methods?
hashCode() doesn't have to be overridden if equals() is.
equals() doesn't have to be overridden if hashCode() is.
hashCode() can always return the same value, regardless of the object that invoked it.
equals() can be true even if it's comparing different objects.
	A.	
1 and 2
	B.	
2 and 3
	C.	
3 and 4
	D.	
1 and 3

Correct Answer: Option C

Explanation:

(3) and (4) are correct.

(1) and (2) are incorrect because by contract hashCode() and equals() can't be overridden unless both are overridden.

9.	
Which statement is true for the class java.util.HashSet?
	A.	
The elements in the collection are ordered.
	B.	
The collection is guaranteed to be immutable.
	C.	
The elements in the collection are guaranteed to be unique.
	D.	
The elements in the collection are accessed using a unique key.
[#]

Your Answer: Option D

Correct Answer: Option C

Explanation:

Option C is correct. HashSet implements the Set interface and the Set interface specifies collection that contains no duplicate elements.

Option A is wrong. HashSet makes no guarantees as to the iteration order of the set; in particular, it does not guarantee that the order will remain constant over time.

Option B is wrong. The set can be modified.

Option D is wrong. This is a Set and not a Map.


10.	
Which one of these lists contains only Java programming language keywords?
	A.	
class, if, void, long, Int, continue
	B.	
goto, instanceof, native, finally, default, throws
	C.	
try, virtual, throw, final, volatile, transient
	D.	
strictfp, constant, super, implements, do
	E.	
byte, break, assert, switch, include
[#]

Your Answer: Option A

Correct Answer: Option B

Explanation:

All the words in option B are among the 49 Java keywords. Although goto reserved as a keyword in Java, goto is not used and has no function.

Option A is wrong because the keyword for the primitive int starts with a lowercase i.

Option C is wrong because "virtual" is a keyword in C++, but not Java.

Option D is wrong because "constant" is not a keyword. Constants in Java are marked static and final.

Option E is wrong because "include" is a keyword in C, but not in Java.

11.	
What will be the output of the program?
class Base
{ 
    Base()
    {
        System.out.print("Base");
    }
} 
public class Alpha extends Base
{ 
    public static void main(String[] args)
    { 
        new Alpha(); /* Line 12 */
        new Base(); /* Line 13 */
    } 
}
	A.	
Base
	B.	
BaseBase
	C.	
Compilation fails
	D.	
The code runs with no output
[#]

Correct Answer: Option B

Explanation:

Option B is correct. It would be correct if the code had compiled, and the subclass Alpha had been saved in its own file. In this case Java supplies an implicit call from the sub-class constructor to the no-args constructor of the super-class therefore line 12 causes Base to be output. Line 13 also causes Base to be output.

Option A is wrong. It would be correct if either the main class or the subclass had not been instantiated.

Option C is wrong. The code compiles.

Option D is wrong. There is output.

12.	
import java.awt.Button;
class CompareReference 
{
    public static void main(String [] args) 
    {
        float f = 42.0f;
        float [] f1 = new float[2];
        float [] f2 = new float[2];
        float [] f3 = f1;
        long x = 42;
        f1[0] = 42.0f;
    }
}
which three statements are true?
f1 == f2
f1 == f3
f2 == f1[1]
x == f1[0]
f == f1[0]
	A.	
1, 2 and 3
	B.	
2, 4 and 5
	C.	
3, 4 and 5
	D.	
1, 4 and 5
[#]

Your Answer: Option C

Correct Answer: Option B

Explanation:

(2) is correct because the reference variables f1 and f3 refer to the same array object.

(4) is correct because it is legal to compare integer and floating-point types.

(5) is correct because it is legal to compare a variable with an array element.

(3) is incorrect because f2 is an array object and f1[1] is an array element.

13.	
Which collection class allows you to access its elements by associating a key with an element's value, and provides synchronization?
	A.	
java.util.SortedMap
	B.	
java.util.TreeMap
	C.	
java.util.TreeSet
	D.	
java.util.Hashtable
[#]

Correct Answer: Option D

Explanation:

Hashtable is the only class listed that provides synchronized methods. If you need synchronization great; otherwise, use HashMap, it's faster.

14.	
Which interface provides the capability to store objects using a key-value pair?
	A.	
Java.util.Map
	B.	
Java.util.Set
	C.	
Java.util.List
	D.	
Java.util.Collection
[#]

Your Answer: Option C

Correct Answer: Option A

Explanation:

An object that maps keys to values. A map cannot contain duplicate keys; each key can map to at most one value.

15.	
Which one creates an instance of an array?
	A.	
int[ ] ia = new int[15];
	B.	
float fa = new float[20];
	C.	
char[ ] ca = "Some String";
	D.	
int ia[ ] [ ] = { 4, 5, 6 }, { 1,2,3 };
[#]

Correct Answer: Option A

Explanation:

Option A is correct. It uses correct array declaration and correct array construction.

Option B is incorrect. It generates a compiler error: incompatible types because the array variable declaration is not correct. The array construction expects a reference type, but it is supplied with a primitive type in the declaration.

Option C is incorrect. It generates a compiler error: incompatible types because a string literal is not assignable to a character type variable.

Option D is wrong, it generates a compiler error <identifier> expected. The compiler thinks that you are trying to create two arrays because there are two array initialisers to the right of the equals, whereas your intention was to create a 3 x 3 two-dimensional array.

16.	
You want a class to have access to members of another class in the same package. Which is the most restrictive access that accomplishes this objective?
	A.	
public
	B.	
private
	C.	
protected
	D.	
default access
[#]

Your Answer: Option A

Correct Answer: Option D

Explanation:

The only two real contenders are C and D. Protected access Option C makes a member accessible only to classes in the same package or subclass of the class. While default access Option D makes a member accessible only to classes in the same package.

17.	
public class Outer 
{ 
    public void someOuterMethod() 
    {
        //Line 5 
    } 
    public class Inner { } 
    
    public static void main(String[] argv) 
    {
        Outer ot = new Outer(); 
        //Line 10
    } 
} 
Which of the following code fragments inserted, will allow to compile?
	A.	
new Inner(); //At line 5
	B.	
new Inner(); //At line 10
	C.	
new ot.Inner(); //At line 10
	D.	
new Outer.Inner(); //At line 10
[#]

Correct Answer: Option A

Explanation:

Option A compiles without problem.

Option B gives error - non-static variable cannot be referenced from a static context.

Option C package ot does not exist.

Option D gives error - non-static variable cannot be referenced from a static context.

18.	
public class MyRunnable implements Runnable 
{
    public void run() 
    {
        // some code here
    }
}
which of these will create and start this thread?
	A.	
new Runnable(MyRunnable).start();
	B.	
new Thread(MyRunnable).run();
	C.	
new Thread(new MyRunnable()).start();
	D.	
new MyRunnable().start();
[#]

Your Answer: Option B

Correct Answer: Option C

Explanation:

Because the class implements Runnable, an instance of it has to be passed to the Thread constructor, and then the instance of the Thread has to be started.

A is incorrect. There is no constructor like this for Runnable because Runnable is an interface, and it is illegal to pass a class or interface name to any constructor.

B is incorrect for the same reason; you can't pass a class or interface name to any constructor.

D is incorrect because MyRunnable doesn't have a start() method, and the only start() method that can start a thread of execution is the start() in the Thread class.

19.	
Which three guarantee that a thread will leave the running state?
yield()
wait()
notify()
notifyAll()
sleep(1000)
aLiveThread.join()
Thread.killThread()
	A.	
1, 2 and 4
	B.	
2, 5 and 6
	C.	
3, 4 and 7
	D.	
4, 5 and 7
[#]

Your Answer: Option D

Correct Answer: Option B

Explanation:

(2) is correct because wait() always causes the current thread to go into the object's wait pool.

(5) is correct because sleep() will always pause the currently running thread for at least the duration specified in the sleep argument (unless an interrupted exception is thrown).

(6) is correct because, assuming that the thread you're calling join() on is alive, the thread calling join() will immediately block until the thread you're calling join() on is no longer alive.

(1) is wrong, but tempting. The yield() method is not guaranteed to cause a thread to leave the running state, although if there are runnable threads of the same priority as the currently running thread, then the current thread will probably leave the running state.

(3) and (4) are incorrect because they don't cause the thread invoking them to leave the running state.

(7) is wrong because there's no such method.

20.	
Which class or interface defines the wait(), notify(),and notifyAll() methods?
	A.	
Object
	B.	
Thread
	C.	
Runnable
	D.	
Class

Your Answer: Option B

Correct Answer: Option A

Explanation:

The Object class defines these thread-specific methods.

Option B, C, and D are incorrect because they do not define these methods. And yes, the Java API does define a class called Class, though you do not need to know it for the exam.


 

 

