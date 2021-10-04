---
layout: default
title: lab info
---

![pi icon](assets/icons8-pi-100.png){: .icon }
## Problem Sheets

Problem sheets alternate between Haskell programming and pen-and-paper solving.  You should expect to spend around 4-6 hours on each problem sheet.

  * Problem sheets in *odd numbered* weeks mostly require Haskell programming
  * Problem sheets in *even numbered* weeks only require pen-and-paper problem solving

Each new problem sheet and the solutions for the previous sheet are released on Mondays at 2am UTC.  Links can be found in the [detailed schedule](schedule.html).  For solutions to Haskell coding problems, see below.

* * *

![test tube icon](assets/icons8-test-tube-100.png){: .icon }
## Labs

Excepting week 1, the labs are Thursdays 1pm-3pm.  During the labs you can get help with the problem sheets from expert TAs and the lecturers.  There are two ways to participate in the labs:

  * In-person, in Bill Brown Suite (except Week 1).   If you have a laptop, please bring it to the lab on odd numbered weeks (although it is generally useful in all weeks to be able to look up definitions etc).  If you cannot bring your own laptop, you are welcome to borrow one of the Suite's bank of Windows laptops, but you will be restricted as per standard University machines.  Please bring pen and paper to even numbered weeks.

  * Online, via Teams.  There are a number of channels created to act as virtual tables where you can work with friends or, if you prefer, you can work independently (there is no requirement to be in a channel).  To get help from one of the TAs in the online version of the lab, simply post a message to the "Lab Support" channel.  For example: "please can I chat about Q3?" , a TA will get in touch.  If you are at a table you can mention the table number.    

* * *

![code fork icon](assets/icons8-code-fork-100.png){: .icon }
## Haskell Code

The [labcode repo](https://github.com/uob-coms20007/labcode){: target="_blank" } contains the starter code for the Haskell programming problems.  Instructions on how to obtain a working Haskell setup are available on the repository's README (view via [Github](https://github.com/uob-coms20007/labcode){: target="_blank" }).

Some of the programming tasks build on each other from one week to the next, but don't worry if you get a little behind, the repository is updated each week to incorporate the solutions to the previous week.  This means that cloning a fresh copy of the repo in Week *n* (for odd numbers *n*) will give you exactly the starter code you need to be able to complete the Week *n* problem sheet.  

If you want to use your own solutions (or partial solutions) in subsequent weeks, rather than cloning a fresh copy of the repo which will give you the model solutions, then you can pull as follows:

```
  git pull origin main -X ours  
```

This will incorporate any changes from the remote labcode repo into your copy whilst keeping any code that you have written.  For example, if in Week 1 you have defined `rngTrace` and `reachable` and `chameleons` but you weren't able to define `circuit` and you left its code untouched, then running the above command will keep your definitions of `rngTrace`, `reachable` and `chameleons` and replace the `undefined` of `circuit` by the model solution.

If you want to start afresh with an old week's starter code, then you can create a new branch from that week's tag.  For example, if in Week 2, you want to start again with the starter code for week 1, then you should clone a fresh copy of the repository and create a new branch. From inside your copy of the repo execute the following, replacing `<branch_name>` with a name of your choice:

```
  git checkout -b <branch_name> week1
```


