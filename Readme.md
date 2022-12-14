### 11785 - Visual Parameter Efficient Tuning for Semi-Supervised Image Classification
This repository contains the code we have both borrowed and implemented for our project on Visual Parameter Efficient Tuning for Semi-Supervised Image Classification. In this study, we test the effectiveness of parameter efficient tuning for semi-supervised image classification on the CIFAR-100 dataset.
This repository has been forked from https://github.com/microsoft/Semi-supervised-learning. The original repository has implemented several semi-supervised learning algorithms and has also implemented several archtectures that can be trained using these algorithms.
We have implemented two variants of prompt tuning for the Vision Transformer as described in the paper - [Visual Prompt Tuning](https://arxiv.org/abs/2203.12119). These are the shallow and deep prompting techniques. Much of the implementation for prompting has been borrowed from the repository that implements this paper - https://github.com/KMnP/vpt

The code that incorporates prompting into the vision transformer can be found at - 
* Shallow Prompting - ```Semi-supervised-learning/semilearn/nets/vit_prompt/```
* Deep Prompting - ```Semi-supervised-learning/semilearn/nets/vit_prompt_deep/```

The corresonding configurations to train these networks with semi-supervised learning algorithms can be found at - 
* FixMatch
  * Shallow Prompting - ```Semi-supervised-learning/config/usb_cv/fixmatch/fixmatch_cifar100_200_prompt.yaml```
  * Deep Prompting - ```Semi-supervised-learning/config/usb_cv/fixmatch/fixmatch_cifar100_200_deep_prompt.yaml```
* AdaMatch 
  * Shallow Prompting - ```Semi-supervised-learning/config/usb_cv/adamatch/adamatch_cifar100_200_prompt.yaml```
  * Deep Prompting - ```Semi-supervised-learning/config/usb_cv/adamatch/adamatch_cifar100_200_deep_prompt.yaml```
* RemixMath
  * Shallow Prompting - ```Semi-supervised-learning/config/usb_cv/remixmatch/remixmatch_cifar100_200_prompt.yaml```
  * Deep Prompting - ```Semi-supervised-learning/config/usb_cv/remixmatch/remixmatch_cifar100_200_deep_prompt.yaml```

In order to train a vision transformer with prompting simply run - 
``` python train.py --c <path_to_config_file>```

In order to change the dataset or any experiment hyperparameters, simply edit the corresponding configuration file.

