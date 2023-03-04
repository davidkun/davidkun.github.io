---
type: page
title: thoughts on OOP design principles
description: "i disagree with a pre-canned test solution to a question about the 'OOP design principles'"
date: 2022-03-18
tags:
- software-design
---

I got a LinkedIn marketing email that actually caught my eye: "take a LinkedIn [skills assessment](https://www.linkedin.com/help/linkedin/answer/a507663/linkedin-skill-assessments?lang=en) to show recruiters you are in the top 30% for that skill set." I honestly didn't care about getting a "badge", but I was genuinely curious to see what kind of questions would be asked.

On their help page, they explain that assessments are created by "subject matter experts" and questions are peer-reviewed. I was hoping that I could find interesting material to incorporate into our evolving technical interview process. Instead, it got me thinking (and writing) about OOP design principles....

The tl;dr about the assessments (I did 4: Git, Java, Python, & OOP) is that they're so-so, not great. Mainly, I'm not a fan of trivia questions, especially for things that are really quick to look up online (even though the questions are time-based, if you know what you're looking for, you can quickly find answers online).

## four principles?

The one question/topic that stuck out to me was about the "four basic principles" of OOP. The two that immediately came to my mind were Encapsulation and Polymorphism (these are the ones I usually hear people mention in technical interviews, too). What were the other two? Apparently, Inheritance and Abstraction. Weird. Polymorphism kind of implies Abstraction, to me, so whatever. Inheritance, though? Sure, inheritance is something you _can_ do in OOP, but is it a "principle"? I've seen rampant use of inheritance (many abstract classes, deep and broad class hierarchies) lead to extremely coupled code that is difficult to test, change, and reason about.

You could say that any recommendation can be misused, misinterpreted, and/or misapplied. We shouldn't fault "Inheritance" because some teams get it wrong. 

I disagree. 

If it truly is a "principle", then together with the other three principles, it _should_ lead to good design. Also, how is it that of the four design principles, two are contradictory? How can we encapsulate something and also inherit from it? The moment you extend a class, you've coupled the new class to it. Even if the parent class has only private fields (rather than protected), the child class has to call the super constructor (i.e., the parent's constructor parameters are exposed to the child class), and similarly with the parent's protected/public methods.

So what are the "basic" principles of OOP?


## five principles?

The set of OOP principles that I'm more familiar with are the [S.O.L.I.D.](https://en.wikipedia.org/wiki/SOLID) design principles. I learned about them mainly from Bob Martin's books (_Agile Software Development_, _Clean Code_, and _Clean Architecture_). Paraphrasing from his [blog post](http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod) on the topic, the principles are:

  * **SRP** (single responsibility): A class should have exactly one reason to change
  * **OCP** (open closed): Classes should be open for extension and closed for modification
  * **LSP** (liskov substitution): Derived classes must be substitutable for their base classes
  * **ISP** (interface segregation): Make fine grained interfaces that are client specific
  * **DIP** (dependency inversion): Depend on abstractions, not on concretions

I think this is a more complete set of principles for OOP. It almost feels unfair to compare these the "four principles" mentioned earlier. For one, these five are much more constraining; you have to **spend more time thinking** about the code you're writing in order to stay aligned with all five. I think it's good to spend more time thinking about code before and during the coding process. (Rich Hickey, creator of [Clojure](https://clojure.org), has a good talk around this topic: [hammock-driven development](https://youtu.be/f84n5oFoZBc).)

Writing code is the shortest part of the software lifecycle. The majority of time, for almost any software product, is spent on maintaining and changing the existing code. So, before you slam some methods together into a new interface, stop and think for a few minutes about what you're doing. And think about the bigger picture, not just about your immediate task. 

Martin Fowler has a good blog post that's somewhat relevant (and a _great_ read): [Is High Quality Software Worth the Cost?](https://martinfowler.com/articles/is-quality-worth-cost.html).

A second indicator that this set of principles is fairly complete, is that it's hard to go wrong if you follow all five. For example, I've seen adherence to DIP lead to bad design (e.g., many classes having way too many constructor parameters), but that's because the SRP was being violated. I've also seen failed attempts to adhere to the OCP, primarily by relying on inheritance (literally extending class to change behavior, which doesn't work well in real life)... in this case the DIP is violated. Yes, even though you inject parameters in your constructors, it doesn't mean you are following the DIP. The "stuff" (abstractions) you inject should enable the OCP. If you need to subclass in order to get a different "flavor" of some behavior, you are missing out on DIP (and probably SRP). When you feel like implementing a slight variation of a particular behavior, you should immediately consider the [Strategy](https://sourcemaking.com/design_patterns/strategy) pattern. Use DIP to inject it; don't subclass for this. Breaking out the behavior like this will also lead to smaller classes (ISP) that are easier to test and swap implementations (OCP).

If your class/code is _not_ easy to unit test (without needing an extensive framework which helps you create / spy on your class under test), then it's most likely poorly designed. Go read Bob Martin's [Clean Code](https://www.amazon.com/dp/0132350882) book and get a different perspective on your code. Also, I recommend reading Chapter 3 ("Bad Smells in Code", by Kent Beck and Martin Fowler) of [Refactoring: Improving the Design of Existing Code](https://www.amazon.com/dp/0134757599) to help you recognize "code smells" (a.k.a. "red flags").

The third indicator of completeness (and the last one I'll discuss), is that there is not tension between the principles. In fact, they appear quite orthogonal to me. It makes me think of an orthonormal basis of an inner product space, e.g., where any vector in that space can be written as a linear combination of the vectors in the basis. I.e., given these five orthogonal principles, we can procure a good design solution to any problem.

## takeaway

Yes, we'll use abstraction, polymorphism, encapsulation, and maybe even some inheritance to get there, but these are more like... practical manifestations of "getting there". The _five_ principles (SRP, OCP, LSP, ISP, DIP) actually keep us on the best path for getting there.
