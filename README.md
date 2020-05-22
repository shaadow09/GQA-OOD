# The GQA-OOD Benchmark 

GQA-OOD is a new dataset and benchmark for the evaluation of VGQ models in OOD (out of distribution) settings. The corresponding paper "*Roses are Red, Violets are Blue... But Should VQA expect Them To?*" is currently under evaluation at the BMVC 2020 conference. 

### Abstract ###

  *To be reliable on rare events is an important requirement for systems based on machine learning. In this work we focus on Visual Question Answering (VQA), where, in spite of recent efforts, datasets remain imbalanced, causing shortcomings of current models: tendencies to overly exploit dataset biases and struggles to generalise to unseen associations of concepts. We focus on a systemic evaluation of model error distributions and address fundamental questions: How is the prediction error distributed? What is the prediction accuracy on infrequent vs. frequent concepts?*

  *In this work, we design a new benchmark based on a fine-grained reorganization of the GQA dataset, which allows to precisely answer these questions. It introduces distributions shifts in both validation and test splits, which are defined on question groups and are thus tailored to each question. We performed a large-scale study and we experimentally demonstrate that several state-of-the-art VQA models, even those specifically designed for bias reduction, fail to address questions involving infrequent concepts. Furthermore, we show that the high accuracy obtained on the frequent concepts alone is mechanically increasing overall accuracy, covering up the true behavior of current VQA models.*


## How is the VQA's prediction error distributed? What is the prediction accuracy on infrequent vs. frequent concepts? 

GQA-OOD is a benchmark based on a fine-grained reorganization of the [GQA dataset](https://cs.stanford.edu/people/dorarad/gqa/index.html), which allows to precisely answer these questions. It introduces distributions shifts in both validation and test splits, which are defined on question groups and are thus tailored to each question.

<p align="center"><img src="images/teaser-a-v6.png" alt="drawing" width="290"/><img src="images/teaser-b-v4.png" alt="drawing" width="300"/></p>
 	
## GQA-OOD evaluation data

GQA-OOD evaluation data are provided in "*data/*". You will find three files for each split (validation and testdev). These files correspond to the "*all*", "*head*" and "*tail*" question-anwsers required to compute "*acc-all*", "*acc-head*" and "*acc-tail*".

All evaluation data files respect the GQA annotation format and can directly be used with the [GQA evaluation script](https://cs.stanford.edu/people/dorarad/gqa/evaluate.html) (of course, replace GQA's evaluation datafiles by the GQA-OOD ones). 

## Benchmark

### VQA architectures

We evaluate several VQA architectures on GQA-OOD:

| Model (trained on GQA)         | acc-all      | acc-tail     | acc-head     |
|--------------------------------|--------------|--------------|--------------|
| Quest. Prior                   | 21.6         | 17.8         | 24.1         |
| LSTM                           | 30.7         | 24.0         | 34.8         |
| BUTD [Anderson et al, CVPR 18] | 46.4 +/- 1.1 | 42.1 +/- 0.9 | 49.1 +/- 1.1 |
| MCAN [Yu et al, CVPR 19]       | 50.8 +/- 0.4 | 46.5 +/- 0.5 | 53.4 +/- 0.6 |

#### Accuracy vs. question-answer rareness (rare on the left, frequent on the right)

<img src="images/tail_plot_models.PNG" alt="drawing" width="400"/>

### VQA bias-reducing techniques

We evaluate on GQA-OOD several VQA methods designed to reduce bias dependacy:

| Technique (trained on GQA)       | acc-all      | acc-tail     | acc-head      |
|----------------------------------|--------------|--------------|---------------|
| BUTD [Anderson et al; CVPR 18]   | 46.4 +/- 1.1 | 42.1 +/- 0.9 |  49.1 +/- 1.1 |
| +RUBi+QB                         | 46.7 +/- 1.3 | 42.1 +/- 1.0 | 49.4 +/- 1.5  |
| +RUBi [Cadene et al, NeurIPS 19] | 38.8 +/- 2.4 | 35.7 +/- 2.3 | 40.8 +/- 2.7  |
| +LMH [Clark et al, EMNLP 19]     | 34.5 +/- 0.7 | 32.2 +/- 1.2 | 35.9 +/- 1.2  |
| +BP [Clark et al, EMNLP 19]      | 33.1 +/- 0.4 | 30.8 +/- 1.0 | 34.5 +/- 0.5  |

#### Accuracy vs. question-answer rareness (rare on the left, frequent on the right)

<img src="images/tail_plot_methods.PNG" alt="drawing" width="400"/>

## GQA-OOD construction code

Scripts for dataset construction from the original [GQA](https://cs.stanford.edu/people/dorarad/gqa/index.html) source is available in code/.


