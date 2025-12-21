# Amazon Lex – Interactive Quiz Chatbot on AWS

## Project Overview
This project focuses on building an interactive chatbot using Amazon Lex.
The chatbot is designed to improve learner engagement by transforming
passive learning into an interactive knowledge-check experience.

The solution demonstrates how conversational AI can be used to reinforce
AWS concepts through quiz-based interactions and immediate feedback.

---

## Problem Statement
Learners often struggle to understand AWS concepts due to:
- Passive learning methods
- Lack of real-time interaction
- Poor knowledge retention

This project addresses these challenges by introducing an interactive
quiz chatbot that encourages active participation.

---

## Project Mission
The goal of this project is to:
- Create an interactive quiz chatbot
- Help learners test their AWS knowledge
- Use simple language and clear feedback
- Improve learning engagement through conversation

---

## Why Amazon Lex
Amazon Lex was selected because it:
- Is purpose-built for chatbots
- Understands natural language inputs
- Makes it easy to build, test, and deploy conversational flows
- Integrates well within the AWS ecosystem

---

## Client Scenario
A fictional educational startup requires:
- An educational quiz chatbot
- Multiple-choice questions
- Feedback for both correct and incorrect answers
- A simple and engaging user experience

---

## Solution Overview
The solution is a quiz-based chatbot built with Amazon Lex that:
- Starts quizzes using simple commands
- Guides users through questions step-by-step
- Evaluates user responses using branching logic
- Provides immediate feedback
- Allows users to continue or exit gracefully

---

## Technical Approach

### Core Components
- **Bot**: Amazon Lex (English – ZA)
- **Intents**: Handle user goals
- **Utterances**: Capture user input
- **Responses**: Deliver information and quiz questions
- **Branching Logic**: Control conversation flow

### Key Intents
- `S3Info` – Provides basic information about Amazon S3
- `S3Quiz` – Initiates and manages the quiz interaction

---

## Quiz Flow Design
1. User starts the quiz with a trigger phrase
2. Bot asks a multiple-choice question
3. User selects an option (A / B / C)
4. Bot evaluates the response
5. Correct or incorrect feedback is provided
6. User is prompted to continue or end the quiz

---

## Challenges Faced
- Understanding Amazon Lex structure
- Handling multiple user inputs correctly
- Managing branching without breaking the flow
- Testing all possible conversation paths

---

## How Challenges Were Solved
- Simplified the bot design
- Built and tested one question at a time
- Collaborated and debugged as a team
- Used consistent response patterns

---

## Testing & Validation
- Tested all utterances in the Amazon Lex test console
- Verified correct intent detection
- Confirmed correct and incorrect answer handling
- Ensured smooth quiz progression and exits

---

## What We Learned
- How Amazon Lex works internally
- How to design conversational flows
- How to apply branching logic effectively
- Team collaboration and problem-solving skills

---

## Future Enhancements
- Add 10+ quiz questions (encryption, versioning, replication)
- Introduce voice interaction
- Integrate with an LMS for score tracking
- Add session memory for progress persistence

---

## Live Demonstration
The chatbot was demonstrated live by:
- Running it in the Amazon Lex console
- Showing correct and incorrect responses
- Explaining the quiz logic and flow

---

## Contributors
Group project completed as part of hands-on AWS learning.

---

## Status
Project completed and validated.
