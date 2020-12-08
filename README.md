# Custom-Trained-Named-entity-recognizer-using-Spacy-library-for-resume-Data-extraction /n

Hello all, sharing one of my experience when i was working on a project to automate the process of extracting meaningful information from Resume and cv. As largest organization receives plenty of resume per day and its become an headache for HR people to went through all the resume …. 
so we build an platform which auto collect the useful information from resume and sending it to HR dashboard…
Due to company policy here i am just sharing the demo and path we followed ..and getting the available data on internet and showing result..
Named-entity recognition (NER) (also known as entity identification, entity chunking and entity extraction) is a sub-task of information extraction that seeks to locate and classify named entities in text into pre-defined categories such as the names of persons, organizations, locations, expressions of times, quantities, monetary values, percentages, etc.


Dataset Collection and annotation…biggest shit
while working on this real time project it tooks pretty much time to collect the data and annotate them…
we gather almost 3000 resume and annotate them using annotation tool such as The data consists of resume which is extracted from a PDF file, followed by a dictionary consisting of a label (Name, Designation, Location, Email-Address etc.) and the start and end index of the value in the resume.
(0, 12, 'Name')
here for demo purpose we are taking only 200 resume with annotation available online publically


We will first load a black SpaCy english model. Then we will write a function which will take the training data as the input. In the function, first we will add a ner i.e. Named Entity Recognition in the last position in the pipeline. Then we will add our custom labels in the pipeline.
Now we are going to prepare our data for training. We are disable all the pipeline components except ner. We are only going to train ner. We are going to train for 30 iterations.
 At each iteration, the training data is shuffled to ensure the model doesn't make any generalizations based on the order of examples. We are again going to read the training data. 
Another technique to improve the learning results is to set a dropout rate, a rate at which to randomly "drop" individual features and representations. This makes it harder for the model to memorize the training data. We have added a dropout of 0.2 which means that each feature or internal representation has a 1/5 likelihood of being dropped.
