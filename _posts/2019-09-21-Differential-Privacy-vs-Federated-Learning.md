---
layout: post
title: What's the Difference Between Differential Privacy and Federated Learning?
---

### What’s the Difference Between Differential Privacy and Federated Learning?

#### First, what are they and why does it matter?
If Firas wanted to know what proportion of MDS students have Type A personalities, he could give a personality quiz to everyone in class and tally up the results. But if the classroom cleaner stole the pile of completed quizzes, they could figure out which quiz belonged to a particular student and maybe even sell that person's quiz to a company targeting data science students. Well, we definitely don’t want that to happen! 

<img src="https://s3.amazonaws.com/lowres.cartoonstock.com/business-commerce-hacker-hacking-computer_crime-cyber_crime-cyber_crime-cwln5521_low.jpg" alt="The_cleaner_took_it" style="width: 500px;"/>

So, what can Firas do to protect student privacy?

Here are a couple of options:

1.    Firas could collect all the quizzes and add a few fake responses to the pile before tallying up the results. Adding a small number of fakes would still let him figure out the rough proportion of students with Type A personalities, but a thief wouldn’t be able to match up a quiz to a student, or even be sure if a particular student took the quiz at all, since they don’t know how much fake information was added. _This is how differential privacy works._
2.    Firas could also give everyone the quizzes along with a key to interpreting the results and then collect only what he really wants to know: whether they have a Type A personality. _This is how federated learning works._

This all may seem trivial since it’s possible that _every_ MDS student has a Type A personality, but if Firas was collecting more sensitive information like medical health records, we’d all be a bit more wary about how safe our data is!

Differential privacy and federated learning are methods of protecting personal privacy while collecting data. Though they both use algorithms and lots of math, they themselves are not _specific_ algorithms. For example, two projects that both use differential privacy to ensure personal privacy can use two very different algorithms to add different fake data at different points of the project.

#### How do differential privacy and federated learning differ?
Though differential privacy and federated learning both try to protect individual privacy, they differ in how they do this. The main differences are:
1.    Where the data is analyzed, and
2.    Whether “noise” (false data) is added to the data

With differential privacy, personal data is collected and analyzed in one central place, and “noise” is added to this central mix to protect the privacy of each individual.$^{[1]}$

With federated learning, data is analyzed where it's collected, and only the results for a specific purpose are sent to a central hub to protect the privacy of each individual.$^{[2]}$

#### Why choose one versus the other?
It may seem like it doesn’t matter if Firas chooses to protect student privacy using differential privacy or federated learning methods since the end goal is the same, but sometimes one of the methods isn’t an option:

>For example, what if UBC didn’t allow instructors to collect personality quiz answers from students, but Firas desperately needed to know what percentage of the MDS class has a Type A personality? Well, he wouldn’t be able to use a differential privacy approach to collect quizzes, but he could use a federated learning approach and ask students to only tell him the results of their quizzes.

Or sometimes you might not be certain what information you’re looking for:

>For example, what if Firas used a federated learning approach and after he counted the number of Type A responses he realized that what he really wants to know is how many people responded _strongly agree_ to the statement “I feel over-worked”? Well, with only the results of the quizzes and not the actual responses to the questions, he may wish he had used a differential privacy approach instead.

Or maybe there are budgetary constraints to consider:

>For example, what if there was a paper shortage at UBC and Firas couldn't give every student a copy of the key to calculate their own personality quiz result? A federated learning method wouldn't be an option then.

There are many more reasons why organizations might choose one method over another, and sometimes one company can even use both.

#### How are they being used today?
Google uses differential privacy for products like Google Maps$^{[3]}$, and uses federated learning for things like Gboard on Android to improve search suggestions.$^{[2]}$ Federated learning is still relatively new, and some argue that it’s “susceptible to attacks that reveal information about participant information from the training set”.$^{[5]}$ Federated learning was introduced by Google in 2017.$^{[6]}$

Apple uses differential privacy in a variety of ways, including a version of it called _local differential privacy_ where the “noise” is added to each individual’s data before it’s combined with other data in a central hub.$^{[4]}$ The amount of added “noise” necessary to ensure privacy using differential privacy was formalized in 2006 by Cynthia Dwork, Frank McSherry, Kobbi Nissim, and Adam D. Smith.$^{[7]}$

##### Sources
[1] Kelleher, John D., and Brendan Tierney, _Data Science_ Cambridge: The MIT Press, 2018. Print.

[2] https://ai.googleblog.com/2017/04/federated-learning-collaborative.html

[3] https://venturebeat.com/2019/09/05/google-open-sources-its-differential-privacy-library/

[4] https://www.apple.com/ca/privacy/docs/Differential_Privacy_Overview.pdf

[5] https://medium.com/luminovo/data-privacy-in-machine-learning-a-technical-deep-dive-f7f0365b1d60

[6] https://medium.com/syncedreview/federated-learning-the-future-of-distributed-machine-learning-eec95242d897

[7] https://en.wikipedia.org/wiki/Differential_privacy
