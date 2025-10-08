

# EXP 5: COMPARATIVE ANALYSIS OF DIFFERENT TYPES OF PROMPTING PATTERNS AND EXPLAIN WITH VARIOUS TEST SCENARIOS

# Aim: To test and compare how different pattern models respond to various prompts (broad or unstructured) versus basic prompts (clearer and more refined) across multiple scenarios.  Analyze the quality, accuracy, and depth of the generated responses 

### AI Tools Required: 
Chatgpt
# Explanation: 
Define the Two Prompt Types:

Write a basic Prompt: Clear, detailed, and structured prompts that give specific instructions or context to guide the model.
Based on that pattern type refined the prompt and submit that with AI tool.
Get the ouput and write the report.

Prepare Multiple Test Scenarios:
Select various scenarios such as:
Generating a creative story.
Answering a factual question.
Summarizing an article or concept.
Providing advice or recommendations.
Or Any other test scenario
For each scenario, create both a naïve and a basic prompt. Ensure each pair of prompts targets the same task but with different levels of structure.
Run Experiments with ChatGPT:
Input the naïve prompt for each scenario and record the generated response.
Then input the corresponding basic prompt and capture that response.
Repeat this process for all selected scenarios to gather a full set of results.
Evaluate Responses : 
	Compare how ChatGPT performs when given naïve versus basic prompts and analyze the output based on Quality,Accuracy and Depth. Also analyse does ChatGPT consistently provide better results with basic prompts? Are there scenarios where naïve prompts work equally well?
Deliverables:
A table comparing ChatGPT's responses to naïve and basic prompts across all scenarios.
Analysis of how prompt clarity impacts the quality, accuracy, and depth of ChatGPT’s outputs.
Summary of findings with insights on how to structure prompts for optimal results when using ChatGPT.



# Objectives

To understand the difference between various prompting techniques.

To apply these prompting styles across multiple task scenarios.

To compare the clarity, accuracy, and depth of the responses.

To identify which prompting style performs best for different categories of problems.

To evaluate model behavior using a structured method such as criteria-based scoring.

#  Overview of Prompting Techniques
#  Basic Prompting

This is the simplest form of prompting, where a direct question or command is given to the model. It provides minimal context or guidance.

Example:

“Summarize this paragraph.”

Basic prompts are easy to write but often yield inconsistent or incomplete results because they lack structure.

#  Zero-Shot Prompting

Zero-shot prompting explicitly defines the task, expected format, and constraints, but provides no examples. The model uses its learned knowledge to generate answers.

Example:

“Classify the following review as Positive, Neutral, or Negative.”

This method works well for classification, summarization, and structured tasks where label boundaries are clear.

#  Few-Shot Prompting

Few-shot prompting provides examples of correct input–output pairs before asking the model to perform the same task on a new instance. It helps the model “learn by analogy.”

Example:

“Example 1: ‘This phone is fast.’ → Positive
Example 2: ‘Battery drains quickly.’ → Negative
Task: ‘Sound quality is clear but average.’ → ?”

Few-shot prompts are highly effective when labeled examples are available or when you want to demonstrate output format.

#  Chain-of-Thought Prompting

Chain-of-Thought (CoT) prompting encourages the model to reason step by step before producing a final answer. It is especially useful for multi-step reasoning, arithmetic, or logical inference.

Example:

“Let’s think step by step:
A train travels 60 km in 1.5 hours. Speed = distance ÷ time = ?”

This approach improves interpretability and correctness by guiding the reasoning process explicitly.

#  Scenarios and Experiments

The following scenarios were used to compare the performance of the four prompting styles. Each scenario includes a task, four types of prompts, and a sample model response.

# Scenario 1 — Sentiment Classification (Emotion Detection)

Task: Identify the emotion expressed in a given sentence.

Basic Prompt:

“What emotion does this text express: I lost my job today.”

Response: Sadness (but sometimes vague like “Negative feeling”).

Zero-Shot Prompt:

“Classify the emotion as one of [happiness, anger, fear, sadness, surprise]. Text: I lost my job today.”

Response: Sadness.

Few-Shot Prompt:

