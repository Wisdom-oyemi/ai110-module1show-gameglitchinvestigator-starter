# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
It looked decent at the start, in my opinion. It had an answer requesting area, buttons to restart the game, submit a guess, and show a hint if applicable. The funniest part is the little message below the page title that says "An AI-generated guessing game. Something is off."


- List at least two concrete bugs you noticed at the start  
I tested the upper limit of the range (100) and the corresponding hint was "Go HIGHER!", which I personally found odd. Another weird glitch happened when I finished all of my 7 guesses; the secret number was given as 11, but checking the debug info gives me a secret number of 18. In addition, I ran a second session to test (in normal difficulty) and the game just...crashed, and refused to accept my input.
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used GitHub Copilot.

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
An AI suggestion that was correct was an analysis on why the game returned "Go HIGHER!" despite the guess being higher than the 100 range, which was due to the incorrect ">" signage. Copilot suggested flipping the sign and refactoring the code int logic_utils.py, which I verified by testing different scores manually.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
An AI suggestion that was misleading was an analysis of the second bug I was having (the issue with the "secret number" changing). It explained the issues, but the lines it suggested I should fix were not  the correct ones. I verified this by manually searching through the lines and identifying the spots for the FIXME comments.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I simply ran streamlit in the terminal to have the game render in my web browser, and played through several rounds (with different outputs) to compare the behavior against the buggy-ness I previously noted.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
The main pytest I ran was for check_guess to return the proper inputs. In that specific case, the test was ran to ensure the correct output for the guess being higher/lower than the secret number, and it showed me that the code previously had incorrect range handling.

- Did AI help you design or understand any tests? How?
Github Copilot helped me understand the tests for both the game-reset feature and the check_guess feature, by explaining in detail what the tests are checking for and suggesting edits to the test to reflect the correct state of the game.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
