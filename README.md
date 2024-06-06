# WordCount

I copied your README exactly.

As for editing the Python script so that instead of treating the words as "strings separated by spaces" it treats them as "contiguous strings of letters" I simply added two lines.

This first line grabs the contiguous strings of letters.
```
words = re.findall(r'[a-zA-Z]+', line)
```

This second line turns all the letters to lowercase to normalize all the words (this line is inside the for loop).
```
word = word.lower()
```