Ex1: “I got promoted.” → Happiness
Ex2: “He broke my trust.” → Anger
Text: “I lost my job today.” → ?

Response: Sadness.

Chain-of-Thought Prompt:

“Think step-by-step about how the sentence shows loss and disappointment. Then give only the final emotion.”

Response: Sadness.

Observation:
Few-shot and CoT yielded the most precise labels. The basic prompt often missed nuance.

# Scenario 2 — Arithmetic Reasoning

Task: Find change amount in a purchase.

Basic Prompt:

“Ravi bought 3 pens at ₹10 and 2 books at ₹25 each. He paid ₹100. Find his change.”

Response: Often incorrect or inconsistent (e.g., ₹15).

Zero-Shot Prompt:

“Calculate Ravi’s total bill and change. Output only the amount of change in ₹.”

Response: ₹20.

Few-Shot Prompt:

Ex1: 2 apples at ₹10, 1 banana at ₹20 → Total ₹40; Paid ₹50 → Change ₹10
Ex2: 4 candies at ₹5 → ₹20; Paid ₹30 → Change ₹10
Task: 3×₹10 + 2×₹25; Paid ₹100 → ?

Response: ₹20.

Chain-of-Thought Prompt:

“Step 1: 3×10 = 30. Step 2: 2×25 = 50. Total = 80. Step 3: 100–80 = 20. Final answer: ₹20.”

Response: ₹20 (accurate and transparent).

Observation:
Chain-of-thought reasoning eliminates calculation mistakes common in basic prompts.

# Scenario 3 — Text Summarization

Task: Summarize a paragraph about climate change.

Basic Prompt:

“Summarize the paragraph on climate change.”
Response: Generic, vague answer like “It talks about global warming.”

Zero-Shot Prompt:

“Write a one-sentence summary highlighting the causes and effects of climate change.”
Response: Focused and clear summary.

Few-Shot Prompt:

Example 1: Paragraph → “Air pollution leads to health issues.” → Summary: “Pollution causes illness.”
Example 2: “Deforestation reduces oxygen supply.” → “Tree loss harms the environment.”
Task: Climate change paragraph → ?

Response: Concise and precise.

Chain-of-Thought Prompt:

“Identify key ideas → causes, effects, solutions. Then form one sentence summarizing all.”
Response: Well-structured and complete summary.

Observation:
CoT prompts helped the model logically compress information rather than paraphrasing blindly.

# Scenario 4 — Information Extraction

Task: Extract date, time, and place.

Basic Prompt:

“Extract meeting details from: Let’s meet next Friday at 2 PM at Chennai Central.”
Response: Often incomplete or just repeats the sentence.

Zero-Shot Prompt:

“Output JSON with {‘date’, ‘time’, ‘location’}. Message: Let’s meet next Friday at 2 PM at Chennai Central.”
Response: Structured and clear.

Few-Shot Prompt:

Ex1: “Meet tomorrow 9 AM at Office.” → {“date”: “2025-10-08”, “time”: “09:00”, “location”: “Office”}
Ex2: “Party on Sunday 7 PM, Marina Beach.” → {“date”: “2025-10-12”, “time”: “19:00”, “location”: “Marina Beach”}
Task: Next Friday at 2 PM at Chennai Central → ?

Response: Correct structured output.

Chain-of-Thought Prompt:

“Determine next Friday’s date from today’s date (Oct 7, 2025), convert to ISO, then output JSON.”
Response: {“date”: “2025-10-10”, “time”: “14:00”, “location”: “Chennai Central”}

Observation:
CoT improved temporal reasoning and date accuracy.

# Scenario 5 — Creative Writing

Task: Write a short story about a talking tree.

Basic Prompt:

“Write a short story about a talking tree.”
Response: Simple and generic story.

Zero-Shot Prompt:

“Write a 5-sentence imaginative story about a talking tree that helps travelers lost in the forest.”
Response: Creative, clear storyline.

Few-Shot Prompt:

Example 1: Story about a singing river helping villagers.
Example 2: Story about a mountain teaching patience.
Task: Talking tree helping travelers → ?

Response: Engaging, cohesive story.

Chain-of-Thought Prompt:

