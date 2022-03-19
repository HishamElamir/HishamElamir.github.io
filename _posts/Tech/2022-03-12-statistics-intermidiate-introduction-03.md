---
layout: post
title: (Intermediate Statistics) 03. Types of Statistics in This Series
categories: Math-Post Data Statistics
description: An Introduction to Intermediate Statistics
keywords: Statistics Math Advanced Data Analysis
---

![Intermediate Stats](/images/blog/intermidiate-stats.png)

## Introduction






For example, Ellen Go-getter is convinced that dissolving sugar in the water
helps cut flowers last longer. She performs an experiment to prove her
hypothesis. She cuts two dozen roses and puts one rose in each vase. She
fills each vase with 3 cups of water, but in 12 of the vases she adds 1 tablespoon of sugar (the other 12 vases constitute the control group, meaning that
Ellen doesn’t apply any new treatment to them to show what happens if she
adds nothing). In the next sections, you follow Ellen through her experiment,
keeping an eye on the statistical analyses that pop up along the way.
Examining Ellen’s data
Ellen counts how many days the flowers still look nice and uses the same criteria for each flower. After ten days, all the flowers have withered to the point
where they need to be thrown away, so the experiment is over. You can see
Ellen’s data in Table 1-1.

// table


Setting the hypothesis
Ellen wants to compare the two methods, water and sugar, to see whether
the roses that had sugar added lasted longer than the regular water group.
She needs to conduct a hypothesis test whose null hypothesis is Ho: There is
no difference in days lasted for sugar group versus control group. Her alternative hypothesis, which she hopes to show, is Ha: The roses in the sugar
group lasted longer than the control group. She figures a two-sample t-test is
in order here. (I discuss hypothesis tests in Chapter 3.)
Checking the conditions
Ellen has taken a few statistics classes before and knows that before she
plunges into an analysis, she needs to check the proper conditions. For a
comparison of two groups, she has to plot the data from each group on a
histogram (a bar graph showing the number of days the flowers lasted,
organized into groupings in numerical order versus the number of flowers
that lasted each number of days). According to what she knows about a twosample t-test, the data in each group has to have a normal distribution before
she starts. That is, the data has to have a bell-shaped curve when you look at
the histogram. Ellen plots the data in histograms for the two groups and gets
the following results (see Figures 1-2a and 1-2b).

// figure

Getting the bad news
As you can see in Figures 1-2a and 1-2b, Ellen’s data doesn’t follow the typical
bell-shaped curve. One of the problems is her data only takes on values that
are positive whole numbers, so numbers like 1.2, 2.3, and the like aren’t possible. (Normal distributions are supposed to have many possible values.) The
other problem is that the data has no values outside the typical two-, three-,
four-, or five-day range, so the histogram doesn’t have a chance to take on a
bell shape. Perhaps more data would have curbed this problem. At any rate,
Ellen knows that the conditions for a two-sample t-test aren’t met here;
namely that the data doesn’t have a normal distribution and is, in fact,
skewed (meaning set off to one side or the other).
Going nonparametric
Undaunted by this turn of events, Ellen employs a nonparametric test of her
data, which is the right thing to do. Statisticians use nonparametric statistics
in situations where the assumptions of the typical analyses aren’t met (like
not having a normal distribution). However, nonparametric stats often give
more conservative (albeit more accurate) results than the typical (parametric) procedures you’re used to using. (I discuss nonparametrics a bit more in
the last section of this chapter. Nonparametric procedures are discussed in
full detail in Chapters 16–19.)
Because Ellen’s data doesn’t have a normal distribution or even a symmetric
distribution (meaning one that looks the same on each side when you split it
down the middle), the mean (or average) isn’t a good measure of the center
of the data, so a two-sample t-test isn’t possible. As an alternative, she can
test whether the two histograms are the same or not, if she compares the histograms of the two populations in question (all roses given water, versus all
roses given sugar water).
Because she’s comparing two groups, Ellen uses a Wilcoxon Rank Sum test,
also known as the Mann-Whitney test (see Chapter 19). The Wilcoxon Rank
Sum test checks whether two populations have the same distribution (meaning whether the two histograms look the same) versus one of the populations
shifting to the right or left. Ellen’s theory is that the sugar group lasts longer,
so she tests Ho: Sugar group and control group have the same distribution
versus Ha: Sugar group is shifted to the right of the control group.
Ellen strikes out
To cut to the chase, the Wilcoxon Rank Sum test unfortunately fails to reject
Ellen’s null hypothesis. She didn’t prove what she wanted to confirm by her
experiment. Not enough roses in the sugar group lasted longer than those
roses in the control group. You can see the underlying reason for this result
by comparing the medians of the two groups. When you find the median of
each of the data sets in Table 1-1, you get the value of 4 in each case. Because
the medians of the two data sets are equal, it’s unlikely that Ellen can find a
statistically significant result by using this test.

