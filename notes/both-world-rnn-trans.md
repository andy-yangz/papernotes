## The Best of Both Worlds: Combining Recent Advances in Neural Machine Translation

### What contribution？

The main controbution as:

1. Proposed several training techniques, such as replace normal attention to multi-head attention, layer normalization, synchronous training, and label smothing, and combine them with normal RNMT model to make a RNMT+ model.
2. Provided a detail comparison between RNMT+, ConvS2S, and Transformer on WMT En-Fr, En-De. Later, they try to combine RNMT+ and Transformer model.

### Why it worth to explore this question？

It is interesting to explore the combination of classical RNN and the newer Transformer in NMT.

### What challenge for this question

1. Empiracally how to improve RNMT further
2. How to combine RNMT+ with Transformer

### Solution idea in this work

1. Several techniques as listed above
2. Af first, do ablation experiment by combine the encoder and decoder from both model, and find the RNN decoder is better. Latter, combine both RNN and Transformer encoder in stacked and concatenated way to achieve richer information. Then, feed the representation to RNN decoder.

#### Result

1. The propsoed RNMT+, outperform other model even Transformer Big a little. This challenged the idea Transformer can capture better intra relation of source and target language.
2. Those traning tachniques indeed improve a lot for NMT model. 
3. RNN decoder is better. And concatenated combine encoder representation is better.

Other I find is that, because those technique help RNN traning a lot, so it doesn't mean Transformer actually bad then RNN in capture the intra relation. We beed wait for further traibing technique for Transformer.