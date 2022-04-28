---
title: 'How to be a better programmer - the redux'
date: Mon, 22 Dec 2008 12:57:21 +0000
draft: false
tags: ['computers', 'football', 'internet', 'Programming', 'Random Ramblings']
---

_"Software development productivity would skyrocket if the least effective 30% were fired tomorrow" --_ [Neal Ford](http://memeagora.blogspot.com/)

It was in the December of 2005 that I first wrote about [how to be a better programmer](http://protoiyer.github.io/posts/becoming-a-better-programmer/). At that time I was into my fifth year as a programmer, and though I wanted to write what I am writing today, I decided to narrow down my scope to non-technical issues. I wrote about code readability and code maintainability that day. As important as these issues were (are), I guess there is a larger issue that must be addressed -- the technical skill set of the programmers. Then I wrote about (nay, linked to) the [fatherly advice to new programmers](http://www.removingalldoubt.com/permalink.aspx/a32977e2-cb7d-42ea-9d25-5e539423affd) \([web archive link](https://web.archive.org/web/20061017124921/http://www.removingalldoubt.com/permalink.aspx/a32977e2-cb7d-42ea-9d25-5e539423affd)\) by Chuck Jazdzewski.

I am now into my eighth year as a programmer, and unfortunately, the rate at which the industry has understood the importance of the quality of code or for that matter about issues like code readability or code maintainability is pretty dismal. This might be justified by arguments like "in service industry, deadline is more important". But people just don't understand that in the rush to push the software out of the door, the quality of the code suffers, which directly affects how quickly you can ship the second or later versions. To make matters worse, people who can really understand the code at a deep level, and who are really interested in programming, is a minority, and I guess it would remain that way for the foreseeable future.

The triggering point for writing that piece three years ago was a mail from my counterpart in UK, who wanted the team to ensure that they are putting comments properly, and (though he didn't explicitly mention the words, he provided an example that pointed to writing) comment at the level of intent. I am not sure how many people read that post (considering that I find it difficult to tell people that I blog; except to my close friends and family), but at least from that day, I made it a point to tell my team members the importance of writing code the proper way, and when required, show them how it is done. The triggering point for writing this has been yet another series of events. I thought it was time I write this down, so that a) I can refer back when I want to, and, b) pass this on to anyone to whom I feel like preaching in the future :).

The first and the most important aspect to become a better programmer is to have something called interest or involvement. Half the crowd I meet are programming just for the sake of doing some work. Programming, unfortunately, is not similar to doing most other jobs where you learn and master something once, and you can carry on without learning anything new for quite some time, and in some cases, for years altogether (or for life). Careers that spring to my mind include Government Service, Accountancy, Banking, Teaching, and certain professions like certain streams of Engineering and Law. Of course, in each of these cases, there is something new to learn every year (or every few years), but compared to the frequency at which things change, and the effort involved to keep ahead of the curve, they do appear trivial and manageable. \[I know this is going to be a controversial perspective, but being a Mechanical Engineer and being someone who has a passion for teaching, and who dreamt about doing M.Tech and becoming a professor, I hope I know what I am talking about here\]. Anyways, I don't mean any kind of disrespect to any of the professions. I am just pointing out the fact that you don't have to explicitly sit down and read a few books on your subject to remain good in many a profession out there.

In programming, what you know today is of little or no use two years down the line. I remember reading way back in 2002 about an interesting incident narrated by David Chappell in his book, Understanding Dotnet, First Edition. Chappell was taking a session on DCOM (if I remember right) at Moscow, when someone in the crowd got up and asked him why is that Microsoft is changing the technology every few years, and how he is finding it difficult to cope up with that. Chappell told him, as a matter of fact, that if he finds the change difficult to cope with, he is perhaps in the wrong profession. I wish we could make more programmers understand this simple fact - the fact that in this profession one can't stop learning. In fact the number of [programmers who have read any of the top 25 books](http://www.construx.com/Page.aspx?hid=1005) on programming or software would be less than 10%. This might be an example of the Sturgeon’s Law (that 90% of people will never care and 10% of people would cover up for them in most professions).

To make matters interesting the IT industry doesn't quite teach them that programming is important, and I live in a society, where if I tell them I am programming in the eighth year of my career, people think I am a (lowly) programmer still, perhaps because I don't have what it takes to be a manager or a team leader who mostly takes care of team management related activities. The trend is to learn programming at the level of writing if..else, for..do and yes, playing around a bit with something called objects (without really understanding what they actually are and what they are meant to be), and do programming for four or five years, all the while remaining at that basic level, never bothering to go out of the way to improve oneself, and jump on the management related bandwagon at the first possible instance.

This is where some of the most successful companies around the world stand out, and it is not a coincidence that most of them are run by people who were great programmers, and who still love and do programming. The best example would be Google and I can never forget the [beauty of this story](http://www.wired.com/techbiz/it/magazine/16-10/mf_chrome?currentPage=all) and what it tells you about the company (or the story of how [Sergey Brin](http://too.blogspot.com/) wrote an application to test Android, and the application was about using the accelerometer in the device to determine the time [an Android phone was in the air](http://www.informationweek.com/blog/main/archives/2008/09/sergey_brin_im.html) [when it is tossed up](http://bits.blogs.nytimes.com/2008/09/23/live-blogging-from-google-phone-event/); the point is there are very talented programmers at the top who are really interested in coding in spite of being so successful), though there are quite a few others like [Microsoft](http://www.microsoft.com/en/us/default.aspx), [Martin Fowler's](http://martinfowler.com/) [ThoughtWorks](http://www.thoughtworks.com/), [Joel Spolsky's](http://www.joelonsoftware.com/) [Fog Creek Software](http://www.fogcreek.com/), and [Steve McConnell's](http://www.stevemcconnell.com/) [Construx Software](http://www.construx.com/). Construx has published the [Construx Professional Ladder](http://www.construx.com/Page.aspx?hid=1004) for its employees who aspire to move up the corporate heirarchy (the ladder), and the best part is that it ensures that those who grow to be the Team Leads or Managers, are people who are widely read, and who have understood the nuances of programming, and can still solve the problem, if the programmers are not able to solve it.

To put matters in perspective, check [this recommended reading list](http://www.construx.com/Page.aspx?hid=981) for a Level 10 programmer at Construx. Please note that Level 10 is not the Architect or the Technical Leader. It is the programmer with some experience ("College graduates will generally start at Level 9. Experienced developers may start at Level 10"). That might appear a bit over the top by your or my standards, but that tells you what separates the great companies from the merely good or average ones -- it is the quality of the people. I think it was Kent Beck (in Extreme Programming Explained, Second Edition) who said something along the lines of "a more talented team will almost always beat an average or less talented team, no matter how disciplined and process oriented the average or less talented team is, and you can't do much about it". A cruel (for me, at least) example of that in the wild is watching the Germans end up as the runners up (or loosing semi finalists) at the World Cups in 2002 and 2006, and in Euro 2008. With a bit more talent (or a bit more botch-up by the opposition, they could have won any of those events).

To be a good programmer, one needs to have a good grasp of the fundamentals of programming (and there is no better language to learn this than C followed by C++, though that unfortunately is out of fashion these days). This must be followed by learning a modern mainstream programming language like Java or C#. But if you start with either Java or C#, you would miss quite a bit on really understanding pointers and objects at a fundamental level. This must be followed by learning, reading and eventually mastering OOAD, UML, Refactoring and Design Patterns. It will be really useful if one can find the time to explore and learn dynamic programming languages like Python or Ruby, as they bring a different perspective to programming, thus enriching one's knowledge and understanding.

Yet another mandatory aspect going forward would be exposure to Agile methodologies (don't think I am crazy, but there is a big crowd out there that doesn't understand what is agile). Even if the team is not 100% agile, there is a lot to learn from the agile community. If anyone has any doubt about agile, the only thing to keep in mind that the top guys of the Design Patterns movement are also the people who were the forefathers of the Agile movement -- people like Ward Cunningham, Kent Beck, Eric Gamma, Martin Fowler, Alistair Cockburn, Dave Thomas and Andy Hunt to name a few that I can recollect over the top of my head. Since each of them are titans in their own rights, there must be something in it for us to learn.

The best part of this learning, IMHO, is that it leaves one in such a strong position to negotiate most of the stuff that comes one's way - a bit like how Dravid could easily and with grace negotiate the unplayable deliveries from the Donalds, McGraths, Pollocks and Waqars of this world, in his pomp, in spite of not having grown up facing them or anyone of their calibre. This was made possible by the fact that in spite of not being a genius like Sachin or Lara, he kept on working on his game, improved every day as a batsman by putting in the effort, and thinking about his game. \[I wrote this without being aware of the match saving 100 he made at Mohali\].

The best resource that I am aware of to learn the basics of the aforementioned stuff , that I am aware of, is listed below. These books helped me immensely in my development as a professional, and I hope at least some of you can and will find them useful.

Programming Language basics:

[The C Programming Language](http://en.wikipedia.org/wiki/The_C_Programming_Language_(book)) by Kerninghan and Ritchie (the K&R book)

[The C++ Programming Language](http://public.research.att.com/~bs/3rd.html) by Bjarne Stroustrup (it is a tome, but worth every minute of your time)

[The Java Programming Language](http://java.sun.com/docs/books/javaprog/) by James Gosling et al (a beautiful book)

[Thinking in Java](http://www.mindview.net/Books/TIJ4) by Bruce Eckel (or the unpublished C# version freely available on the net)

Design basics:

[UML Distilled](http://www.amazon.com/UML-Distilled-Standard-Modeling-Language/dp/020165783X) by Martin Fowler

[Refactoring](http://www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Technology/dp/0201485672) by Martin Fowler

[Applying UML and Patterns](http://www.amazon.com/Applying-UML-Patterns-Craig-Larman/dp/0137488807) by Craig Larman

[Object Oriented Analysis](http://www.amazon.com/Object-Oriented-Analysis-Yourdon-Computing/dp/0136299814) by Peter Coad and Edward Yourdon

[Object Oriented Design](http://www.amazon.com/Object-Oriented-Design-Yourdon-Press-Peter/dp/0136300707) by Peter Coad and Edward Yourdon

Design Patterns:

Design Patterns by Gamma et al. \[the GoF book; I am yet to read this as it is in C++\]

[Head First Design Patterns](http://headfirstlabs.com/books/hfdp/) by Eric Freeman, Elisabeth Freeman, Kathy Sierra, Bert Bates

[Design Patterns Explained](http://www.amazon.com/Design-Patterns-Explained-Perspective-Object-Oriented/dp/0201715945) by Alan Shalloway and James R. Trott

Taking the skills to the next level:

[Code Complete](http://cc2e.com/) by Steve McConnell, Second Edition

[The Pragmatic Programmer](http://www.pragprog.com/the-pragmatic-programmer) by Andy Hunt and Dave Thomas

[Software Craftsmanship: The New Imperative](http://www.mcbreen.ab.ca/SoftwareCraftsmanship/) by Pete McBreen

Books on Agile:

[Extreme Programming Explained: Embrace Change, Second Edition](http://www.amazon.com/Extreme-Programming-Explained-Embrace-Change/dp/0321278658/ref=pd_lpo_k2_dp_k2a_3_txt/177-1090539-0987205?pf_rd_m=ATVPDKIKX0DER&pf_rd_s=lpo-top-stripe-2&pf_rd_r=1ZMQX4Q1RCWFFP6PV2Y3&pf_rd_t=201&pf_rd_p=304485601&pf_rd_i=0201616416), by Kent Beck (there are two editions and it is fascinating to read both back to back :)

[Agile Software Development: The Cooperative Game, Second Edition](http://www.amazon.com/Agile-Software-Development-Cooperative-Game/dp/0321482751), by Alistair Cockburn

There are no shortcuts to mastery in any field, and software is no different. Unless you read some of the above books, you wouldn't even know what all you miss (in terms of knowledge and skills missing from your toolbox). Again, this must be supplemented by some real hard work at the PC -- programming, trying to implement and refine what one has learned. As the old saying goes, there is no substitute for practice.

Next, since we live in a society, we do need to work upon our soft skills, and people interaction skills come right at the top of the skills to acquire. One of the best resource to learn from this would be [How to win friends and influence people](http://www.amazon.com/How-Win-Friends-Influence-People/dp/0671723650) by Dale Carnegie, as attested by both Jeff Atwood and Steve McConnell. In fact, if I remember right, McConnell writes something along the lines of "it must be made a mandatory book for every member of the team". How true!

Internet is such a free and ever available source to learn new stuff. In addition to reading MSDN or other technology oriented sites, read the great programmer's blogs and learn from the masters. Let [Google Reader](http://www.google.com/reader) be your best friend in this attempt. It has been for me, for three years now.

Update \[14-Jan-09\]: cleaned up the essay a bit and included a few more links in the story.
