# LeadGenerator
🎯 Qualify sales leads with machine learning

Setup

Start off by running the following command:

pip install -r requirements.txt
You'll also need to download the stopword from the nltk package. Run the Python interpreter and type the following:

import nltk
nltk.download('stopwords')
1. Experiment with your own algorithms

We'd love to see more algorithms on the leaderboard, so send us a pull request once you've implemented one.


To test our your own algorithm, simply add it the run.py file and run the script:

python run.py
Thanks to lampts for implementing the best performing algorithm so far, the SGDClassifier.

Leaderboard:

Algorithm	Precision	Recall	F1 Score
SGD Classifier	0.872	0.940	0.905
Random Forest	0.845	0.915	0.878
PS: We're also experimenting with a neural net (in TensorFlow) in the nn.py file.

2. Create your own lead qualifier

To create your own lead qualifier, you'll need to get hold of company descriptions (to create your dataset). We currently use FullContact for this.

Note: We've added dummy data, so that you can run both scripts without getting errors, and to give you examples on how the sheets should look like.

Train Algorithm

This script trains an algorithm on your own input data. It expects two excel sheets named qualified and disqualified in the input folder. These sheets need to contain two columns:

URL
Description


Run the script:

python run.py
It'll dump three files into the qualify_leads project:

algorithm
vectorizer
tfidf_vectorizer
You're now ready to start classifying your sales leads!

Qualify Leads

This is the script that actually predicts the quality of your leads. Add an excel sheet named data in the input folder. Use the same format as the example file that's already there.

Run the script:

python run.py
It'll output an excel sheet with a column named Prediction, where 1 equals qualified and 0 equals disqualified:

