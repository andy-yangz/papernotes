# Paper notes：A Study of Reinforcement Learning for Neural Machine Translation

TLDR

### What contribution？

Mainly two contribution:

1. Explored several aspects for reinforcement learning (RL) in NMT， such as how to generate target sentence to calculate reward, reward shaping, and substract a baseline reward for stable.
2. Apply this RL method to monolingual data to further enhance the performance

### Why it worth to explore this question？

There are not so many works about RL for NMT, because of several problems. For applying RL in NMT, there are still many points worth to explore.

### What challenge for this question

The main challenge is how to set reward function *R* appropriately in this equation:

![](https://ws3.sinaimg.cn/large/006tNbRwgy1fv7kmjo88qj30pe04ydg9.jpg)

Because there are problems such as high variance of gradient estimation, and objective instability.

And a small challenge is how to apply RL to monolingual data.

### Solution idea in this work

For the first challenge, authors propose several techniques:

1. Use *multinomial sampling*  instead *beam search* during generating target, for more diverse candidate;

2. Because calculating reward in sentence, it makes the rewards too sparse, and RL training inefficient. Authors use *reward shaping* to calculate cumulative reward.

   ![](https://ws4.sinaimg.cn/large/006tNbRwgy1fv7kyln03ij30kq01wt8w.jpg)

3. RL suffer from high variance in gradient estimation. To solve this, they minus a average reward for reward in each timestep. About how to calculate the average reward, they use use a simple network.

4. To further stablize RL, they combine the normal **maximal likelihood estimation** (MLE) training with RL training.

Comment: Actually, from the result, it shows the 2 and 3 seem do not help improve the result. Instead, the 1 and 4 improve the result substantially.

For the second challenge, they just train a MLE model first based on bilingual data. Then they use this model to translate monolingual data to make synthetic parallel data.

After conbine all the techniques, the final model shows a big improvement.

