# ASSIGNMENT: Sampling and Reproducibility in Python


# Author: Tagimasa

1. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post  

We have the following main sampling stages:

   s1- attendance sampling
   s2- infection sampling
   s3- prim. tracing sampling
   s4- sec. tracing

s1 - The sample size is 1,000 individuals attending one of the events - wedding or brunch. The sampling frame - 800 individuals are assigned to the brunch, 200 individuals are assigned to the wedding.
s2 - The model define Infection probability as 10% - np.random.choice(). It is binomial distribution – yes/no (infected or not inf.). 
s3 - The model defines the success rate for tracing infected people is 20% - TRACE_SUCCESS (0.2). 
s4 - Then secondary tracing (SECONDARY_TRACE_THRESHOLD = 2) applied to the events that have 2 traced cases. So, 
That is what mentioned in the blog, that contact tracing lead to higher presentation of large events – for example weddings, and that creates disproportion in the results and further analysis- the chart represents true and observed proportion of infections resulted from the weddings.

2. Does this code appear to reproduce the graphs from the original blog post? 

Not the same but very similar – please see attached .png files with graphs from the blog post and Python script file whitby_covid_tracing.py run 50000 and 1000 number of repetitions. 
The difference in the histogramms: The peak of Proportion of cases is around 0,2 but with decreasing number of iterations from 50.000 to 1.000 the weight of cases moves from 0,15 to 0,25, i.e. in case of 50.000 iterations high weight of 0,15 while in case of 1.000 iterations weight is high in 0,25. 

3. Modify the number of repetitions in the simulation to 1000 (from the original 50000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results 

The peak of Proportion of cases is around 0,2 but with decreasing number of repetitions from 50 to 1k the weight of cases moves from 0,15 to 0,25

4. Describe the changes you made to the code and how they affected the reproducibility of the script file 

I used randome seed - np.random.seed(42) to ensure the simulation is reproducible.

Please see the charts
![chart from the blog](https://github.com/Tagimasa/sampling/blob/task-1/02_activities/assignments/chart%20from%20the%20blog.png)
![50000  rep chart](https://github.com/Tagimasa/sampling/blob/task-1/02_activities/assignments/chart%20_50000%20_rep.png)
![1000  rep chart](https://github.com/Tagimasa/sampling/blob/task-1/02_activities/assignments/chart_1000%20_rep.png)

```

## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `HH:MM AM/PM - DD/MM/YYYY`
* The branch name for your repo should be: `sampling-and-reproducibility`
* What to submit for this assignment:
    * This markdown file (sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `sampling-and-reproducibility`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
