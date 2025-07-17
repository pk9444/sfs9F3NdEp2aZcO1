# POTENTIAL TALENTS

## CONTEXT

The client is a talent sourcing and management company who are interested in finding talented individuals for sourcing these candidates to tech companies. They are facing three main challenges:

- To understand what the role is very well to fill in a role, this requires understanding the tech company's requirements and what they are looking for in a potential candidate.
- To understand what factors make a candidate shine for a given role that the tech company is searchinh for.
- To find those paricularly talented individuals is another key challenge.

#### CURRENT SCENARIO
- The nature of the taks required a lot of human labour and is fully of manual operations.
- Presently, the client is semi-automated, sourcing is not a concern, but finding the right candidate is the main concern.
- The client uses a keyword-based search method to find the right candidate for a given role, such as "*Full-Stack Software Engineer*" or "*Aspiring Human Resources*".

## DATA DESCRIPTION

The data comes from the client's own sourcing efforts. Any field/attritbute that could directly reveal personal details have been removed and have been assigned a unique identifier for each candidate.

### ATTRIBUTES

- **id** : unique identifier for candidate (numeric)
- **job_title** : job title for candidate (text)
- **location** : geographical location for candidate (text)
- **connections**: number of connections candidate has, 500+ means over 500 (text)

**Output (desired target)**:
- **fit** - how fit the candidate is for the role? (numeric, probability between 0-1)

**Keywords**: "*Aspiring human resources*" or "*seeking human resources*"

## PROJECT GOALS
- To predict how fit the candidate is based on the provided information (i.e. the target variable fit)
- Build a ranking based robust system, in this case an unsupervised learning approach, to rank the fitting candidates based on a fitness which is our success metric.
- Once an initial ranking is achieved, re-rank the candidates, because, for instance, the 1st candidate might not be the right fit, but the 7th might be.
- Determine a cut-off point that would work for other roles without losing high potential candidates.
- Automate the process in such a way that it prevents the human bias as much as possible.

## METHODOLOGY

<img width="1819" height="488" alt="Apziva_P3_Methodology" src="https://github.com/user-attachments/assets/ae50b6cc-c9f9-4430-9a71-83592aba61f3" />

## BUSINESS RECOMMENDATIONS

### AUTOMATED I/O PIPELINE 

The ranking algorithm can be robustly automated using the following pipeline, since the entire methodology has been made functional: 

![Apziva_P3_Automated_Pipeline.png](attachment:079c7bc4-8539-411f-bf75-0b039ac1a422.png)

**INPUT** : The client/user is required to only set three inputs:
- The CSV/JSON file in this consistent format - id, job_title, location, connection - [*Must be ensured by the client]
- Set target keywords, such as "Aspiring Human Resources", "Seeking Human Resources" - It can be updated as per requirement
- How many candidates to star? Can star only 1 or even multiple candidates

**OUTPUT** : The client will recieve a list of potential candidates based on the ranking algorithm inbuilt with dedicated functions. 

### FUTURE SCALABILITY

- The pipeline can be easily extended to other job roles by modifying the target keywords.
- The feedback mechanism and thresholding approach are role-agnostic, making the system scalable across departments.
- Since the algorithm is fully functional, it can be integrated into HR dashboards or web-based ATS systems for real-time candidate shortlisting.
