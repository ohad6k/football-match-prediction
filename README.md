Football Match Outcome Prediction — Serie A
Project Overview

This project predicts the outcome of Serie A football matches (Win, Draw, Loss) using historical match data enriched with advanced feature engineering and machine learning models.
The pipeline covers data cleaning, feature engineering, model training, hyperparameter tuning, and evaluation.
To view the projcet report including results you can download MatchPrediciton.pdf file.
 Data Source

    Dataset: matches_serie_A.csv (includes match statistics, team lineups, venues, dates, and results)

    Data contains both raw match info and advanced statistics such as expected goals (xG), possession, shots, and more.

 Data Preparation & Feature Engineering

    Removed unnecessary columns (e.g., referee, round, notes).

    Filled missing attendance data by average home team attendance.

    Imputed missing numeric stats (xG, xGA, Dist, FK) using medians.

    Encoded categorical features like Result (W=2, D=1, L=0), Venue, Day of Week, and Season Stage.

    Processed dates and times to extract features like month, day, and whether the match was in the evening or not.

    Cleaned and split team formations into consistent numeric features.

    Calculated rolling averages and momentum features for the last 5 and 30 matches.

    Computed custom features:

        Win/Draw/Loss streaks

        Rest days and games played in the last 10 days (fatigue factors)

        Elo ratings per team and Elo difference between teams before the match

        Opponent form and fatigue statistics

        Head-to-head averages

        Home vs away performance differences

        Momentum and trend features based on xG, shots, and goals

 Modeling Approach

    Selected the top 20 most important features based on Random Forest feature importance.

    Split data into training (80%) and testing (20%) sets with stratified sampling on the Result.

    Standardized numeric features using StandardScaler.

    Trained and evaluated multiple classification models:

        Support Vector Machine (SVM)

        Gaussian Naive Bayes

        Gradient Boosting Classifier

    Performed 5-fold stratified cross-validation to evaluate models on the training set.

    Conducted hyperparameter tuning with Grid Search for SVM and Gradient Boosting.

    Final evaluation on the test set included accuracy, precision, recall, F1-score, confusion matrix, and classification report.




 How to Run

    Ensure you have required libraries installed:

pip install pandas numpy scikit-learn matplotlib

    Place matches_serie_A.csv in the /data folder.

    Run the main preprocessing and modeling script.

    Inspect output metrics and saved models.