Breaking the rules
According to the rules that all good statisticians live by, Ellen’s story should
end there. She may still be convinced that sugar indeed helps roses last
longer. She may use sugar with her roses for the rest of time and tell her
friends to use it too. But, she isn’t allowed to say that sugar water gives statistically different results than water alone; her analysis failed to show that.
But remember, Ellen’s last name is Go-getter, so she’s out to get those results.
She knows that nonparametric tests usually give more conservative results
than regular tests, and despite the fact that the conditions aren’t met, she
decides to analyze her data again, this time using the two-sample t-test.
Putting her data into a two-sample t-test takes only two more clicks of the
mouse, and Ellen’s results give her a p-value of 0.043. Using the usual significance level used for hypothesis tests, 0.050, her p-value is less than this
number, so she can reject Ho. (In a two-sample t-test, Ho is that there’s no
difference in the means of the two groups. And her Ha in this case is that
the mean of the sugar group is larger than the mean of the control group.)
So Ellen gleefully cheers herself on for getting the results she wanted and
decides there’s no harm in trying a different analysis when all else fails.
Seeing the error of Ellen’s ways
But again, “Houston. . .” — you know the rest. Ellen’s problem is that she
cheated her way to getting a result that’s incorrect. She knew that the conditions for the two-sample t-test weren’t met, but when the correct analysis
failed to get the results she wanted, she found an analysis that did. The trouble is, the results of the two-sample t-test are bogus.
Now it may not be a life-and-death situation whether your roses actually do
last a little bit longer on sugar or not. (Incidentally, the gardening crowd says
they don’t, and that sugar in fact can encourage the growth of stem-clogging
bacteria so the flower can’t take in water.) But imagine a situation where doctors are trying to test to see whether a certain medication helps people get
over an illness faster or whether some procedure helps cancer patients live
longer. Now you’re talking about results with a very serious impact.
Using the wrong data analysis for the sake of getting the results you desire
results in two major problems:
* You mislead your audience into thinking that your hypothesis is actually
correct, which it may not be.
* Sooner or later someone is going to try to replicate those results and
will find out that they can’t be replicated. This discovery will result in a
loss of your credibility big time. And unfortunately, you mislead many
people in the meantime.












Because you’re reading this book, you’re likely familiar with the basics of statistics. You’re now ready to take it up a notch. That next level
involves using what you know, picking up a few more tools and techniques
at the intermediate level, and finally putting it all to use to help you answer
more realistic questions by using real data.
In statistical terms, you’re ready to enter the world of the data analyst. This
world’s an exciting one, with many options to explore and many tools available. But, as you may have guessed, you have to navigate this world very
carefully, choosing the right methods for each situation. In this book, you can
see that I’m including the underlying theories and ideas behind the methods
where necessary to help you make good decisions — and not just get into the
point-and-click mode that today’s software packages offer.
In this chapter, you review the terms involved in statistics as they pertain to
data analysis at the intermediate level. You get a glimpse of the impact that your
results can have by seeing what these analysis techniques can do. You also gain
insight into some of the common misuses of data analysis and their effects.


