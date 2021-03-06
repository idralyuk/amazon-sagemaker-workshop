# Amazon SageMaker Workshop

Amazon SageMaker is a fully-managed service that enables developers and data scientists to quickly and easily build, train, and deploy machine learning models at any scale. In this workshop, you'll create a SageMaker notebook instance and work through sample Jupyter notebooks that demonstrate some of the many features of SageMaker.  For example, you'll create model training jobs using SageMaker's hosted training feature, and create endpoints to serve predictions from your models using SageMaker's hosted endpoint feature. Along the way you'll see how machine learning can be applied to both structured data (e.g. from CSV flat files) and unstructured data (e.g. images).  

![Overview](/images/overview.png)

## Prerequisites

### AWS Account

In order to complete this workshop you'll need an AWS Account with access to create AWS IAM, S3 and SageMaker resources. The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work.

Some of the resources you will launch as part of this workshop are eligible for the AWS free tier if your account is less than 12 months old. See the [AWS Free Tier page](https://aws.amazon.com/free/) for more details.  We are also providing a credit for the workshop if you attend the scheduled workshop sessions in the AWS Pop-up Lofts in San Francisco or New York.

### AWS Region

SageMaker is not available in all AWS Regions at this time.  We recommend running this workshop in either of the following AWS Regions:  Oregon or N. Virginia.

### Browser

We recommend you use the latest version of Chrome or Firefox to complete this workshop.

## Modules

This workshop is divided into multiple modules. Module 1 must be completed first, followed by Module 2.  You can complete the other modules (Modules 3 and 4) in any order.  

1. Creating a Notebook Instance
2. Video Game Sales Notebook
3. Distributed Training with TensorFlow Notebook
4. Image Classification Notebook 

Be patient as you work your way through the notebook-based modules. After you run a cell in a notebook, it may take several seconds for the code to show results. For the cells that start training jobs, it may take several minutes. In particular, the last two modules have training jobs that may last up to 10 minutes.  

After you have completed the workshop, you can delete all of the resources that were created by following the Cleanup Guide provided with this lab guide. 

### Module 1:  Creating a Notebook Instance

In this module we will start by creating a SageMaker notebook instance, which we will use to run the other workshop modules.

#### Launching the Notebook Instance
1. Sign into the AWS Management Console https://console.aws.amazon.com/.
2. In the upper-right corner of the AWS Management Console, confirm you are in the desired AWS region. Select either Oregon or N. Virginia.
3. Click on Amazon SageMaker from the list of all services.  This will bring you to the Amazon SageMaker console homepage.

![Services in Console](/images/Picture1.png)

4. To create a new notebook instance, go to 'Notebook instances', and click the 'Create notebook instance' button at the top of the browser window.

![Notebook Instances](/images/Picture2.png)

5. Type [First Name]-[Last Name]-Lab-Server into the Notebook instance name text box, and select ml.p2.xlarge for the Notebook instance type.
6. In the resulting modal popup, choose 'Create a new role', and select 'None' under the S3 Buckets you specify – optional. Click and Create role.

![Create IAM role](/images/Picture3.png)

7. You will be taken back to the Create Notebook instance page, click 'Create notebook instance'.

#### Accessing the Notebook Instance

1. Wait for the server status to say InService. This will take a few minutes.

![Access Notebook](/images/Picture4.png)

2. Click Open. You will now see the Jupyter homepage for your notebook instance.

![Open Notebook](/images/Picture5.png)


### Module 2:  Video Game Sales Notebook

In this module, we'll work our way through an example Jupyter notebook that demonstrates how to use an Amazon-provided algorithm in SageMaker. More specifically, we'll use SageMaker's version of XGBoost, a popular and efficient open-source implementation of the gradient boosted trees algorithm. Gradient boosting is a supervised learning algorithm that attempts to predict a target variable by combining the estimates of a set of simpler, weaker models. XGBoost has done remarkably well in machine learning competitions because it robustly handles a wide variety of data types, relationships, and distributions. It often is a useful, go-to algorithm in working with structured data, such as data that might be found in relational databases and flat files. 

To begin, follow these steps:

1. Download this repository to your computer by clicking 'Clone or download' then 'Download ZIP'.
2. In your notebook instance, click the 'New' button on the right and select 'Folder'.  
3. Click the checkbox next to your new folder, click the 'Rename' button above in the menu bar, and give the folder a name such as 'video-game-sales'.
4. Click the folder to enter it.
5. To upload the notebook, click the 'Upload' button on the right, then in the file selection popup, select the file 'video-game-sales.ipynb' from the folder on your computer where you downloaded this GitHub repository. Then click the blue 'Upload' button that appears in the notebook next to the file name.
6. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.

### Module 3:  Distributed Training with TensorFlow Notebook

In this module we will be using images of handwritten digits from the [MNIST Database](http://yann.lecun.com/exdb/mnist/) to demonstrate how to perform distributed training using SageMaker. Using a convolutional neural network model based on the [TensorFlow MNIST Example](https://github.com/tensorflow/models/tree/master/official/mnist), we will demonstrate how to use a Jupyter notebook and the [SageMaker Python SDK](https://github.com/aws/sagemaker-python-sdk) to create your own script to pre-process data, train a model, create a SageMaker hosted endpoint, and make predictions against this endpoint. The model will predict what the handwritten digit is in the image presented for prediction. Besides demonstrating a "bring your own script" for TensorFlow use case, the example also showcases how easy it is to set up a cluster of multiple instances for model training in SageMaker.

1. In your notebook instance, click the 'New' button on the right and select 'Folder'.
2. Click the checkbox next to your new folder, click the 'Rename' button above in the menu bar, and give the folder a name such as 'tensorflow-distributed'.
3. Click the folder to enter it.
4. To upload the notebook, click the 'Upload' button on the right, then in the file selection popup, select the file 'TensorFlow_Distributed_MNIST.ipynb' from the folder on your computer where you downloaded this GitHub repository. Then click the blue 'Upload' button that appears in the notebook next to the file name.
5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.
6. NOTE:  training the model for this example may take up to 10 minutes.

### Module 4:  Image Classification Notebook

For this module, we'll work with an image classification example notebook. In particular, we'll use SageMaker's image classification algorithm, which is a supervised learning algorithm that takes an image as input and classifies it into one of multiple output categories. It uses a convolutional neural network (ResNet) that can be trained from scratch, or trained using transfer learning when a large number of training images are not available. Even if you don't have experience with neural networks or image classification, SageMaker's image classification algorithm makes the technology easy to use, with no need to design and set up your own neural network.  

Follow these steps:

1. In your notebook instance, click the 'New' button on the right and select 'Folder'.  
2. Click the checkbox next to your new folder, click the 'Rename' button above in the menu bar, and give the folder a name such as 'image-classification'.
3. Click the folder to enter it.
4. To upload the notebook, click the 'Upload' button on the right, then in the file selection popup, select the file 'Image-classification-transfer-learning.ipynb' from the folder on your computer where you downloaded this GitHub repository. Then click the blue 'Upload' button that appears in the notebook next to the file name.
5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.
6. NOTE:  training the model for this example may take up to 10 minutes.  However, keep in mind that this is relatively short because transfer learning is used rather than training from scratch, which could take many hours.  

### Cleanup Guide

To avoid charges for resources you no longer need when you're done with this workshop, you can delete them or, in the case of your notebook instance, stop them.  Here are the resources you should consider:

- Endpoints:  these are the clusters of one or more instances serving inferences from your models. If you did not delete them from within the notebooks, you can delete them via the SageMaker console.  To do so, click the 'Endpoints' link in the left panel.  Then, for each endpoint, click the radio button next to it, then select 'Delete' from the 'Actions' drop down menu. You can follow a similar procedure to delete the related Models and Endpoint configurations.

- Notebook instance:  you have two options if you do not want to keep the notebook instance running. If you would like to save it for later, you can stop rather than deleting it. To delete it, click the 'Notebook instances' link in the left panel. Next, click the radio button next to the notebook instance created for this workshop, then select 'Delete' from the 'Actions' drop down menu. To simply stop it instead, just click the 'Stop' link.  After it is stopped, you can start it again by clicking the 'Start' link.  Keep in mind that if you stop rather than delete it, you will be charged for the storage associated with it.  







