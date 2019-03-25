Tasks to answer in your own README.md that you submit on Canvas:

	1.	See logger.log, why is it different from the log to console?

Logging is the process of writing log messages during the execution of a program to a 
central place. This differs from the log to console as a log is specific to one
location and not everything has access to the logger.

	2. Where does this line come from? FINER org.junit.jupiter.engine.execution.ConditionEvaluator logResult Evaluation of condition [org.junit.jupiter.engine.extension.DisabledCondition] resulted in: ConditionEvaluationResult [enabled = true, reason = '@Disabled is not present']

This comes from the org.junit.jupiter.engine.execution.ConditionEvaluator class.

	3.	What does Assertions.assertThrows do?

Asserts that an specific exception is thrown from the method call when it fails.

	4.	See TimerException and there are 3 questions
		1. What is serialVersionUID and why do we need it? (please read on Internet)
Used during deserialization to verify that the sender and the 
receiver are serialization compatible.
    
		2. Why do we need to override constructors?
The constructor is not overridden in the TimerException.java 
(using @Override), however we 'override' the constructor by 
creating a new constructor function with a new method signature. 
We do this so that the super constructor can be called with non-default
parameters (super(message)).
     
		3. Why we did not override other Exception methods?
Because this would override the other Exception methods' functionality. There
is no need to do this unless ones wishes to implement their own functionality
for the Exception methods.

	5. The Timer.java has a static block static {}, what does it do? (determine when called by debugger)

Static blocks are used for static initializations of a class, and therefore
the code inside of the block is only executed once. We use the static block
in this instance to initialize the logger with its configFile and print any error messages we may have with the initialization.

	6. What is README.md file format how is it related to bitbucket? (https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html)

README.md (Mark-down) file format is used on BitBucket for formatting text. It is
used during any pull requests for any descriptions or comments and in README files
that have the .md file extension.

	7. Why is the test failing? what do we need to change in Timer? (fix that all tests pass and describe the issue)

In Timer.timeMe, timeNow was set to null, so (System.currentTimeMillis() - timeNow)
was throwing an exception that was not TimerException. This caused the test to fail,
as the test was expecting the TimerException. To fix this, initialize timeNow to 
System.currentTimeMillis().

	8. What is the actual issue here, what is the sequence of Exceptions and handlers (debug)

As described above, the order of Exceptions and handlers was
NullPointerException -> Handle NullPointerException -> TimerException
Handle TimerException. This caused an issue as the test was expecting 
TimerException but received NullPointerException.

	9. Make a printScreen of your eclipse JUnit5 plugin run (JUnit window at the bottom panel) 
	10. Make a printScreen of your eclipse Maven test run, with console
	11. What category of Exceptions is TimerException and what is NullPointerException

TimerException extends Exception, so it is checked. NullPointerException is a runtime
error and therefore is unchecked.

	12. Push the updated/fixed source code to your own repository.


