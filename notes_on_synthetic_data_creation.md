# L0 Syn Data Creation
1. SDV - Synthetic Data Vault

Seems to be using alrogithms to learn patterns from real data, which is not available in this case.

Although, its ability to setup mutliple data wiht Entity Relationship seem interesting, although one would have to likely encoded the statistical relationship that we are looking for within.

`conda install -c pytorch -c conda-forge sdv`

2. Mostly.AI

Synthetic data via real data. Althrough through DataLLM we could also create it from 0 via prompts

`pip install -U datallm`

Require API key, which can be acquired from [website](https://data.mostly.ai/docs/routes#authentication)
Please also save it on the 

# Other Potential Sources for real data
3. Kaggle
Seems to be quite limited in quality and range.



# Conclusion on data synthesis
Hybrid Approach + prompt (via MostlyAI -DataLLM or Gretel, or other LLM) to generate some synthetic data. This can then be followed by using SDV to encode some statistical assumptions business.
