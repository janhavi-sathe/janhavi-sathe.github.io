---
layout: post
title:  "Does Latent Semantic Analysis (LSA) work for conversations"
date:   2020-03-18 01:30:00 -0600
categories: natural language processing, data science, conversational ai, blog
custom_excerpt: "What is Latent Semantic Analysis (LSA)? It works well on structured documents, but will it work for analyzing human conversations?"
---

# Does Latent Semantic Analysis (LSA) work for conversations

_NOTE: This article was originally published on Medium: [https://medium.com/symbl-ai-engineering-and-data-science/what-is-lsa-a67965b712ca](https://medium.com/symbl-ai-engineering-and-data-science/what-is-lsa-a67965b712ca) for Symbl.ai's blog. Reposting here as I have lost access to my Medium account._ 

![](/assets/images/lsa-header.png)

Latent Semantic Analysis (LSA) is a theory used for identifying and extracting topics from a document (i.e. topic modeling). It is used widely to analyze news, tweets, and many more NLU applications. Although the theory is seemingly rather mathematical in nature, there’s more to it than just the math. I will attempt to break it down and explain key features without delving into the math.

In this piece, I will go through the distributional hypothesis which is the basis of LSA, explain how LSA works, talk about further versions of it, and explore how LSA would figure in real-time analysis of conversations.

---

## The Distributional Hypothesis
The distributional hypothesis says that words occurring frequently in a document are related. I use the word “frequently” loosely here, but what it means is that _if you come across two words that occur more frequently in a paragraph compared to other words, they are related to each other_. This relation may be anything — they could be opposites, synonyms, part of a common phrase — but in general, the words are often found together in the same context.

It’s like how you’d find a group of cousins together in a family get-together. It doesn’t matter how they’re your cousin, whether they’re a blood cousin or step-cousin or really far away cousin or your arch-nemesis since you were born. All that’s certain is you’re related.

You might come up with many obvious problems in executing this, such as “but what about the waiters roaming amongst the cousins who’re not related to me?”, that is “what about words like conjunctions and prepositions that occur so frequently but aren’t exactly relevant?” which is a valid point. There are many other critiques of this approach, which is why it’s still a hypothesis and not a theory. We’ll address all these together later.

To sum it up, the popular slogan of the distributional hypothesis should suffice-

> “A word is known by the company it keeps.” (J.R. Firth)

A lot of the basic criticisms have simple enough solutions that make this approach quite a good and useful one to study.

. . .

## LSA Basics
Continuing with my previous example, now that we know that we are looking at a room full of cousins at a family party, let’s tune in to the details and get some intel. We will use LSA for this.

Each cousin represents one word and all hundreds of cousins are in this room. After enough observations, you’d be able to see that the cousins who are close will be standing next to each other, often found huddled- bickering OR catching up (strongly related). The ones who are very awkward and indifferent to each other are in separate corners of the room, not interacting much (weakly related).

This is basically LSA. If the floor was a graph paper, **you would be able to tell how strongly cousins (words) are related based on the distance between them**. In actual LSA, instead of the words naturally arranging themselves on the floor, your learning model will move them around until it’s right. (LSA is an unsupervised learning model). This animation, which you may have seen on [Wikipedia](https://en.wikipedia.org/wiki/Latent_semantic_analysis), shows exactly that.

![](/assets/images/lsa-Topic_model_scheme.gif)

_Not all words have equal importance_. For example, in a news article about cybercrime, the words ‘message’ or ‘website’ may be used a lot, and the actual platform of the crime may only be mentioned twice. This is the problem of the distributional hypothesis that we mentioned before. _In LSA, we assign weights to words and then calculate the distance_. Just like a weighted average is a better indicator of things, a weighted distance solves the problem of “styrofoam peanut” words. Essentially, the overall setting can be best assessed if you focus on the most influential, opinionated cousins. So we remove the others from consideration (they flit from group to group and make analysis difficult.) How do we actually do this? Math.

### LSA++ : pLSA, LDA, lda2vec
Based on what method is used to get your final cousin distribution on the floor, you have a few variations. pLSA is a probabilistic LSA which uses probability theories to pick out the opinionated cousins. If every time you go to a cousin’s meeting you bet on the possible ways the arrangement might be and use the guess you made last time to better your next guess, that’s sorta pLSA. Latent Dirichlet Allocation (LDA) is a version of pLSA.

Lda2vec is a neural network made by using something called word2vec with LDA that makes the topic analysis better in terms of generalization. (I will explain all of those in detail in another piece so that I can do them proper justice.)

---

## All talk, talk, talk
As a conversational intelligence platform, at Symbl, the concern was whether we could use LSA methods for conversations. The short answer is no, not really.

**LSA works well in structured and concise documents** such as business reports, news articles, and essays, **but conversations are hardly ever as clean**. They can move from topic to topic very quickly, they’re staggered, sometimes communication is not verbal, grammar goes for a toss. While making transcripts, there may be noise from surroundings, improper pronunciations and many other things that add errors.

**Conversations** are also **not dependent on the current context**. You may refer to something that happened years ago. **LSA relies on “context” being established in the conversation**, which puts it at a disadvantage here.

> Consider the simple task of extracting topics from a meeting. A simple non-contextual topic modeling system (like LDA, frequency-based modeling) would end up detecting “Email” as a topic of discussion because it was used multiple times. But in reality, that result may not be relevant in the context of that meeting once you understand it, because “Email” was just used many times in different contexts for completely different important things. Maybe people wanted to connect over an email to follow up, sending additional documents etcetera. A human would rate in such a scenario, “Email” as not a relevant topic. But perhaps something which was mentioned only once in the course of that conversation like “Great User Experience” is a much more relevant topic of discussion because the conversation was all about ways to achieve a great user experience.  
> -- Toshish Jawale, CTO and Co-founder at Symbl

All of these make LSA based topic extraction inadequate and much less accurate. This forced us to look at other methods of topic extraction more suited to conversations.

LSA approaches are limited in their application but pretty good for those applications. If you have any more questions, do comment and we would be happy to answer!

Keep an eye out for more articles and check out [symbl.ai/blog](https://www.symbl.ai/blog)!

--- 

## Further Reading:

My top must-read recommendations:

* An article for clean explanations of the math — [Topic Modeling with LSA, pLSA, LDA, lda2vec](https://medium.com/nanonets/topic-modeling-with-lsa-psla-lda-and-lda2vec-555ff65b0b05).
* A blog that simply does a great job of explaining the pros and cons in general- [The Distributional Hypothesis: semantic models in theory and practice](https://www.thecrowned.org/the-distributional-hypothesis-semantic-models-in-theory-and-practice).