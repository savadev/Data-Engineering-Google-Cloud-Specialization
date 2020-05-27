## 1. What is ML?

* So you've heard a lot about Machine Learning or ML, let's start with a definition. What is ML? Here's the definition I like to use. ML is a way to get predictive insights from data to make repeated decisions off of. You do this using algorithms that are relatively general and applicable to a wide variety of datasets. Think of a typical company and how they use their data today. Perhaps they have a dashboard that business analysts and decision-makers view on a daily basis, or report that's read on a monthly basis. This is an example of a backward-looking use of data, looking at historical data to create reports and dashboards. This is what people tend to mean when they talk about BI or Business Intelligence. A lot of data analytics is backward-looking, nothing wrong with that. But instead we're going to use ML or Machine Learning to generate forward-looking or predictive insights. Of course, the point of looking at historical data might be to make those decisions. Perhaps business analysts examined the data and they suggest new policies or rules. They could suggest for example that's possible to raise the price of a product in a certain region. Now, that business analyst is making a predictive Insight but is that scalable? Can the business analyst make such a decision for every single product in every single region? And can they dynamically adjust the price every second? Now, here's where the computers get involved. In order to make decisions around predictive insights repeatable, you need ML. You need a computer program to derive those insights for you. So ML is about making predictive insights from data, many of them at a time. It's about scaling up BI and decision-making. The other part of the Machine Learning definition is around the use of standard algorithms. ML uses standard algorithms to solve what looked like seemingly different problems. Normally when we think of computers, we think a programs that do different things. For example, the software that you use to file your taxes is very different from the software that used to get directions home when you're driving. Machine Learning is a little different, you use the same software under the hood. That's what we mean when we say ML uses standard algorithms. But you can train that that software to do very different things. You can train the software to estimate the amount of taxes that you owe. Or train that same software to estimate the amount of time it will take to get you home. The ML software once trained on your specific use case is called a Model. So you now have a model that can estimate your taxes or a model that can estimate the time to get you home. We use the term Model because it's an approximation, it's a model of reality. For example, we're giving the computer lots of historical data on drive times in New York City and it'll learn the relationships in the data, traffic patterns, seasonality, time of day impact to predict today's commute time home. Whatever the domain ML modeling requires lots of training examples. We'll train the model to estimate tax by showing it many, many, many examples of prior year tax returns. Or train the model to estimate trip duration by showing it many, many, many different journeys. So the first stage of ML is to train in ML model with lots of good examples. An example consists of an input and the correct answer for that input, that's called the Label. In the case of structured data that is rows and columns of data, an input can simply be a single row of data. In unstructured data like images, an input could be a single image say like of a cloud that you want to classify. Is this a rain cloud or is this not? Now, imagine you work for a manufacturing company. You want to train a Machine Learning model to detect defects in these parts before they get assembled into the final products for users. Well, you can start by collecting a dataset of the images for these parts. Some of these parts would be good, some of these parts could be fractured or broken up. And for each image, you'll assign the corresponding label. That's the right answer broken or not broken part. And then use this set of examples as training data for your model. After you train the model, you can then use it to predict the label of images that it has never seen before. Learn from the past predict for the future. Here your input for the trained model is an image of the part. Because the model has already been trained it's correctly able to predict at this part is in good condition. Note that the image here is different from the ones used in our training examples. But it's still works because the ML model has generalized, it hasn't memorized the training data those specific examples that you shown it. And it's learned a more general idea of what a good-looking part, what a good condition for that part looks like. So why do we say these algorithms are standard? Well, the algorithms exist independently of your use case. Even though detecting manufacturing defects and parts in those images and detecting something like diseased leaves and tree images, are two very different use cases, the same algorithm an image classification network works for both. Similarly, there are standard algorithms for predicting the future value of a time series dataset or to transcribe human speech to text. ResNet is a standard algorithm for image classification. Now, it's not crucial to understand how an image classification algorithm works, only that it's the algorithm that you should use if you need to classify images of automotive parts. When you use the same algorithm on different datasets, there are different features or inputs relative to the different use cases, and you can see them represented visually here. You might be asking yourself isn't the logic different you can't possibly use the same rules for identifying defects in manufacturing that you do in identifying different types of leaves. You're right, the logic is different, but ML doesn't use logical if-then rules. The image classification network isn't like that set of rules if this then that but a function that learns how to distinguish between categories of images. So even though we start with the same standard algorithm, after training the trained model that classifies leaves is different from the trained model that classifies manufacturing parts. And guess what, you can actually reuse the same code for the other use cases focused on the same kind of task. So in our example, we were identifying manufacturing defects, but the higher level tax was classifying images. You can reuse the same code for another image classification problem, like finding examples of your products in photos posted on social media. However, you still have to train it separately for each use case. The main thing to know is that for Machine Learning your model will only be as good as your data. And more often than not you yield a lot data for Machine Learning. For our example that we talked about, you'll need a large dataset of historical examples of both rejected parts and parts in good condition in order to train a model to categorize the parts as defective or not. The basic reason why ML models need high-quality training data is because they don't have human general knowledge like we do. Data is the only thing that they have access to to learn from.

