java cSD6502 Programming II 1
Lab Work
continued from last lab(week 5)
Task 1:Inheritance
1. Let’s add a few more classes to the PolytechLibrary which you created in last lab session.
(a) Add a class and name it Teacher.cs
(b) Add attributes(ﬁelds) such as FirstName, LastName, Email Address and Subject as properties.
(c) Add another class name it Student.cs
(d) Add some ﬁelds(properties), FirstName, LastName . . . .
Wait, didn’t you add same ﬁelds already for teacher class. Teacher and students have things in common
 such as ﬁrstname, lastname, email address and so on. Unlike Teacher, students do not have
subject to teach. We can make use of a OO concept called inheritance here. What we can do is deﬁne
a class, say person, and put all the common ﬁelds (attributes) there. Then make Student and Teacher
classes inherit all the common attribute from Person class. Of course, we will add the unique ﬁelds of
their own in their class deﬁnition.
2. Add a class person
3. Add common attributes to Person class and remove those from Teacher and student class
public class Person {
public string FirstName { get; set; }
public string LastName { get; set; }
public string Email { get; set; }
}
Also,
Teacher and Student should now look like this,
public class Teacher : Person {
public string Subject { get; set; }
}
public class Student : Person {
}
Note: The class names Teacher and Student is followed by a colon and then Person. The Person
class is called base or parent class. Similarly Teacher and student classes are called derived or child
or subclass. Also, if you are working with VS 2022 replace internal keyword public. VS2022/.Net
framework 6 automatically adds internal keyword when you add a new class ﬁle.
.SD6502 Programming II 2
One other thing, if you don’t want others who are using the PolytechLibrary to be able to use the
Person class directly(by directly I mean creating an object and using it from their code) you can make
person class abstract. In this way you are making others to use Teacher and Student class directly
from their code.
4. Add a keyword abstract before the class keyword in the deﬁnition of person class
public abstract class Person {
public string FirstName { get; set; }
public string LastName { get; set; }
public string Email { get; set; }
}
Let’s add some attributes(feilds) to the empty Student class. A attribute called GradLevel to show
what level they are studying in. What type of data a GradLevel would hold ? In our polytech we
have level 5, level 7 and level 8 graduates. How would you model this ﬁxed but discrete set of
data ? Enumeration datatype are perfectly suited in this situation. So let’s deﬁne a enum and call it
Gradlevels. Also, add a property to get and set Gradlevels ﬁeld.
public class Stude代 写SD6502、C++
代做程序编程语言nt: Person {
public enum GradLevels {Level_5, Level_7, Level_8, Level_9 }
public GradeLevels GradLevel {get; set; }
}
Task 2: Working with derived class objects
Let’s go back to our PolytechFormApp. Double click the button to get the source code.
Try making it a new Person, i.e. create an object of Person class. Did you get any error why?
Create Teacher and Student objects and try and access all the ﬁelds.
Task 3:Abstract methods
Abstract classes are classes that are designed such that you can’t instantiate them or use them directly. The
same is true for abstract methods. An abstract method is a method with no code in it. Let’s say, for example,
we want to implement a method that will allow us to get a grade point average, but it’s going to be a different
computation depending on whether you’re talking about the teacher or the student. The student is going to
have the average of all the grades for the semester or the period or whatever time period we’re talking about
and the teacher’s grade point average is going to be the average grade point average for all of the students
in this class. So it makes sense to have two different, completely different implementations of a function by
the same name. So create the abstract method and then override it in each of the subclasses with speciﬁc
implementations for those classes.
.SD6502 Programming II 3
public abstract float ComputeGradeAverage ( ) ;
In Student class
public override float ComputeGradeAverage ( ) {
return 4.0f;
}
In Teacher class
public override float ComputeGradeAverage ( ) {
//TODO: fix the implementation later
return 0.0f;
}
Note: If a method(s) is declared abstract in base class all derived classes must have its deﬁnition (implementation).
 In this case method ComputeGradeAverage must be implemented by Student and Teacher
classes. Otherwise, the code won’t compile. Also, note that you can also declare any method abstract in
non-abstract class.
Task 4: Testing the abstract method
Now that you have an abstract method and an overridden version of it in our two subclasses, why don’t we
take a look at what it looks like in our test program ?
Add two buttons and write code to test the overridden version of ComputeGradeAverage from both
classes.
Task 5:
Do all the examples exercise from Lecture slides. Codes are given here in the folder, try to understand:
1. How base and derived classes work in C#
2. How polymorphism is achieved in C#
3. What does extension methods do in C# and why it is useful?
Task 5:
Start working on your assignment.
Submission
NO submission needed. You will continue this work in the next lab. Show to your lab instructor when you
complete week 7 lab.
Credits: C# essentials, Bruce Van Horn.
.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
