# Relation Prediction of Tolkien's Stories
Relationship extraction of The Hobbit and The Lord of the Rings
The project uses the sentences with characters' name to build a relation prediction model through DistilBERT.
## The Content and Source of the Tables
#### name.xlsx
name.xlsx concludes the name, male, race and other names of the characters
The table is downloaded from https://lotr.fandom.com/wiki/Main_Page. Thanks a lot!!!
#### c1_c2_done.xlsx,neo4j.xlsx
c1_c2_done.xlsx concludes the relationship tuples extracted from the books. Only the tuples from the sentences, which conclude more than two characters, are extracted.
The table is created based on the background of the books, please let me know if there are any errors, thanks!
neo4j.xlsx has similar content with the c1_c2_done's. The source of the sentence is marked in the table as the value "book".
## The purpose of each part in the code.

### sentence extraction
This part shows the way I used to achieve the sentences conclude characters.
You can choose to pass this part cause the tables we need to build the model is already exist
### Create the Relationship Tuple
You can choose to start from the *create the relationship dataset for the model*, cause the tables we need to build the model is already exist.
This step helps to build dataset *train_set* and *test_set* for the next step. The procedures to form the datasets are as follow:
  1.  Add the character1 and character2 into the sentence concludes them to build a new sentence like <$character1$character2$sentence>.
  2.  Add races of the characters into the sentence and get the new sentences like <$character1$character2$race1$race2sentence>. The information about race is useful in the recognition for the background of the books. You can choose to add more information or just pass this step.
### DistilBERT Model
### LSTM and TextCNN with Word2Vec
These two parts are for the relation prediction. The model can reach higher accuracy and f1-score compares wigh LSTM and TextCNN.
### Visualization with neo4j
Through neo4j, we can do the visualization easily like this.
![graph (20)](https://user-images.githubusercontent.com/78463659/160290072-03446bc3-ee46-46b6-a516-bf65ade370d8.png)
![graph (19)](https://user-images.githubusercontent.com/78463659/160290074-51c07bd0-379e-4a77-8faf-44cea6347369.png)
