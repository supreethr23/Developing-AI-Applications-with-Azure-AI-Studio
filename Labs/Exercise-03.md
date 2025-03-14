# Lab 03: Evaluation Flow Setup

## Lab Overview
In this lab, you will set up and analyze evaluation flows for an AI model using Azure AI Foundry. You will manually review model responses to various inputs, providing a detailed evaluation of the model's performance. By setting up specific evaluation metrics, such as coherence and fluency, you will automate the evaluation process using a provided dataset. This hands-on experience will help you understand how to critically assess and refine AI model outputs, ensuring the model meets desired performance standards.

## Lab Objectives
In this lab, you will perform the following:
- Task 1: Set Up Evaluation Metrics
- Task 2: Run and Analyze Evaluation Flows

## Task 1: Set Up Evaluation Metrics

You can manually review model responses based on test data. Manually reviewing allows you to test different inputs one at a time to evaluate whether the model performs as expected.

1. From the left navigation menu, under the **Access and Improve** section, select **Evaluation (1)**. On the **Assess and compare AI application performance** select **Manual evaluations (2)** tab. Select **+ New manual evaluation (3)**.

   ![](./media/evaluation-1.png)

1. A new window opens with your previous **system message** already populated and your deployed model selected.

   ![](./media/d50.png)

1. In the **Manual evaluation result** section, you'll add five inputs for which you will review the output. Enter the following five questions as five separate inputs by selecting **+ Add Inputs**:

   `Can you provide a list of the top-rated budget hotels in Rome?`

   `I'm looking for a vegan-friendly restaurant in New York City. Can you help?`

   `Can you suggest a 7-day itinerary for a family vacation in Orlando, Florida?`

   `Can you help me plan a surprise honeymoon trip to the Maldives?`

   `Are there any guided tours available for the Great Wall of China?`

1. Select **Run** from the top bar to generate outputs for all questions you added as inputs.

    ![](./media/image-20.png)

1. You can now manually review the **Outputs** for each question by selecting the thumbs up or down icon at the bottom right of a response. Rate each response, ensuring you include at least one thumbs up and one thumbs down response in your ratings.

   ![](./media/d51.png)

   > **Note:** If you receive an error in any of the output while executing the run "exceeded token rate limit of your current AIService", then please rerun the failed ones after couple of minutes.

1. Select **Save results (1)** from the top bar. Enter **manual_evaluation_results (2)** as the name for the results, and select **Save (3)**.

   ![](./media/gpt-4-demo18.png)
   
1. Using the menu on the left, navigate to **Evaluations (1)**. Select the **Manual evaluations (2)** tab to find the manual evaluations you just saved **(3)**. Note that you can explore your previously created manual evaluations, continue where you left of, and save the updated evaluations.

   ![](./media/manual.png)

## Task 2: Run and Analyze Evaluation Flows

This process systematically assesses the performance and effectiveness of AI-generated responses by conducting dataset evaluation. It involves executing evaluation workflows, collecting data, and thoroughly analyzing model outputs to identify strengths and weaknesses. By leveraging detailed insights from these analyses, organizations can make informed decisions, refine model performance, and optimize their AI-driven processes. Continuous evaluation ensures that processes remain efficient, effective, and aligned with organizational goals, ultimately enhancing overall performance and productivity.

1. From the left navigation menu, under the **Access and Improve** section, select **Evaluation (1)**. On the **Assess and compare AI application performance** select **Automated evaluations (2)** tab. Select **Create a new evaluation (3)**.

   ![](./media/evaluation-metrics.png)

1. On the **What do you want to evaluate?** pane, select **Dataset**.

   ![](./media/whatdoyouwant.png)

1. Create a new evaluation with the following settings:
    - **Evaluation name**: **Modelevaluation-<inject key="DeploymentID" enableCopy="false"/> (1)**
    - Select **Next (2)**.
       
       ![](./media/createnewevaluation.png)

    - Open a new tab and paste the new link **https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-studio/main/data/travel-qa.jsonl** JSONL file. press **Ctrl A** 
      and **Ctrl C** to select all and **Copy**.
  
    - Search for **Visual Studio (1)** in the Windows search bar of the vm and select **Visual Studio (2)**.

       ![](./media/vsc.png)

    - From the **File (1)** menu, select **New Text File (2)**, 

       ![](./media/d8.png)

    - **Paste the copied code**.

    - Navigate to **File (1)** and click on **Save as (2)**.    

       ![](./media/d9.png)    

    - Click on **Desktop (1)**, Enter the File name as **Sample (1)** select **JSON Lines (3)** for Save as type and then click on **Save (4)**.

       ![](./media/d10.png)        

1. Navigate back to **Azure AI foundary**, where your **creating a new evaluation**.
   
    - **Select the data you want to evaluate**: **Add your dataset (1)**, and select **Upload file (2)**.
  
         ![](./media/addyourdatasets.png)

    - Select the file that you downloaded **(1)** and click on **Open(2)**

         ![](./media/d11.png)    

    - Select **Next (2)** 

    - **Select metrics**: **Coherence (1), Fluency (2)**
    - **Connection**: Your AI Services connection - **ai-modelhub<inject key="DeploymentID" enableCopy="false"/>xxxxxxxx_aoai (3)**
    - **Deployment name/Model**: **gpt-4o model (4)**

         ![](./media/d13.png)  

    - Scroll down to **How does your dataset map to your evaluation input**. Ensure that **${data.query} (1)** is selected for the **query**, and **${data.response} (1)** is selected for the **response**.

    - Select **Next (2)**

         ![](./media/dataquery-037.png)  

    - Select **Submit**

      >**Note:** Wait for the evaluations to be completed, you may need to refresh.

1. Select **Evaluation (1)** from the left navigation menu, and under **Automated Evaluation (2),** choose the newly created evaluation run.

   ![](./media/evaluationmetrics238.png)

1. Explore the **Metric dashboard** and select **Data** from the top menu to view the **Detailed metrics results**.

    ![](./media/image-26.png)

    ![](./media/image-27.png)

## Review
In this lab you have completed the following tasks:
- Set Up Evaluation Metrics
- Ran and Analyzed Evaluation Flows

### You have successfully completed the lab. Click on **Next >>** to procced with next exercise.
