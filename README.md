Movie Recommender System
This project demonstrates a movie recommender system using Python. The system is designed to recommend movies based on various features
like genres, keywords, cast, and crew. The project is implemented using a combination of data processing and machine learning techniques.

Dataset
The project uses two datasets:tmdb_5000_movies.csv: Contains information about 5,000 movies including their genres, overview, etc.
tmdb_5000_credits.csv: Contains details related to the cast and crew of the movies.
These datasets are merged on the title of the movies to form a consolidated dataset for further processing.

Project Workflow
Data Loading:The datasets are loaded into Pandas DataFrames.
Data Merging:The movies and credits datasets are merged on the movie title.
Data Cleaning:- Unnecessary columns are dropped, and the dataset is filtered to include only relevant columns such as movie_id, title,
              overview, genres, keywords, cast, and crew.
              - Missing values are handled, and duplicates are removed.

Feature Extraction:The genres, keywords, cast, and crew fields are processed to extract relevant information. 
For example:- Genres and keywords are converted from a JSON-like structure to a list of strings.
            - The top 3 cast members are extracted.
            - The director's name is extracted from the crew.
The overview column is tokenized into words.

Data Preprocessing:
Spaces within names and tags are removed to create a more consistent structure.
A new tags column is created by combining the processed overview, genres, keywords, cast, and crew data.

Building the Recommender System:
A similarity matrix is generated based on the tags column using methods such as TF-IDF or CountVectorizer (not fully detailed in the preview).

Making Recommendations:Based on the similarity matrix, recommendations for movies are generated when a user inputs a movie title.
