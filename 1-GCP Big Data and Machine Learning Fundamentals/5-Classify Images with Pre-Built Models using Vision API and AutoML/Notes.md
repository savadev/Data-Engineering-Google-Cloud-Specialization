## 1. Where is unstructured ML used in business?

* in this course, you've been applying machine learning to your structured datasets with custom models. It's time to widen our aperture and look at unstructured datasets, like images and also other approaches to doing ML that don't involve custom model building. Here's our agenda. We'll first see how ML on unstructured datasets is driving value for businesses. Then, we'll look at the intuition and models behind unstructured data. After that, is a critical topic on choosing the right ML approach. Whether to build a model from scratch, or use pre-existing building blocks. Lastly, we'll do a demo to classify text using three different approaches and compare the results. Here are just a few customer examples of companies who have used the ML tools on Google Cloud Platform on their datasets. The left to right ordering is reflective of more low-level programming to more abstraction and UI based. Aucnet built their own custom model to classify images of car parts and estimate price. Ocado used parsed results from the Natural Language API to route customer emails to the correct responders. Giphy use the out-of- the box vision API to find the text and memes using optical character recognition. It then can reject inappropriate uploads based on sentiment or keywords. Uniqlo designed to shopping chat bot using the dialogue flow UI. Dialogue flow is a Google owned company which specializes in building ML based interfaces like intelligent chatbots. Let's look at some other use cases for ML and business. You might be Airbus and use machine-learning to differentiate between Clouds and snow cover. If you're stumped like I am, the Clouds are in the upper right part of the right image highlighted in red. You might be an economic forecasts firm looking to track the global fleet of container ships via satellite imagery. Knowing the amount of cargo being carried, might help improve your economic forecast by days or months ahead of the official numbers. Medical images are ripe for innovation. For example, you could diagnose medical conditions like diabetic retinopathy earlier when it's easier to treat and prevent blindness. The key takeaway is that ML can automate tasks that may save or assist a human team. Recently, the latest models are even outperforming humans in some domains. Also image classification as a field is more than just binary classification tools. Later in this course, you will experiment with the pre-built Vision API model which allows you to pass through a JSON request and get back a ranked list of associated labels for your image. Also if you have more than one subject matter in a photo, you can draw bounding boxes and classify pieces of an image as well. Modern image classification models can even generate captions describing what is going on in the image, like a map of dependencies, like two hockey players are fighting over a puck. Here it's important to call out that even the best models can and will make mistakes in their predictions. Like the road sign captioned as a refrigerator filled with lots of food and drinks. As you saw, there were a lot of impressive uses for machine learning these days. Like detecting objects and images, helping to detect diseases and even enabling cars to drive themselves. But AI can also be used in more playful ways too. Through a pose estimation model, a Google AI experiment called moved mirror, can match your real-time movements to hundreds of images of people doing similar poses from around the world. Feel free to try it out yourself and have some fun. Then tune back into this course to learn how image classification models extract features like these from images.

## 2. How does ML on unstructured data work?

* Earlier in the course, you built custom models with BigQuery ML using columns of data as features and predicted the value of your labels. But what about unstructured data? How does ML learn the features? It's best illustrated with a quick example. What do you see here? It's a cat. But, how do you know? Your eyes have the benefit of many years of evolution and intuition to allow you to perceive and interpret those pixels on the screen. How could we teach a machine to understand that this particular collection of pixels is a cat? If you let yourself fall back into rules making, you might say look for cat-like eyes in the images. What about this image? Your brain still knows it's likely a cat, but the machine now has no basis to go off up with our old rule of "look at the eyes." Okay. What if we added a bunch more hard-coded rules? Like look for eyes, ears, and a nose. So is this still a cat? What about this? Again, hard coding rules completely fails us here. That's where deep learning comes into play. As this Wired article states, Iif you want to teach a neural network to recognize a cat, you simply show it thousands of photos of cats and let it figure it out." This is similar to how we teach children to recognize and classify new objects. In 2012, that's exactly what the Google Research team with Jeff Dean and Andrew Ng did. What you see here, is what the deep learning neural network figured out what a cat is based on looking at over 10 million images and processing the model on over 16,000 computers. Now, a familiar architecture for deep learning is the neural network, which is a model inspired by our own human brain. Here, it takes the input image and classifies it as a cat or a dog. Again, we're not telling the model to focus on looking for dark colors or cat whiskers. It builds its own recipe for determining the correct label to apply at the end. As you can see from the image, modern ML models can scale and handle even tricky data points like the dog hiding in a laundry basket. Machine-learning, specifically deep learning, is at the core of many Google products like Google Photos, which can classify and group photos like photos of your pets together in an album. Note that this is now multiple machine-learning models in one. First, it needs to identify whether the photo you just took is of a dog. Second, it needs to identify whether this dog is your pet based on comparing this photo to the history of photos you have with that specific dog. Deep learning, remember, that's a sub-discipline of machine learning, is incredibly useful when we as humans can't even map out our intuition about what makes a prediction correct or not. That's where we just show the computer at 10,000 images of a cat and hope it figures it out. With recent leaps in ML research at Google, Computer Vision has come a very long way.

