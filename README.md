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


  I also craeted my own examples about my favourite sport  basketball and and set the api model to gpt-4o-mini and in the prompt i added that "give me a one line       answer" to make it short, i asked three questions to the model to which it answered correctly
   <img width="1872" height="894" alt="image" src="https://github.com/user-attachments/assets/e3b89d91-9e40-4dfd-bd1c-d6e627a69452" />
   <img width="1138" height="254" alt="image" src="https://github.com/user-attachments/assets/f277ced5-b2ec-44ce-9c7b-d5018cefd96a" />


  lesson 2(Prompt Hub): solution of versioning, storing and iterating on our prompts overtime, prompt template includes template message, model configuration and          output schema
        When we create a prompt one prompt is defaultly created(Chat-style Prompt which has list of messages) and the other is not default(Instruct-style prompt           which provides message with a single message).
         In the system setting i put a prompt "You are a teacher and you teach {subject}". I have also set the output property as string. I saved the prompt and           named "teacher". 
          Using the "pull_prompt", i used this teacher prompt and asked the question to it.
           i asked 3 questions of my choice about different subjects.
           <img width="1479" height="839" alt="image" src="https://github.com/user-attachments/assets/7f3d6724-e45d-47ce-a0ed-55891fe216aa" />
           earlier when we pulled the prompt we did not include the model but now we will include it.When we include the model to true, in the output we get to see              the "answer", this is the output of gpt-4o-mini output.
            <img width="1461" height="679" alt="image" src="https://github.com/user-attachments/assets/15b0dce5-6b98-4d82-8fe8-aa87438b08ac" />
          If we make changes in our system make write "You are a teacher from the future, 2500 AD and you teach {subject}", then this makes a new commit.Then i               ask question related to what are the common topics for a matrix student of a particular subject of that time?
            <img width="1472" height="676" alt="image" src="https://github.com/user-attachments/assets/1bcd13d1-e752-4bd6-ae92-52bc414cd670" />
          I also learnt to push the prompts programmatically to the prompt hub trough stk. I named a science_prompt and now it will answer accordingly an i used                 push_prompt to push this prompt upto langsmith prompt hub. 
             <img width="1451" height="545" alt="image" src="https://github.com/user-attachments/assets/209d83c3-2837-47a8-8ad2-26e90122fa6c" />
           Now I imported ChatOpenAI and specified the model name and chained it with the prompt hub.
             <img width="1473" height="600" alt="image" src="https://github.com/user-attachments/assets/b4a90b37-caf7-4699-ad3c-a46ec2a49c14" />
             Here is my saved science prompt:
              <img width="1893" height="855" alt="image" src="https://github.com/user-attachments/assets/2b9beebd-2453-43bd-b163-e74acf997589" />


  Lesson 3(Prompt engineering lifecycle) : I will import this langsmith_rag from app.py filr where i have defined this application and ask questions about it. I                have asked 2 question about the topics.          
        <img width="1457" height="488" alt="image" src="https://github.com/user-attachments/assets/db0d8e80-a050-4c5b-acab-ae3ed2a6c406" />
        Here in the Langsmith we can see our latest trace:
          <img width="1789" height="777" alt="image" src="https://github.com/user-attachments/assets/ab750908-fe18-4387-984b-3ea4b062e050" />
        This was my program view:
          <img width="1904" height="871" alt="image" src="https://github.com/user-attachments/assets/10edcad4-2737-4751-86d9-8a4778ba1ccd" />
         I made question and answer as my two variables and ran in the playground with 4 repetitions to amke my answer more clear:
           <img width="892" height="864" alt="image" src="https://github.com/user-attachments/assets/94797281-2c18-42cc-8627-68cf44ae8fd3" />
           <img width="827" height="905" alt="image" src="https://github.com/user-attachments/assets/9e84d1b5-7a95-42e5-8990-18568a0c9ce4" />
         I gave the syatem a command to give the code whenever needed:
           <img width="1611" height="825" alt="image" src="https://github.com/user-attachments/assets/cd61803d-6fdd-4654-92cf-dae870701d23" />
         With the help of dataset to get the particular answer to the particular qustion i defined both the question and answer in the dataset.So, I started this            dataset in the playground without repetition with open ai.
           <img width="1734" height="898" alt="image" src="https://github.com/user-attachments/assets/bdc18547-7e2a-4e28-ba46-b7d456776f77" />
           <img width="1636" height="879" alt="image" src="https://github.com/user-attachments/assets/5d046490-836e-4777-9b49-97bf6da37d4b" />
         So, instead of using the rag manually in the code, i pulled it from Prompt hub from the langsmith and here we will nor require any rag prompt in our code:
           <img width="817" height="101" alt="image" src="https://github.com/user-attachments/assets/5a8d8f6f-a778-4250-ae6d-8f976f74c113" />
         So i checked this with the help of three examples:
           <img width="1457" height="837" alt="image" src="https://github.com/user-attachments/assets/cc034a3e-8fda-420b-abf5-1b5aa9763aee" />




 Lesson 4 (Prompt Canvas) : In this lesson i learnt about canvas prompts, here i gave instructions to the cahatbot LLM agent that to be precise on what we want in         the output.
        <img width="1496" height="872" alt="image" src="https://github.com/user-attachments/assets/25c15c27-5863-46bb-82d9-61064df0d640" />
      I played with the prompts and asked the chat to do changes and also asked it to suggest me how i can improve this prompt , i also manually added thing in            the  prompt.
      Using this i asket some questions without repetitions:
        <img width="1635" height="843" alt="image" src="https://github.com/user-attachments/assets/8e5a7176-1599-469b-bcf8-16e2f33651a2" />
      I also changed a particular text of the canvas prompt:
        <img width="1491" height="789" alt="image" src="https://github.com/user-attachments/assets/1d627050-ea30-4ccd-9a43-6157b22836d7" />
        <img width="1415" height="746" alt="image" src="https://github.com/user-attachments/assets/6cf7042b-30f5-4321-addd-985b2f85e2c0" />
      I also created a quick action:
        <img width="492" height="506" alt="image" src="https://github.com/user-attachments/assets/5d69d228-ff62-4c96-aec7-b810e813b146" />
        <img width="1482" height="821" alt="image" src="https://github.com/user-attachments/assets/b291824a-dbf9-45b0-82cd-7edd64528cb8" />
        <img width="1484" height="841" alt="image" src="https://github.com/user-attachments/assets/c21d1113-f42c-4402-8c7b-482540ea70da" />







 

           




















    
