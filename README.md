

# AI Use Cases
> 2. Implement a product recommendation model for either cross or upselling from customer behavious

- The implementations details fo the various steps can be found in the notebooks
- The Input and Output resides in the data folder

# Enviroment

Ideally, with conda/mamba, via local environment

`mamba env create -n py312syndata --file env.yml`

Whereby, all the notebooks will be executed using the created environment.
Alternatively, you can create an environment with the relevant libaries as well (refer to the libraries section, or use notebook kernel + pip install)

# Notebooks

## 1. **L0_DataScope.ipnyb**
**Hybrid Data Generation**
1. Rules and stats-based generation
    - Single wide table with Customer/policies/payment etc
2. DataLLM - MostlyAI augmentation
    - Augmentation with prompts
    - Required API KEY, [MostlyAI](https://data.mostly.ai/docs/routes#authentication), and save it to .env as
3. Manually Clean Up
    - Date casting
    - Issue/Termination Date
    - Fraction(termination Date) to None

## 2. **L1_DataGeneration.ipnyb**
**Generating cross-sell & upsell data with SVD**
- Select customers of certain profiles - high value (premium/income) / dependencies/ recency, and use rules/assumptions to appoint them to purchase additional policies
    1. GaussianCopulaSynthesizer
    2. Constraint
    3. Conditional Generation
    4. Additional into Tables
- Aim to get like 20% of the customers with either upsell/sell

## 3. **L2_MLApproach.ipnyb**
**ML-based Approach**
- Feature Eng
    - Event Base Feature Engineering
    - Capture only Cross-sell/Upsell Policy Purchase Events
        - Single Purchase events are discarded in this modeling, although it is possible to make use of them to extract demography favorable for certain policies at times.
- ML Training
        - Premodel processing
        - Casting/Train Val Separation
    - LightGBM Model
        - Required API KEY for [wandb](https://wandb.ai/home), although, the relevant codes can be disabled as it is just there for logging purpose
        - However, since wandb logging is embeded within the logics, it is best to grab/register an account and insert the API key via the jupyter interface

## 4. **L3_Validation.ipnyb**
**Evaluate the models**
- Performance metrics
    - WandB Logging - Metrics, Artifacts (Table, Model.pkl, plots)
    - Multi-Classification Metrics Logging
    - SHAP for the encoded class to investigate the customer purchase behavior
- AI ethics
    - FairLearn



# Libraries Used
- python=3.12
- SDV
- datallm (pip install)
- pandas
- numpy
- polars
- seaborn
- scikit-learn
- lightgbm
- fairlearn


# .env file
The API keys necessary for accessing DataLLM and Weights & Biases (wandb) are, by default, retrieved from a .env file, which is not committed to the version control system and requires manual creation. The .env file follows a specific format, which is

```
DataLLM=<your_api_key_here>
WANDB=<your_api_key_here>
```

# Clean up/Uninstall Env
Once you are done, the environment can be removed via 
`mamba env remove -n py312syndata`