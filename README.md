# Cooking Mining 

Use cooking mining to generate log files form recipes. This log files are suitable for process mining. Use this logs to discover the unified process behind your favorite food.

## Setup

### TreeTagger
1. Install TreeTagger: https://www.cis.uni-muenchen.de/~schmid/tools/TreeTagger/

2. Make sure to follow the install instructions.

3. Use the **English parameter file (BNC tagset)** and save it as english.par in the lib folder of the TreeTagger.

### Data set
1. Download the Data Set: https://www.kaggle.com/shuyangli94/food-com-recipes-and-user-interactions?select=RAW_recipes.csv

2. Create an /data folder in the project and copy the **RAW_recipes.csv** into the folder.

## Usage

Open the nlp.ipynb with jupyter lab.

Choose if you want to select the recipes by recipe name or categories (selectByName = True/False).

- **By recipe name**: Define the name by using the variable name. All recipes containing a substring of this name are selected.

- **By categories**: Define the categories by using the variable categories. All recopies containing all the defined categories are selected.

Define the maximum numbers of recipes you want to have in your log file. By using the max_recipes variable. 

Execute the file to generate a log file.

## Result
 
The resulting log file is a csv file containing following columns:

- **case_id**: id of the case (recipe ID)
- **event_id**: id of the event
- **order**: the estimated time of execution(duration in minutes/stepID)
- **activity**: the executed activity (cut,mix,..)
- **ingredient**: the used ingredient (apple,salt,..)

## How to use this file

Use the file as input for process mining tools (ProM,Disco,...) make sure to use the order column as timestamp with the pattern 'm' for minutes.
