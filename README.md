# Creating a machine learning model in 2 hours to project the best fantasy baseball players
My attempt to make my first machine learning algorithm. This model projects the MLB baseball players that will produce the most fantasy points in under 2 hours (before my draft). This is by no means a finished or polished product, just something to showcase what I can do in a time crunch. This is my first attempt at using machine learning. Because of the time crunch, I did not make a lot of comments or explain too in-depth what I was doing in many of the steps. I plan on improving upon this project in the future since I did make some mistakes that I could not feasibly solve in 2 hours in a different repository.

## Table of Contents
* [Introduction](#2-hour-ml-challenge)
* [Setup Instructions](#setup-instructions)
* [Methodology](#methodology)
* [Results](#results)
* [Errors and Mistakes](#errors-and-mistakes)
* [Improvements](#improvements)
* [Acknowledgments](#acknowledgments)
* [License](#license)
* [Contact Information](#contact-information)

## Setup Instructions
**Run the Notebook locally**
1. **Clone the repository**
   * Clone the repository to your local machine using the following commands in a Bash shell terminal:
     1. `git clone https://github.com/ArdenAChen/2-Hour-ML-Challenge.git`
     2. `cd 2-Hour-ML-Challenge`
2. **Install Jupyter Notebooks and necessary libraries**
   * To install Jupyter Notebooks and the libraries, input into the terminal: `pip install -r requirements.txt`.
     * The packages included in `requirements.txt` are `Jupyter Notebooks`, as well as the libraries `pandas`, `NumPy`, and `scikit-learn`
3. **Open and Run the Notebook**
   * Start Jupyter Notebook by running the following command in the terminal: `jupyter notebook`
   * Navigate to the file `fantasy_baseball.ipynb` in the browser and open it
   * At the top, under `Run`, click on `Run All Cells` to run every cell. You can also run each cell individually by pressing `Shift` + `Enter`, or `Ctrl` + `Enter` (`Cmd` + `Enter` for Mac).

## Methodology
I spent around 20 minutes thinking about what data would be the best for my analysis and getting the data, as I only wanted to include factors that were the most indicative of success. I had to get two different datasets, one for pitchers and one for hitters. I ultimately got all my data off statcast data from [Baseball Savant](https://baseballsavant.mlb.com/). I then had to wrangle the data by getting rid of duplicate rows and handling columns with empty values. I also calculated the fantasy points for each of the players based on Yahoo Fantasy's standard scoring system. I then normalized the numerical data, and trained scikit-learn's [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) model. I ran some simple tests on the model (R^2 and MAE), and displayed the top 40 scoring players from 2024 and 2023 as the model's best projected players.

## Results
The model works as a simple predictor of which players will score the most points based on that player's production in 2024 and 2023. The model is not very high-depth, but it can accurately determine which players had great fantasy production, and use that data to project who will be good in 2025.

## Errors and Mistakes
While I tried my best to perfect the project in 2 hours, there were some mistakes I caught that were out of the time scope of 2 hours to fix such as:
* Pitcher data lacking saves statistic (crucial for calculating fantasy points for relievers)
* Batter data lacking runs scored statistic (crucial for calculating fantasy points for hitters)
To solve these errors I would have had to try to find these stats off of a different website or dataset which would have involved merges and more data wrangling which I could not afford to do in the time-span.

## Improvements
Below are things that are not necessarily errors but things that I do feel like I could improve upon:
* Make the pitcher model: If you look through the notebook, you may notice I was also working on the pitcher dataset, but I realized I did not have enough time to do both in 2 hours and needed something that I could use right before my draft, so I settled for just making the hitter model first. It would likely follow the same principles as the hitter model though.
* Feature selection: The model was very basic as it only took into account the counting stats and a few of the stats that I considered good indicators for achieving higher counting stats. It simply chose players with great fantasy production from last year (or 2023 if they were unable to play many games in 2024) as a predictor for success in 2025. I would like to add more depth to the model, and I might even change what machine learning model I use entirely.
* Actual fantasy points projection: I was unable to find out how I could convert the normalized values back to the actual values. While I achieved my goal of making something that would rank players based on projected fantasy points, I could not see how many points they're projected, just their Z-scores.

## Acknowledgements
* Thanks to MLB's [Baseball Savant](https://baseballsavant.mlb.com/) for providing the data used in the project.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact Information
For any questions or feedback, please contact me at `aac@ucsb.edu`.
