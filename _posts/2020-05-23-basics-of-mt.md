---
layout: post
title: "How does Google Translate work?"
categories: mt
author:
- Sorcha Gilroy
meta: "Manchester"
---

Automatic translation tools such as Google Translate have come along in huge bounds over the last decade. While most of these systems [still have many issues](https://interestingengineering.com/30-best-and-worst-google-translate-fails-that-will-make-you-cringe-forever), they can be extremely useful for translating individual words or simple sentences. If you've ever wondered how these systems work, hopefully this post will help you understand what's happening behind the scenes. 

## The tech jargon

The people who build and research systems like google translate work in the field of **machine translation**. Machine translation has been [discussed for hundreds of years and actively researched since the 1950s](https://en.wikipedia.org/wiki/History_of_machine_translation). Thanks to the massive improvement in the power of computers in the last 30 years, we're now able to use these systems in our every day lives. But how does a machine translation system know how to translate from one language to another? The basic answer is by giving the system tons of examples of translations between those languages. 

The technical term for this is **training** - a common phrase used in the artificial intelligence/machine learning community. Put simply it means that we give the computer lots of examples to learn from so that it can carry out some task in the future. In machine translation, the task is translating from one language to another but in general this can be anything from recognising cats in photographs to generating speech from text.    


## Learning from examples

To demonstrate how reading examples of translated sentences can help translate new sentences, I'll start by showing three phrases in Irish and their English translations:


Phase | Irish                | English          
------|--------------------- | --------------------- | 
1     |Ith mé an ceapaire    | I ate the sandwich    | 
2     |Ith sí an cáca        | She ate the cake      |
3     |Cáca agus brioscaí    | Cake and biscuits     |


Just from these three examples, we can immediately make some pretty reasonable guesses for which words are translations of one anothe. For example, the Irish word *cáca* appears in phrases 2 and 3 but not 1, the word *cake* in English also appears only in phrases 2 and 3 so it's a good chance those two words mean the same thing. We can also deduce that the word *ith* in Irish probably means *ate* in English and so on. 

This is essentially what's happening when a machine translation system is being trained, it's looking at millions and millions of examples of sentences that mean the same thing in two languages and it comes up with a kind of dictionary. This dictionary won't be as certain as the English-French pocket dictionary you would have had at school, but given enough data it will have an idea of which words are much more likely than others to be translations of one another. Using phrase 3 from the example above, the dictionary would think that the word *agus* in Irish is equally likely to mean *and* and *biscuits* in English. If we had a lot more examples, the system would see that *agus* appears in Irish sentences with *and* in the corresponding English sentences far more than English sentences with *biscuits* and so *agus* probably means *and*. 


## When is this hard?

The example hopefully demonstrated that machine translation systems can only learn about words they've seen before. Naturally, this makes it very difficult to deal with uncommon words as they may have appeared in the dataset very few times, or not at all. English is what is known as a *morphologically poor* language, which basically means that we don't change our base words very much compared to other languages, we just add more words when modifying them. For example, the German word *Freundschaftsbezeugung* means *demonstrations of friendship* in English. If a machine translation system hasn't seen that particular German word before then it won't be able to translate it. Because of issues like this, lots of research has been done to first break down the words in the sentences into smaller pieces before creating the dictionary, and this can help a lot.
  
## Where does the data come from?

There are some particularly helpful datasets for training machine translation systems. One type of dataset in particular is translated parliamentary proceedings. The Canadian parliamentary proceedings are all recorded in both English and French. This gives us hundreds of thousands of examples of translations between French and English which can be used to train systems. Similarly, the European Parliament proceedings are incredibly helpful, and there is a [dataset](https://www.stamt.org/europarl) available for anyone to use for training their own machine translation system that includes 21 languages and 15 years of proceedings.

Another source of data is the internet, tons of websites have been translated into multiple languages for the different countries they serve. People training machine translation systems sometimes download these webpages and pull off the text that has been translated. The difficulty here is making sure that the translation wasn't also done by a machine and may not be correct!

A substantial issue with using the internet to train machine translation systems is that the internet is [overwhelmingly dominated by English](https://unbabel.com/blog/top-languages-of-the-internet). There are around 7,000 languages in the world but the vast majority don't appear on the internet at all, or very little. This in turn means that many translation systems are only really good at the common languages: English, French, German, Spanish etc. As an Irish speaker who has occasionally used Google translate, I find it works well for individual words or short phrases but struggles a lot with full sentences.

This post was intended to give a high level introduction to the area of machine translation. If you want to learn more detail, I'd recommend reading about the [IBM models](http://www.cs.columbia.edu/~mcollins/courses/nlp2011/notes/ibm12.pdf) and the more recent advances in [neural machine translation](https://towardsdatascience.com/neural-machine-translation-15ecf6b0b). 
