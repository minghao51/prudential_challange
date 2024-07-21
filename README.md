

# Conda env creation
`conda create -n py311syndata python=3.11 numpy pandas polars seaborn jupyterlab ipykernel`

# Syn Data Creation
1. SDV - Synthetic Data Vault

Seems to be using alrogithms to learn patterns from real data, which is not available in this case.

Although, its ability to setup mutliple data wiht Entity Relationship seem interesting, although one would have to likely encoded the statistical relationship that we are looking for within.

`conda install -c pytorch -c conda-forge sdv`

2. Mostly.AI

Synthetic data via real data. Althrough through DataLLM we could also create it from 0 via prompts

`pip install -U datallm`

3. [Gretel.AI](https://console.gretel.ai/dashboard)

Its Interface for prompt engineeing a synthetic data is used to use compare with that of Mostly.AI, there isn't any means for calling them via code, and that asking it to generate over 1K records seems to just cause it be unresponsive.

# Other Potential Sources for real data (non prioritory)
3. Kaggle
Seems to be quite limited in quality and range.



# Conclusion on data synthesis
Hence, it look slike perhaps it would be better if I use prompt (via MostlyAI -DataLLM or Gretel, or other LLM) to generate some synthetic data. Then encode some statistical asusmptions business/I had come across instead the datasets.

