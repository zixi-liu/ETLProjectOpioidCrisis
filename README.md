# ETL Project - 2020 Opioid Data Hackathon

## What is the scope of prescription drug misuse

Misuse of prescription opioids, CNS depressants, and stimulants is a serious public health problem in the United States. According to NIH studies, the reasons for the high prevalence of [prescription drug misuse](https://www.drugabuse.gov/publications/research-reports/misuse-prescription-drugs/what-scope-prescription-drug-misuse) vary by age, gender, and other factors, but likely include ease of access. The number of prescriptions for some of these medications has increased dramatically since the early 1990s. Moreover, misinformation about the addictive properties of prescription opioids and the perception that prescription drugs are less harmful than illicit drugs are other possible contributors to the problem. Although misuse of prescription drugs affects many Americans, certain populations such as youth and older adults may be at particular risk.

## Partner Organizations

- [Prevention Point](http://www.ppponline.org) works to improve access to and quality of health and human services for underserved and vulnerable populations
- [Health Federation of Philadelphia](http://www.healthfederation.org) works to improve access to and quality of health and human services for underserved and vulnerable populations
- City of Philadelphia

## Data

Prescription drug monitoring programs (PDMPs), state-run electronic databases used to track the prescribing and dispensing of controlled prescription drugs to patients, are important tools for preventing and identifying prescription drug misuse.

### Prevention Point

#### Naloxone refill_events
In many states, individuals must receive a prescription to carry overdose reversal drugs like Narcan (Naloxone). In 2014, Pennsylvania passed legislation allowing any citizen who could be in the position to administer overdose reversal drugs to receive, carry, and administer such drugs. Prevention Point, among other locations, trains and hands out refills for Narcan (Naloxone).  Narcan is an overdose reversal drug administered either intravenously or intranalasally. 

Individuals receiving training or refills through Prevention Point are required to fill out a questionnaire about their experiences with overdoses and related demographic information.

- psp_overdose_events.csv: Information on overdose responses and naloxone administrations.
- pp_refill_events.csv: Information collected at time of naloxone refills of Naloxone at PP.

## Research Questions

It's very important that we look at the recovery process with regards to building understanding in the general public. We want to know whether prescribing/refilling Narcan could help the patient to survived or not.

Here are things we want to look at when we load data:

We have all naloxone refills of Naloxone at PP and all overdose responses and naloxone administrations in Philadelphia in 2018. We want to build a scheme that contains the number and amount of naloxone refills each month and the survival rate and rate of naloxone administered for overdose incidents each month.

## Transform

In order to transform the overdose responses and naloxone refills of Naloxone data and use it in our study we performed the following:

- Performed data cleaning on overdose responses and naloxone refills of Naloxone data (i.e removing missing data and outliers). 
- Summarized total number of naloxone refills received at PP and total amount of naloxone used by participant by month for year 2018.
- Summarized survival rate and rate of Naloxone Administered for overdose incidents at PP by month for year 2018.
- Conducted a merge on incident months and refill months to create a dataframe.


## Load

We transfered the final dataframe into a Database. We created a database named OpioidData and a table to match the columns from the final dataframe using MySQL server connector to store our clean dataset. We will reconnect to the database and generate additional tables for the data frames.
