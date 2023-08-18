# Find-Word

Find-Word is a problem from the [java-tutorial](https://github.com/its-triple-s/java-tutorial) created by [@its-triple-s](https://github.com/its-triple-s).

This java program finds the total number of times a word has appeared in a text file.
This program takes a command line argument such as `texts/short.txt` indicating the text file it must read. It then takes a word as user input. The program then reads the entire text file to find the total number of occurrences of that word.

This problem has been designed to help learners develop the logic of:
- how to skim through Strings
- incorporate various String and char functions
- use Scanner and File objects
- implement Call by Reference
- utilize command line arguments

## Description

Find-Word works as a word searching tool for a text file, its nature is similar to the feature we often use in documents to find matching words by pressing **Ctrl + F**. The output of this program should be the total number of times a word has appeared (or occurred) in a text file.

**Note:**

- To make things less complex, this program shall only find the occurrences of one single word (which doesn't contain any letter or symbol) and not a sequence of words or a phrase.

- We are also assuming that the user enters the proper path to a text file as the first argument while executing the program.

You have been provided with a few text files in the folder [texts](texts) which are to be used during the execution of a program.

## Example

In the text file [longer.txt](https://github.com/geekygiganerd/Find-Word/blob/main/texts/longer.txt) the word 'Mary' occurs 2 times.

![find-word-longer](https://github.com/geekygiganerd/Find-Word/assets/128626253/27979515-8536-4d9d-8c8a-ba9965f0e095)

So, the program must output 2 as the occurrences for the word 'Mary' in [longer.txt](https://github.com/geekygiganerd/Find-Word/blob/main/texts/longer.txt).

![word-search-longer](https://github.com/geekygiganerd/Find-Word/assets/128626253/45d10e41-4927-4dd5-b025-900f18344935)

## How to solve? 

The entire process can be broken down into 4 simple steps:
- [Input the path to text file and the word to be searched](#input)
- [Scan each line from the text file](#scan)
- [Count the occurrences of the word in each line](#count)
- [Display the output](#Display)

There are 3 methods in the program:
- `void main(String args[])`
- `int find(String word, String text)`
- `void display(int occurences)`

### Input:

The inputs are taken in the `main()` method. The path to the text file must be entered as the first command line argument during program execution. For example

```
$ java FindWord texts/short.txt
```

Here `short.txt` is the text file in the folder `text`. Since the `main()` method accepts a **String array** named `args` as parameter, `texts/short.txt` is stored as the first element int the array, i.e. `args[0] = "texts/short,txt"`. This element is then used to create a File object named `textfile`.

The search-word must be entered by the user upon being prompted and stored in the variable `word` using a Scanner object `scan`.

### Scan:

The next important step is to scan each line from the text file. This is done using a Scanner object `scan` created for the File object `textFile`.

Within the **while-loop** the [hasNextLine()](https://www.geeksforgeeks.org/scanner-hasnextline-method-in-java-with-examples/) method of the Scanner class is used to check if `scan` has another line, if so then the line is stored in a String variable `text`.

`text` is searched through to find the occurrences of `word` using the user-defined `find()` method, which returns the count of occurrenes. This returned integer value is then added to the variable `occurrences` which was initially set to 0.

This process is repeated using the loop to find the total number of times `word` appeared in `textfile`.

### Count:

To count the number of times `word` appeared `text` the user-defined `find()` method is called by Reference (using the class object `obj`) in `main()` method. `find()` accepts two String arguments: the search-word and the line of text respectively.

You must apply your logic in the **for-loop** to go through each word in `text` and count the number of times `word` has appeared in it. For this purpose you may have to extract each character from `text` and concatenate them to `tmp` a temporary variable created to temporarily store one word at a time from `text`. This can be done using the String function [charAt()](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html#charAt-int-).

When you want to concatenate an extracted character you may want to check if its a letter, for this purpose you may use the char function [isLetter()](https://www.javatpoint.com/post/java-character-isletter-method)

```
Character.isLetter(ch)
```

If the extracted character is not a letter it indicates the end of a word, so you should check if the extracted word `tmp` and `word` are the same. For this purpose you may use the **String** method [equals()](https://www.w3schools.com/java/ref_string_equals.asp) such as

```
tmp.equals(word)
```

**Note:**

- You must empty `tmp`, i.e. set to null or blank after you encounter the end of a word.
- The last character in `text` that has the index `lineLength - 1` (where `lineLength` is the length of `text`) may be a letter, in that case you should concatenate it to `tmp` as well as check if it matches with `word`.

### Display:
Finally the main function should call the `display()` method (keep in mind it is a non-static method) to display `occurrences`. Within `display()` you should simply print `occurences` appropriately.

You must understand the entire process correctly. The main() method is almost complete and you are not expected to change it much, your task is to:

- complete the TODOs in `FindWord.java` and fill up all the `//...`
- implement your logic in `find()` method to find the total number of times the `word` has appeared in each line of text
- complete the `display()` method.

## Usage

Fork this repository to create a copy in your GitHub account and write your own source code to solve this problem.

Visit [this link](https://github.com/its-triple-s/java-tutorial#usage) to learn how to fork this repository and create a codespace to write your code.

## How to execute the program?

1. After you have completed your source code in **FindWord.java**, open the terminal in your codespace by pressing the shortcut **Ctrl + `**

2. In the terminal, navigate to the directory `Find-Word/` and type `ls` to list the contents of the directory.

![ls](https://github.com/geekygiganerd/Find-Word/assets/128626253/92cd0495-3a81-4e15-9b27-2329e9a798ee)

3. Now compile your source code by typing the command below and create `FindWord.class`.

```
$ javac FindWord.java
```

![compile](https://github.com/geekygiganerd/Find-Word/assets/128626253/2d0ab15b-e7c4-4367-8395-5aafc01a23cd)

4. Run or execute your program by typing `java FindWord` and providing the path to a text file as command line argument, e.g. `texts/short.txt`

```
java FindWord texts/longer.txt
```

![run](https://github.com/geekygiganerd/Find-Word/assets/128626253/39b3b2f0-0495-4789-bf0c-de258d7ae0e9)

5. Type the search-word when prompted, for example 'Mary'

```
Search-word: Mary
```

The output for occurrences of the word 'Mary' in [longer.txt](https://github.com/geekygiganerd/Find-Word/blob/main/texts/longer.txt) must be 2, provided the text file has not been edited.

![word-search-longer](https://github.com/geekygiganerd/Find-Word/assets/128626253/a9373c0e-2f60-46a0-a9a4-b19cd2a5225a)

## Outputs

Below is a list of correct outputs for other text files and words. Your program must produce the same results to be correct.

## Solution

It is advised to first try and solve this problem on your own before viewing the solution.
You will find the solution to this problem [here](https://github.com/its-triple-s/java-tutorial/blob/main/solutions/Find-Word/FindWord.java).

## License

This repository is licensed under the [MIT License](LICENSE).

## Contribution

If you wish to make improvements to this problem, you are welcomed. Fork this repository, make changes and send a pull request. Pull requests for solutions are accepted [here](https://github.com/its-triple-s/java-tutorial/tree/main/solutions/Find-Word)

## Author

[Sk. Sameer Salam (@its-triple-s)](https://github.com/its-triple-s)
