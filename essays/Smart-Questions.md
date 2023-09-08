---
layout: essay
type: essay
title: "An Overflow Of Inquiry"
# All dates must be YYYY-MM-DD format!
date: 2023-09-07
published: true
labels:
  - Stack-Overflow
  - SMART questions
summary: "An essay about a well made question I found in stack overflow"
---
<img width="225px" height="225px" src="../img/sflow-logo.png" class="img-thumbnail" >

## How SMART Questions Are An Essential Tool For Software Engineeers

Sometimes, a software developer would find themselves lost in a clueless situation where they don't have any idea what to do next. In this occasion, what would be the best option for the developer? Stack Overflow? Yeah.... prob 9/10 times, but how do you display your worries in a set of words that form an inquiry that would get you most if not all the answers you had hoped to gain? the answer to this is to ask a SMART question on the forum. With the advent of ChatGPT, the importance of formatting your words correctly in a question are magnified drastically. In internet forums, much like chatgpt, a post would need to be formatted to a point where the overall context, the question, and what you're trying to find out can be seen through you're words posted. In forums, the user/ the software engineer has a goal they want to achieve, smart questions are essential to accomplish this as they help give a more appropriate answer that solves the post.

## Unknown Technical Processes

SMART questions can be found in multiple forums, one such forum is stack overflow. In stack overflow, one of the posts that ask a smart question probes an answer for the inquiry about ["Why is processing a sorted array faster than processing an unsorted array?"](https://stackoverflow.com/questions/11227809/why-is-processing-a-sorted-array-faster-than-processing-an-unsorted-array). 
This question from stack overflow has the user ask the forum, a question that although sounding easy to explain, once you go in depth to it is hard to clarify clearly. The question the user asks is, why would processing a sorted array be faster than processing an unsorted array?. The user in the forum had a sudden curiosity as he experienced a programming situation where somehthing unexpected occured, a difference in completion for the same task on two different arrays where one was sorted and the other wasn't. He had used the inputted array in an algorithm where being sorted theoretically wouldn't affect the runtime of the algorithm, as no sorting was needed to lower the overall runtime. Although the algorithm was unambiguous in the code to filter through an array, the user still had a lower recorded time on presorted arrays over unsorted arrays. Because this question had all the context given, an answer with a detialed analogy had been given, one where it explained clearly how the sorted array allowed a predicting system to run through it faster, much like a train going on stops where they know which turn to take. The sorted array had the computers prediction system go through it faster as their was an established pattern, not like the unsorted chaotic elements of the opposing array. The question was formatted in a way that allowed relatable interepreations to be explained to the asker.

This is the C++ code the user provides in the post that allows the sorted array to be processed faster
```cpp
for (unsigned i = 0; i < 100000; ++i)
    {
        for (unsigned c = 0; c < arraySize; ++c)
        {   // Primary loop.
            if (data[c] >= 128)
                sum += data[c];
        }
    }
```


## The  Detrimental Ambiguity Of Not So Smart Questions

If a forum is not explicit, explaining all context towards the intended problem, people would find it hard to answer the post, as the question may be too ambiguous in its format. Having a question being broad makes it harder for people to find a solution that encompasses the problem, this was the case for the stack overflow post asking  ["What is the difference between java and javascript?"](https://stackoverflow.com/questions/245062/whats-the-difference-between-javascript-and-java#:~:text=Java%20is%20class%2Dbased%3B%20JavaScript,constructors%22%20are%20just%20standard%20functions.). Unlike the previous smart question which provides a context to the situation where it seemed ubnderstandable that they would not be able to find an answer elsewhere, this question had broad contexts that allowed for more general interepretation of the question. There is no added context in the prompt, just this single question that seems broad, "What is the difference between java and javascript?". This question and post isn't so smart as the user would be able to find the diffrences of java and javascript in other sources before making this post, which would allow a more specialized smart question to be made at the time, such as "why is the syntax for creating variables in javascript is so different compared to java?" Having a general answer would also be detrimental to learning more about the said question, as details would be omitted to give a more convenient explanation for the solver to answer the broad topic. The answers for this question had a variety of ranges that explains alot of aspects for each language that differs from each other that although are relatable to the question, may not be what the poster is looking for.

## Overall Need For Software Engineeers And Smart Questions

Overall, SMART questions are a key tool that can't be skipped to have a quick convenient question replace it. It is important to be precise and explicit when asking a question, keep all context in the open and clearly state the goal that you want achieved while answering the question. A more detailed question allows for a more detailed answer and a keen understanding of the problem that occur in the present. On the other hand, a not so smart question may lead to the answer enver being found or the answer being too ambiguous to make an impact for your predicaments.
