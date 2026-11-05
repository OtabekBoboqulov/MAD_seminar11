## Mobile application development - special keywords

### Task - 1
It is not a good idea to use inline for 200 line code, because in lecture it is said that if function is small it can benefit from it, also in this task I have obtained that inlined functions produce more code.
### Task - 2
Error is saying illegal use inline parameter, because code is trying to add inline parameter to list, which requires object. But inline parameters are not objects, so it is suggesting to use noinline.
Fixed program prints:

    Saved: Write report
    Pending reminders: 1
    Reminder: finish 'Write report'
It shows that function that prints reminder is added to list which is printed at the end with forEach.
If we try to add save to the list it again says illegal use of inline parameter, since it is not an object.
When code runs reminder is stored in object.
### Task - 3
findFirst returns only first value because it uses regular return which will cause forEach lambda to close enclosing function too, while in second case where return@forEach is used it will behave as a continue, it just skips to the next iteration, so if it doesn't match it is skipped, else item is printed.
If there is a match `"No contact contains '$query'"` is never printed as function uses early return. Search finished is printed always as it doesn't depend on any function or its result, it is just a print in main function.
return is prohibited in case when we try to use each because it is not an inline function, which means it can't return from enclosing function
`a bare return is allowed in a lambda when it is inlined `
### Task - 4
It is saying that cannot inline action parameter because it can contain non-local return, so it is suggesting to use crossinline.
It is saying prohibited because with crossinline we have said to compiler that this function won't return, because if it returned it causes non-local return. It is prohibited in this case because our inline lambda function is executed in another execution context, Runnable object in this case.
### Task - 5
At first run it print 35.5, and in second it prints 10.0 because when 20000 is entered it will just stop looping and 5 is never read.
Lambda in let leaves the loop while in run just skips the iteration.
orSkip is another execution context so it is showing an error:
`break or continue crosses a function or class boundry`
If orSkip is inline error disappears, but it warns to specify label for clarifying:
`Similar to non-local return, you can apply break and continue jump expressions in lambdas passed as arguments to an inline function that encloses a loop`
### Task - 6
In second case all inputs except city is turned to null because in city there was no method used, it was just returned as T (String).
T is used as a parameter on when because we need to return different results based on its value and at the end when returning an error.
When String in calling the function is changed to Char it gives an error at run time because there is nothing wrong with code itself, it is default case in when that is causing an error.
### Task - 7
When we remove reified it will be erased in function body, which means we can't access it as an ordinary value.
filterIsInstance produces the same result and when checked its code it uses public and **inline**.
### Task -8
It printed 112.00 for 100 and 4 for the word count.
Double.withVay  is marked inline completely and in String.wordCount only getter is inlined. Both get() work the same.
### Task - 9
(building the report...) is printed when user inputs yes because in debug function it checks debugEnabled which is set according to user input.
If we change debug to ordinary function with message: String and give the result of the buildReport to it as a message it will print (building the report...) anyway because now in order to access message it should run function entirely. In first case when buildReport was passed as parameter message it was executed after check.


