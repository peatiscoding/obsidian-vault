#knowledge-sharing
## Agenda

0. Goal .....
	1. Better understanding of the requirements
	2. How to gather requirements like Muze
	3. How to process/consume/fulfill requirements
1. Intro. Anatomy of requirements
2. Anatomy of Developers
3. Requirements vs Developers
4. Summary
## Anatomy of Requirements

What are the requirements?

```
In the world of business analysis, requirements define precisely what you are going to create or accomplish—what the effort will include, what it will not include, how it will be done, and by whom.
```

### Type of Requirements: By the book

There are so many standards and definition of requirements in the research. Here are some that I think it is worth the time of your brain to consume.

1. **Functional requirement**: defines what a product must do. What is the feature/ function. From system point of view; The action that your system provide so that it is "operational".
2. **(System) Technical requirement**: define how the system should perform, emphasis on effectiveness/ responsiveness, and scalability of the system. How well the system will operates under certain circumstances. It extends to stability, and robustness of the system.

These are 2 side of the coins that works hand-in-hand. Functional requirement means it would serve the purpose of the system. But doesn't mean the system will be robust. And the system can be robust as hell but it compute the value wrong all the time.
### Type of Requirements: By the experiences
1. The Business Goal
2. The Edge Case
3. The Nice to have
4. The Politic
#### The Business Goal
These requirements are the one that actually deliver Business' values.
#### The Edge Case
These requirements most of the time; Non-technical stake holder may neglect these edge cases.

These edge cases doesn't always need the system to smartly fix it. It just need a way for system to be able to address it. Example
1. System can just offer a warning to detect the problem and display the warning.
2. System can offer a block in case if such Edge Case will actually create the unexpected condition within the system.
However most of the time the above 2 solutions will consider too vague or too implicit to user. They will ask a remedy solution to be presented right away on the UI.

Edge case often contribute a very rare occurence. Hence, math wise it doesn't make sense to invest preparing the system to handle 1% of the traffic. 
#### The Nice to Have
These requirements are a bit blur. And actually quite subjective but it often than most deliver a bit of value to the system. These nice to have need some mediation. For example; User would like the changing a system to be approved first.

Note that not all **nice to have requirements** must be removed. But it should be prioritized later than Business Goal.

Other examples:
- The requirement that served the same goal. Example, alternate solution of the same problem. i.e. Key-in from UI, and Upload the file.
- Also the requirement that treat customer as Stupid as possible.
- And the requirement that treat the system as superior being.
- Note that all of these requirements must served only small fraction of Business values.
- Extremely configurable system. Please use Lego to implement your system.
#### The Politic
These are actually the most important ones. Even though, most of the time it deliver absolute 0 values to Client's org. It does yield high-value to the HIPPOs and if such HIPPOs are the one holding gun to our head then we would also benefit from such requirements. And that's the most case.

In some case; it may comes in form of Technical Requirement; Please use this sub-optimal service provider. ;)

Now we all know what are the requirements. Let's see how should we extract them effectively.
## Determine the Requirement Type

## Elicit the Requirements
Why do we need to Elicit the Requirements?
### Define: Elicit

```
e·lic·it
/əˈlisət/

evoke or draw out (a response, answer, or fact) from someone in reaction to one's own actions or questions.
```

### Know who you are talking to

This share a very important insight about the way you should frame your questions to.
### Read between the lines

// TODO: 
### Ask the Right questions
#### Let's try:

Need from Top Level: "I want you to build the App that can sell our Farmers' products."
- This can actually goes 2 ways.
	- Solution Oriented: Who will operate the system? Is it a platform for Farmer to sell on their own? Who will handle the shipment.
	- Business Oriented: What type of products you are selling? is it seasonal? How fast you want it!
- But none of them is optimal. these are not a good questions; It should be WHY?
	- Our goal is to unearth the reason behind it so that we can actually understand the real need that sit behind those words.
### Important Concepts
* Determine the Business Value; But this can be very subjective. The way to classify this is to see if it is a MUST otherwise the Goal cannot be accomplished. Or it is to enhance the experience of the users.
- Asking why?
- Simulate yourselves in different roles. And understand each role's needs.