## 2. Machine Learning and AI

* In this topic, you'll be introduced to the different options that exist in GCP when it comes to leveraging Machine Learning. First though, you'll explore the relationship between Machine Learning, Artificial Intelligence and Deep Learning. A very common question asked, what's the difference between AI, Artificial Intelligence, Machine Learning and Deep Learning? Well, one way to think about it is AI is the discipline like something like physics. AI refers to machines that are capable of acting autonomously, machines that think. AI has to do with the theory and methods to build machines that can solve problems by thinking and acting like humans. Machine Learning within there is a tool set like Newton's Laws of Mechanics. Just as you can use Newton's laws to figure out how long it'll take a ball to drop and when it falls off a cliff, you can use Machine Learning to scalably solve certain kinds of problems using data examples. But without the need for any custom code. Deep Learning is a type of Machine Learning that works even when the data consists of unstructured data, like images, speech, video, natural language text and so on. One kind of deep learning is image classification. A machine can learn how to classify images into categories when it's shown lots of different examples. And the really cool thing about deep learning is that oftentimes in a really complex problems it can do better than at it. The basic difference between Machine Learning and other techniques in AI is that in Machine Learning machines learn. They don't start out intelligent, they become intelligent. Back to our example. Let's say we've built a Machine Learning model to find bad manufactured parts, and then we want to remove them. Quality control is now pretty inexpensive. So what? The business factor motivating us isn't my business will save money. It's I could add add quality control throughout our entire manufacturing process. Instead of just doing the quality control at the end of the manufacturing line. We can now insert it everywhere and improve overall quality. The opportunity is for organizations to take advantage of the ease of creating new models to continue to transform their business. So now that you know what ML is and I hope that you start to come up with some of those ideas of your own related to it. Much of the hype around ML now is because the barriers to entry a building these models has fallen dramatically. You don't have to be an astrophysicist to do Machine Learning. This is because the convergence of a number of critical factors, the increasing availability of data. The increasing maturity and sophistication of those ML algorithms for you to choose from. And the increasing power in the availability of computing hardware and software through things like cloud computing. Let me show you an example. Imagine we want to build that ML model to identify those diseased leaves to predict the health of the trees. Remember we can do that using a standard algorithm for image classification. You don't need to have a PhD in image processing. You just need to know which algorithm should you choose off the shelf. But back to our ML model, another critical ingredient for ML is that data. We need to collect lots of images of leaves. Today you can do that pretty easily with the camera on your phone. Finally, we need the hardware and the software to make that happen. That's easier now than it has ever been in the past. We can use the cloud to power or ML model so that we can do it cost effectively.

## 3. ML options on Google Cloud Platform

* Different options exist when it comes to leveraging machine learning. Advanced users who want more control over the building and training of their ML models will use tools that offer the levels of flexibility that they're looking for. This can involve developing custom models through an ML library, like TensorFlow, that's supported on AI platform. This option works well for data scientists with the skills and the need to create a custom TensorFlow model. But increasingly, you don't have to do that. Google makes the power of machine learning available to you even if you have a limited knowledge machine learning. You can use Cloud AutoML, like you're going to do in one of your labs, to build on Google's machine learning capabilities to create your own custom machine learning models that are tailored to your specific business needs. And then, integrate those models into applications and websites. All without running a line of TensorFlow code. Alternatively, Google has a range of pre-trained, meaning you don't need to bring your own data, machine learning models that are ready for immediate use within applications in ways that the respective APIs are designed to support. Such pre-trained models are excellent ways to replace user input with machine learning.

## 4. Game: Reviewing key ML concepts

* Let's do a quick recap of the basics of machine learning with a fun demo that you can show your friends and your co-workers. Pause the video, and then navigate to quickdraw.withgoogle.com, and then play the quick drawing game that's powered by machine learning. Here's the algorithm behind the game that we just played. It's called a deep neural network, or DNN. The layers are meant to mimic our own human brains in the way that we perceive stimuli. With each layer, a trained model learns more and more about the image of this dog that's hiding in a laundry basket. Starting from things like basic detection of edges in the photo, and then colors, and ultimately arriving at a final decision of is this a cat or is this a dog. You'll get a chance to build your own image recognition model later on in the course. And spoiler alert, you don't need to write any code. But if you want additional intuition of how these model types like DNNs work, check out the TensorFlow neural network playground at playground.tensorflow.org. It was one of my favorite learning tools for when I was understanding how do computers actually think. And it shows just how far ML has come, that we can build these models at scale into applications like Google photos.

## QuizNotes

* What is the difference between AI and ML?
	* AI is a discipline while ML is a toolset
* What is the primary impact of ML?
	* It allows business operations to scale