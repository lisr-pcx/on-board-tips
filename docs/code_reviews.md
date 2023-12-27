# Code Reviews

The term is used to identify all the activities of code analysis with the goal to identify bugs, non conformities and design flaws. After the review the code changes are usually merged with the official codebase and/or delivered to final users.

This process can be formal or informal, but in any case it is suggested to follow some guidelines (create them if not defined). Technically there are multiple way to perform a review: email thread, company templates (word, excel), tools-assisted (Git cloud web services).

Keep in mind that for new developers the code review can be a way to discover and understand the sw architecture and the sourcecode.

During a review these aspect shall be considered:

+ coding style (use sw tools for checking)
+ coding rules
+ safety and defensive code
+ sw requirements
+ logic, algorithms, and code flow
+ design and architecture (flexibility and mantenibility)
   
Code reviews are not an exam, the scope is to check the code not the programmer who wrote it. Do not set or perceive code reviews as a personal attack. The reviewer wants the same as you: creating high-quality software, you are both on the same side.

## Rules for the programmer

Have an *open and humble mindset* about the feedback you are going to receive.

+ Mind that code can be improved
+ You are not perfect. Accept that you will make mistakes
+ Don’t infer your professionalism and reliability as a software developer from infallibility and flawlessness of your code
+ Mind the IKEA effect. You might place a too high value on your own code
+ Consider feedback as a valuable new perspective on your code (avoids a tunnel vision)
+ Code reviews are a valuable source of best practices and experiences
+ Code reviews are a discussion, not a dictation. It’s fine to disagree, but you have to elaborate your reservations politely and be willing to make compromises

## Rules for the reviewer

For the reviewer, it’s important to pay attention to *the way they formulate the feedback*. This is extremely crucial for your feedback to be accepted.

+ Use I-messages:
    - Right: “It’s hard for me to grasp what’s going on in this code.”
    - Wrong: “You are writing cryptic code.”
+ Talk about the code, not the coder.
    - Right: “This code is requesting the service multiple times, which is inefficient.”
    - Wrong: “You’re requesting the service multiple times, which is inefficient.”
+ Ask questions instead of making statements.
    - Right: “What do you think about the name ‘userId’ for this variable?”
    - Wrong: “This variable should have the name ‘userId’.”
+ Always refer to the behavior, not the traits of the author.
    - Right: “I believe that you should pay more attention to writing tests.”
    - Wrong: “You are sloppy when it comes to writing tests.”
+ Accept that there are different solutions
    - Right: “I would do it in another way, but your solution is also fine.”
    - Wrong: “I always do it this way and you should too.”
    - Distinguish between common best practices and your personal taste.
    - Mind that your criticism may just reflect your personal taste and not an objectively wrong code.
    - Make compromises and be pragmatic.
+ Don’t jump in front of every train
    - Don’t be a pedant. Don’t criticize every single line in the code. This will annoy the author and reduce their openness to further feedback.
    - Focus on the flaws and code smells that are most important to you.
+ Respect and trust the author
    - Nobody writes bad code on purpose.
    - The author wrote the code to the best of their knowledge and belief.
+ Mind the **OIR rule** of giving feedback
    - Observation: “This method has 100 lines.”
    - Impact: “This makes it hard for me to grasp the essential logic of this method.”
    - Request: “I suggest extracting the low-level-details into subroutines and give them expressive names.”
+ Before giving feedback, ask yourself:
    - Is it true? (opinion != truth)
    - Is it necessary? (avoid nagging, unnecessary comments and out-of-scope work)
    - Is it kind? (no shaming)
+ Be humble! You are not perfect and you can also improve.
+ It’s fine to say: Everything is good!
+ Don’t forget to praise.

## Focus on
   
### Coding style and coding rules

In progress

Quick overview on static analysis tools

### Safety and defensive code

In progress

Quick overview on dynamic analysis tools

### SW requirements

In progress

### Logic algorithms and code flow

In progress

### Design and architecture

In progress

## Links and resources

[Google code review overview](https://google.github.io/eng-practices/review/)

[Guidelines for better, faster pull request reviews](https://github.com/mawrkus/pull-request-review-guide)

[Curated list of resources about code reviews](https://github.com/mgreiler/all-about-code-review)

[Awesome list of code review resources](https://github.com/joho/awesome-code-review)

[Michael Lynch post](https://mtlynch.io/code-review-love/)
