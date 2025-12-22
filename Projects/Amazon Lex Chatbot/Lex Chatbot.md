# Amazon Lex Interactive Quiz Chatbot (AWS)

## Project Overview
This project demonstrates the design and implementation of an interactive
educational chatbot using Amazon Lex (V2). The chatbot delivers a structured,
quiz-based learning experience that helps learners actively test their
understanding of AWS concepts through conversational interaction rather than
passive study.

The project focuses on conversational flow design, conditional branching,
and user experience using the Amazon Lex Visual Builder.

---

## Problem Statement
Learners often struggle to understand AWS concepts because:
- Traditional learning methods are passive
- There is limited real-time interaction
- Information is forgotten quickly

This project addresses these challenges by introducing an interactive
quiz chatbot that encourages active participation and provides immediate
feedback.

---

## Project Objectives
- Build a functional chatbot using Amazon Lex
- Design intent-driven conversations
- Implement conditional branching logic
- Handle correct and incorrect user responses
- Ensure a clean and predictable conversation flow
- Deliver a demo-ready chatbot without external dependencies

---

## Why Amazon Lex
Amazon Lex was selected because it:
- Is purpose-built for conversational chatbots
- Uses Natural Language Processing (NLP)
- Supports intents, utterances, and conditional branching
- Allows fast testing through the AWS console
- Integrates seamlessly within the AWS ecosystem

---

## Solution Overview
The solution is an interactive quiz chatbot that:
- Welcomes the user
- Asks whether the user wants to start the quiz
- Presents multiple-choice questions
- Evaluates responses using conditional logic
- Provides feedback for correct and incorrect answers
- Allows the user to continue or exit the quiz cleanly

---

## Bot Configuration
- Platform: Amazon Lex V2
- Language: English (ZA)
- Voice: Disabled
- Backend: Amazon Lex only (no Lambda integration)
- Design Approach: Stateless and deterministic

---

## Conversation Flow
High-level conversation flow:
Welcome → Start Quiz?
→ Question → Answer Check
→ Feedback → Continue?
→ Next Question / End


The chatbot is designed using message nodes and condition nodes in the
Amazon Lex Visual Builder.

---

## Intents Used
- S3Info  
  Provides basic information about Amazon S3.

- S3Quiz  
  Controls the quiz flow, question delivery, and branching logic.

---

## Conditional Branching Logic
Conditional branching is used to:
- Separate correct and incorrect answers
- Control quiz progression
- Validate user input (A, B, C / YES, NO)
- Prevent infinite loops and dead-end conversations

### Conditional Branching Screenshots
![Conditional Branching – Branch 1](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/Amazon%20Lex%20Chatbot/images/conditional%20branching.%20branch%201.PNG?raw=true)

![Conditional Branching – Branch 2](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/Amazon%20Lex%20Chatbot/images/conditional%20branch%202.PNG?raw=true)

---

## Slot Configuration
Slots were explored and tested during development but intentionally kept
minimal in the final implementation to avoid:
- Slot exhaustion
- Complex state management
- Unnecessary validation overhead

![Slots Configuration](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/Amazon%20Lex%20Chatbot/images/slots.PNG?raw=true)

---

## Quiz Flow Example
Example quiz question format:
Question:
What does Amazon S3 stand for?

- A Simple Storage Service
- B Secure Server Storage
- C Smart Storage System

  

Answer handling:
- A → Correct feedback
- B or C → Incorrect feedback
- Any other input → Retry prompt

---

## Testing and Validation
- All utterances were tested using the Amazon Lex test console
- Intent recognition accuracy was verified
- Correct, incorrect, and invalid inputs were tested
- All conditional branches were validated
- Clean exit paths were confirmed
- No infinite loops were observed

---

## Challenges Encountered
- Understanding the Amazon Lex Visual Builder structure
- Managing branching limits
- Handling different user inputs consistently
- Designing a clear YES/NO decision flow

---

## Solutions Applied
- Simplified the overall bot design
- Used explicit condition nodes instead of complex slots
- Tested one branch at a time
- Followed consistent naming conventions
- Avoided unnecessary session attributes

---

## Key Learnings
- Conversational design is more important than complexity
- Clear branching improves user experience
- Simple bots are easier to test and explain
- Amazon Lex works best with focused, well-defined intents
- Planning the flow before building saves time

---

## Future Enhancements
- Add more quiz questions (encryption, versioning, replication)
- Introduce voice interaction
- Integrate AWS Lambda for scoring logic
- Connect the chatbot to an LMS for progress tracking

---

## Project Status
Completed, tested, and ready for review.
