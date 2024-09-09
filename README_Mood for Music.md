
# Mood for Music

The mood detector model detects the mood of the user from still images and videosand recommends music accordingly. The system uses images or video analysis to infer user's mood and provide personalised music recommendation to enhance their emotional experience. After predicting the emotion from face our system takes the predicted emotion as input and generate recommendation by processing the provided dataset. We will predict the music mood from a model trained with data_moods.csv. The recommender system will generate top 40 songs to recommend to the user.

## Focus Areas
**Image/Video Analysis**: Develop algorithms to analyze still images or videos and extract mood-related features.
- **Mood Classification**: Create a machine learning model that classifies the user's mood based on the extracted features.
- **Music Recommendation**: Build a music recommendation engine that suggests music based on the user's mood classification.
- **User Interface**: Design an intuitive and user-friendly interface to capture images/videos and display music recommendations.
## Data Sources
The dataset for this project comprises images categorized as ‘Happy’, ‘Sad’.

## Music Mood Prediction
Every songs in the main dataset data_moods.csv is predicted to one of the mood among 4 moods listed below-

Happy 2. Sad 3. Energetic 4. Calm
By using a music mood classifier model we predicted each songs mood in our intermediate dataset MusicMood in the Dataset folder.
## Music Recommendation
Our main project file is music_recommender.ipynb file. This recommendation system is using content based filtering. We follow these steps to recommend music-

Dataset Pre-processing
Feature Engineering
Connect to Music API
Create Playlist Vector
Generate Recommendation using cosine similarity
So according to this project, we will take an image of an user and predict emotion using Mood Detection model. By prioritizing the songs from our main dataset MusicMoodFinal.csv with music mood comparing with different face emotion, this system will generate top 40 songs to recommend for a particular spotify playlist.
## Reference
The project necessitates the following reference: Python 3.x NumPy Pandas Matplotlib scikit-learn
