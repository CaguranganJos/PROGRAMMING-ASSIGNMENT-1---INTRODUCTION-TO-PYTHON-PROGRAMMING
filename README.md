# **Programming Assignment 1: Introduction to Python**
Deadline: August 27, 2025; 11:59 pm

<br>

## I. Table of Contents:
1. Programming Assignment 1.1: Alphabet Soup Problem
2. Programming Assignment 1.2: Emoticon Problem
3. Programming Assignment 1.3: Unpacking List Problem
4. Author
   
## II. Programming Assignment 1.1: Alphabet Soup Problem
Instructions: Create a function that takes a string and returns a string with its letters in alphabetical order
#### Overview of the entire code
```python
def alphabet_order(word):
    word = word.lower() 
    letters = list(word) 
    letters.sort() 
    final = "".join(letters) 
    return final 

print(alphabet_order("hello")) 
print(alphabet_order("Advance")) 
print(alphabet_order("PRoGrAmMinG")) 
```

#### Outcome
```
ehllo
aacdenv
aggimmnoprr
```

#### Step-by-step thought Process
1. This is the main function of this code. I used the function name alphabet_order and the parameter of the function "word" to easily remember where I need to put the words or string I want to arrange alphabetically. The entirety of this function sorts or arranges the characters of the parameter word. 
```python
def alphabet_order(word):
```

2. Before separating the characters in the string, I first used an operation *.lower()* in the string, *word*, to make all the characters lowercase. Since the operation *.sort*, which is used in the next lines of the code, is case sensitive. By doing this, it will prevent the code from putting the upper case letter first; making it more accurate.
```python
word = word.lower()
```

3. Before sorting the letters, I first need to separate each character in the string by using the operation *.list()* and store it in *letters* as a list of characters.
```python
letters = list(word)
```

4. Now that I have turned all letters into lowercase, separated each letter as an individual character, and stored them in *letters*. I can now sort them using *.sort()*, which arranges them in ascending order (based on ASCII order).
```python
letters.sort()
```

5. Now that they are arranged in ascending order. I can now put them together as one word in the string finals. Using the operation *.join(letters)*, it glued all the characters in the list *letters*, making it a one-word stored in string *final*.
```python
final = "".join(letters)
```

6. Finishing the function, all I need to do now is return the value to the function.
```python
return final
```

7. To test if the program runs well, I have printed different styles of words, all lowercase, one uppercase, and random uppercase to test the accuracy of the code.
```python
print(alphabet_order("hello"))
print(alphabet_order("Advance"))
print(alphabet_order("PRoGrAmMinG"))
```

<br>

## III. Programming Assignment 1.2
Instructions: Create a function that changes specific words into emoticons. Given a sentence as a string, replace the words smile, grin, sad, and mad with their corresponding emoticon:
#### Overview of the entire code
```python
def emotifier(sentence):
    emoji = {"smile": ":)", "grin":":D", "sad":":((", "mad":">:("}
    words = sentence.split()

    for i in range(len(words)):
        lower_case = words[i].lower()
        if lower_case in emoji: 
            words[i] = emoji[lower_case]

    result = " ".join(words) 
    return result 

print(emotifier("This is smile"))
print(emotifier("This is Grin"))
print(emotifier("This is SaD"))
print(emotifier("This is MAD"))
```

#### Outcome
```
This is :)
This is :D
This is :((
This is >:(
```

#### Step-by-step thought Process
1. I first defined a function named *emotifier* that has a parameter named *sentence*. This function contains the dictionary, split operation, and a looping statement that changes the words that have a corresponding *key* in the dictionary. Before the "for loop statement", I first made a dictionary containing keys that are the words and values that are the emoticons. Now that I have made the dictionary, the next thing I need to do is to treat the words in a sentence as different valued characters using the operation *.split*, which made the sentence to a list of words.
```python
def emotifier(sentence):
    emoji = {"smile": ":)", "grin":":D", "sad":":((", "mad":">:("}
    words = sentence.split()
```
2. Now that the sentence is split into individual words, I can make a for loop statement that changes specific words into an emoticon. However, there is a chance that the words and the keys inside the dictionary may not be equal due to the difference in cases(uppercase and lowercase). To solve this, I first use the operation *.lower()* to make all the words lowercase stored in *lower_case* as a list. The if statement indicates that if a word stored in *lower_case* has a corresponding key, then it will be replaced with the key's value. Then I needed to join the words together as well as the "replaced word" into one sentence using the operation *.join()*. Lastly is to return the result into the function.
```python
for i in range(len(words)):
        lower_case = words[i].lower()
        if lower_case in emoji: 
            words[i] = emoji[lower_case]

result = " ".join(words) 
    return result 
```
3. To test if the code runs well and is accurate, I printed sentences containing words that represent an emoticon. These words have different styles: all lowercase, one uppercase, random uppercase, and all uppercase. With these, I can test the code if it runs well even if the words have different cases(lower/upper). 
```python
print(emotifier("This is smile"))
print(emotifier("This is Grin"))
print(emotifier("This is SaD"))
print(emotifier("This is MAD"))
```

<br>

## IV. Programming Assignment 1.3
Instructions: Unpack the list writeyourcodehere into three variables, being first, middle, and last, with middle being everything in between the first and last element. Then print all three
variables.
#### Overview of the entire code
> 1st code using numbers
```python
numbers = [1,2,3,4,5,6] 

first = numbers[0] 
middle = numbers[1:-1] 
last = numbers[-1] 

print("first:",first) 
print("middle:",middle) 
print("last:",last)
```
##### Outcome
```
first: 1
middle: [2, 3, 4, 5]
last: 6
```
> 2nd code using words
```python
words = ["Apple", "Banana", "Cherry", "Dragon Fruits", "Egg Plant", "Finger Lime"] 

first = words[0] 
middle = words[1:-1] 
last = words[-1] 

print("first:",first) 
print("middle:",middle) 
print("last:",last)
```
##### Outcome
```
first: Apple
middle: ['Banana', 'Cherry', 'Dragon Fruits', 'Egg Plant']
last: Finger Lime
```

#### Step-by-step thought Process
1. I first made a list containing words and numbers that I will use as my list to unpack. I made three variables: first, middle, and last. Since the first element is in the 0 index, then I can store that element in variable *first* using *list_name[0]*. This method is also applicable to the variable *last*, since the index -1 is always the last element in a list, therefore I can store the element in index -1 to the varaible *last* using *list_name[-1]*. Lastly, I used the range operation in the middle variable using *list_name[1:-1]*, this operation indicates that all the elements starting from index 1 to index -1 (excluding -1) will be in the list contained in variable *middle*.
> Using numbers:
```python
numbers = [1,2,3,4,5,6] 

first = numbers[0] 
middle = numbers[1:-1] 
last = numbers[-1] 
```
> Using words:
```python
words = ["Apple", "Banana", "Cherry", "Dragon Fruits", "Egg Plant", "Finger Lime"] 

first = words[0] 
middle = words[1:-1] 
last = words[-1] 
```
2. To test if the code runs well I printed  the words: "first", "last", and "middle" together with their corresponding variables.
using numbers
```python
print("first:",first) 
print("middle:",middle) 
print("last:",last)
```
using words
```python
print("first:",first) 
print("middle:",middle) 
print("last:",last)
```

## V. Author
Name: Cagurangan, Jos Kendirck L.
<br>
Section: 2ECE-B
