# 1. Exploratory data analysis

## Objective:
- Understand our data as well as possible (a small step forward is better than a big step back)
- Develop an initial modeling strategy 

## Basic checklist
#### Shape analysis :
- target variable**: SARS-Cov-2 exam result
- rows and columns**: 5644, 111
- types of variables**: qualitative: 70, quantitative: 41
- Missing values analysis** :
    - many NaN (half of the variables > 90% NaN)
    - 2 groups of data 76% -> viral test, 89% -> blood levels

#### Background analysis:
- **Target visualization**:
    - 10% positive (558 / 5000)
    
    
    
- Significance of variables**:
    - standardized continuous variables, skewed, blood test
    - age quantile : difficult to interpret this graph, clearly these data have been processed, we could think 0-5, but it could also be a mathematical transformation. We can't know because the person who put this dataset does not specify it anywhere. But it is not very important
    - qualitative variable : binary (0, 1), viral, Rhinovirus which seems very high



- Relation Variables / Target** :
    - target / blood : Monocytes, Platelets, Leukocytes levels seem to be related to covid-19 -> hypothesis to be tested
    - target/age : low age individuals are very little contaminated ? -> be careful, we don't know the age, and we don't know when the dataset dates (if it is about children, we know that children are affected as much as adults). On the other hand, this variable could be interesting to compare with the results of blood tests
    - target / viral : double diseases are very rare. Rhinovirus/Enterovirus positive - covid-19 negative ? -> hypothesis to be tested ? but it is possible that the region is undergoing an epidemic of this virus. Moreover, one can very well have 2 viruses at the same time. All this has no link with covid-19
    
    
    
## More detailed analysis

- Relationship Variables / Variables** :
    - blood_data / blood_data : some variables are very correlated : +0.9 (to be checked later)
    - blood_data / age : very low correlation between age and blood levels
    - viral / viral : influenza rapid test gives bad results, maybe we should drop it
    - relation disease / blood data : blood levels between sick and covid-19 are different
    - relation hospitalization / is sick : 
    - relation hospitalization / blood : interesting in case we want to predict in which department a patient should go


- NaN analysis** : viral : 1350(92/8), blood : 600(87/13), both : 90

### null hypotheses (H0): 

- Individuals with covid-19 have significantly different levels of Leukocytes, Monocytes, Platelets
    - H0 = Mean levels are EQUAL in positive and negative individuals

- Individuals with any disease have significantly different levels
