---
layout: post
title: (Pandas Guide) Iteration Tips
categories: Python Pandas DataScience
description: How to make your iterations much faster with Pandas
keywords: Advanced DataAnalysis Python Pandas DataScience
---

![Pandas Logo](/images/blog/pandas-logo.png)

## Introduction

| ![Pandas Logo](/images/blog/pandas-side.png) | Using Pandas 🐼, we made our projects pipeline much easier and indeed faster.Pandas is one of the popular Python libraries among the data science community, as it offers vast API with flexible data structures for data explorations and visualization. Pandas is the most preferred library for cleaning, transforming, manipulating, and analyzing data. |


Let's start our example with init some data frame for us to play with ⚽, I will create a `DataFrame` with 1 million record to test the difference between the two ways of iterating over.

```python
cols = np.random.rand(1_000_000, 2)
df = pd.DataFrame(
    data={'a': cols[:, 0], 'b': cols[:, 2]}
)
print(df.shape)
```

> **Hint**: You can see me writing the 1 million as `1_000_000` with underscores in between, it is the same for python. But for human eyes, it is more readable this way 👀.

## Regular Iteration 🤕

In my day-to-day work, I used to use this way. For many reasons, such as it is the known one to me and I though that it's efficient when it is the only way for doing stuff (_when I can't use vecorization for example_).

Feature engineering and feature explorations require iterating through the data frame. There are various methods to iterate through the data frame, iterrows() being one of them. The computation time to iterate through the data frame using iterrows() is slower.

And if you search over the internet, you will find for example that the top answer in stack overflow is to use the `iterrows` method to iterate over the rows. And for long time, I thought it is the most efficient way for iterating, using the example below:

`Iterrows()` method is a Pandas built-in function to iterate through your data frame. It should be completely avoided as its performance is very slow compared to other iteration techniques. `Iterrows()` makes multiple function calls while iterating and each row of the iteration has properties of a data frame, which makes it slower.

```python
for idx, row in iterrows():
    do_something_with(row)
```

And seems that this way takes on my machine around `20`~`30` second, or some time between those intervals. You can test those results in your machine and share what you have got too 🧪⚗️.


## Tupled Iteration 🦾

`Itertuples()` is a Pandas inbuilt function to iterate through your data frame. `Itertuples()` make a comparatively less number of function calls than `iterrows()` and carry much lesser overhead. `Itertuples()` iterates through the data frame by converting each row of data as a list of tuples.


I used to name this way with tupled iteration, as we get each row as a tuple and work with it. One more useful thing in this method, it that you can access the columns names with much easier way compare to use the array accessing methodolgy in `iterrows()`.


```python
for t in df.itertuples():
    do_something_with(t)
```

After using `itertuples()` I found that I took something between `400`~`600` ms to iterate through a data frame with 1 million records that are around **50x** times faster than `iterrows()`.


## Final Words 👌👌

**Vectorization** is always the first and best choice. You can convert the data frame to NumPy array or into dictionary format to speed up the iteration workflow. Iterating through the key-value pair of dictionaries comes out to be the fastest way with around 280x times speed up for data that contains millions of records 🤑.