Because of the dangers and lingering effects of using the wrong techniques in
the wrong situation to analyze data to answer questions, knowing what’s happening behind the scenes of any data analysis and staying within the rules of
well-chosen techniques and appropriate practices is very important. In other
words, it’s crucial for you to take your knowledge of statistics to the next level.
Intermediate statistics is an extension of introductory statistics, so the jargon
follows suit and the techniques build on what you already know. If you’ve
been able to grasp the ideas from the first course, you’ll find no trouble with
the terminology for intermediate statistics. If you’re still unsure about some
of the terms from introductory statistics, you can consult your textbook from
your first course or see my other book, Statistics For Dummies (Wiley), for a
complete rundown.
In this section, you get an introduction to the terminology you use in intermediate statistics, and you get a broad overview of the techniques that statisticians use for the purpose of analyzing data and the big picture behind them.


Population parameter
A parameter is a number that summarizes the population (the entire group
you’re interested in investigating). Examples of parameters include the mean
of a population, the median of a population, or the proportion of the population that falls into a certain category.
Suppose you want to determine the average length of a cell-phone call among
teenagers (ages 13 to 18). You’re not interested in making any comparisons;
you just want to make a good guesstimate as to what the average time is. So
you want to estimate a population parameter (such as the mean or average).
The population is all cell-phone users between the ages of 13 and 18 years old.
The parameter is the average length of a phone call this population makes.
Sample statistic
You normally can’t study every member of an entire population (how would
you like to measure and record the length of every single cell-phone call
made by all teenagers?). So you can’t determine population parameters
exactly; you can only estimate them. But all is not lost; by taking a sample (a
subset of individuals) from the population and studying them, you can come


up with a good guess (estimate) of the population parameter, if you play your
cards right. A subset of this population is called a sample. A sample statistic is
a single number that summarizes that subset of the population.
For example, in the cell-phone scenario, you select a sample of teenagers and
measure the length of their cell-phone calls over a period of time (or look at
their cell-phone records if you can gain access legally). You take the average
of the cell-phone call lengths. For example, the average length of 100 cellphone calls may be 12.2 minutes — this average is a statistic. This particular
statistic is called the sample mean, because it’s the average value from your
sample data.
You can also find a statistic called the sample proportion (the proportion of
individuals in the sample that have a certain characteristic — for example, the
percentage of female teens who use cell phones). Many different statistics are
available (which you probably picked up in intro stats) to study different characteristics of a sample, such as the median, variance, and standard deviation.
Confidence interval
A confidence interval is a range of values that provides reasonable estimates
for a population parameter. A confidence interval is based on a sample and
the statistics that come from that sample. The main reason you want to provide a range of possible values rather than a single number is that sample
results vary from sample to sample.
For example, say you want to estimate the percentage of people who eat
chocolate. According to the Simmons Research Bureau, 78 percent of adults
reported eating chocolate, and of those, 18 percent admitted to eating sweets
frequently. What’s missing in these results? These numbers are only a single
sample of people, and those sample results are guaranteed to vary from
sample to sample. You need some measure of how much you can expect
those results to move if you were to repeat the study.
This expected movement in your statistic is measured by the margin of error,
which reflects a certain number of standard deviations of your statistic you
add and subtract to have a certain confidence in your results (see Chapter 3
for more on margin of error). If the chocolate-eater results were based on
1,000 people, the margin of error would be approximately 3 percent, meaning
the actual percentage of people who eat chocolate in the entire population is
expected to be 78 percent, plus or minus 3 percent. In other words, it’s somewhere between 75 percent and 81 percent. Now if you only base these results
on a sample of 100 people, the margin of error balloons to 10 percent, meaning the percentage of chocolate eaters can only be reported to be between 68
and 88 percent. Notice how much wider the interval becomes when a smaller
sample size is used. This result confirms that more data means more precision in your results (provided the data is collected properly).


