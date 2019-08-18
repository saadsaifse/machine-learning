# Bayes Rule

We read what Random Variables are and also discussed their probability distributions in case of discrete and continuous random variables. But what if we have a scenario where we know the probability of a random variable and based on that we need to find out the probability of another random variable. For example, finding the probability of someone getting a heart attack provided the probability of the person being alcoholic.

Bayes rule allow us to find the required probability based on a conditional probability already given to us.

Bayes rule is defined as 

Pr(*X* = *x* | *Y* = *y*) = ( Pr(*Y* = *y* | *X* = *x*) Pr(*X* = *x*) ) /  Pr(*Y* = *y*)

Lets consider that the *X* random variable represents a person getting heart attack. And *Y* represents the person being a smoker or not. Then according to Bayes rule, we should have the following before we can calculate the probability of the person getting heart attack if he is a smoker.

1. Pr(*Y* = *y* | *X* = *x*) : Probability of being a smoker given that the person has a heart attack (this could possibly be easier to find out based on past data)
2. Pr(*X* = *x*) : Probability of a person getting a heart attack
3. Pr(*Y* = *y*) : Probability of a person being a smoker


Hence, Bayes rule or Bayes theorem allows us to find a conditional probability, giving us a better probability estimation based on our existing knowledge.