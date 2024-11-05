# Rote Practice for LeetCode

This program is inspired by the book _Make It Stick_. I read the first few chapters of the book, and I am inspired to make a program that can track your learning progress. 

# Features
### Spaced repetition
This is the main feature of the program. This program allows you to see what is the list of programs that are due for repeated practice. You will be able to know which Leetcode question to do when you open this up.

# Getting Started
**I will write this once I have get the program to a working state.**

# Progress
There are a few tasks which I foresee that I need to do:
1. Build the schema for retrieval practice

This will be the schema for DynamoDB. I planned to build a test table using the Amazon developer console first. The second stage of this will be to have the actual DynamoDB table built using the command line command. An additional optional step is to build this in the AWS Cloud Development Kit (CDK).

2. Manually set up the Postman to pull data of past practiced questions

There seems to be a unofficial API of Leetcode. I have read it before. I will find out what do I need to query my past practice time for a particular question. I probably need a credential, and a URI with some query parameter.

3. Insert and update the data into the DynamoDB

I will pull the data for a few questions, then explore how to insert those new data into the database. Similarly as step 1, first using the developer console, then AWS CLI, and optionally in AWS CDK. These form the basis for the full fledge program.

4. Write GoLang function to pull from Leetcode website

Once I have done all the preceding steps, I have tested the technical feasibility of this feature, and I can pull all the materials together into a program, i.e a GoLang program. I deliberately choose GoLang for the program, because I am going to embed this into a AWS Lambda function. The GoLang program will query the attempted data of a question from Leetcode system and update the information in the database.

5. Automate pulling data

Once I have finished the program, the next thing is to schedule pulling the question bank information and updating the database. I might need to tweak the program to query and update a range of questions, and do this in batches. This should be done a rate limited way, so that I don't trigger any rate limiting mechanism of the Leetcode system.

6. Pull data from DynamoDB for question to practice

Once we have the data, the important thing is to retrieve the data. I will write a query on developer console to return the data, then progress to adapt it in the AWS CLI, and format it in a way that I will be able to digest it easily. If needed, I can build a simple front-end to check daily.