## 3. Comparing approaches to ML

* We've covered machine learning throughout this course, but that was just one approach, custom model building. In our first challenge, you may recall you inherited a Spark ML job that your data science team created to predict housing rentals. The second challenge had you create a forecasting model with BigQuery ML from scratch, although you've saved time by coding and running it in just SQL. It's now time to zoom back out on approaches to machine learning and even look at some ways we can apply it without having to write code at all. There are three approaches to AI that you should consider. You have already seen and built custom models with BigQuery ML, and we have a separate set of courses on TensorFlow for even deeper model building. A good rule of thumb is to consider custom model building only when you have a lot of data, like 100,000 plus to millions of examples. But what if you don't? Consider using a pre-built AI which are models like the Video Intelligence and Cloud Vision APIs that you saw before. In addition, if you're looking to build a chat bot, start with Dialogflow, which is a full fledged application with ML built in. But what about if the building blocks don't work well for the specificity, you need on your data? That's when you should consider Auto ML as a good candidate. It can even work with just a little bit of data like 10-100 images per label. This lesson covers each of these approaches in detail. First step is using pre-built AI building blocks for your use case. Pre-built models are offered as services. In many cases, these building blocks can be used to create the application you want without the expense or complexity of creating your own models. Cloud-Speech-to-Text converts audio to text for data processing, Cloud Natural Language API recognizes parts of speech called entities and sentiment, Cloud Translation converts text in one language to another, Dialogflow Enterprise Edition is used to build chatbots to conduct conversations, Cloud Text-to-Speech converts text into high-quality voice audio, Cloud Vision API is for working with and recognizing content in still images, and Cloud Video Intelligence API is for recognizing motion and action in video. Good machine-learning models require lots of high-quality training data. As we mentioned before, you should aim for 100,000 plus records to train on for custom model. If you don't have that kind of data, pre-built models are a great place to start. Let's take a look back at one of the most popular ones that I use when I travel overseas, the Translation API.

## 4. Using pre-built AI to create a chatbot