Hypothesis test
A hypothesis test is a statistical procedure that you use to test an existing
claim about the population, using your data. The claim is noted by Ho (the
null hypothesis). If your data support the claim, you fail to reject Ho. If your
data don’t support the claim, you reject Ho and conclude an alternative
hypothesis, Ha. The reason most people conduct a hypothesis test is not to
merely show that their data support an existing claim, but rather to show
that the existing claim is false, in favor of the alternative hypothesis.
The Pew Research Center studied the percentage of people who go to ESPN
for their sports news. Their statistics, based on a survey of about 1,000
people, found that in 2000, 23 percent of people said they go to ESPN; while in
2004, only 20 percent reported going to ESPN. The question is this: Does this
3-percent reduction in viewers from 2000 to 2004 represent a significant trend
that ESPN should worry about?
To test these differences formally, you can set up a hypothesis test. You set
up your null hypothesis as the result you have to believe without your study,
Ho = no difference exists between 2000 and 2004 data for ESPN viewership.
Your alternative hypothesis (Ha) is that a difference is there.
In very general terms, here’s what’s happening with a hypothesis test. You
have the sample data, and you find the statistics that are relevant. In this
case, you have two sample percentages, one for 2000 and one for 2004. You
take the difference between the two samples (3 percent), and divide it by the
standard error for the difference. The standard error measures how much the
difference in the statistics is expected to change from sample to sample. In
this case, the standard error comes to about 1.8 percent (for specific calculations see Chapter 3).
Taking the difference in the statistics (3 percent = 0.03) divided by the standard error (1.8 percent = 0.018) gives you the value of 1.67 (called the test
statistic). This value represents the difference between the two statistics, in
terms of number of standard errors. This result has a universal interpretation. Roughly speaking, if your test statistic falls between –2.00 and +2.00,
that means the results you found don’t differ enough to get excited about,
because 95 percent of the time, this outcome happens just by chance. (And
this example falls right into that situation.) After you take the variability of
the sample results into account, the difference in these particular samples
doesn’t transfer over to the populations they represent. So, because you
can’t reject Ho, you have to say the percentage of viewers of ESPN in the
entire population probably didn’t change from 2000 to 2004.
Because you have a 95 percent confidence level, this test uses a significance
level (α level) of 1 – 0.95 = 0.05 or 5 percent. This percentage measures how
likely your results would have been just by chance.


The trouble is that people often just report the sample statistics and give no
regard to the expected amount of change with a new sample. This disregard
leads to big mistakes in the conclusions (more on hypothesis testing in
Chapter 3).
Analysis of variance (ANOVA)
ANOVA is the acronym for analysis of variance. You use ANOVA in situations
where you want to compare the means of more than two populations. For
example, you want to compare the lifetime of four brands of tires, in number
of miles. You take a random sample of 50 tires from each group, for a total of
200 tires, and set up an experiment to compare the lifetime of each tire, and
record it. You have four means and four standard deviations now, one for
each data set. But you have different types of variability in your data, each
measured by using various sums of squares. (Remember from your intro stats
that the variance of a data set is the total of all the squared distances
between the data and the mean, all divided by n – 1.)
One of the types of variability in your data is called the variability between
treatments (also known as SST, the treatment sums of squares). SST measures the variation in the average lifetimes of each brand of tire, compared to
the overall average lifetime. If SST is large, you have a chance that there’s a
difference in lifetimes due to the treatment (in this case, the brand of tire).
Next, you have the variability within the treatments (also known as SSE, the
error sums of squares). SSE measures the overall average amount of variability of the tire lifetimes within each particular brand (after all, not all tires are
created equal, even if they’re of the same brand). If SSE is large, you have so
much variability within the tire brands themselves, that it will be harder to
see any real difference between the brands, even if it actually exists.
And finally, you have the total overall variability in the data values if you just
put them all together into one big data set. This variability is known as SSTO,
the total sums of squares. ANOVA splits up the total variability (SSTO) into
the between-groups variability (SST) plus the within-groups variability (SSE).
Then, to test for differences in average lifetime for the four brands of tires, you
compare the mean sums of squares for treatments (MST) to the mean sums
of squares for error (MSE) in a ratio called the F-statistic. If this ratio is large,
then the variability between the brands is more than the variability within the
brands, giving evidence that not all the means are the same for the different
tire brands. If the F-statistic is small, that means not enough difference was
between the treatment means, compared to the general variability within the
treatments themselves. In this case, you can’t say that the means are different
for the groups. (I give you the full scoop on ANOVA in Chapters 9 and 10.)


