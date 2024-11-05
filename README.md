# LeetCode Spaced Repetition Practice System

## Overview

This project aims to develop a spaced repetition system for LeetCode practice, inspired by the cognitive science principles outlined in the book "Make It Stick". The system is designed to optimize learning and retention of coding skills by scheduling practice sessions based on individual performance and forgetting curves.

## System Architecture

### Data Storage
- **Primary Database**: Amazon DynamoDB

### Backend Services
- **Language**: GoLang
- **Deployment**: AWS Lambda functions
- **API Integration**: Unofficial LeetCode API for practice data retrieval

### Frontend (Optional)
- Lightweight interface for daily practice recommendations

## Key Features

1. **Spaced Repetition Algorithm**: Core functionality to determine optimal practice intervals
2. **Automated Data Collection**: Regular updates of user practice data from LeetCode
3. **Personalized Practice Recommendations**: Daily suggestions based on user history and performance
4. **Progress Tracking**: Visualization of long-term learning progress

## Development Roadmap

### Phase 1: Data Model and Storage
1. Design and implement DynamoDB schema
   - Initial setup via AWS Management Console
   - Migration to AWS CLI for reproducibility
   - (Optional) Implementation using AWS CDK for infrastructure as code

2. Develop data insertion and update mechanisms
   - Console-based testing
   - CLI implementation

### Phase 2: Data Retrieval and Processing
1. Set up Postman collection for LeetCode API testing
   - Identify required endpoints and authentication methods
   - Create and test API queries for practice history

2. Develop GoLang functions for data retrieval
   - Implement API calls to LeetCode
   - Process and transform retrieved data
   - Integrate with DynamoDB for storage

### Phase 3: Automation and Scheduling
1. Implement batch processing for efficient data updates
2. Design and deploy rate-limiting mechanism to prevent API abuse
3. Set up AWS CloudWatch events for scheduled data pulls

### Phase 4: Retrieval and Presentation
1. Develop DynamoDB queries for practice recommendations
   - Console-based testing
   - CLI implementation for data extraction
2. Design data presentation format for easy consumption
3. (Optional) Develop simple frontend for daily practice suggestions

## Getting Started

(To be completed upon reaching a functional prototype stage)