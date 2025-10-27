1. Agentic AI (DeepLearning.AI): [Link](https://learn.deeplearning.ai/courses/agentic-ai/lesson/pu5xbv/welcome!) : **[70% Done]**
   . . .
   
   A. Module-4:
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
   