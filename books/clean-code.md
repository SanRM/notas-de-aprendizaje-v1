- [Meaningful Names](#meaningful-names)
  * [Use Intention-Revealing Names](#use-intention-revealing-names)
  * [Avoid disinformation](#avoid-disinformation)
  * [Make meaningful distinctions](#make-meaningful-distinctions)
  * [Use pronounceable names](#use-pronounceable-names)
  * [Use searchable names](#use-searchable-names)
  * [Avoid encodings](#avoid-encodings)
  * [Hungarian Notation](#hungarian-notation)
  * [Member prefixes.](#member-prefixes)
  * [Interfaces and Implementations](#interfaces-and-implementations)
  * [Avoid mental mapping](#avoid-mental-mapping)
  * [Class Names](#class-names)
  * [Method Names](#method-names)
  * [Don't be cute](#don-t-be-cute)
  * [Pick one word per abstract concept](#pick-one-word-per-abstract-concept)
  * [Don't pun](#don-t-pun)
  * [Use solution domain names](#use-solution-domain-names)
  * [Use problem domain names](#use-problem-domain-names)
  * [Add meaningful context](#add-meaningful-context)
- [Functions](#functions)
  * [Small!](#small-)
  * [Blocks and indenting](#blocks-and-indenting)
  * [Do One Thing](#do-one-thing)
  * [One level of abstraction per function](#one-level-of-abstraction-per-function)
  * [Reading Code from Top to Bottom](#reading-code-from-top-to-bottom)
  * [Switch statements](#switch-statements)
  * [Use descriptive names](#use-descriptive-names)
  * [Function arguments.](#function-arguments)
  * [Common monadic functions](#common-monadic-functions)
  * [Flag arguments](#flag-arguments)
  * [Dyadic functions.](#dyadic-functions)
  * [Triads](#triads)
  * [Argument objects](#argument-objects)
  * [Argument lists](#argument-lists)
  * [Verbs and keywords](#verbs-and-keywords)
  * [Have No Side Effects.](#have-no-side-effects)
  * [Output Arguments.](#output-arguments)
  * [Command query separation](#command-query-separation)
  * [Prefer Exceptions to Returning Error Codes](#prefer-exceptions-to-returning-error-codes)
  * [Extract Try/Catch Blocks.](#extract-try-catch-blocks)
  * [Error Handling Is One Thing.](#error-handling-is-one-thing)
  * [The `Error.java` dependency magnet](#the--errorjava--dependency-magnet)
  * [DRY (Don't Repeat Yourself)](#dry--don-t-repeat-yourself-)
  * [Structured Programming](#structured-programming)
  * [How do you write functions like this?](#how-do-you-write-functions-like-this-)
- [Comments](#comments)
  * [Comments Do Not Make Up for Bad Code](#comments-do-not-make-up-for-bad-code)
  * [Explain Yourself in Code](#explain-yourself-in-code)
  * [Good Comments](#good-comments)
    + [Legal Comments](#legal-comments)
    + [Informative Comments](#informative-comments)
    + [Explanation of Intent](#explanation-of-intent)
    + [Clarification](#clarification)
    + [Warning of Consequences](#warning-of-consequences)
    + [TODO Comments](#todo-comments)
    + [Amplification](#amplification)
  * [Bad Comments](#bad-comments)
    + [Mumbling](#mumbling)
    + [Redundant Comments](#redundant-comments)
    + [Misleading Comments](#misleading-comments)
    + [Mandated Comments](#mandated-comments)
    + [Journal Comments](#journal-comments)
    + [Noise Comments](#noise-comments)
    + [Scary Noise](#scary-noise)
  * [Don't Use a Comment When You can Use a Function or a Variable](#don-t-use-a-comment-when-you-can-use-a-function-or-a-variable)
  * [Position Markers](#position-markers)
  * [Closing Brace Comments](#closing-brace-comments)
  * [Attributes and Bylines](#attributes-and-bylines)
  * [Commented-Out Code](#commented-out-code)
  * [HTML Comments](#html-comments)
  * [Nonlocal Information](#nonlocal-information)
  * [Too Much Information](#too-much-information)
  * [Inobvious Connection](#inobvious-connection)
  * [Function Headers](#function-headers)
- [Formatting](#formatting)
  * [The Purpose of Formatting](#the-purpose-of-formatting)
  * [Vertical formatting](#vertical-formatting)
  * [Vertical openness between concepts](#vertical-openness-between-concepts)
  * [Vertical density](#vertical-density)
  * [Vertical distance](#vertical-distance)
  * [Horizontal formatting.](#horizontal-formatting)
  * [Horizontal Openness and Density](#horizontal-openness-and-density)
  * [Horizontal Alignment](#horizontal-alignment)
  * [Indentation](#indentation)
  * [Team Rules](#team-rules)
- [Objects and Data Structures](#objects-and-data-structures)
  * [Data Abstraction](#data-abstraction)
  * [Data/Object Anti-Symmetry](#data-object-anti-symmetry)
  * [The Law of Demeter](#the-law-of-demeter)
  * [Train Wrecks](#train-wrecks)
  * [Hybrids](#hybrids)
  * [Hiding structure](#hiding-structure)
  * [Data Transfer Objects](#data-transfer-objects)
  * [Active Record](#active-record)
- [Error Handling](#error-handling)
  * [Use Exceptions Rather Than Return Codes](#use-exceptions-rather-than-return-codes)
  * [Write Your Try-Catch-Finally Statement First](#write-your-try-catch-finally-statement-first)
  * [Use Unchecked Exceptions](#use-unchecked-exceptions)
  * [Provide Context with Exceptions](#provide-context-with-exceptions)
  * [Define Exception Classes in Terms of a Caller's Needs](#define-exception-classes-in-terms-of-a-caller-s-needs)
  * [Define the Normal Flow](#define-the-normal-flow)
  * [Don't Return Null](#don-t-return-null)
  * [Don't Pass Null](#don-t-pass-null)
- [Boundaries](#boundaries)
  * [Using Third-Party Code](#using-third-party-code)
  * [Exploring and learning boundaries](#exploring-and-learning-boundaries)
  * [Learning Tests Are Better Than Free](#learning-tests-are-better-than-free)
  * [Using Code That Does Not Yet Exist](#using-code-that-does-not-yet-exist)
  * [Clean Boundaries](#clean-boundaries)
- [Unit Tests](#unit-tests)
  * [The Three Laws of TDD](#the-three-laws-of-tdd)
  * [Keeping Tests Clean](#keeping-tests-clean)
  * [Tests Enable the -ilities](#tests-enable-the--ilities)
  * [Clean Tests](#clean-tests)
  * [Domain-Specific Testing Language](#domain-specific-testing-language)
  * [One Assert per Test](#one-assert-per-test)
  * [Single Concept per Test](#single-concept-per-test)
  * [F.I.R.S.T](#first)
- [Classes](#classes)
  * [Class organization](#class-organization)
  * [Encapsulation](#encapsulation)
  * [Classes Should Be Small!](#classes-should-be-small-)
  * [The Single Responsibility Principle](#the-single-responsibility-principle)
  * [Cohesion](#cohesion)
  * [Maintaining Cohesion Results in Many Small Classes](#maintaining-cohesion-results-in-many-small-classes)
  * [Organizing for Change](#organizing-for-change)
  * [Isolating from Change](#isolating-from-change)
- [Systems](#systems)
  * [Separate Constructing a System from Using It](#separate-constructing-a-system-from-using-it)
  * [Separation of Main](#separation-of-main)
    + [Factories](#factories)
    + [Dependency Injection](#dependency-injection)
  * [Scaling Up](#scaling-up)
    + [Cross-Cutting Concerns](#cross-cutting-concerns)
  * [Java Proxies](#java-proxies)
  * [Pure Java AOP Frameworks](#pure-java-aop-frameworks)
  * [AspectJ Aspects](#aspectj-aspects)
  * [Test Drive the System Architecture](#test-drive-the-system-architecture)
  * [Optimize Decision-Making](#optimize-decision-making)
  * [Use Standards Wisely, When They Add Demonstrable Value](#use-standards-wisely--when-they-add-demonstrable-value)
  * [Systems Need Domain-Specific Languages](#systems-need-domain-specific-languages)
- [Emergence](#emergence)
  * [Design Rule 1 - Runs All The Tests](#design-rule-1---runs-all-the-tests)
  * [Design Rule 2 - No Duplication](#design-rule-2---no-duplication)
  * [Design Rule 3 - Expressive](#design-rule-3---expressive)
  * [Design Rule 4 - Minimal Classes and Methods](#design-rule-4---minimal-classes-and-methods)
- [Concurrency](#concurrency)
  * [Why Concurrency?](#why-concurrency-)
  * [Myths and Misconceptions](#myths-and-misconceptions)
  * [Challenges](#challenges)
  * [Concurrency Defense Principles](#concurrency-defense-principles)
    + [Single Responsibility Principle](#single-responsibility-principle)
    + [Corollary: Limit the Scope of Data](#corollary--limit-the-scope-of-data)
    + [Corollary: Use Copies of Data](#corollary--use-copies-of-data)
    + [Corollary: Threads Should be as Independent as Possible](#corollary--threads-should-be-as-independent-as-possible)
  * [Know Your Library](#know-your-library)
    + [Thread-Safe Collections](#thread-safe-collections)
  * [Know Your Execution Models](#know-your-execution-models)
    + [Producer-Consumer](#producer-consumer)
    + [Readers-Writers](#readers-writers)
    + [Dining Philosophers](#dining-philosophers)
  * [Beware Dependencies Between Synchronized Methods](#beware-dependencies-between-synchronized-methods)
  * [Keep Synchronized Sections Small](#keep-synchronized-sections-small)
  * [Writing Correct Shut-Down Code Is Hard](#writing-correct-shut-down-code-is-hard)
  * [Testing Threaded Code](#testing-threaded-code)
    + [Treat Spurious Failures as Candidate Threading Issues](#treat-spurious-failures-as-candidate-threading-issues)
    + [Get Your Nonthreaded Code Working First](#get-your-nonthreaded-code-working-first)
    + [Make Your Threaded Code Pluggable](#make-your-threaded-code-pluggable)
    + [Make Your Threaded Code Tunable](#make-your-threaded-code-tunable)
    + [Run with More Threads Than Processors](#run-with-more-threads-than-processors)
    + [Run on Different Platforms](#run-on-different-platforms)
    + [Instrument Your Code to Try and Force Failures](#instrument-your-code-to-try-and-force-failures)
      - [Hand-Coded](#hand-coded)
      - [Automated](#automated)
- [Successive Refinement](#successive-refinement)
  * [Args Implementation](#args-implementation)
    + [How did I do this?](#how-did-i-do-this-)
  * [Args: The Rough Draft](#args--the-rough-draft)
    + [So I Stopped](#so-i-stopped)
    + [On Incrementalism](#on-incrementalism)
  * [String Arguments](#string-arguments)
  * [Conclusion](#conclusion)
- [Smells and Heuristics](#smells-and-heuristics)
  * [Comments](#comments-1)
  * [Environment](#environment)
  * [Functions](#functions-1)
  * [General](#general)
  * [Java](#java)
  * [Names](#names)
  * [Tests](#tests)

# Meaningful Names

## Use Intention-Revealing Names

* The name of a variable, function, or class should answer why it exists, what it does, and how it is used.

## Avoid disinformation

* Avoid words whose entrenched meanings vary from our intended meanings (i.e., `hp`, `aix`, etc.)

## Make meaningful distinctions

* Mention of noise words (i.e., `a`, `an`, `the`, etc.)
* Noise words are redundant.
* Distinguish names in such a way that the reader knows what the differences offer.

## Use pronounceable names

## Use searchable names

* Longer names trump shorter names, and any searchable name trumps a constant in code.
* Single-letter names can ONLY be used as local variables inside short methods. The length of a name should correspond to the size of its scope.

## Avoid encodings

* Encoded names are seldom pronounceable and are easy to mis-type.

## Hungarian Notation

* Trend toward smaller classes and shorter functions.
* Java programmers don't need type encoding.

## Member prefixes.

## Interfaces and Implementations

* If you must encode the interface or the implementation, choose the implementation (i.e., `ShapeFactoryImpl`).

## Avoid mental mapping

* Clarity is king. 

## Class Names

* Classes and objects should be nouns or noun phrases (i.e., `Customer`, `WikiPage`, etc.) 

## Method Names 

* Methods should have verbs or verb phrase names (i.e., `postPayment`, `deletePage`, etc.)
* Accessors, mutators and predicates should be named for their value and prefixed with `get`, `set` and `is`. 
* When constructors are overloaded, use static factory methods with names that describe the arguments (i.e., `Complex.FromRealNumber(23.0)`)

## Don't be cute

* Choose clarity over entertainment value.
* Say what you mean. Mean what you say.

## Pick one word per abstract concept

## Don't pun

* Avoid using the same word for two purposes.

## Use solution domain names 

## Use problem domain names

* When there is no "programmer-eese" for what you're doing, use the name from the problem domain. 

## Add meaningful context

* Shorter names are generally better than longer ones, so long as they are clear.

# Functions

## Small!

* Functions should not be 100 lines long and should hardly ever be 20 lines long.

## Blocks and indenting

* Blocks within if, else, while statements, and so on should be one line long.
* The indent level of a function should not be greater than one or two.

## Do One Thing

* FUNCTIONS SHOULD DO ONE THING. THEY SHOULD DO IT WELL. THEY SHOULD DO IT ONLY.

## One level of abstraction per function

* Like broken windows, once details are mixed with essential concepts, more and more details tend to accrete within the function.

## Reading Code from Top to Bottom

* The Stepdown rule.

## Switch statements

* Mention of polymorphism.
* Mention of Single Responsibility Principle (SRP).
* Mention of Open Closed Principle (OCP).
* Mention of Abstract Factory.
* Heuristic: switch statements can be tolerated if they appear only once, are used to create polymorphic objects, and are hidden behind an inheritance relationship so that the rest of the system can't see them.

## Use descriptive names

* Ward's principle: "You know you are working on clean code when each routine turns out to be pretty much what you expected."
* How? 1. Small functions, 2. Do one thing, 3. Good names.
* Long descriptive names over short enigmatic names.
* Be consistent in your names. Use the same phrases, nouns, and verbs in the function names you choose for your modules.

## Function arguments. 

* The ideal number of arguments for a function is zero (niladic). 
* Next comes one (monadic), followed closely by two (dyadic). 
* Three arguments (triadic) should be avoided where possible. 
* More than three (polyadic) requires very special justification, and then shouldn't be used anyway.
* Arguments are hard from conceptual, testing points of view.
* Mention of instance variable vs. input argument.
* Output arguments are harder to understand than input arguments.

## Common monadic functions

* Asking a question about the argument, transforming it into something else and returning it. 
* Choose names that make the distinction clear. 
* Event; overall program is meant to interpret the function call as an event and use the argument to alter the state of the system. Use this form with care. Choose
names and contexts carefully.
* Avoid monadic functions that don't follow these forms.

## Flag arguments

* Avoid.

## Dyadic functions. 

* Be aware that they come at a cost, and you should take advantage of what mechanisms are available to you to convert them into monads.

## Triads

## Argument objects

* When a function seems to need more than two or three arguments, it is likely that some of those arguments ought to be wrapped into a class of their own.

## Argument lists

## Verbs and keywords

* Choosing good names for a function can go a long way towards explaining the intent of the function and intent of the arguments.
* Example of `assertExpectedEqualsActual` over `assertEquals`.

## Have No Side Effects. 

* Mention of Temporal coupling.

## Output Arguments. 

* Much of the need for output arguments disappears in OO languages because `this` is intended to act as an output argument.
* Output arguments should be avoided.

## Command query separation

* Functions should either do something or answer something, but not both.

## Prefer Exceptions to Returning Error Codes

* When you return an error code, you create the problem that the caller must deal with error immediately. 
* The benefit of using exceptions is that the error processing code can be separated from the happy path code and can be simplified.

## Extract Try/Catch Blocks.

* Extract the bodies of the `try` and `catch` blocks out into functions of their own.

## Error Handling Is One Thing.

* A function that handles errors should do nothing else.

## The `Error.java` dependency magnet

* Fixed by using exceptions instead of error codes.

## DRY (Don't Repeat Yourself)

* Many principles and practices serve the practice of controlling or eliminating duplication.

## Structured Programming

* Single-entry, single-exit rule. 
* One return statement in a function.
* No break or continue statements in a loop.
* Never, ever, any goto statements.
* If you keep your functions small, the ocassional multiple `return`, `break`, or `continue` statement does no harm and can sometimes be more expressive than the single-entry, single-exit rule.

## How do you write functions like this? 

* Writing software is like any other kind of writing (i.e., an incremental process)

# Comments

* Comments are always failures.
* Why? Because they lie. Not always, not intentionally, but too often. Programmers can't realistically maintain them.

## Comments Do Not Make Up for Bad Code

* Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments.

## Explain Yourself in Code

* Example of using self-explaining class method.

## Good Comments

### Legal Comments

* Where possible, refer to a standard license or external document rather than putting all the terms and conditions into the comment.

### Informative Comments

* Example alternative of self-explaining class method.
* Example alternative of special class that converts the formats of dates and times.

### Explanation of Intent

* Provides the intent behind a decision.
* Example of comment explaining intent to get race condition.

### Clarification

* Translate the meaning of some obscure argument or return value into something that's readable.

### Warning of Consequences

* Example of warning about function not being thread safe.

### TODO Comments

* Jobs that the programmer thinks should be done, but for some reason can't do at the moment.
* Not an excuse to leave bad code in the system.
* Scan through them regularly and eliminate the ones you can.

### Amplification

* Amplify the importance of something that may otherwise seem inconsequential.

## Bad Comments

### Mumbling

* If you decide to write a comment, make sure it is the best comment you can write.
* Any comment that forces you to look in another module for the meaning of that comment has failed to communicate to you.

### Redundant Comments

* Not more informative and less precise than the code.
* Does not justify the code, or provide intent or rationale.
* Not easier to read than the code.

### Misleading Comments

* Statements in comments that are not precise enough to be accurate.

### Mandated Comments

* Abolish rules that enforce mandated comments.

### Journal Comments

* Should be removed. We have source control systems that make them obsolete.

### Noise Comments

* Restate the obvious and provide no new information.
* Replace temptation to create noise with determination to clean your code.

### Scary Noise

* Javadocs example.

## Don't Use a Comment When You can Use a Function or a Variable

## Position Markers

* Refrain from using.

## Closing Brace Comments

* Try to shorten functions instead.

## Attributes and Bylines

* Refrain from using, source control system is better at that.

## Commented-Out Code

* Don't do this!

## HTML Comments

* Abomination.

## Nonlocal Information

* If you must write a comment, then make sure it describes the code it appears near.

## Too Much Information

* Don't put interesting historical discussions or irrelevant descriptions of details into comments.

## Inobvious Connection

* The connection between a comment and the code it describes should be obvious.

## Function Headers

* A well-chose name for a small function that does one thing is usually better than a comment header.

# Formatting

## The Purpose of Formatting

* Code formatting is about communication, and communication is the professional developer's first order of business.

## Vertical formatting

* Small files are usually easier to understand than large files are.
* The Newspaper metaphor.

## Vertical openness between concepts

* Nearly all code is read left to right and top to bottom.
* Each line represents an expression or a clause.
* Each group of lines represents a complete thought. Those thoughts should be separated from each other with blank lines.

## Vertical density

* Lines of code that are tightly related should appear vertically dense.

## Vertical distance

* Concepts that are closely related should be kept vertically close to each other.
* *Variable declarations*. Variables should be declared as closed to their usage as possible.
* *Instance variables*. Should be declared at the top of the class.
* *Dependent functions.* If one function calls another, they should be vertically close, and the caller should be above the callee, if at all possible.
* *Conceptual affinity.* The stronger the conceptual affinity between bits of code, the less vertical distance there should be between them.
* *Vertical ordering.* A function that is called should be below a function that does the calling.
 
## Horizontal formatting. 

* Strive to keep lines short (120 characters).

## Horizontal Openness and Density

* Use horizontal white space to associate things that are strongly related and disassociate things that are more weakly related.
* Examples: assignment operators, function names and the opening parenthesis, precedence of operators.

## Horizontal Alignment

* Prefer unaligned declarations and assignments.
* If there are long lists that need to be aligned, the problem is the length of the lists, not the lack of alignment.

## Indentation

* *Breaking Indentation.* TL;DR don't.
* *Dummy Scopes.* Avoid.

## Team Rules

* A team of engineers should agree upon a single formatting style, and then every member of that team should use that style.

# Objects and Data Structures

## Data Abstraction

* A class exposes abstract interfaces that allow its users to manipulate the essence of the data, without having to know its implementation.
* Examples of Point class and Vehicle interface.

## Data/Object Anti-Symmetry

* Objects hid their data behind abstractions and expose functions that operate on that data. Expose behavior, hide data.
* Data structures expose their data and have no meaningful functions.
* Example of Geometry class.
* Example of polymorphic shape classes.
* Procedural code: easy to add new functions, hard to add new data structures.
* OO code: easy to add new classes, hard to add new functions.
* Heuristic: whether we want to add new data types or we want to add new functions informs the decision of whether to use procedural or OO code.

## The Law of Demeter

* A method `m` of an object `a` may only invoke the methods of the following kinds of objects: `a` itself, `m`'s parameters, any objects instantiated within `m`, `a`'s attributes, global variables accessible by `a` in the scope of `m`.
* Specific case of loose coupling.

## Train Wrecks

* Chains of calls are generally considered to be sloppy style should be avoided.
* Discussion on whether example block violates the Law of Demeter.

## Hybrids

* Hybrid structures that are half objects and half data structures.
* Avoid creating them because they are the worst of both worlds.

## Hiding structure

* If working with an object, we should be telling it to do *something*.

## Data Transfer Objects

* Quintessential form of a data structure: a class with public variables and no functions.
* Data transfer object, DTO.
* Beans are examples of DTOs.
* `Address` class example.

## Active Record

* Special forms of DTOs.
* Data structures with public (or bean-accessed) variables; but they typically have navigational methods like `save` and `find`.
* Usually direct translations from database tables, or other data sources.
* Treat them as data structures.

# Error Handling

## Use Exceptions Rather Than Return Codes

* Old approach: either set an error flag or return an error code that the caller could check.
* Problem: clutters the caller with error checks; it is also easy to forget to check all errors.
* Solution: throw an exception when you encounter an error.
* Benefit: 1) cleaner from lack of error handling obstruction, 2) you will not miss errors you would have to check otherwise

## Write Your Try-Catch-Finally Statement First

* Try block transaction analogy.
* Catch is responsible to leave program in a consistent state. Think of it as doing the rollback in a database transaction.
* Helps you think what the user of the code should expect, no matter what goes wrong with the code that is executed in the try.
* Add tests that force exceptions, then add behaviour to handler to satisfy the tests.

## Use Unchecked Exceptions

* Checked exception are not necessary for the production of robust software.
* Cost of checked exceptions? Violation of open/closed principle and encapsulation.
* Benefit? None unless you are writing a critical library and must catch that checked exception.

## Provide Context with Exceptions

* Goal: provide enough context to determine the source and location of an error.
* Guideline: 1. create informative error messages and instantiate the exception with them. 2. Mention a. the operation that failed and b. the type of failure. Log the exception in the catch.

## Define Exception Classes in Terms of a Caller's Needs

* Most important concern in defining exception classes is how they are caught.
* Handling 3rd party library call exceptions guidance.
* Use different exception classes only if you want to catch one exception and allow the other one to pass through.

## Define the Normal Flow

* Special case pattern.
* Create a class or configure an object so that it handles a special case for you.

## Don't Return Null

* Guidance 1: if you are tempted to return null from a method, consider throwing an exception or returning a special case object instead.
* Guidance 2: if you are calling a non-null returning method for a third-party library, consider wrapping that with a method that throws an exception or returns a special case object.
* Example of empty list as special case object.

## Don't Pass Null

* Guidance: avoid passing null in your code whenever possible.
* No good way to deal with a null that is passed by a caller accidentally.

# Boundaries

## Using Third-Party Code

* Example of using generics to improve code readability.
* Better way: do not pass 3rd party interfaces around system. Encapsulation is one way to achieve that.

## Exploring and learning boundaries

* Concept of learning tests; call the third-party APIs, as we expect to use them in our application. Controlled experiments.

## Learning Tests Are Better Than Free

* Additional benefits; validate for breaking changes during upgrades.
* Boundary tests.

## Using Code That Does Not Yet Exist

* Write interface under your control. Add adapter when 3rd party API is ready.

## Clean Boundaries

* Manage 3rd party interfaces by having very few places in the code that refer to them.
* Solutions/patterns: 1. encapsulate them, or 2. use an adapter to convert from perfect to provided interface.

# Unit Tests

## The Three Laws of TDD

* You may not write production code until you have written a failing unit test.
* You may not write more of a unit test than is sufficient to fail, and not compiling is failing.
* You may not write more production code than is sufficient to pass the currently failing test.
* The tests and the production code are written together.

## Keeping Tests Clean

* Test code is just as important as production code.

## Tests Enable the -ilities

* Unit tests keep code flexible, maintainable, and reusable. 
* Having an automated suite of unit tests that cover the production code is the key to keeping your design and architecture as clean as possible. Tests enable all the -ilities, because tests enable change.

## Clean Tests

* Readability is what makes a clean test. 
* What makes tests readable? The same thing that makes all code readable: clarity, simplicity, density of expression. 
* [Build-check-pattern](https://dkbalachandar.wordpress.com/2016/05/09/build-operate-check-acceptance-pattern/). Build up the test data, operate on the test data, check that the operation yielded the expected result.

## Domain-Specific Testing Language

* Testing language. Will not exist upfront, but it rather evolves from the continued refactoring of test code that has failed a threshold of readability. 

## One Assert per Test

* School of thought that every test function in JUnit should have one and only assert statement.
* Mention of given-when-then test naming convention.
* Mention of the [template method pattern](https://refactoring.guru/design-patterns/template-method/java/example#:~:text=Template%20Method%20is%20a%20behavioral,changing%20the%20overall%20algorithm's%20structure.). 

## Single Concept per Test

* Minimize the number of asserts per concept and test just one concept per test function. 

## F.I.R.S.T

* Fast. Independent. Repeatable. Self-Validating. Timely. 

# Classes

## Class organization

* Order: public static constants, private static variables, private instance variables, public functions, private utilities.
* Follow stepdown rule.

## Encapsulation

* Loosening encapsulation (i.e., making variables and utility functions non-private) is always a last resort.

## Classes Should Be Small!

* Count number of responsibilities.
* The name of a class should describe what responsibilities it fulfills.

## The Single Responsibility Principle

* A class or module should have one, and only one, reason to change.
* Trying to identify responsibilities (reasons to change) often helps us recognize and create better abstractions in our code.
* We want our systems to be composed of many small classes, not a few large ones. Each small class encapsulates a single responsibility, has a single reason to change, and collaborates with a few others to achieve the desired system behaviors.
* Tools and toolboxes analogy.

## Cohesion

* The more variables a method manipulates the more cohesive that method is to its class.
* We would like cohesion to be high.

## Maintaining Cohesion Results in Many Small Classes

* When classes lose cohesion, split them.
* Breaking a large function into many smaller functions often gives opportunity to split several smaller classes out as well.
* `PrintPrimes` program example.

## Organizing for Change

* Mention of OCP (Open-Closed Principle: Open for extension but closed for modification).
* Structure systems so that we muck with as little as possible when we update them with new or changed features.

## Isolating from Change

* Mention of DIP (Dependency Inversion Principle).
* Our classes should depend upon abstractions, not on concrete details.

# Systems

## Separate Constructing a System from Using It

* Mention of Lazy Initialization/Evaluation idiom.

## Separation of Main

* The `main` function builds the objects necessary for the system, then passes them to the application, which simply uses them.

### Factories

* Abstract factory pattern.

### Dependency Injection

* Dependency Injection (DI) is a mechanism to separate construction from use.
* It is the application of Inversion of Control (IoC) to dependency management; an object should not take responsibility for instantiating dependencies itself. Instead, it should pass this responsibility to another "authoritative" mechanism, thereby inverting the control.
* Spring Framework provides the best known DI container for Java.

## Scaling Up

### Cross-Cutting Concerns

* Examples: persistence, security, transactions, caching, failover.
* Mention of Aspect-Oriented programming (AOP). Modular constructs called aspects specify which points in the system should have their behavior modified in some consistent way to support a particular concern.

## Java Proxies

* Interface `Bank`, wrapped by the proxy, and a Plain-Old Java Object (POJO), `BankImpl`, that implements the business logic.
* Proxy API requires `InvocationHandler` object. `BankProxyHandler` uses the Java reflection API to map the generic method invocations to the corresponding methods in `BankImpl`, and so on.

## Pure Java AOP Frameworks

* Spring AOP, JBoss AOP.
* Each "bean" is like one part of a nested "Russian doll".
* Mention of data accessor object (DAO).
* Mention of nested decorators.

## AspectJ Aspects

* AspectJ language, an extension of Java that provides "first-class" support for aspects.

## Test Drive the System Architecture

* Ideal of writing application's domain logic using POJOs, decoupled from any architecture concerns at the code level.
* Mention of Big Design Up Front (BDUF).

## Optimize Decision-Making

* Modularity and separation of concerns make decentralized management and decision-making possible.
* It is best to postpone decisions until the last possible moment.

## Use Standards Wisely, When They Add Demonstrable Value

## Systems Need Domain-Specific Languages

* Mention of Domain-Specific Languages (DSLs).

# Emergence

## Design Rule 1 - Runs All The Tests

* A design must produce a system that acts as intended.
* A system that is comprehensibly tested and passes all of its tests all the time is a testable system.

## Design Rule 2 - No Duplication

* Duplication is the primary enemy of a well-designed system; additional work, risk, and unnecessary complexity.
* Mention of TEMPLATE METHOD pattern.

## Design Rule 3 - Expressive

* The majority of the cost of a software project is in long-term maintenance.

## Design Rule 4 - Minimal Classes and Methods

* Keep overall system small while also keeping functions and class small.

# Concurrency

## Why Concurrency?

* Concurrency is a decoupling strategy: decouple what gets done from when it gets done.
* Concurrency improves both the throughput and the structures of an application.

## Myths and Misconceptions

Common myths and misconceptions:
* Concurrency always improves performance
* Design does not change when writing concurrent programs
* Understanding concurrency issues is not important when working with a container such as a Web or EJB container

Correct assumptions:
* Concurrency incurs some overhead
* Correct concurrency is complex
* Concurrency bugs aren't usually repeatable
* Concurrency often requires a fundamental change in design strategy.

## Challenges

* Example with shared class instance between two threads.

## Concurrency Defense Principles

### Single Responsibility Principle

* Rec: Keep your concurrency-related code separate from other code.

### Corollary: Limit the Scope of Data

* Rec: Take data encapsulation to heart; severely limit the access of any data that may be shared.

### Corollary: Use Copies of Data

### Corollary: Threads Should be as Independent as Possible

* Rec: Attempt to partition data into independent subsets that can be operated on by independent threads, possibly in different processors.

## Know Your Library

### Thread-Safe Collections

* Rec: Review the classes / packages available to you.

## Know Your Execution Models

### Producer-Consumer

* The queue / buffer between the producers and consumers is a bound resource.

### Readers-Writers

* Tough balancing act between throughput and starvation and accumulation of stale info.

### Dining Philosophers

* Philosophers = threads, forks = resources.
* Rec: Learn the basic algorithms and understand their solutions.

## Beware Dependencies Between Synchronized Methods

* Rec: Avoid using more than one method on a shared object.
* Otherwise: Client-Based Locking, Server-Based Locking, Adapted Server.

## Keep Synchronized Sections Small

* Rec: Keep your synchronized sections as small as possible.

## Writing Correct Shut-Down Code Is Hard

* Rec: Think about shut-down early and get it working early. It's going to take longer than you expect. Review existing algorithms because this is probably harder than you think.

## Testing Threaded Code

* Rec: Write tests that have the potential to expose problems and then run them frequently, with different programmatic configurations and system configurations and load. If tests ever fail, track down the failure. Don't ignore a failure just because the tests pass on a subsequent run.

### Treat Spurious Failures as Candidate Threading Issues

* Rec: Do not ignore system failures as one-offs.

### Get Your Nonthreaded Code Working First

* Rec: Do not try to chase down nonthreading bugs and threading bugs at the same time. Make sure your code works outside of threads.

### Make Your Threaded Code Pluggable

* Rec: Make your thread-based code especially pluggable so that you can run it in various configurations.

### Make Your Threaded Code Tunable

* Getting the right balance of threads typically requires trial and error.

### Run with More Threads Than Processors

* The more frequently context switching occurs, the more likely you'll encounter code that is missing a critical section or causes deadlock.

### Run on Different Platforms

* Rec: Run your threaded code on all target platforms early and often.
* Note: Less applicable in the era of containerized applications.

### Instrument Your Code to Try and Force Failures

#### Hand-Coded

* Divide system up into POJOs that know nothing of threading and classes that control the threading.

#### Automated

* Tools like Aspect-Oriented Framework, CGLIB, or ASM, ConTest.
* Rec: Use jiggling strategies to ferret out errors.

# Successive Refinement

## Args Implementation

Note: this chapter is particularly difficult to read because it contains a lot of code.

### How did I do this?

* To write clean code, you must first write dirty code and then clean it.

## Args: The Rough Draft

### So I Stopped

* `ArgumentMarshaller`.

### On Incrementalism

* Discipline of Test-Driven Development (TDD).

## String Arguments

* Putting things in so that you can take them out again is pretty common in refactoring. Rubik's cube analogy.
* Much of good software design is simply about partitioning -- creating appropriate places to put different kinds of code. This separation of concerns makes the code much simpler to understand and maintain.

## Conclusion

* Bad schedules can be redone, bad requirements can be redefined. Bad team dynamics can be repaired. But bad code rots and ferments.

# Smells and Heuristics

## Comments

* C1: Inappropriate Information.
* C2: Obsolete Comment.
* C3: Redundant Comment.
* C4: Poorly Written Comment.
* C5: Commented-Out Code.

## Environment

* E1: Build Requires More Than One Step
* E2: Tests Require More Than One Step

## Functions

* F1: Too Many Arguments
* F2: Output Arguments
* F3: Flag Arguments
* F4: Dead Function

## General

* G1: Multiple Languages in One Source File
* G2: Obvious Behavior is Unimplemented. Mention of "The Principle of Least Surprise".
* G3: Incorrect Behavior at the Boundaries.
* G4: Overriden Safeties.
* G5: Duplication. Mention of DRY principle. Duplication is a missed opportunity for abstraction. Mention of polymorphism. Mention of template method, strategy pattern.
* G6: Code at Wrong Level of Abstraction.
* G7: Base Classes Depending on Their Derivatives.
* G8: Too Much Information.
* G9: Dead Code.
* G10: Vertical Separation.
* G11: Inconsistency.
* G12: Clutter.
* G13: Artificial Coupling.
* G14: Feature Envy. Eliminate Feature Envy because it exposes the internals of one class to another.
* G15: Selector Arguments. Better to have many functions than to pass some code into a function to select the behavior.
* G16: Obscured Intent.
* G17: Misplaced Responsibility.
* G18: Inappropriate Static. In general, you should prefer nonstatic methods to static methods.
* G19: Use Explanatory Variables
* G20: Function Names Should Say What They Do
* G21: Understand the Algorithm
* G22: Make Logical Dependencies Physical
* G23: Prefer Polymorphism to If/Else or Switch/Case
* G24: Follow Standard Conventions
* G25: Replace Magic Numbers with Named Constants
* G26: Be Precise. Ambiguities and imprecision in code are either a result of disagreements or laziness. In either case they should be eliminated.
* G27: Structure over Convention. Enforce design decisions with structure over convention.
* G28: Encapsulate Conditionals.
* G29: Avoid Negative Conditionals.
* G30: Functions Should Do One Thing
* G31: Hidden Temporal Couplings. Structure the arguments of your functions such that the order in which they should be called is obvious.
* G32: Don't Be Arbitrary.
* G33: Encapsulate Boundary Conditions. Boundary conditions are hard to keep track of. Put the processing for them in one place.
* G34: Functions Should Descend Only One Level of Abstraction.
* G35: Keep Configurable Data at High Levels
* G36: Avoid Transitive Navigation. The Law of Demeter.

## Java

* J1: Avoid Long Import Lists by Using Wildcards.
* J2: Don't Inherit Constants. Mention of static import.
* J3: Constants versus Enums.

## Names

* N1: Choose Descriptive Names
* N2: Choose Names at the Appropriate Level of Abstraction
* N3: Use Standard Nomenclature Where Possible
* N4: Unambiguous Names
* N5: Use Long Names for Long Scopes
* N6: Avoid Encodings
* N7: Names Should Describe Side Effects

## Tests

* T1: Insufficient Tests
* T2: Use a Coverage Tool!
* T3: Don't Skip Trivial Tests
* T4: An Ignored Test Is a Question about an Ambiguity
* T5: Test Boundary Conditions
* T6: Exhaustively Test Near Bugs
* T7: Patterns of Failure Are Revealing
* T8: Test Coverage Patterns Can Be Revealing
* T9: Tests Should Be Fast

