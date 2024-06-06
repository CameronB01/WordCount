# WordCount

I copied your README exactly.

I used the austen.txt, shelley.txt, and bronte.txt books as the dataset.

As for editing the Python script so that instead of treating the words as "strings separated by spaces" it treats them as "contiguous strings of letters" I simply added two lines.

This first line grabs the contiguous strings of letters.
```
words = re.findall(r'[a-zA-Z]+', line)
```

This second line turns all the letters to lowercase to normalize all the words (this line is inside the for loop).
```
word = word.lower()
```

After creating this new Python file I inserted it into the scripts folder.
```
curl https://raw.githubusercontent.com/CameronB01/Hadoop/main/mapper_v1.py -o scripts/mapper_v1.py

chmod 777 scripts/mapper_v1.py
```

I then ran the following Mapred Stream to count the words.
```
hdfs dfs -rm -r /user/sandbox/words
mapred streaming \
  -input /user/sandbox/books \
  -output /user/sandbox/words \
  -mapper mapper_v1.py \
  -reducer reducer.py \
  -file scripts/mapper_v1.py \
  -file scripts/reducer.py

hdfs dfs -ls /user/sandbox/words
hdfs dfs -head /user/sandbox/words/part-00000
```
