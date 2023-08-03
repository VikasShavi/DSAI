# Word Count

## This example gives us the every word count present in the file.

## We have three files:
  1. word_count_data.txt ---> this has several words. We have to get word counts from this file.
  2. mapper.py ---> this will separate all words and print each with a format "word 1".
  3. reducer.py ---> this will read all those printed outputs from mapper.py and make a dictionary of words as key and their counts as the corresponding values.

## To run all this using hadoop:
  1. Making a directory named "word_count_in_hadoop" in hadoop to store our files,
     ```
     hdfs dfs -mkdir /word_count_in_hadoop
     ```
  2. Copying the data file "word_count_data.txt" to the folder,
     ```
     hdfs dfs -copyFromLocal ~/Downloads/word_count_data.txt /word_count_in_hadoop
     ```
  3. To check our file is in the correct folder,
     ```
     hdfs dfs -ls /word_count_in_hadoop
     ```
  4. Make the mapper.py and reducer.py as executables,
     ```
     chmod 777 mapper.py reducer.py
     ```
  5. Running the mapper.py and runner.py to get word counts in a file named "output"
     ```
     hadoop jar ~/Download/hadoop-streaming-3.2.4.jar -input /word_count_in_hadoop/word_count_data.txt -output /word_count_in_hadoop/output -mapper ~/Download/mapper.py -reducer ~/Download/reducer.py
     ```
  6. Now to read the output,
     ```
     hdfs dfs -cat /word_count_in_hadoop/output
     ```