Multiple comparisons
Suppose you conduct ANOVA, and you find a difference in the average lifetimes of the four brands of tire (see preceding section). Your next questions
would probably be, which brands are different, and how different are they?
To answer these questions, you use multiple-comparison procedures.
A multiple-comparison procedure is a statistical technique that compares
means to each other and finds out which ones are different and which ones
aren’t. You’re then able to put the groups in order, from those with the largest
mean to those with the smallest mean, realizing that sometimes two or more
groups were too close to tell and so you put them in the same group.
Suppose you compare the exam scores of four different classes (call them
class one, class two, class three, and class four), and your ANOVA procedure
finds out that not all the means were the same. That means the F-statistic is
large. Next, you use multiple-comparison procedures in order to make separate comparisons and figure out which classes were about the same and
which ones were different, and come up with an ordering of the classes. It
may be, for example, that class four was statistically higher than all the
others; classes one and two were statistically equivalent, but both were lower
than class four. And class one was in a group all by itself at the bottom. The
ordering is: class four (highest average), classes two and three (tied for
second highest), and class one (the lowest average).
Never take that second step to compare the means of the groups if the ANOVA
procedure doesn’t find any significant results during the first step. (See Chapter 11 for more information.)
Many different multiple-comparison procedures exist to compare individual
means and come up with an ordering in the event that your F-statistic does
find that some difference exists. Some of the multiple-comparison procedures
include Tukey’s test, LSD, and pairwise t-tests. (While these tests’ names may
cause you to raise an eyebrow, don’t worry. They’re legitimate statistical
tests.) Some procedures are better than others, depending on the conditions
and your goal as a data analyst. I discuss multiple-comparison procedures in
detail in Chapter 11.
Interaction effects
An interaction effect in statistics operates the same way that it does in the
world of medicine. Sometimes if you take two different medicines at the same
time, the combined effect is much different than if you take the two individual
medications separately.


Interaction effects come up when you have a model that includes two or
more variables, and you’re using those variables to explain differences or to
make comparisons regarding some outcome. When you have two or more
variables in a model, you can’t automatically study the effect of each variable
separately; you also have to take into account the way those variables interact in terms of the outcome. In other words, you have to examine whether or
not an interaction effect is present.
For example, suppose medical researchers are studying a new drug for
depression and want to know how this drug affects the change in blood pressure for a low dose versus a high dose of the drug. They also compare the
effects for children versus adults. In total, the model being studied has one
response variable, an increase in blood pressure, and two factors that may
possibly explain changes in the outcome, namely age group (adults versus
children) and dosage level (low versus high). It could be that dosage level
affects the blood pressure of adults differently than the blood pressure of
children. This type of model is called a two-way ANOVA model, with a possible
interaction effect between the two factors (age group and dosage level). See
Chapter 11 for more.
One of the first things statisticians do when they have a two-way ANOVA is to
plot the mean outcomes for each group they’re comparing and look for patterns. This is called an interaction plot. One interaction plot for the drugstudy scenario is in Figure 1-3.

// figure


As you can see by Figure 1-3, the lines cross. If you look at the line representing children, you can see that the mean increase in blood pressure is low for
the low dose of the drug, but then for the high dose of the drug; the increase
in blood pressure goes way up. Alternatively, the reaction is the exact opposite for adults; on the low dose, the mean increase in blood pressure is very
high, but for the high dose, the increase is very low. If the doctors neglected to
study children as well as adults, the results of this study could be extremely
damaging to children if doctors applied the rules for adults to children. This
example shows that interaction effects are very important to look at.
Figure 1-4 shows the situation where you have no interaction effect for this
drug. The lines are parallel, which tells you that the mean blood pressure
increases more on a higher dosage of the drug for both adults and children.
Because the line for the adults is higher up than the line for children, that
means that overall, the increase in blood pressure is more for adults than the
increase in blood pressure for children, no matter what the dosage level is.

// figure


Correlation
The term correlation is often misused. Statistically speaking, the correlation
measures the strength and direction of the linear relationship between two
quantitative variables (variables that represent counts or measurements only).
You aren’t supposed to use the word correlation to talk about relationships
of any other kind. For example, it’s wrong to say that a correlation exists
between eye color and hair color. While these variables may be related in