* Next, let's discuss how you can build an intelligent chatbot on top of an already existing solution. Increasingly, customers do not want to go to your website and click on a button or even send you an email, they want to talk to someone interactively. The first solution years ago was setting up a call center and manually answering each call, but that doesn't scale. So many companies have turned to automation and machine learning to help solve this problem. Gartner estimates that in a few years, companies will be investing more in creating conversational interfaces like chatbots than even on mobile app development. Is this chatbot demo just the Speech API paired with a transcription service on top? Nope. What I'm showing here is a high level conversational agent tool called Dialogflow, which has ML built into its conversations. Dialogflow is a platform for building natural and rich conversational experiences. It was formerly named api.ai until Google acquired it and rebranded it into Dialogflow. At its core, Dialogflow is a powerful natural language understanding engine to process and understand natural language input. In other words, it lets you easily achieve a conversational user experience by handling the natural language understanding for you. Dialogflow has seen continuous growth in its developer community and is becoming a conversational experience standard. Google is an AI company with a goal to make AI easy, fast, and useful for enterprises and developers. Dialogflow is built on some of the same world-class AI assets and capabilities that were originally developed for products like Gmail and Search with new ones being utilized on an ongoing basis. It incorporates Google's ever-growing AI experience including machine learning expertise, search capabilities, speech recognition, and of course natural language understanding. It has built-in entity recognition which enables your agent to identify entities and label by types such as person, organization, location, events, products, and media. Also sentiment analysis to give an understanding of the overall sentiment expressed in a block of text. Even content classification, allows you to classify documents in over 700 predefined categories like common greetings and conversational styles. It has multi-language support so you can analyze text in multiple languages. Dialogflow works by putting all of these ML capabilities together which you can then optimize for your own training data and use case. Dialogflow then creates unique algorithms for each specific conversational agent, which continuously learns and is trained and retrained as more and more users engage with your agent. The three core benefits to using Dialogflow are building conversational experiences faster, engaging end users more efficiently, and maximizing reach across geographies and platforms. Build your agent quickly by starting with just a few training phrases or using one of over 40 pre-built agents. These pre-built agents can be used directly out of the box or imported into your agent to build on and customize for your own use case. These include everything from food delivery to hotel reservations to news and reminders. You can easily import these pre-built agents from the Dialogflow console. You can rely on Dialogflow's built-in natural language understanding capabilities, model training, and analytics that are already taken care of for you. Dialogflow's built-in analytics can tell you a lot about your users' interactions with your agent. For example, it can show you the breakdown of how often different intents are triggered. This shows you how your users are spending their time in conversation with your agent. This can also help you prune any underutilized intents. You can also deploy your agent on multiple platforms and utilize single-click integration such as Facebook Messenger, Kik, Twilio, Twitter, Slack, and Cisco Spark just to name a few. The Google Assistant integration allows you to quickly deploy your agent to any Assistant-enabled platform such as the mobile app or Google Home device. The web demo integration allows you to test out your chatbot in an embedded web page. There are also integrations for other popular apps such as Facebook Messenger, Slack, and Twitter which are enabled with quick authentication. With all of these features and the natural-language understanding good built-in, let's see the kind of smart, rich, relevant conversations that Dialogflow can bring to life.

## 5. Customizing Pre-built models with AutoML

* We'll continue our tour of pre-built models with high performing custom ML models with one surprising twist. You can build them with no code. Welcome to AutoML. Let's say I'm a meteorologist and I want to predict weather trends and flight plans from images. There are more than 10 different types of clouds, and each type could represent different patterns of weather that I may want to know ahead of time before it strikes. If I'm a pilot, or farmer, or a travel agency, or even just someone who wants to know if it's going to rain today or not. If we want to predict on weather, this means we need to identify not just that there's a cloud, but also what type of cloud. For example, a cirrus cloud is usually associated with fair weather, whereas cumulonimbus cloud usually foreshadows rain. So let's revisit our Vision API and see how well it does on this new problem. Here we show the image to the Vision API. After I uploaded the image to the Vision API, here are the results for the labels it inferred. The pre-trained model likely was never taught to recognize cloud types to this granularity. We need something a little more custom that we can train ourselves. If you need to extend the capabilities of the AI building blocks, consider AutoML. Here we will use our own labeled dataset of cloud images and train a custom model using AutoML Vision. Let's take a look at the AutoML Vision in action. In this dataset, you've got five image classes corresponding to five different types of clouds. Click on the different labels to filter by cloud type. The numbers tell us how many images are associated with each particular label. Once you've uploaded and labeled your images, you're ready to train your model.
Start transcript at 1 minute 53 seconds1:53
You can specify your model name and your training budget. You actually get one compute hour for free for training. But for datasets with more than 1000 images, you can train for longer. So let's imagine that we received an email notification indicating that our model has been trained and now we want to evaluate it and look at its performance. Simply click on "Evaluate" up at the top and it's going to give you a lot of data about your model. You'll notice a few key metrics that are included here. Area under the precision-recall curve, and you can think of precision as a measure of the quality and recall as a measure of the quantity. So precision is the number of photos correctly classified as a particular label divided by the total number of photos classified with that label. So for all photos that our model classified as cumulus what percentage were correctly classified? Recall is number of photos classified as a particular label divided by the total number of photos with that label. So what percentage of my cumulus labeled photos were correctly classified as cumulus by my model? So you want to think about for your use case, if you care more about classifying photos correctly precision or getting a high number of correctly classified photos. Recall. You probably cared about both, but the metric is typically plotted as a trade-off. Ideally, you'll want to model in the top right corner. Now another great feature on the evaluation page of AutoML Vision is this confusion matrix. So you can see here the photos and which ones were labeled with a predicted label that was either true or false. What you want ideally is a diagonal line like we see here. But it looks like our cirrus predictions aren't performing as well as the other labels. So you can actually click on the items in the confusion matrix to see the photos that were misclassified. So here if I click on this box, it shows me that 23 percent of the photos for cirrus were actually classified as altostratus. So I'll click on that here and it's actually going to bring up the specific images that were classified correctly as cirrus, as well as the ones that are classified incorrectly as altocumulus.
Start transcript at 4 minutes 18 seconds4:18
Lastly, let's show a prediction using this particular ML model. So you can navigate to the "Predict" tab and upload an image. So I'm going to find an image on my computer of a cloud that I want to have the computer identify and predict its cloud type.
Start transcript at 4 minutes 43 seconds4:43
So you can see I've uploaded my photo here and it's predicting it's a cumulus cloud which is correct, and there you have it. That's the AutoML Vision product in action. The big takeaway here is not what we did, but what we didn't do. As we talked about at the beginning, typically when building a custom model, you have several steps which are complex and time-intensive. With AutoML, we don't have to do any of that. However, as great as AutoML is, it can't solve every ML problem, which is why you learned how to build a CNN by hand earlier in the course. Behind the scenes, AutoML is powered by the latest ML research. While your model trains, the AutoML platform actually trains and evaluates multiple models and compares them against each other. This Naznet approach or neural architecture search produces an ensemble of ML models and chooses the best one. Like go and self-driving cars, deep learning is now doing. Deep learning as you saw with the neural architecture search. But how well does a code list model you build with AutoML compare with some of the other image classification models you may have heard of? This graph is a refresh of the best models for ImageNet published in 2017. The x-axis is model size. The y-axis is accuracy. The best possible model position would be the green dot. What you want is a small model left on the x with great accuracy, top of the y. Our world has been trending towards big heavy models that aren't exactly like a brain. That's the black line. AutoML powered by Naznet is shown in the red line. The AutoML networks are smaller and more efficient. I'll provide a link to the Google AI blog so you can track the latest developments. Here's a final recap on when you should use the Vision API versus AutoML Vision. Recall that with AutoML Vision, you are primarily doing classification on image data that you are providing to the service. We did this in our demo where we needed the model to learn a label, the type of cloud that the Vision API didn't know. AutoML requires no coding experience, while the Vision API requires you to be familiar with invoking APIs with a programming language of your choice.

