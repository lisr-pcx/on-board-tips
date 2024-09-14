# Technical Documentation

Forget the idea "My code is self documented", anyone who use your baseline need a good source of information about logical operations, design choice, guidelines, theory behind .. , troubleshooting, tips and tricks.  
Do not confuse writing clear - and clean - code, with the documentation process, they are both necessary but they have different goal.

Remember that writing documentation is part of the task. Only once documentation is added the activity can be mark as done.

## How to write technical documents

Identify your audience:

+ Internal use (System design, architecture ..)
  Things that your worked on, that bugged you, what's unclear

+ External use (API doc, ..)
  Quick start, issues, FAQ, examples ..

Always include a table of contents or summary in your documentation, and keep in mind the reader approach follow these steps:

1. SEARCH (meaningful titles, headings, keywords, tags)
2. SCAN (the entire page without reading)
3. NAVIGATE (links to related topics)
4. RESULT (short words and more sentences)

Write in simple english, anyone can do that, **just be clear, simple and go straight to the point**. The goal is to provide information (to help people), this is not an essay.

Always share your text/draft with other team members and ask for feedbacks/reviews to improve clarity.

!!! tip
    Avoid "single points of failure": don't be the silo of information of your team.  
    If you are the only one able to fix/do some stuff then forget about holidays and relaxing time.  
    Share knownledge and make everyone confortable to manage the source code.

## Docs as a Code

Documentation as code is the process of creating and maintaining documentation in the same way as it is done for code.  
This involves usually version control software, Markdown formatting, and defined workflows. In this way the development and product teams work closely together, and easily share the knownledge.

Another benefit is that your documents are always updated and synchronized with the development process (CI/CD integration).

## Writing tips by J. Schulgasser (Wix)

+ Assume that your audience is already familir with industry/terms, but make sure to explain anything project-specific
+ Use active words for any action performed by reader/system.
+ Use the present tense for all situation (future tense is almost never required or desiderable).
+ Use sentence case in headers.
+ Capitalize proper names.
+ Always capitalize acronyms.
+ Do not use gerunds in task headers.
+ Use numbered list to indicate steps in sequence and bulleted lists otherwise.
+ For each steps describe where the step occurs, what to do, and what the expected result is (if applicable)
+ Long procedures should be broken up into several smaller ones.
+ If it is a feature name then should be capitalized.
+ Link the first use to a definition if they are unfamiliar.
+ Continually use the same terms for UI elements, system entities, and actions.
+ A reader should be able to find all uses of the same word by performing a simple search.
+ Emphasize important content using notes or bold text.
+ Use bold for words that appear in the UI.
+ Never use gender pronouns.
+ Use links that contains the subject to which they are linking.
+ Make use of automated spelling and grammars tools.
+ Add useful alternative text for images.

## Links

[Tech Docs, how can I write them better](https://youtu.be/0e22AQJTuOA)  