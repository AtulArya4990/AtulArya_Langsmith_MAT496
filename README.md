# AtulArya_Langsmith_MAT496
# Module-0 Summary-: In this module i leraned to call api keys from .env files, a function that retrieves data fromt the text file and accordingly answers whatever we ask.here. We asket questions about langsmith, if the question is not related to that just reply "i don't know".
Module-1 Summary
  
  lesson-1(Tracing Basics): In this module I learned the basics of tracing and learned that it acts like a tree which has many branches(runs) and sub-runs, and also about metadata that stores more information about runs.



  lesson-2(Tracing Basics): These are types of runs-:
                                         LLM: Invokes an LLM
                                         Retriever: Retrieves documents from databases or other sources
                                         Tool: Executes actions with function calls
                                         Chain: Default type; combines multiple Runs into a larger process
                                         Prompt: Hydrates a prompt to be used with an LLM
                                         Parser: Extracts structured data
                  in each code we have to make the run types as these 6 runtypes and we have to see the output.


  lesson-3(alternating tracing methods): till now we have used traceable decorator to run to set up tracing, langchanin/langraphs gets    tracing out of the box, with trace()- want more control over what inputs and outputs get logged and cannot use decorators and wrappers, wrap_openai()-use the openAI SDK directly.



  lesson-4(Conversational Threads): it is a series of messages or exchanges in a conversation that are connected by a common topic, question, or task. Each thread usually has:

          
#Module-2 Summary

Video 1: Datasets

I learned about datasets which are primarily a list of examples which are used to test and evaluate our llm application rather than just doing a few random "gut checks". In this module we created datasets which comprised of both inputs and outputs. I also learned how to tag a paricular version of a dataset. These version tag are helpful when we want to test our appllication on previous versions of the application after making a few changes to the initial versions. I also learned how to add new data to the dataset directly from the trace runs and manually. Then i leanred about schema which enssures our data (current and future) is stored in a fomatted way. I also explored the feature to add some AI genrated examples. I also explored split which is used to isolate a few examples which we think are very important for our llm application to score good on. I also learned that we can share the dataset with others, download it or clone it.

Video 2:

I learned about evauluators in this module. They are essentially functions or processes used to score and quantify the performance of your Large Language Model (LLM) application or agent on specific test cases. They compare the dataset example against the output of our llm and rate them based on a score. Furthermore evaluators can be defined in both the jupyter notebook or LangSmith website directly inside the database. We can define evaulators using our own custom code or use an llm as a judge.

Video 3: Experiments

Experiments are basically running your llm application over a dataset and evauluating its performance with evaluators. We can run experiments in our SDK( using evaluate() ) or in the langsmith UI. I also analysed the impact of chanhing the llm model on the evaulation of the performance. I also learned how to run our experiment on specific subsets of examples like the initial version of the dataset and the split versions, and individual examples. I also learned that we can run our experiment over a certain example for x number of times this ensures us that we get consitent results. We can also run our experimnets with different parameters such as repetition, concurrent threads and metadata.




Module 3 Summary
    
lesson 1(Playground): Here, I learned if I give the same prompt to different AI's,how differently they will respond to the same prompt, we can compare their performances and choose the best answer out of them.   Repetitions are very useful for consistency and double checks that if I am able to respond to a question correctly every time(useful for high temperature or complex prompts).
   We need to insert our api key and after that we can select any model of ai, here i used gpt 4o mini. 
   <img width="1845" height="876" alt="image" src="https://github.com/user-attachments/assets/e41694d8-4734-454b-bbef-de1453a6407d" /> (this is the example of question taht the module tutor made us do).


  I also craeted my own examples about my favourite sport  basketball and and set the api model to gpt-4o-mini and in the prompt i added that "give me a one line answer" to make it short, i asked three questions to the model to which it answered correctly

    
