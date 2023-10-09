---
layout: post
title: Monty Hall Problem
date: 2021-07-28 12:39:00-0400
description: formal but easy-to-follow probability approach, my first shot of writing a blog post
comments: true
---

The [Monty Hall Problem](https://en.wikipedia.org/wiki/Monty_Hall_problem) is very interesting and covered by tons of online posts. Unfortunately, none of those I have found is precise enough about how the mathematics derivation works out. So I decided to write this blog and approach this simple problem in a (maybe over-)technical way.

Let me play the game with you. Suppose you're on this game show, and you're given the choice of three doors. You know one of them has a car behind it. That is to say, if the door No. that has the car is a **random variable** \\(C\\), it can only take values from \\(\\{1,2,3\\}\\). You have the opportunity to pick a door. It would be wonderful if you know what \\(C\\) is so that you can open the right door and drive that Ferrari back home. Unfortunately, you do not. All the three doors are the same to you at this moment, which means \\(C\\) is **uniformly distributed** over \\(\\{1,2,3\\}\\): 

\\[P(C=1) = P(C=2) = P(C=3) = 1/3\\]

Every door is born equal, so let's just pick door No. 1.

Now the host, who knows what's behind each door, opens another door.

Wait! Do not look! Let's now play a little mental game, put ourselves at the host position, and think about which door we should have opened. Maybe this game-theoretic thinking can reveal something interesting.

Now you are the host. You come out and see the player has picked door No. 1, and you ought to open another door. Can you just arbitrarily open a door? No! Because if you open the door that has the car, your boss will tear you off and kick you out of the show! 
*So which door to open depends on which door has the car.* But which one has the car? 
Let's check all the possibilities:

* The car is behind door No. 1, i.e. \\(C=1\\). The player has picked the right door, so you, the host, can just *uniformly* open door No. 2 or No. 3.
* The car is behind door No. 2, i.e. \\(C=2\\). The player has picked the wrong door, and you do not want to open the right door, so the only option left is door No. 3.
* The car is behind door No. 3, i.e. \\(C=3\\). The player has picked the wrong door, and you do not want to open the right door, so the only option left is door No. 2.

Now you know something:

* The door No. that the host will open, which is another random variable \\(O\\), will only take values from \\(\\{2,3\\}$\\).
* The value of \\(O\\) will *randomly* depend on the value of \\(C\\). That is to say, for each value of \\(C\\), there is a **conditional probability distribution** \\(P(O \mid C)\\).

Amazingly, this simple mental game just told us what the conditional probability distribution \\(P(O \mid C)\\) is:


* \\(P(O=1\mid C=1) = 0\\), \\(P(O=2 \mid C=1) =1/2\\) and \\(P(O=3 \mid C=1) = 1/2\\)
* \\(P(O=1\mid C=2) = 0\\), \\(P(O=2 \mid C=2) =0\\) and \\(P(O=3 \mid C=2) = 1\\)
* \\(P(O=1\mid C=3) = 0\\), \\(P(O=2 \mid C=3) =1\\) and \\(P(O=3 \mid C=3) = 0\\)

Now it is time to open your eyes and see which door the host has really opened! He opened No. 3! And of course, there is no car behind it! Now he asks you, "Do you want to pick door No. 2?"

You then ask yourself, "Which door is more likely to have the car behind it, given the host just opened door No. 3?" That is to ask,"Which probability is larger, \\(P(C=1 \mid O=3)\\) or \\(P(C=2 \mid O=3)\\)?" Now you can laugh loud, because you have taken Probability 101 and know about [Bayes' theorem](https://en.wikipedia.org/wiki/Bayes%27_theorem). You rigoroulsy work it out:

\\[P(C=1 \mid O=3) = \frac{P(C=1, O=3)}{P(O=3)} = \frac{P(O=3\mid C=1)P(C=1)}{P(O=3\mid C=1)P(C=1) +P(O=3\mid C=2)P(C=2) +P(O=3\mid C=3)P(C=3)} = \frac{1}{3}\\]

So \\(P(C=2 \mid O=3) = 2/3\\)! Of course it is to your advantage to switch your choice now!

*What if the host has opened door No. 2?* Just go through this analysis again and you will find that you still like to switch the door to No. 3!

*Does it depend on your choice of the door?* What if you have picked the door No. 2 or No. 3 at the beginning? It does not affect the mental game, the host's strategy and your game-theoretic approach anyway, so still switch!

Therefore, our conclusion is: *always switch to the other door!* Then you have \\(2/3\\) chance to drive this Ferrari back home!

Now you already know how to play this game. *What if there are \\(N\\) doors out there? Would you still switch? Which one would you switch to? What is the chance to win?*
