# Sprint Challenge: Authentication - Dad Jokes

This challenge allows you to practice the concepts and techniques learned over the past week and apply them in a concrete project. This Sprint explored Authentication. During this Sprint, you studied Introduction to Authentication, Using Sessions and Cookies, Using JSON Web Tokens (JWT), and Client-side Authentication. In your challenge this week, you will demonstrate proficiency by creating an application that will give you a list of random dad jokes, as long as you are authorized.

- **DISCLAIMER** Authentication is a subject that many people spend a large amount time throughout their careers obtaining knowledge over. This is not something we expect you to have a mastery over, rather, we're preparing you to be able have an intelligent conversation about the subject.

## Instructions

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This is an individual assessment. All work must be your own. Your challenge score is a measure of your ability to work independently using the material covered through this sprint. You need to demonstrate proficiency in the concepts and objectives introduced and practiced in preceding days.

You are not allowed to collaborate during the Sprint Challenge. However, you are encouraged to follow the twenty-minute rule and seek support from your PM and Instructor in your cohort help channel on Slack. Your work reflects your proficiency w/ Authentication and your command of the concepts and techniques in the Introduction to Authentication, Using Sessions and Cookies, Using JSON Web Tokens (JWT), and Client-side Authentication modules.

You have three hours to complete this challenge. Plan your time accordingly.

## Commits

Commit your code regularly and meaningfully. This helps both you (in case you ever need to return to old code for any number of reasons and your project manager.

## Description

In this challenge, you build a real wise-guy application. _Dad jokes_ are all the rage these days. Currently the application is trying to receive some `Dad Jokes`, however we are currently locked out.

Implement an User Authentication System in order to access the jokes from the Jokes API that we want to consume. You will need to ensure that your system uses `bcrypt` for hashing and encrypting your user's passwords, as well as JWT for handling the authorization aspect of the app.

## Self-Study/Essay Questions

Demonstrate your understanding of this week's concepts by answering the following free-form questions. Edit this document to include your answers after each question. Make sure to leave a blank line above and below your answer so it is clear and easy to read by your project manager.

1. What is the purpose of using _sessions_?
Sessions are used to have data persistance after a user leaves a website. Normally, when we change pages or leave a website, the server forgets everything about the user. So, for the sake of user experience, sessions are used to tell the server there's no need to prompt the user for his password once again. The server adds a datapoint that says there's a session on a specific device by a specific account. Hence, you can have multiple sessions when logged in across multiple devices with the same account (if the database allows that.) Some sites will limit the amount of sessions to one per account or will keep track of how many you have running in tandem. When dealing with SaaS products, this is how they usually keep track of the number of accounts connected to a single payment plan.

1. What does bcrypt do to help us store passwords in a secure manner.
Bcrypt is a module that takes care of the hashing for us. In essence, Bcrypt is an all-in-one solution. For the moment, Bcrypt's hashing function hasn't been broken yet. What's more, Bcrypt allows for both manual and automatic salting, as well as doing multiple rounds of hashing. Often, a normal Bcrypt hash will go through between 1000 and 8000 rounds of hashing to further obfuscate the hash.

1. What does bcrypt do to slow down attackers?
As per the above, Bcrypt makes it more difficult to reverse engineer the hash by doing multiple rounds of hashing, to the order of many thousands. This adds another level of security. Malicious actors won't know _how many times_ the password has been hashed, on top of not knowing the hashing function itself. Therefore, when trying to brute-force it, one would have to both try tens of thousands of possible passwords, but also run every single one of those through tens of thousands of hasing cycles just to go through all possible permutations. 

1. What are the three parts of the JSON Web Token?
The header, the payload, and the signature. The header contains key-value pairs informing the server about the used algorithm and token-type (i.e. JWT). The payload contains all the data we'd like to store in the token. This can be a JSON object with identifiers (like user_id) and data regarding user-behaviour or other data you'd like to persist. Finally, the signature is made by taking the header and payload and encoding them in base64 and then signing/adding a secret at the end. With the proper secret, this can then be reverse engineered once the token comes back.

## Project Set Up

Follow these steps to set up and work on your project:

- [x] Create a forked copy of this project.
- [x] Add PM as collaborator on Github.
- [x] Clone your OWN version of Repo (Not Lambda's by mistake!).
- [x] Create a new Branch on the clone: git checkout -b `<firstName-lastName>`.
- [x] Implement the project on this Branch, committing changes regularly.
- [x] Push commits: git push origin `<firstName-lastName>`.

Follow these steps for completing your project:

- [x] `cd` into the root of the project and run `yarn` to install dependencies.
- [x] Once you have your `node_modules` go ahead and run `yarn server` or `npm run server` to start your node server.
- [x] Submit a Pull-Request to merge <firstName-lastName> Branch into master (student's  Repo).
- [x] Add your Project Manager as a Reviewer on the Pull-request
- [x] PM then will count the HW as done by  merging the branch back into master.

Helpful Tip on Testing this Project:

- [ ] **TEST** this project using **`POSTMAN`**.

## Minimum Viable Product

- [x] Implement the `register` function inside `/config/routes.js`.
- [x] Implement the `login` function inside `/config/routes.js`.
- [x] Use JSON Web Tokens for authentication.

**Note** The migrations and a database with empty users is already included

- [x] Add the authentication related code. If everything is done correctly, visiting `/api/jokes` should return a list of jokes.

## Stretch Problem: Build a front end to interface with your User Auth System

- Add a React client that connects to your API and has pages for `Sign Up`, `Sign In` and showing a list of `Jokes`.
- Once you have the functionality down, style it!
