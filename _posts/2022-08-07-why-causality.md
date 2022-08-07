# Why We Need Causality
## Introduction
We understand the world around us through causes, not statistics and probabilities. Our minds are designed to understand why something happened and not the odds of it happening [1]. Which is why we struggle with probabilities and seek to assign a cause to an event. Thinking causally allows our minds to pack knowledge down efficiently for ease of remembering and applying to new situations [2, 3]. But causality is just a framework, it requires evidence, or data; and the way we look at that data plays a role in how we interpret the world around us.

For example, a gender bias study on Berkeley graduate school admissions for the fall of 1973 showed men were accepted at a much higher rate than women (44% of men vs 35% of women). It seemed like the school was discriminating, so it charged Peter Bickel with analyzing the data for further explanation [2]. Analyzing the data in aggregate (i.e., for all departments together) confirmed the bias against women, however, when Bickel analyzed the data by department it revealed little bias, and in fact it seemed more departments where biased against men than women [4].

How can this be? Can the university really be discriminating against both? The reversal of a statistical relationship is called [Simpson's Paradox](https://en.wikipedia.org/wiki/Simpson%27s_paradox), and it occurs when looking at data in aggregate versus splitting it into groups. When we choose a way of looking at the data we are making an assumption about the world that created that data. Most examples of Simpson's Paradox are benign, but in this study it raises a concern about the analysis. If there is discrimination occurring it is because of someone's actions, and *how we split the data cannot change those actions*.

Bickel favored the results split by department, arguing that departments are the decision-making bodies in the problem [2, 4]. This interpretation leaves us feeling a little unsatisfied, however, and Judea Pearl hit on this when asking how the university can be discriminating when the individual departments are not? [2]. 

Before we dig deeper we need define the the difference between "bias" and "discrimination". "Bias", in the statistical sense, is a tendency of the data to favor one outcome more than expected by random chance [4]. While "discrimination" is the direct effect of gender on an applicant's acceptance regardless of their qualifications [4]. Bias is merely a pattern in the data and that pattern shows up against women in the aggregate data and against men in the split data. But these patterns do not explain the direct cause that gender has on the outcome. What we are asking is a causal question: "what is the effect of gender on admission?"

## Need for causality
Statistics is about analyzing data for patterns and correlations. When the data is good and our assumptions are sound, then the outcome of statistical analysis is correct. In the Berkeley study, running into Simpson's Paradox brings those assumptions into question, because we cannot have discrimination at the level of the university but not within the departments. Bickel is left to his own judgment, as there is no statistical way to decipher which set of assumptions is correct.

The goal of causality is to go one level deeper into the process that created the data. Judea Pearl developed a graphical way of codifying existing knowledge and assumptions, which allows us to build a model of the process [2]. A basic example is "X causes Y" and a graph where an arrow goes from X to Y as shown below.

<div class="mermaid">
graph LR;
	X-->Y;
</div>

This causal graph not only informs our analysis, but lets us easily communication our assumptions to others. Better yet, as Pearl showed, the graph allows us to test these assumptions using data [2]. The caveats, however, are that a correct analysis is dependent on the correctness of the graph and that multiple graphs could explain the same data [2, 5]. The upside is that we can understand how changes will impact the outcome and ask questions like: [5]
		- Will a change improve the outcome?
		- Why a decision work?
		- What should we do?
		- What are the overall effects?

## Applying Causality to the Berkeley Study
 In the Berkeley study there are three variables: gender, department, and admission. We know that neither department nor admission can effect gender, that is purely genetics. We are interested in the effect of gender on admission, so we assume that relationship exists. Bickel showed a relationship between gender and department, and while this is more likely an influence of society on gender, we assume there is a causal relationship. We end up with the following causal graph of the problem [2].

<div class="mermaid">
graph LR;
	G(Gender) --> D(Department);
	G --> A(Admission);
	D --> A;
</div>

This graph codifies our knowledge and assumptions, but more importantly, it shows the process that created the data. Gender has a direct effect on admission and an indirect effect mediated through department. The total effect is the combination of both direct and indirect effects, and this is what Bickel calculated when using the aggregate data [2]. 

Splitting the data by department, however, does not negate the indirect effect of gender on admission. Pearl has shown that conditioning on a mediator is never a good idea because it creates a conditional independence between gender and admission while still trying to calculate the overall effect [2]. For the Berkeley data, causal reasoning tells us we need to use the aggregated data to understand the effect of gender on admission.

## Disentangling Effects
Unfortunately, we still haven't answered if discrimination occurred. We know gender has an overall effect on admission, but we are no closer to answering if it's a direct effect (and is discrimination), a mediated effect based on the departments to which women tend to apply, or a combination of the two. Luckily, the field of causality allows for such mediation analysis, where we can begin to decipher the values of direct and indirect effects.

The details of such analysis are outside the scope of this post, but I hope that I have highlighted the need for causal analysis. Statistics only describes data and not the world it comes from, and the results are subject to the assumptions made when interpreting the data. Causal reasoning, especially the work of Pearl, seeks to make those assumptions clear to help us better understand the processes in the world that created the data. When we ask about discrimination at Berkeley, we are asking about the actions taken that created the data.

Statistics is more like a photo of the world. It shows us important insights, but it is incomplete and can be misinterpretation. Causality is like trying to understand the 3D structure of the world that created that photo. Causality, however, is not a silver bullet as multiple causal graphs can explain the same data and we are dependent on correct knowledge and assumptions used to construct the graph. This makes causality harder to implement than statistics, there is no one-size-fits-all-problems approach, but in the end it allows us to answer more important questions.

## Further Resources
This post is only an introduction on why causality is needed to answer certain questions and only covers some of the basics. Causality, or what Pearl refers to as "the new science of cause and effect", is a burgeoning field of study that includes more topics than I could even list in a post of this length. To get started, I recommend these Medium posts by Shawhin Talebi ([link 1](https://towardsdatascience.com/causality-an-introduction-f8a3f6ac4c4a), [link 2](https://towardsdatascience.com/causal-inference-962ae97cefda), [link 3](https://towardsdatascience.com/causal-discovery-6858f9af6dcb)) as an introduction to the topics of causality. I also recommend Judea Pearls' [*The Book of Why*](https://www.basicbooks.com/titles/judea-pearl/the-book-of-why/9780465097616/) for a much more comprehensive introduction.

## References
[1] Kahneman, Daniel. _Thinking, Fast and Flow_. Macmillan, 2011.

[2] Pearl, Judea, and Dana Mackenzie. _The Book of Why: The New Science of Cause and Effect_. Hachette UK, 2018.

[3] "Causality for Machine Learning". _Cloudera Fast Forward_. 2020. https://ff13.fastforwardlabs.com/

[4] Bickel, Peter J., Eugene A. Hammel, and J. William O'Connell. "Sex Bias in Graduate Admissions: Data from Berkeley: Measuring bias is harder than is usually assumed, and the evidence is sometimes contrary to expectation." _Science_ 187.4175 (1975): 398-404.

[5] Sharma, Amit and Kiciman, Emre. "DoWhy | An end-to-end library for causal inference". https://py-why.github.io/dowhy/v0.8/index.html

[6] Shawhin Talebi. "Causality: An Introduction". _Medium_. 2021. https://towardsdatascience.com/causality-an-introduction-f8a3f6ac4c4a