## 6. Building a Custom Model

* Earlier in the course, you saw a few ways to create a custom ML model. We'll briefly review them here, and point you to additional resources where you can practice building more yourself. One of the easiest ways to create a custom model on structured data from scratch, is to try out BigQuery ML. Earlier in this course, you practiced creating a machine learning data set and identifying features and labels. Choosing the right model type for your data set and what you are trying to predict or infer. Providing any custom model options, training the model and evaluating its performance, inspecting what the model learned about the weight of each feature and predicting an unknown future data. I'll provide additional resources and links for you to practice and learn more about BigQuery ML. Lastly, we mentioned that ML engineers often create their own models using open-source libraries, like TensorFlow running on GCP. The value of these models can be huge, if you build and train them correctly or minimal if they are not done well. If you're looking for experience building TensorFlow models on GCP, check out our ML on GCP specialization in our additional resources section of the course.


## QuizNotes

* If you have an image classification task for identifying whether a car is present in a photo or not, which solution should you try first?
	* Try the Cloud Vision API first

## Module Resources

[AutoML Vision documentation](https://cloud.google.com/vision/automl/docs/)
[Vision API documentation](https://cloud.google.com/vision/#resources)
[ML on GCP Coursera course (learn TensorFlow)](https://www.coursera.org/specializations/machine-learning-tensorflow-gcp)

### Additional Coursera courses:

* [Continue with the Data Engineering specialization](https://www.coursera.org/specializations/gcp-data-machine-learning)
* Explore the [ML](https://www.coursera.org/specializations/machine-learning-tensorflow-gcp) and [Advanced ML](https://www.coursera.org/specializations/advanced-machine-learning-tensorflow-gcp) specialization

### Documentation:

[Cloud AutoML](https://cloud.google.com/automl/)

[BigQuery ML](https://cloud.google.com/bigquery-ml/docs/bigqueryml-intro)

[Building custom ML models with TensorFlow](https://www.tensorflow.org/tutorials/)