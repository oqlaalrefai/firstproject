## How to use Random Module
The random module provides access to functions that support many operations
- Random functions
  - Randint : If we wanted a random integer
  - random: If you want a larger number, you can multiply it.
  - Choice : generate a random value from the sequence sequence.
  - Shuffle :The shuffle function, shuffles the elements in list in place, so they are in a random order.
  - Randrange : Generate a randomly selected element from range(start, stop, step)

## What is Risk Analysis
risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test.
The probability of any unwanted incident is defined as Risk

- Why use Risk Analysis?
using risk analysis at the beginning of a project highlights the potential problem areas
- the possible risks that you could encounter :
  - Use of new hardware
  - Use of new technology
  - Use of new automation tool
  - The sequence of code
  - Availability of test resources for the application
-  risks that are unavoidable:
  - The time that you allocated for testing
  - A defect leakage due to the complexity or size of the application
  - Urgency from the clients to deliver the project
  - Incomplete requirements
-  tackle the situation with care :
  - Conduct Risk Assessment review meetingPremature Release Risk: a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required
  - Use maximum resources to work on high-risk areas
  - Create a Risk Assessment database for future use
  - Identify and notice the risk magnitude indicators: high, medium, low.
- risk magnitude indicators:
  - **High**: means the effect of the risk would be very high and non-tolerable
  - **Medium**: it is tolerable but not desirable
  - **Low**: it is tolerable.
- Risk Identification Process :
  - Business Risks : may come from your company or your customer, not from your project. its the most common
  - Testing Risks : You should be well acquainted with the platform you are working on, along with the software testing tools being used.
  - Premature Release Risk: a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required
  - Software Risks: You should be well versed with the risks associated with the software development process.
- There are three perspectives of Risk Assessment:
  - Effect : To assess risk by Effect
  - Cause : To assess risk by Cause is opposite of by Effect.
  - Likelihood : To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.
- How to perform Risk Analysis?
  - Searching the risk
  - Analyzing the impact of each individual risk
  - Measures for the risk identified
## TestCoverage
- called code coverage
- you can't go into production with less than 87% coverage
- you should use things like TDD and must get 100% coverage.
- TDD is a very useful, but certainly not sufficient, tool to help you get good tests.
- Certainly low coverage numbers, say below half, are a sign of trouble. But high numbers don't necessarily mean much, and lead to ignorance-promoting dashboards.
-  you are doing enough testing if the following is true:
  - You rarely get bugs that escape into production, and
  - You are rarely hesitant to change some code for fear it will cause production bugs.
- One sign you are testing too much is if your tests are slowing you down.
- It's worth running coverage tools every so often and looking at these bits of untested code. 








