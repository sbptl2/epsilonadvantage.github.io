---
layout: post
---
# Helmets Galore

In an early morning discussion with some friends the other day, an interesting question was floated to me: Do helmets make us safer on the road? And how some of the risks of bike riding (like riding on roads without bike lanes or in areas that aren't too familiar with bikers) compare to the amount of protection given a helmet? Also Why


I tend to like playing various board games, but I also tend to be pretty bad at thinking things through. (I'm pretty lazy...) Towards a fix for this, let's try and take a step back to come up with various heuristics and lower the barrier to entry for creating good, low computation tactics. So how do we come up with a good strategy? I think it's helpful to ask some of the following questions:

[1] Is there a simple metric that's good to optimize on the first order?

[2] What would you like the world to look like? What are good positions to be in and how can we move towards them?

[3] Ask questions! When playing you will end up in scenarios where you aren't sure what's the best thing to do. While it's probably bad when this happens in a game, If I do this, what's a good way for the player to respond? For simpler games, we can even think about the equilibrium for the game.

[4] Answer the questions you ask!! This probably goes without saying, but I feel like I ask questions and don't touch them ever again sometimes.

## Chess

A great game to start with is probably Chess, mostly as it is so complicated that brute force strategies won't work (at least for humans). (Disclaimer, I'm pretty bad at chess, so maybe people who are better play differently.) Usually when I play chess, I either see a trap or tactic where I can win some material (a reasonable first order metric) or I have absolutely no idea what a good move is by this metric. In the latter case, I usually try to follow positional heuristics like develop your pieces, have good center control, grab open files, etc.

## Solitaire

I randomly decided I was going to play a bunch of solitaire today, so I tried to learn a few good heuristics. I wasn't feeling over lazy so that always helps in terms of looking ahead. Other than this I tried to favor creating open piles and in general maximizing the variance of the stack sizes. (My gut feeling is that an empty stack is pretty useful, so it's worth having some extra imbalance to increase the probability of one.) Of course, I'm not actually sure if this is a good strategy. I'll have to actually think about how well it works!

## Wordle

My strategy here was actually a bit strange (and not very fun tbh). I wanted to roughly halve the space of possibilities each time, but I'm quite bad at reverse look ups i.e. most words with these letters look like this. So instead, I would sample a bunch of consistent words from memory and then use this to answer the reverse look up. It worked decently well, but felt like too much work and too time consuming to be a good strategy.
