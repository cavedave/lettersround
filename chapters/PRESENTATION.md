# Cracking Countdown: A Data-Driven Journey to Find the Most Powerful Words
Can we Moneyball countdown?

A project by David Curran and Gemini.

**Key takeaway**: The statistically best words aren't just the most common ones; they're the ones that work best *together*.

---

## Slide 2: Quotes

> "Virtually everyone suffers from the deeply ingrained habit of considering language as a medium of communication."
>
> ― Dmitri Borgmann, *Language on Vacation*


> "If you challenge conventional wisdom, you will find ways to do things much better than they are currently done."
>
> - Bill James

> "You are not buying into this Bill James bullshit are you?" Scout
> "We are card counters at the blackjack table. And we're gonna turn the odds on the casino." 
>
> - Billy Beane in Moneyball the film
---

## Slide 3: Moneyball

Find a game where the KPI being chased after is not the right one. 
In Baseball people thought they were buying players. they should have been buying getting on base. 

In Countdown people think they are trying to find words they know. They should be looking to learn words that will come up.

---

## Slide 4: How countdown works

Take 9 letters from a bag of tiles that looks like

#### **Consonant Pile**

| Group         | Letters           | Frequency per Letter |
|---------------|-------------------|-----------------------|
| Most Common   | R, S, T           | 9                     |
| Very Common   | N                 | 8                     |
| Common        | D                 | 6                     |
| Mid           | L                 | 5                     |
| Semi-Rare     | G, M, P           | 4                     |
| Uncommon      | C                 | 3                     |
| Rare          | B, F, H, V, W     | 2                     |
| Very Rare     | J, K, Q, X, Y, Z  | 1                     |

#### **Vowel Pile**

| Letter | Frequency |
|--------|-----------|
| E      | 20        |
| A      | 15        |
| I      | 13        |
| O      | 13        |
| U      | 7         |



---



## Slide 5: The Initial Question


![how words help](../coverage_comparison_top1000.png){ width=100% }



---


## Slide 5: pick better words greedy algorithm


![how words help](../coverage_comparison_top1000.png){ width=100% }



---


## Slide 3: The Initial Question

- **Goal**: Create a "perfect" study list of 100 words to maximize success in the Countdown letters round.
- **Starting Point**: An existing project with a basic word simulation.
- **Initial Hypothesis**: The "best" words are simply the ones that appear most frequently in random letter draws.

---

## Slide 3: The First Hurdle & A Key Discovery

- **Problem**: The naive "cumulative coverage" of the most frequent words was flawed. It double-counted games and could exceed 100%.
- **Insight**: This is a classic probability problem (non-mutually exclusive events). We needed to measure the *true, non-overlapping coverage*.
- **Result**: The true coverage of the top 100 most frequent words was only **9.05%**. The overlap was a massive factor.

---

## Slide 4: The Innovation: A Greedy Algorithm

- **New Goal**: Don't just find the most frequent words. Find the "portfolio" of 100 words that work best as a team.
- **Method**: A greedy algorithm. At each step, it selects the word that adds the most *new, previously-uncovered* games.
- This prioritizes words with unique letter combinations that fill gaps in the existing list.

---

## Slide 5: The Results

- The greedy algorithm produced a new, optimized list of 100 words.
- **True Coverage**: **10.01%**
- This is a **10.6% relative improvement** over the naive list (10.01 vs 9.05) – a significant edge.
- To achieve this, the algorithm swapped out **59 of the original top 100 words**, proving that a smarter selection process yields a very different list.

---

## Slide 6: Sanity Check 1: The Score vs. Coverage Dilemma

- **Your Insight**: Are we losing points by only picking 7-letter words?
- **Experiment**: We modified the algorithm to optimize for *potential score* (weighting 8- and 9-letter words higher).
- **Surprising Result**: The algorithm *still* chose an all 7-letter-word list. Their frequency is so high it outweighs the point bonus of longer words.

---

## Slide 7: Sanity Check 2: The Other Top 100 List

- **Question**: Why does a list from a site like `countdownresources.wordpress.com` contain so many 8-letter words like `ASTEROID` and `RATIONED`?
- **Investigation**:
    1.  That list is based on a different dictionary and/or letter frequency.
    2.  Our greedy algorithm actively *rejected* those words because they have too much letter overlap with our top choices (e.g., `ANESTRI` and `NOTARISE`).
- **Conclusion**: This validates our portfolio-based approach over a simple frequency ranking.

---

## Slide 8: The Final, Definitive List

- We have proven through multiple iterations and rigorous validation that our original greedy algorithm, using the `sowpods.txt` dictionary, produced the most statistically effective list.
- This process demonstrates the power of iterative, data-driven analysis to arrive at a non-obvious and robust conclusion.

---

## Slide 9: Q&A 