some way, they’re not quantitative variables, so you can’t discuss their relationship in terms of a correlation. (In this case, you would use the term association; in Chapter 14, you see how to test for association of two categorical
variables.)
The long and short of correlation is the following: Correlation is a number
between –1.0 and +1.0. Positive one indicates a perfect positive relationship;
in other words, as you increase one variable, the other one increases in perfect sync. On the other side of the coin, a correlation that is –1.0 indicates a
perfect negative relationship between the variables. As one variable increases,
the other one decreases in perfect sync. A correlation of zero indicates that
you found no linear relationship at all between the variables. Most correlations in the real world aren’t exactly +1.0, –1.0, or 0 — they fall somewhere in
between. The closer to +1.0 or –1.0, the stronger the relationship is; the
closer to 0, the weaker the relationship is.
Figure 1-5 shows an example of a plot showing the number of coffees sold
at football games in Buffalo, New York, as well as the air temperature (in
Fahrenheit) at each game. This data set seems to follow a downhill straight line
fairly well, indicating a negative correlation. When you calculate the correlation, you get the value of –0.741. This value says that coffees sold has a fairly
strong negative relationship with the temperature of the football game. This
makes sense, because on days when the temperature is low, people will get
cold and want more coffee. On days when the temperature is higher, people
will tend to drink less coffee and perhaps tend more toward soft drinks, which
are cold. I discuss correlation further, as it applies to model building, in
Chapter 4.

// figure


Linear regression
After you’ve determined that two variables have a fairly strong linear relationship, you may want to try to make predictions for one variable based on
the value of the other variable. For example, if you know that a fairly strong
negative linear relationship exists between coffees sold and the air temperature at a football game, you may want to use this information to predict how
much coffee is needed for a game, just by knowing the temperature. This
method of finding the best-fitting line is called linear regression.
In the coffees and temperature example (see Figure 1-5), the best-fitting line
has the equation y = 49,337 – 554 * x , where x is temperature and y is the
number of coffees sold. So when the temperature (x) is zero degrees, you can
expect to sell around 49,337 coffees (this is how you interpret the y-intercept
of the line). To interpret the slope of this line, think of –554 as –554 divided
by one and use the old rise-over-run idea using coffees and degrees of temperature. Applied here, it means that for every one degree increase in temperature, you can expect the coffee sales to decrease by 554. You can use this
line to make predictions for reasonable values of the temperature (x). For
example, if the temperature is a cold 20-degrees Fahrenheit, you can predict
that the number of coffees sold will be around 49,337 – 554 * 20 = 38,257.
When you use only one variable to predict the response, the method of
regression is called simple linear regression. (I review the basics of simple
linear regression in Chapter 4. But many other types of regression are out
there, many of which I discuss in this book.)
Most researchers use more than one variable to predict a response; this technique is called multiple linear regression. (Check out Chapter 5 for the details
about multiple linear regression.) Multiple linear regression has many issues
of its own because some variables you can use in the model may be related
to each other, making overlapping contributions to the response. That possibility of overlapping makes their individual contributions hard to track. You
also have to watch for interaction effects when using more than one variable
to predict a response.
Simple and multiple linear regression assume that the response variable (the
one being studied) is quantitative in nature (that is, it measures or counts
something). However, you may be interested in making predictions about a
variable that has only two outcomes: yes or no. For example, whether or not
a certain horse will win a race; whether a baby will be a girl or a boy; or
whether or not a tropical storm is going to make landfall. These situations
require a different kind of regression called logistic regression. (I discuss logistic regression in Chapter 8.)



Finally, you may be interested in building a model for which a straight line
doesn’t fit. For example, you may want to predict miles per gallon, using the
speed of the car. While high speeds get low miles per gallon, low speeds can
get low miles per gallon as well. So the relationship between speed and miles
per gallon actually follows that of a parabola (an upside-down bowl, in this
case). This kind of relationship is called a quadratic relationship. More generally speaking, relationships that don’t follow a straight line are called nonlinear relationships, and the technique you use to handle these situations is
called (no surprise) nonlinear regression. I get into the meat of this technique
in detail in Chapter 7.
Chi-square tests
Correlation and regression techniques all assume that the variable being
studied in most detail (the response variable) is quantitative. That is, the
variable measures or counts something. However, you can run into many situations where the data being studied isn’t quantitative, but rather qualitative.
In other words, the data themselves represent categories, not measurements
or counts.
For example, suppose you want to compare the views of the president by
political affiliation. Say that in this particular year, the president is a
Republican, and you select a random sample of 150 Republicans, 150
Democrats, and 150 Independents to find out their views on the president.
The data may look like Table 1-2.

