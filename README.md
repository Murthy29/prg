# if else  statement statement in c#


using System;
 
 namespace simple
 {
 class main
 {
 staic void Main(string[]  args)
 {
 int age;
 Console.WriteLine("enter your age");
 int age=Parse.int(Console.ReadLine());
 if(age>=18)
 {
 Console.WriteLine("eligible for vote");
 else
 Console.WriteLine("not eligible");
 Console.ReadKey();
 }
 }
 }
 
