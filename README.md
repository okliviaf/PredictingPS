# Predicting Perceptual Speed From Search Behaviour

Perceptual Speed (PS) is a cognitive ability that is known to affect multiple factors in Information Retrieval (IR) such as a user's search performance and subjective experience. However PS tests are difficult to administer which limits the design of user-adaptive systems that can automatically infer PS to appropriately accommodate low PS users. Consequently, this paper evaluated whether PS can be automatically classified from search behaviour using several machine learning models trained on features extracted from TREC Common Core search task logs. Our results are encouraging: given a user's interactions from one query, a Decision Tree was able to predict a user's PS as low or high with 86% accuracy. Additionally, we identified different behavioural components for specific PS tests, implying that each PS test measures different aspects of a person's cognitive ability. These findings motivate further work for how best to design search systems that can adapt to individual differences.

## Data format

To be released.

## Code

In order to ease reproducibility, we release the code that we use to run the models reported in our paper
in a dedicated Google Colab notebook. The link will be release as soon as possible on this webpage.

## Citation

```
@inproceedings{foulds2020sigir,
  title={Predicting Perceptual Speed From Search Behaviour},
  author={Foulds, Olivia, Suglia, Alessandro, Azzopardi, Leif and Halvey, Martin},
  booktitle={Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval (SIGIR ’20), July 25–30, 2020, Virtual Event, China. ACM,New York, NY, USA},
  doi={https://doi.org/10.1145/3397271.3401210},
  year={2020}
}
```

## Authors

- Olivia Foulds (olivia.foulds@strath.ac.uk)
- Alessandro Suglia (as247@hw.ac.uk)
- Leif Azzopardi (leifos@acm.org)
- Martin Halvey (martin.halvey@strath.ac.uk)