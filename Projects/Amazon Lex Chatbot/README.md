# AWS Lex Interactive Chatbot Project

## Project Overview
This project demonstrates the design and implementation of an interactive chatbot using
Amazon Lex. The chatbot supports intent-based conversations and an educational quiz
flow using branching logic.

The solution was built to showcase practical understanding of conversational AI concepts,
user interaction design, and AWS-managed AI services.

---

## Objectives
- Design and deploy an Amazon Lex chatbot
- Implement intent-driven conversation flows
- Build a quiz-based interaction using conditional branching
- Test and validate chatbot responses
- Demonstrate the solution through a live interaction flow

---

## Technology Stack
- AWS Management Console
- Amazon Lex (V2)
- Natural Language Processing (NLP)
- Intent & Utterance Modeling
- Conditional Branching Logic

---

## Architecture Summary
- Single Lex Bot
- Multiple Intents
- Defined Utterances per Intent
- Static Responses with Conditional Flow Control
- Test Console for validation

---

## Part 1: Basic Chatbot Implementation

### Bot Configuration
- Language: English (ZA)
- Advanced Configuration: None
- Deployment Type: Test console

### Intent Design
Intent Name:
- `S3Info`

Utterance Example:
- "What is S3?"

Response Logic:
- Static informational response returned when intent is matched

Outcome:
- Successfully deployed a functional chatbot
- Verified correct intent recognition
- Confirmed accurate response delivery

---

## Part 2: Knowledge Quiz Chatbot (Challenge)

### Scenario
The chatbot simulates an educational assistant for a fictional client,
delivering a knowledge-check quiz on AWS services.

### Quiz Intent
Intent Name:
- `S3Quiz`

Trigger Utterances:
- "Start quiz"
- "Quiz me on S3"
- "I’m ready for the quiz"

### Quiz Flow Design
- Multiple-choice questions
- User input evaluated through branching logic
- Separate responses for correct and incorrect answers
- Option to continue or exit the quiz

Example Question Flow:
- Question prompt
- User selection (A / B / C)
- Conditional evaluation
- Feedback response
- Follow-up prompt

---

## Branching Logic
- Correct answers trigger positive feedback and continuation prompt
- Incorrect answers provide correction and retry/continue option
- Flow ensures user is never stuck in a dead-end conversation

---

## Testing & Validation
- Tested all utterances via Lex test console
- Verified correct intent resolution
- Validated branching for all answer paths
- Confirmed smooth conversation exit handling

---

## Challenges Encountered
- Managing intent slot limits
- Designing clean branching without exceeding constraints
- Avoiding conversation loops
- Ensuring consistent user experience across paths

---

## Key Learnings
- Intent design must remain focused and minimal
- Branching logic should be planned before implementation
- Simpler conversation flows outperform complex designs
- Testing early prevents architectural rework

---

## Outcome
The final chatbot delivers:
- A stable intent-based response system
- An interactive educational quiz
- Clear user guidance and feedback
- A professional, demo-ready solution

---

## Next Improvements
- Integrate Lambda for dynamic responses
- Add session memory for scoring
- Expand quiz topic coverage
- Connect chatbot to a web interface

---

## Author
Project completed as part of AWS hands-on learning and practical cloud development.