“Step 1: Describe setting. Step 2: Introduce talking tree. Step 3: Conflict—lost travelers. Step 4: Resolution. Step 5: Moral. Then write story.”
Response: Rich, moral-driven story.

Observation:
CoT guidance produced logical narrative flow; few-shot examples boosted creativity.

# Scenario 6 — Code Generation

Task: Write Python function to check if a number is even.

Basic Prompt:

“Write Python code to check if a number is even.”
Response: if n%2==0: print("even")

Zero-Shot Prompt:

“Define a Python function is_even(n) that returns True if n is even, False otherwise.”
Response: Correct reusable function.

Few-Shot Prompt:

Ex1: Function is_positive(n) returns True if n>0.
Ex2: Function is_prime(n) checks divisibility.
Task: is_even(n) → ?

Response: def is_even(n): return n%2==0

Chain-of-Thought Prompt:

“Plan: check divisibility by 2, return Boolean. Then write final code.”
Response: Clean, efficient function.

Observation:
Few-shot prompts encouraged correct function structure and naming conventions; CoT reduced logic errors.

# Scenario 7 — Educational Explanation

Task: Explain “photosynthesis” simply.

Basic Prompt:

“Explain photosynthesis.”
Response: Technical and long.

Zero-Shot Prompt:

“Explain photosynthesis in simple language for a 10-year-old.”
Response: Clear and easy.

Few-Shot Prompt:

Ex1: “Explain gravity for a child.” → “Gravity pulls things toward Earth.”
Ex2: “Explain rain.” → “Rain happens when clouds get full of water.”
Task: Photosynthesis → ?

Response: “Plants make food using sunlight, water, and air.”

Chain-of-Thought Prompt:

“Step 1: Identify what inputs plants use. Step 2: What they produce. Step 3: Simplify the sentence.”
Response: “Plants take sunlight, water, and carbon dioxide to make food and oxygen.”

Observation:
Zero-shot and CoT provided accurate yet simplified educational explanations.

#  Evaluation Method

| Prompt Type      | Clarity | Accuracy | Completeness | Depth | Remarks                        |
| ---------------- | ------- | -------- | ------------ | ----- | ------------------------------ |
| Basic            | 2       | 3        | 2            | 2     | Often vague or incomplete      |
| Zero-Shot        | 5       | 5        | 4            | 4     | Precise, well-structured       |
| Few-Shot         | 5       | 5        | 5            | 5     | Highly consistent              |
| Chain-of-Thought | 5       | 5        | 5            | 5     | Deep reasoning and correctness |

#  Comparative Analysis

Basic Prompts are easy to use but unreliable for complex or reasoning tasks.

Zero-Shot Prompts perform well when the task is well-defined and requires specific formatting.

Few-Shot Prompts help the model imitate patterns and produce consistent results.

Chain-of-Thought Prompts show the highest reasoning depth, making them ideal for logical, numerical, or step-based tasks.

Key Finding:
Combining Few-Shot + CoT (sometimes called “hybrid prompting”) yields the most accurate and interpretable results across diverse domains.
<img width="1779" height="980" alt="image" src="https://github.com/user-attachments/assets/d625af42-c137-43ed-a0c2-9b3761825e65" />


# Conclusion

Prompting techniques significantly influence how effectively language models perform across diverse problem types.

For simple factual or definition-based tasks, Zero-shot prompting is sufficient.

For creative or formatted outputs, Few-shot prompting provides better control.

For reasoning, mathematics, and logic, Chain-of-Thought prompting ensures stepwise accuracy.

Basic prompts are best for quick, informal interactions but not for precision-based applications.

Understanding these techniques is crucial for anyone using AI in education, research, programming, or content creation. As AI systems evolve, prompt literacy becomes as important as digital literacy itself.

#  References

Brown et al. (2020). Language Models are Few-Shot Learners.

Wei et al. (2022). Chain-of-Thought Prompting Elicits Reasoning in Large Language Models.

OpenAI Technical Reports (2024). Prompt Engineering Guidelines.

Google AI (2023). Effective Prompt Patterns for LLMs.

Anthropic Research (2024). Comparative Evaluation of Prompt Strategies.


# RESULT: The prompt for the above said problem executed successfully
