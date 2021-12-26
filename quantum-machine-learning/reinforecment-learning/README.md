---
description: >-
  @Glimpse  The Reinforcement Learning the algorithm has to understand the
  quality of the last steps. This means how good or bad an action worked.
---

# Reinforcement Learning

What we mean by goals and purposes can be well thought of as maximizing the aspected value of the cumulative sum of the value of a received scalar signal (reward) -  mobi dick

@BCP [\[ Document \]](https://docs.google.com/document/d/1AyzCiXk-LSRffas9YPaP1QIRRhcQDZhbiCCcFWJLYI8/edit?usp=sharing)

@git [https://github.com/ohioh/IntroductionQuantumComputing/blob/main/GettingStarted/ReinforcementLearning.ipynb](https://github.com/ohioh/IntroductionQuantumComputing/blob/main/GettingStarted/ReinforcementLearning.ipynb)

![\[ LINK \]](<../../.gitbook/assets/image (8).png>)

{% embed url="https://www.youtube.com/watch?v=FFW52FuUODQ" %}
\#
{% endembed %}

Reward-Strategy:

( optimal behavior is achieved by reaching the goal )

One way is to define a state where the goal is achieved as having plus one reward, and all others are 0 reward, that's sometimes called the goal rewarding coding.-Littman\


Another is to penalize the agent with a -1 each step in which the goal has not been achieved. Once the goal is achieved, there's no more cost, that's the action penalty representation.

(And both schemes can lead to big problems for goals with really long horizons)

@Fun Computer scientist love the computer scientist love recursion.&#x20;

In **inverse reinforcement learning**, a trainer demonstrates an example of the desired behavior, and the learner figures out what rewards the trainer must have been maximizing that makes this behavior optimal.\
**meta reinforcement learning:** learning at the evolutionary level that creates better ways of learning at the individual level.



#### Recommended Documents:

"Handbook of Reinforcement Learning and Control" -Springer ( Yan Wan, F. Lewis )

"Machine Learning mit Python und Scikit-learn und TesnorFlow" mitp

Deep Reinforcement Leanring with Guaranteed Perfomrance - Springer Yinyan Zhang, shuai Li

Algorthms and model views ( [https://gym.openai.com/envs/#mujoco](https://gym.openai.com/envs/#mujoco) )

\-> from [https://www.data-science-architect.de/reinforcement-learning-mit-python/](https://www.data-science-architect.de/reinforcement-learning-mit-python/)

@nature [https://www.nature.com/articles/nature14236](https://www.nature.com/articles/nature14236)

@paper [Reinforcement Learning: An Introduction](https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf)

@Introduction-Book-Github-Repo: [https://github.com/JaeDukSeo/reinforcement-learning-an-introduction](https://github.com/JaeDukSeo/reinforcement-learning-an-introduction)

examples of decision under uncertainty:

@paper [\[ LINK \]](https://www.imperial.ac.uk/media/imperial-college/administration-and-support-services/enterprise-office/public/Decision-making-under-uncertainty-FINAL.pdf)

@page [\[ LINK \]](https://towardsdatascience.com/reinforcement-learning-rl-101-with-python-e1aa0d37d43b)

## # Reinforcement Learning: Bellman Equation and Optimality [\[ Part 1 \]](./#9b09) , [\[ Part 2 \]](https://towardsdatascience.com/reinforcement-learning-markov-decision-process-part-2-96837c936ec3) , [\[ Part 3 \]](./#9b09)  <a href="#9b09" id="9b09"></a>

## @wiki [\[ Optimalitätsprinzip von Bellman \]](https://de.wikipedia.org/wiki/Optimalit%C3%A4tsprinzip\_von\_Bellman) <a href="#9b09" id="9b09"></a>
