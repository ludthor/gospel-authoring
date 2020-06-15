# gospel-authoring
DNN applied over the Four-Gospel Corpus (RV60): The aim is to identify the most probable BOOK given some fragment.

The original data was extracted from: https://www.unoenelsenor.com.ar/biblia.htm and after was manually splited, extracting the books of interest for the project.

- 14/06/2020

At this point this project is built on two files:

1. generate.ipynb: This script takes care of the data extraction. It reads the TXT files (One per each gospel) and generates multiple CSV files stored in the 'processed/' folder. 

2. script.ipynb: The main script. It loads the CSVs, merge them in one only file. Also, creates the flow for the training using the fast.ai built-in functions. 

The first iteration of the training was completed with results:
A lot of work is needed here for improvements.
_______________________________
train_loss: 0.692559
valid_loss: 0.673879
accuracy: 0.593023
_______________________________

- 15/06/2020

Parametric optimization: I adjusted the batch_size to 16
                         Changed the optimizer for RMSProp
                         Changed the learning rate to a slice [1e-3 : 1e-2] 
                         Changed the loss Function to Cross Entropy
                         
Balance the dataset by sampling to 170 observation per book.

Plot the confusion matrix

Display a sample of the prediction using learn.show_results()

Test on Specific data: Fragments of "Acts of the apostles" and "First Epistle of John" -> Test succesful

Troubles: I'm starting to see the fact that the trhee first gospels (Matthew, Mark, Luke) have a common origin. Mark got a little amount of predictions and Matthew and Mark fragmenst are usually false attributed to Luke. This effect was reduced a bit using the balance samplig at the begining. 

Last epoch metrics:
________________________________
train_loss: 1.328234
valid_loss: 1.292800
accuracy: 0.411765
________________________________

*Note: In some other rounds of training, I got near 46% accuracy results.
