# Download GQA and put it in gqa/

# To get acc-all, acc-tail and acc-head
>python evaluation.py --ood_test --predictions [prediction path (on ood_testdev_all or gqa_testdev)]

# To draw acc vs. alpha plot
> python evaluation.py --eval_tail_size --predictions [prediction path (on ood_val_all or gqa_val)]

# To construct the dataset GQA-OOD
> python build_gqa_ood.py --alpha 0.2 --split val

# Requirements are available in requirement.txt
