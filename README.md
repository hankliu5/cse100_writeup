# Star Point 2: Efficient PredictCompletions

If you're gotten here and you still want more, we're providing this "star point" option.  However, this is just a suggestion.  Any significant extension or project will be considered for a star point.  If you're interested, keep reading.

## What is a "star point"?  
Star points are challenging, open-ended extensions designed to engage those who really want to learn more and go beyond the basic requirements. However, these are not extra credit.

If you do "enough" starpoint and are "close enough" to the boundary, you may be moved up to the higher grade, but do these star point extensions because you are intellectually curious and want a challenge.  Not for the grade.  

The course staff will not answer questions like "If I do this, will I get a star point?".  If you are doing the star point extension just to get the starpoint, then you're doing it for the wrong reason.  Only do it if you would be happy whether or not you get the point in the end.

We have two suggested star points for this assignment. You can choose to do one or both of these depending on your interest.

#### 1. Implement Efficient PredictCompletions that beats the reference solution

For implementing AutoComplete we have provided you with a reference solution that implements this function using an exhaustive search technique.

While doing an exhaustive search is good enough for finishing the PA, to earn the starpoint you need to design and implement an algorithm that consistently beats the running time by at least a factor of 10 on the specific test examples we provide, and others with similar tree structure.  

What we mean by "similar tree structure" is that we will also test on similar-length prefixes that have subtrees of similar size to the examples we provide.  If you beat the reference by at least a factor of 10 on our examples and you haven't done anything tricky to hard-code for just these solutions you should be fine.

The file `benchtrie.cpp` implements a program that times your implementation of the predictCompletions method in DictionaryTrie.  You can use this program to see if your solution beats the reference solution.  However, more importantly, you must use this program as a template for benchmarking in general.

To test the runtime of the reference solution, `refbenchtrie` has been provided to you. It will run 5 tests using our reference solution and output the times taken. The same 5 tests are already provided for you in the `benchtrie` main method. Note that the testers will take a long time to build the dictionary using the `freq_dict.txt` file.

In terms of timing, these are the cases we are definitely testing for:

- The first 10 completions of each letter of the alphabet: We expect your implementation to be at least 10 times faster than the reference implementation when searching for the first 10 completions of ANY letter of the alphabet. This includes letters with many completions (e.g. "a" and "t"), and letters with relatively few completions (e.g. "q" and "x").
- The sum of the first 10 completions of every letter of the alphabet: We expect your implementation to be at least 100 times faster than the reference implementation when searching for the first 10 completions of ALL letters of the alphabet. What this means is if we looped from "a" to "z" and returned the first 10 completions of each of them, the total run-time should be 1/100th of the reference run-time.
- If any test case takes longer than a minute to complete, you will likely lose some or all points for that case.
- Note that this isn't an exhaustive list of what we will test for in terms of timing:  We may test for other prefixes. For timing purposes, we will not test on any prefixes longer than 5 characters (including spaces), and any prefix we test for timing purposes will be in the tree, and will have at least 100 completions. For example, if "troll" is not a prefix in the dictionary, or if it was but only has 2 completions, we will not test that prefix for timing. We expect such prefixes to beat the reference code by a factor of 2 when searching for the first 10 completions.

##### NOTE:
You cannot use caching (i.e) you cannot store multiple keys in a single node  in the dictionary via some data structure or create multiple copies of the dictionary/keys via other data structures during insert. Implementations that use caching will not receive the StarPoint.

In StarPoint.pdf explain the algorithm that you used for PredictCompletions with an example.  You will also submit all your Dictionaryclasses and implementation.

#### 2. Implement SpellCorrection

Extend your DictionaryTrie class to support Spell Suggestions.  Your program `spellCheck.cpp` will allow the user to type in words to check the spelling of.

If the word is spelled correctly (i.e. it was found in the trie), inform the user. If the word is misspelled, However, you should inform the user that they were incorrect, and provide a potential alternative.

You can use the trie to come up with `somesuggestion` of the word they may have intended, by simply returning a word that was found somewhere on the path to the word they were typing ("yesterday" might be a suggestion for the word "yesterdayz", for example).

If no word exists on that path, you should inform the user that you have no suggestions for them. The suggestions being provided by the above method is fairly weak, and will probably not find suggestions for some common misspellings.

However, this can be remedied by expanding the search in the tree. Instead of focusing on the path from the root to the last node, you can start looking down other branches.

To determine if a word is a good suggestion, you can use various metrics. One possible metric is the hamming distance, which simply computes the number of characters in each string are mismatched. This is a fairly weak metric for spell checking, but likely will produce slightly better results than the above. Another metric is the Levenshtein distance, which better handles strings of different lengths. Each of these metrics measure how different two strings are. Implement one of the above algorithms, and provide a handful of better suggestions by ranking them using the implemented metric.

##### Spell Check a File
It is not very useful to have a stand alone program for spell checking. It would be better if you could specify a file to be spell checked, and perform this operation on that file.

You must produce a new file, which is a spell checked version of the original file. This program should take, as a command line arguments, the dictionary file name AND a plain text file to spell check.

Your program should build a trie as normal using the dictionary. It should then check each word sequentially in the file. For every misspelled word, you should provide suggestions and ask the user which suggestion should be used. For ease of use, one of the suggestions should be the "incorrectly" spelled word.

After you have finished checking the specified file, you should write a new file with the string "_checked" appended to the end of the file name. This file will be essentially a copy of the original file, but with all of the spellings "corrected" by the users choices.

You will turn in a makefile that generates the executable `spellcheckfile`, `spellcheck`, `starpoint.pdf` and your code as part of your submission.

In `starpoint.pdf` explain the algorithm you used to provide suggestions. Also explain how you tested your program.
