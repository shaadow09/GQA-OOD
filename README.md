# GQA-OOD (BMVC 2020 Submission)

Here is the GQA-OOD benchmark described in the paper "Roses are Red, Violets are Blue... But Should VQA expect Them To?".

## How is the VQA's prediction error distributed? What is the prediction accuracy on infrequent vs. frequent concepts? 

GQA-OOD is a benchmark based on a fine-grained reorganization of the GQA dataset (https://cs.stanford.edu/people/dorarad/gqa/index.html), which allows to precisely answer these questions. It introduces distributions shifts in both validation and test splits, which are defined on question groups and are thus tailored to each question.

## Benchmark

### VQA architectures

| Model                          | acc-all      | acc-tail     | acc-head     |
|--------------------------------|--------------|--------------|--------------|
| Quest. Prior                   | 21.6         | 17.8         | 24.1         |
| LSTM                           | 30.7         | 24.0         | 34.8         |
| BUTD [Anderson et al, CVPR 18] | 46.4 +/- 1.1 | 42.1 +/- 0.9 | 49.1 +/- 1.1 |
| MCAN [Yu et al, CVPR 19]       | 50.8 +/- 0.4 | 46.5 +/- 0.5 | 53.4 +/- 0.6 |

### VQA bias-reducing techniques