// table

In looking at how the numbers appear across the columns for various rows
in Table 1-2, you may suspect that something is up. It appears that Republicans
tend to approve of the president, while Democrats tend to disapprove,
and Independents are split down the middle. (So much for the spirit of
bipartisanship. . . .)


Now does this association you found in the data set for this sample of 450
people carry over to the entire population? In order to answer this question,
you need to conduct a hypothesis test. And not just any hypothesis test — a
Chi-square test for independence. You’re testing to see whether the two qualitative variables, political affiliation and views on the president, are related or
not. If they are related, the variables are deemed not independent; if they are
unrelated, the variables are independent.
A Chi-square test basically does the following: It figures out the number of
values that you expect to see in each cell of the table if the variables are independent (these values are brilliantly called the expected cell counts). The Chisquare test then compares these expected cell counts to what you actually
saw in the data (called the observed cell counts) and compares them to each
other in a Chi-square statistic (see Chapter 14).
If the Chi-square test statistic is large, you’re likely to find an association
between the two variables, because the total differences are large between
the observed and expected cell counts. In other words, the variables are not
independent, and you can look at the observed cell counts to discuss the
relationship you see. If the Chi-square test statistic is small, then you can’t
conclude you’ve found a relationship, and the two variables are independent.
In the case of political affiliation and views on the president, the Chi-square
test statistic is huge, and you conclude a relationship is there somewhere.
You can say that in the population, Republicans tend to support the president, Democrats tend to oppose the president, and the Independents are
split down the middle. (You can find the details of how to find the expected
counts and conduct the Chi-square test in Chapter 14.)
You can also use the Chi-square test to see whether your theory about what
percent of each group falls into a certain category is true or not. For example,
can you guess what percentage of M&Ms fall into each color category? More
on these Chi-square variations, as well as the M&Ms question, in Chapter 15.

Nonparametrics
Nonparametrics is an entire area of statistics that provides analysis techniques to use when the conditions for the more traditional and commonly
used methods aren’t met. For example, in order to use a t-test, the data needs
to be collected from a population that has a normal distribution (that is, it
has to have a bell-shaped curve). In order to do a hypothesis test for two
means, the data from each group must be from its own normal population. In
fact, most all of the commonly used data-analysis procedures have conditions that must be met in order to use them.

The trouble with these requirements is that many times people forget or just
don’t bother to check those conditions, and if the conditions are actually not
met, the entire analysis goes out the window, and the researcher doesn’t
even know it. Or, someone finds out that the conditions aren’t being met, yet
she still goes ahead and uses the procedures anyway (for more on this faux
pas, see the section in this chapter “No *(data)* fishing allowed”).
While many of the traditional methods are what statisticians call robust, with
respect to violations of their conditions (that’s fancy terminology for the fact
that they’re pretty forgiving), you can only push the window so far. Proceeding
to use a statistical procedure that isn’t appropriate causes a great deal of trouble with respect to the correctness of the conclusions and the credibility of the
researcher.
Have no fear, nonparametrics comes to your rescue. If the conditions aren’t
met for a data-analysis procedure that you want to do, chances are that an
equivalent nonparametric procedure is waiting in the wings. And the good
news is that they’re generally pretty tame, in terms of formulas, and most statistical software packages can do them just as easily as the regular (parametric) procedures.
Conditions aren’t checked automatically by statistical software packages,
before doing a data analysis. It’s up to the user to check any and all appropriate conditions, and if they’re seriously violated, to take another course of
action. Many times a nonparametric procedure is just the ticket. For much
more information on different nonparametric procedures, see Chapters 16
through 19.



## What Now 🤔

This part of the series is ends here, but the series continues.
Stay tuned for the next part, if not uploaded yet 😅.
And if you have any feedback, you can send me on email or twitter.

See You Soon,
Hisham.