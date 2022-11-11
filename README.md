# preprocessing
This module transforms raw text resumes into matrices or vectors for training

============Folder structure==============

This module contains 2 main sub-directories
- data
- preprocessing

The sub-directory preprocessing contains the class Preprocessor which is designed to 
proprocess raw text resumes contained in the file (data/resume_samples.txt). 

# Dependencies :
- Anaconda
- numpy
- nltk
- gensim
- spacy

1. conda create -n resume python=3.7 && conda activate resume

2. pip install spacy==2.0.5 scipy==1.4.1 numpy==1.14.3 nltk==3.6.3 gensim==3.8.3 pillow

3. python -m spacy download en_core_web_sm

4. python -i
   import nltk
   nltk.download('stopwords')
   nltk.download('punkt')
   exit()
   
5. sudo apt install git-lfs

6. git clone https://github.com/florex/preprocessing && cd preprocessing && git lfs install

7. sed --in-place 's/self.output_dir = "E:\/Thèse\/datasets\/dws\/"+str(self.cv_length)/self.output_dir = "output"/g' preprocessing/PreProcessor.py

8. mkdir output

9. python process_data.py



# Execution :
To preprocessed raw text resumes,   

First, change the path to the output_dir in the file preprocessor.py (edit the property output_dir of the class Preprocessor)

Then run the command :

python process_data.py

This operation creates subdatasets corresponding to the resume length in the directory <output_dir> 

The operation creates two additional files :
   - resumes_refs.py : which associates a sample data id to the path of the original resume.
   - resumes_words.py : which represents a dictionary where keys are hashed words'vectors and values are corresponding words


The resulting dataset is in form of a matrix : 

The first column of the matrix is an integer representing the id of the resume.

The last 10 columns represent the classes of the resumes.

The columns between the id and the classes represent the flatten form of a resume matrix.

By default, each resume is encoded into a matrix of shape (500,100).

# Cite this :
Jiechieu, K.F.F., Tsopze, N. Skills prediction based on multi-label resume classification using CNN with model predictions explanation. Neural Comput & Applic (2020). https://doi.org/10.1007/s00521-020-05302-x
