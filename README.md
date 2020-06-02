# Predicting Perceptual Speed From Search Behaviour

Perceptual Speed (PS) is a cognitive ability that is known to affect multiple factors in Information Retrieval (IR) such as a user's search performance and subjective experience. However PS tests are difficult to administer which limits the design of user-adaptive systems that can automatically infer PS to appropriately accommodate low PS users. Consequently, this paper evaluated whether PS can be automatically classified from search behaviour using several machine learning models trained on features extracted from TREC Common Core search task logs. Our results are encouraging: given a user's interactions from one query, a Decision Tree was able to predict a user's PS as low or high with 86% accuracy. Additionally, we identified different behavioural components for specific PS tests, implying that each PS test measures different aspects of a person's cognitive ability. These findings motivate further work for how best to design search systems that can adapt to individual differences.

## Data summary

The Machine Learning Models for this paper were derived from code which has been deposited on GitHub at the following link: [Per_query_PS_classification.ipynb]().

Please note: this code reads off 3 datasets which are separate CSV files (one for each Perceptual Speed classification task: Finding A’s; Number Comparison; and Overall Perceptual Speed).

The following table explains the data in the CSV files:

| Feature name             | Feature description                                                                                                                                                                                                                                                                                                       |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Participant_number       | Unique id for each participant (38 in total)                                                                                                                                                                                                                                                                              |
| no_of_actions            | Total number of events triggered by the user during a query session (e.g., number of doc. clicked, number of doc. hovered, etc.)                                                                                                                                                                                          |
| time_query               | Time spent issuing the query (in seconds)                                                                                                                                                                                                                                                                                 |
| time_on_serp             | Total time on SERP (in seconds)                                                                                                                                                                                                                                                                                           |
| time_on_documents        | The sum of all time spent viewing articles (in seconds)                                                                                                                                                                                                                                                                   |
| time_session_overall     | Total time spent for entire search session (in seconds)                                                                                                                                                                                                                                                                   |
| serp_page_viewed_to      | The number of SERPs that were navigated to                                                                                                                                                                                                                                                                                |
| document_click_count     | Number of unique articles clicked (and thus viewed).                                                                                                                                                                                                                                                                      |
| document_click_depth     | Depth of the last result/article snippet clicked in the SERP. For example, if 5 articles were returned on a SERP, and the user clicked on article numbers 1, 2, and 4, the document_click_depth is then set to 4.                                                                                                         |
| document_hover_count_raw | The number of times a hover event occurs (a plain count from the number of hover events that took place, regardless of whether a result/article snippet was hovered over before in the SERP for a given query).                                                                                                           |
| document_hover_count     | The number of times a hover event occurs over a result snippet/article (ignoring articles that have been hovered before). For example, if you hover over article 1, then 2, then 1 again, the count is 2.                                                                                                                 |
| document_hover_depth     | Depth of the last result/article snippet hovered over in the SERP. This is the same as 'document_click_depth' but for hovers instead of clicks.                                                                                                                                                                           |
| ad_hover_count           | Overall count of how many times adverts have been hovered on. It did not compute unique ads, and therefore a count of 6 may mean 6 unique ads were hovered on, or 3 unique ads were hovered on twice each.                                                                                                                |
| ad_hover_count_top       | Number of mouse hovers over ads positioned as a banner on the top of a screen.                                                                                                                                                                                                                                            |
| ad_hover_count_side      | Number of mouse hovers over ads positioned on the right-hand side of a screen.                                                                                                                                                                                                                                            |
| ad_hover_count_bot       | Number of mouse hovers over ads positioned as a banner on the bottom of a screen.                                                                                                                                                                                                                                         |
| ad_click_count           | Number of total adverts (ads) clicked                                                                                                                                                                                                                                                                                     |
| Depth                    | This is the estimated number of items inspected. It was computed from taking the maximum figure given, whether that was from the document_click_depth or document_hover_count, unless the max was below 3, the default minimum value for depth was set to 3.                                                              |
| time_per_snippet         | Calculated from the time_on_SERP divided by depth                                                                                                                                                                                                                                                                         |
| time_per_document        | The mean time spent on articles (in seconds). It's been calculated from the time_on_documents field divided by the document_click_count.                                                                                                                                                                                  |
| query_length             | Length of query                                                                                                                                                                                                                                                                                                           |
| query_tokens_count       | Number of words per query                                                                                                                                                                                                                                                                                                 |
| FA_binary                | Categorised based on median split of results from Finding A's Perceptual Speed (PS) Test.     0: Low PS     1: High PS                                                                                                                                                                                                    |
| NC_binary                | Categorised based on median split of results from Number Comparison Perceptual Speed (PS) Test.     0: Low PS     1: High PS                                                                                                                                                                                              |
| overall_PS               | To derive an overall Perceptual Speed (PS) measure, a participant who scored low in both FA and NC received an overall low score;   high in both FA and NC received an overall high score; and if one test were   high and the other low, received a medium classification.     0: Low PS     1: Medium PS     2: High PS |

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

## Ethical Approval

The user study that generated the search logs was approved by the University of Strathclyde Computer and Information Sciences Departmental Ethics Committee (Application ID: 1044). 

## Acknowledgments

This work was part funded by BAE Systems Maritime and EPSRC as part of an Industrial Cooperative Award in Science & Technology (CASE) Studentship (EP/S513908/1).