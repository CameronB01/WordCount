# WordCount

I copied your README exactly.

For editing the python script from treating words as "strings separated by spaces" to treating them as "contiguous strings of letters" I simply added two lines.

This line grabs the contiguous strings of letters.
```
words = re.findall(r'[a-zA-Z]+', line)
```

The line turns all the letters to lowercase to normalize (this line is inside the for loop).
```
word = word.lower()
```
