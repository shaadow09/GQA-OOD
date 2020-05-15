# GQA-OOD (BMVC 2020 Submission)

Here is the GQA-OOD benchmark described in the paper "Roses are Red, Violets are Blue... But Should VQA expect Them To?".

## How is the VQA's prediction error distributed? What is the prediction accuracy on infrequent vs. frequent concepts? 

GQA-OOD is a benchmark based on a fine-grained reorganization of the GQA dataset (https://cs.stanford.edu/people/dorarad/gqa/index.html), which allows to precisely answer these questions. It introduces distributions shifts in both validation and test splits, which are defined on question groups and are thus tailored to each question.
