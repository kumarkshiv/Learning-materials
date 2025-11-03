1. Agentic AI (DeepLearning.AI): [Link](https://learn.deeplearning.ai/courses/agentic-ai/lesson/pu5xbv/welcome!) : **[100% Done]**
   . . .
   
   A. **Module-4:**
      - . . .
      - **Hands-on: Adding component-level evaluation to your Agenti Workflow:**
         i. When your Agentic workflow is complex, when one component is performing poorly --> Doing an end-to-end evaluation is time-consuming.
         ii. It is difficult to see the end-to-end improvement by just improving one component. (Due to randomness introduced by other components).
         iii. Do component-level evaluations.
           - Identify the component performing poorly.
           - Design an evaluation for that component --> Add this evaluation to your Agentic workflow.
           - Example: **Web Search** of a research workflow.
             - See if the component is returning the URLs from your list of preferred domains.
             - Compute the ratio of **preferred** vs **total results**.
             - Return **PASS / FAIL** for a prompt.
            
      - **Practical tips for Building Agentic AI**:
         i. Improving **non-LLM** components performance:
           - Tune hyperparameters of the components (e.g., # results, date range in websearch component, etc.)
           - Replace the component (e.g., try a different web search engine, etc.)
         ii. Improving **LLM** components performance:
           - Improve your prompts (e.g., add more explicit instructions or examples to prompt, use **few-shot** prompting, etc.)
           - Try different LLMs and use evaluations to pick the best model. **(Need skill to identify a good model)**
           - If a task is too complex for the model --> **Decompose** the task into multiple steps (e.g., Generation, reflection, etc.)
                   
      - **Q) How can you identify a good model for a particular task?**
         - Play with different models. (Have a set of evaluations, read other people's prompts for ideas of how to best use models, etc.)
         - Use different models in your Agentic workflow (Observe which model works better for which type of tasks, use easy-to-use libraries like [Aisuite](https://github.com/andrewyng/aisuite))

      - **Latency, Cost and Optimization**
         - **First** focus on getting high-quality Outputs and high performance (This is the hardest part.)
         - When the entire workflow is working end-to-end with high-quality output and performance, then we should focus on optimizing cost and latency.
         - _Ideas for Optimizing time:_
           - Benchmark or time for each component of the workflow.
           - Identify the components that have the most room to make it faster.
           - Take advantage of parallelism (e.g., web fetch task, analyze multiple URLs in parallel.)
           - Try less intelligent and smaller models **(faster)** that can work better for a particular task.
         - _Ideas for Optimizing cost:_
           - Track the cost per unit (e.g., per token, per API, etc.) for each component in the workflow.
           - Identify if there are cheaper alternatives for the component.
        - This exercise gives clarity about which component we should focus on to improve it further.
        - **Development process of Agentic Workflow:**
          - Building and analyzing Agentic workflow should happen back and forth as shown in the table below.
                      | Build                           | **<<< =========== >>>** | Analyze                           |
            |---------------------------------|:-----------------------:|-----------------------------------|
            | 1. Build end-to-end system.     |                         |                                   |
            |                                 |                         | 2. Examine the outputs and traces |
            | 3. Improve individual component |                         |                                   |
            |                                 |                         | 4. Build evals, compute metrics   |
            |                                 |                         | 5. Error Analysis                 |
            |                                 |                         | 6. Component-level Evals          |
            
   B. **Module-5: Patterns for Highly Autonomous Agents**
      - Planning the Workflows:
        - Example: Customer service Agent.
        - ![Customer Service Agent](https://github.com/user-attachments/assets/b867413f-b9ac-4fe2-a7d1-588ecc0baaf4) {width=100}
        - One advantage with LLMS: We do not have to decide in advance, what is the sequence in which to call in order to answer a fairly complex customer request
      - Creating and executing LLM plans:
        - Clear and unambiguous way to do this is format your plan in text to JSON format. (Ask an LLM to format the plan to a JSON format.)
        - ![Prompt-Creating LLM plans](https://github.com/user-attachments/assets/95644994-99ab-4fb4-9b05-a3eea3b0bf10){width=250}
