---
layout: default
title: welcome
---

![i icon](assets/icons8-info-100.png){: .icon }
## Welcome

Welcome to the home of COMS20007: Programming Languages and Computation.  

This 20cp unit introduces you to some of the fundamentals of programming languages.  We will look at two very simple programming languages: a domain specific language for string matching, called *Regular Expressions*, and a general purpose imperative programming language called *While*.  In each case, we will study their:
  * *Syntax and semantics:* how to describe the programming language mathematically.
  * *Expressive power:* how to understand the limitations of the programming language by proving theorems.

This unit gives you a taster of several important topics in theoretical computer science: [Programming Language Theory](https://en.wikipedia.org/wiki/Programming_language_theory), [Theory of Formal Languages](https://en.wikipedia.org/wiki/Formal_language) and [Computability Theory](https://en.wikipedia.org/wiki/Computability_theory). It prepares you for courses in the programming languages theme in your third and fourth year, especially *COMS30040: Types and Lambda Calculus* and *COMSM0067: Advanced Topics in Programming Languages*, but it's primary purpose is to make you better at *thinking* about computer programs.

* * *

![contacts](assets/icons8-smartphone-tablet-100.png){: .icon }
## Contacts

The unit is run by François Dupressoir, Alex Kavvos and Steven Ramsay.

{: .invisitable style="margin:2em 0em 0em 2em;"}
|![Francois](Francois.jpg) |![Alex](Alex.jpg) |![Steven](wbc.jpg)  |
| [François Dupressoir][1] | [Alex Kavvos][2] | [Steven Ramsay][3] |

[1]: https://fdupress.net/
[2]: https://www.lambdabetaeta.eu
[3]: https://sjrsay.github.io

Outside of lectures and labs, please reach out to us via the unit [Team](https://teams.microsoft.com/l/channel/19%3a2NEgj0jbvDp5YdVZoqdcuNkusuf8W4rNUDpeDcMclPE1%40thread.tacv2/General?groupId=c1248506-faa4-4027-8362-142951c82bcc&tenantId=b2e47f30-cd7d-4a4e-a5da-b18cf1a4151b) rather than by email.  Feel free to ask questions about the unit material, how the units runs, or anything at all to do with programming language theory, formal language theory or computability right in the [General](https://teams.microsoft.com/l/channel/19%3a2NEgj0jbvDp5YdVZoqdcuNkusuf8W4rNUDpeDcMclPE1%40thread.tacv2/General?groupId=c1248506-faa4-4027-8362-142951c82bcc&tenantId=b2e47f30-cd7d-4a4e-a5da-b18cf1a4151b) channel.  We love to hear what you are thinking!


* * *

![schedule](assets/icons8-schedule-100.png){: .icon }
## Schedule

*See [detailed schedule](schedule.html) for a comprehensive day-by-day synopsis.*

The unit is divided into three parts, each of which is run by one of the three lecturers.

{: .pure-table-striped .pure-table}
| Period | Lecturer | Topic |
|:------:|:--------:|:------| 
| Weeks 1-4    | Steven Ramsay | Regular Expressions |
| Weeks 5,7  | François Dupressoir | While Language: Operational Semantics |
| Weeks 8-11   | Alex Kavvos | While Language: Expressive Power  |

<br/>

You should expect to spend around *12 hours per week* working on this unit.  There are 5 main activities (approximate time in parentheses, overall there is some slack):

  * __Lectures (2 hr).__ There are two lectures each week, *Thursdays at 3pm* and *Fridays at 2pm in Chemistry LT1*. 

  * __Q&A (1 hr).__ Except in Week 1, on Mondays at 10am, we have a lecture slot in the timetable, but we will use it as a Q&A session where you can ask about the problems from the previous week, or any of the material so far in the unit.  Like office hours, but on a larger scale.

  * __Labs (2 hr).__  Except in Week 1, labs run every Monday from 11am-1pm in MVB 2.11 and MVB 1.15.  Most of the time, you will need pen and paper to work on the problems, occasionally you will want to do some (Haskell) programming.  We have an excellent selection of teaching assistants on this unit, and their sole responsibility in each lab is to *help you*.  Some of the problems are not designed to be solved by a single person in a short amount of time, so you will need the help of the TAs and/or the help of your peers in order to solve them. 

  * __Problem sheets (2-6 hr).__ You will only learn on this unit by completing the problem sheets.  There is one sheet released each week.  You will spend time working on the sheets in labs, but you will likely need longer to complete them fully in your own time.

  <!-- * __Office hours (<1 hr).__ Each week there will be office hours with the lecturer, either online or in their office in MVB.  These will be irregular and advertised separately in each week. -->

  * __Reading (2 hr).__  You will often benefit from alternative explanations of the same concepts, which would not fit into the time available for lectures.  You will need to spend time revising and rethinking topics before you can solve the associated problems.

*The most important activity is to give a serious attempt (at least 3 hours) to each problem sheet and get help when you are stuck. The easiest way to do this is to attend the weekly lab.  If you do not, you will likely fail this unit.*

* * *

![map and marker](assets/icons8-map-marker-100.png){: .icon }
## Navigating the course

The unit is distributed over four locations:

* This [blackboard page][bb], which contains:
    - the [welcome page](welcome.html), listing administrative information about the unit
    - the [detailed schedule](schedule.html), which gives brief lecture synopses, the problem sheets and their solutions

* The [reference book][rf]{: target="_blank" }, which contains a reference version of technical material introduced in the lectures: you will need to refer to this when completing the problems.  

* The [team][te]{: target="_blank" }, where you post your questions and we do our best to answer them.

[bb]: https://www.ole.bris.ac.uk/auth-saml/saml/login?apId=_183_1&redirectUrl=https%3A%2F%2Fwww.ole.bris.ac.uk%2Fwebapps%2Fblackboard%2Fexecute%2FcourseMain%3Fcourse_id%3D_247719_1
[rf]: https://uob-coms20007.github.io/reference/
[lc]: https://github.com/uob-coms20007/labcode
[te]: https://teams.microsoft.com/l/channel/19%3a2NEgj0jbvDp5YdVZoqdcuNkusuf8W4rNUDpeDcMclPE1%40thread.tacv2/General?groupId=c1248506-faa4-4027-8362-142951c82bcc&tenantId=b2e47f30-cd7d-4a4e-a5da-b18cf1a4151b

* * *

![report card](assets/icons8-report-card-100.png){: .icon } 
## Assessment

The unit is 100% assessed by a written exam in the January exam period.

This exam is considered open book in the following sense:
*Candidates may bring to the exam room 1 double-sided A4 page of notes in any format.*

In addition, almost all of the important definitions from the unit are available for your reference at the back of the exam paper.  A practice paper is available [here](papers.html) so that you can familiarise yourself with the format.

The exam is a series of problems to solve in the same style as the weekly problem sheets.  There will be questions covering material from all parts of the unit.  The difficulty of questions is related to your possible marks in the following way:

* 1* questions only account for approximately 40% of available marks.
* 1* and 2* questions account for approximately 70% of available marks.
* 1\*, 2\* and 3* questions account for approximately 100% of available marks.

Unfortunately, this is not quite true for the practice paper linked above, because we had to assemble it from a number of sources due to changes in the material taught this year.  Partial marks are given for partially correct answers.  This is important, because you are unlikely to answer all the 3* question(s) completely correctly in the given time, but it is possible to obtain some marks for an attempt.

The distribution of marks by topic is as follows:
* 40 marks are available for questions on regular expressions, automata and regular languages.
* 30 marks are available for questions on the syntax and semantics of the While language.
* 30 marks are available for questions on computability.

However, *you should make sure you are confident on all topics* because the exam will contain 1*, 2* and 3* questions within each of these topics.

General feedback sent to students on the overall performance in last years exam can be viewed [here](feedback.txt).  Note, the question numbers do not correspond directly to those in the practice paper (linked above) because the practice paper is not exactly the same as last year's exam, due to changes in the material taught for this year.

* * *

{: style="text-align:center"}
Icons in this course are from the '[Hand Drawn](https://icons8.com/icons/carbon-copy)' icon collection by [Icons8](https://icons8.com/).