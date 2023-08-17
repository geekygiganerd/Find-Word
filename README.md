# Find-Word

This program is a problem from the [java-tutorial](https://github.com/its-triple-s/java-tutorial) created by [@its-triple-s](https://github.com/its-triple-s).
This java program finds the total number of times a word has appeared in a text file.
This program takes a command line argument such as `texts/short.txt` indicating the text file it must read. It then takes a word as user input. The program then reads the entire text file to find the total number of occurrences of that word.

## Description

This program works as a word searching tool for a text file, its nature is similar to the feature we often use in documents to find matching words by pressing **Ctrl + F**. The output of this program should be the total number of times a word has appeared (or occurred) in a text file. To make things less complex, this program shall only find the occurrences of one single word and not a sequence of words or a phrase, we are also assuming that the user enters the proper path to a text file while executing the program.

You have been provided with a few text files in the folder [texts](texts) which are to be used during the execution of a program.

## Usage

- Visit [java-tutorial/README/Usage](https://github.com/its-triple-s/java-tutorial#usage) to learn how to fork the problem program and solve it.

## Example

In the text file [longer.txt(]https://github.com/geekygiganerd/Find-Word/tree/main/texts) the word **Mary** occurs 2 times.

![find-word-longer](https://github.com/geekygiganerd/Find-Word/assets/128626253/27979515-8536-4d9d-8c8a-ba9965f0e095)

So, upon executing the program and finding the word **Mary** in `texts/short.txt` the output in the terminal must be 2.

![word-search-longer](https://github.com/geekygiganerd/Find-Word/assets/128626253/45d10e41-4927-4dd5-b025-900f18344935)

## How to execute the program?

1. After you have completed your source code in **FindWord.java**, open the terminal in your codespaces by pressing the shortcut `Ctrl + `` `

In the terminal of your codespace, navigate to the directory `Find-Word/` and compile your source code by typing `javac FindWord.java` to create `FindWord.class`.

```
$ javac FindWord.java
```

![compile](https://github.com/geekygiganerd/Find-Word/assets/128626253/2d0ab15b-e7c4-4367-8395-5aafc01a23cd)

```
Enter a word to search for: ****the****
The word `the` appears 5 times in texts/short.txt.
```

## How to solve?



## Solution

It is advised to first try and solve this problem on your own before viewing the solution.
You will find the solution to this problem [here](https://github.com/its-triple-s/java-tutorial/blob/main/solutions/Find-Word/FindWord.java).

## License

This repository is licensed under the [MIT License](License).

## Contribution

If you wish to make improvements to the problem of this repository, you are welcomed. Fork this repository, make changes and send a pull request. Pull requests for solutions are accepted in [java-tutorial/solutions/Find-Word](https://github.com/its-triple-s/java-tutorial/tree/main/solutions/Find-Word)

## Author

[Sk. Sameer Salam (@its-triple-s)](https://github.com/its-triple-s)
