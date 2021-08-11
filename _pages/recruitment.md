---
layout: page
permalink: /recruitment/
title: recruitment
#description: 
nav: true
---

Welcome! Thank you for your interest in working with me. 

I am generally interested in ***all kinds of machine learning problems***, and I'd be thrilled to work with you if you reach out to me with your favorite research topics. 
If you'd like to, please send your application to <hongyuan@ttic.edu>. 
Your application should include
- your up-to-date CV; 
- 1~3 contacts for (if needed) reference letters; 
- what you'd like to work on, and why you do; 
- a short description about your background and how it has prepared you for your research interests. 

Of course, you might be a technically strong student that has genuine interest in research but doesn't know where to start. 
In that case, I would highly recommend you think about the following projects that I am currently working on. 

#### Event Sequence Modeling

*Events are everywhere.* They include: 
- *Medical events.* Each patient has a sequence of doctor’s visits, tests, diagnoses, and medications. 
- *Consumer events.* Each online consumer has a sequence of online views and purchases. 
- *Life events.* Some people use smart devices to record their eating, traveling, walking, and sleeping. 
- *Social media events.* Facebook and Twitter users generate posts, shares, comments, and messages. 
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/med-example.jpeg">
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/edu-example.jpeg">
    </div>
</div>
Two examples of event sequences in the medical (left) and educational (right) domains. 

I build *neural probabilistic models* for sequences of events, with which one could *predict what events will happen in the future and when they will happen*. 
For example, one may probabilistically predict a patient's prognosis, eventual diagnosis, and treatment cost based on their symptoms and treatments so far. 

My past work includes flexible models ([neural Hawkes process](https://arxiv.org/abs/1612.09328) & [neural Datalog through time](https://arxiv.org/abs/2006.16723)) and efficient algorithms ([particle smoothing](https://arxiv.org/abs/1905.05570) & [noise contrastive estimation](https://arxiv.org/abs/2011.00717)). 

Future research directions might be: 
- breaking the limitation of autoregressive neural models (what are they?); 
- exploring data augmentation techniques (what would be the challenges?); 
- faster inference (why is the current rejection-sampling method slow?);
- ...  

Maybe you can even come up with your own research questions in this area? 

#### Event-Based Reinforcement Learning

*Predictive models may help decision making.* 
In an interactive environment, an intelligent agent may act more wisely if it can predict *what* will happen and *when* they'll happen in response to each action that it may take. 

In the medical scenario shown below, an intelligent assistant reads the previous electronic health records, predicts the future condition---in this case, severe illness and a high-risk surgery---of the patient, and suggests right clinical measurements (to gather more information) and treatments (for improvement) at right times, aiming to cure or alleviate the illness and make that high-risk surgery no longer needed. 
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" style="max-width: 50%;" src="{{ site.baseurl }}/assets/img/med-rl-example.jpg">
    </div>
</div>
<!---
- *Medical events.* An intelligent medical assistant may suggest tests and treatments at the right time, to gather information and improve the patient's future health condition. 
- *Consumer events.* An intelligent shopping guide may learn to intersperse the customer views and purchases with offers, recommendations, and navigation guidance, aiming to maximize long-term customer satisfaction, including engagement and transaction speed. 
- *Life events.* By anticipating behaviors, a smart device may perform helpful supportive actions, including issuing reminders and placing orders in advance. 
- *Social media events.* An intelligent social assistant may learn to choose the best timing to notify each user of (say) each incoming message, according to the sender and/or content, thus to maximize long-term user satisfaction. 
-->

<br>
Similar intelligent agents can also benefit other application domains like education, social, etc. 

I work on general techniques that can use reinforcement learning (RL) to enable such agents. 
What motivates novel RL methods is that we have to consider *timings* in those applications: 
- when reading previous events, the agent needs to take their occurrence times into account; 
- when predicting future events, the agent needs to predict when they will happen; 
- when taking actions, the agent needs to know when to do them---e.g., too early or too late clinical treatments may not really help but only be a waste of resources. 

<!---
Advances in this area would call for: 
- new formalism---timing is not included in Markov decision processes; 
- new algorithms---when to do it, that is a question; 
- scarce interactions---we are often not allowed to interact with real users (patients, students, ...). 
-->

#### Novel Transformer Models

Transformer architectures have shown astonishing performance in a wide range of machine learning tasks such as machine translations, few-shot learning, multi-modal learning, etc. 
A large body of research has been done to improve its efficacy and efficiency. 

I am generally interested in whether any of the following techniques would help a Transformer model learn and generalize better: 
- *look-ahead*: how each possible word may (re-)shape the model distribution over future possible words;  
- *uncertainty quantification*: how uncertain the model is about its predictions; 
- ... 

