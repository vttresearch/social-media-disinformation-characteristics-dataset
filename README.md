# Social media disinformation characteristics dataset

This dataset was collected by VTT Technical Research Centre of Finland in 2025, to study the relationship between disinformation characteristics in a text, intentionality, and the number of shares in social media. The dataset contains article URLs, number of shares of the Mastodon post where the URL was mentioned, and details about the detected disinformation characteristics.

The dataset was collected by extracting well-known news website URLs from Mastodon posts. The disinformation scores were added based on six tactics described in [^1]. The dataset is provided in csv-format, and the more detailed description can be found below.

## Dataset description

- `url`: This is the article URL appearing in the Mastodon post. The article content (text) has been processed using Disinformation LLMs (v2) by National Centre for Scientific Research Demokritos, Greece [^1].
- `publish_date`: This is the publish date of the article parsed from the article content.
- `reblogs_count`: This is the post share, the number of times the post (containing the URL) shared in Mastodon.
- `pc1`: This is the intention score based on the domain of the URL. The pc1 scores, derived from data published in [^2] [^3], were computed based on various source ratings. A higher pc1 corresponds to high-intention sources (i.e., more reliable domains), while a lower pc1 corresponds to low-intention sources, such as fake news producers. For URLs that included the term ‘substack’, the average pc1 value was used as the score.
- `C[Classifier_LLM | Signal]`: This is the maximum score (confidence value) across the article detected by the `Classifier_LLM` with `Signal` (subcategory) label. Disinformation tactics are categorized into six LLM-based classifier types [^1] (Conspiracy Theory, Trolling, Discredit, Pseudoscience, Science Denialism, Polarization), with each classifier consisting multiple signal subcategories.
- `S[Classifier_LLM | Signal]`: This is the text segment with the maximum score across the article detected by the `Classifier_LLM` with `Signal` (subcategory) label.

## License

Copyright © 2025 VTT Technological Research Centre of Finland Ltd. This dataset is licensed under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0). See `LICENSE` for more information.

## Acknowledgements

This dataset was built for Horizon Europe project TITAN (AI for Citizen Intelligent Coaching against Disinformation), which has received funding from the EU Horizon Europe research and innovation programme under grant agreement No.101070658, and by UK Research and innovation under the UK governments Horizon funding guarantee grant numbers 10040483 and 10055990.

More information on [project's website](https://www.titanthinking.eu/) and project's [EU CORDIS website](https://doi.org/10.3030/101070658).

## Contact

If you have questions regarding this dataset you can contact ville.ollikainen@vtt.fi or arttu.lamsa@vtt.fi

## Citation

If you use this dataset, please cite this repository and the following article:

```
@article{
}
```

## References

[^1]: De Vooght, E., Duelen, A., Petasis, G., Van den Broeck, W., Desimpelaere, L., Picone, I., Giacobone, G. A., Pollini, A., Katsamori, D., Bang Badum, N., Stamatellos, G., Kapetanakis, P., Paparrigopoulos, I., & Papachristou, E. (2025). Building a GenAI Socratic Chatbot for Critical Thinking: Insights From Cross-Cultural Cocreation, Living Labs and Pilots. In Modern Media Literacy: Generative AI, Social Media, and the News (pp. 353-399). IGI Global. https://doi.org/10.4018/979-8-3373-0872-2.ch012

[^2]: Lin, H., Lasser, J., Lewandowsky, S., Cole, R., Gully, A., Rand, D. G., & Pennycook, G. (2023). High level of correspondence across different news domain quality rating sets. PNAS Nexus, 2(9), 1-8. https://doi.org/10.1093/pnasnexus/pgad286

[^3]: GitHub - [hauselin/domain-quality-ratings](https://github.com/hauselin/domain-quality-ratings/tree/main): Comprehensive database of ratings for 11k news domains.
