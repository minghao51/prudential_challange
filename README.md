

# AI Use Cases
2. Implement a product recommendation model for either cross or upselling from customer behavious

The implementations can be found in the notebooks, with the Input and Output resides in the data folder. All these are commited into the Git Repo.

# Notebooks

## 1. **L0_DataScope.ipnyb**
**Hybrid Data Generation**
1. Rules and stats based generation
    - Single wide table with Customer/policies/payment etc
2. DataLLM - MostlyAI augmentation
    - Augmentation with pormpts
    - Required API KEY
        - Acquire from [website](https://data.mostly.ai/docs/routes#authentication), and save it to .env
3. Manually Clean Up
    - Date casting
    - Issue/Termination Date
    - Fraction(termination Date) to None

## 2. **L1_DataGeneration.ipnyb**
**Generating cross-sell & upsell data with SVD**
- Select customers of certain profile - high value (premium/income) / dependences/ recency, and use rules to set them to purchase additional policies
- To maintain consistent customer profile, after synthesizing the data, we would substitute the customer profile and sizing.
    1. GaussianCopulaSynthesizer
    2. Constraint
    3. Conditional Generation
    4. Additional into Tables
- Aim to get like 20% of the customers with either upsell/xsell

## 3. **L2_MLApproach.ipnyb**
**## **ML-based Appraoch**
- Feature Eng 
    - Event Base Feature Engineering
    - Capture only Cross-sell/Upsell Policy Purchase Events
        - Single Purchase events are discarded in this modelling, although it is possible to make use of them to extracts demography favourable for certain policies at times.
- ML Training
    - Premodel processing
        - Casting/Train Val Seperation
    - LightGBM Model

## 4. **L3_Validation.ipnyb**
**Evaluate the models**
    - Performance metrics
        - WandB Logging - Metrics, Artifacts (Table, Model.pkl, plots)
        - Multi-Classification Metrics Logging
    - AI ethics
        - FairLearn


# Enviroment
`mamba create -n env_name packages_in_env.yml -c channels_in_env.yml`

# Libraries Used
- python=3.12
- SDV
- datallm
- pandas
- numpy
- polars
- seaborn
- scikit-learn
- lightgbm
- fairlearn


