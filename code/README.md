## Constructing GQA-OOD dataset

We provide the code necessary for constructing the GQA-OOD dataset. 

### 1) Download [GQA's original questions](https://cs.stanford.edu/people/dorarad/gqa/download.html) and put them in gqa/

In the paper, we use the version 1.2 of the dataset.

### 2) Construct the GQA-OOD dataset

To extract questions used for evaluating with the GQA-OOD benchmark, launch:

> python build_gqa_ood.py --alpha 0.2 --split val

## Evaluating on GQA-OOD

We also provide some scripts to evaluate your model's predictions on GQA-OOD. The predictions must respect the standard GQA format.

### Measuring acc-all, acc-tail and acc-head
To obtain the three metrics described in the paper, launch:
> python evaluation.py --ood_test --predictions [prediction path (on ood_testdev_all or gqa_testdev)]
Those are measured on the testdev split of GQA-OOD.

### Drawing acc vs. alpha plot
To draw analyse the influence of alpha against the model accuracy, launch:
> python evaluation.py --eval_tail_size --predictions [prediction path (on ood_val_all or gqa_val)]
This analyse is performed on the validation split of GQA-OOD. A plot will be saved in plot/.

#### Please, find the python requirements in requirement.txt
