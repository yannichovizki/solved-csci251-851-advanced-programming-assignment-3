Download Link: https://assignmentchef.com/product/solved-csci251-851-advanced-programming-assignment-3
<br>
<strong>Aim:</strong>

This assignment is to familiarise you with the use of STL container classes in your programs.

<strong>On completion you should know how to:</strong>

<ul>

 <li>Write C++ code using STL container class objects.</li>

 <li>Devise programs requiring data manipulation with STL containers.</li>

 <li>Gain experience writing and debugging complex C++ programs incrementally.</li>

</ul>

<strong> </strong>

<strong>Prerequisites: </strong>

Before you undertake this assignment please review the week 8 lecture notes on the Standard Template Library (STL). Also, download and study the week 7&amp;8 STL example programs in the Examples folder. The following links may also prove useful for learning STL containers: <u>http://www.cplusplus.com/reference/stl/</u> <u>http://www.cprogramming.com/tutorial/stl/stlintro.html</u> <u>http://www.sgi.com/tech/stl/stl_introduction.html</u>

If you are unsure on how to do something with STL, try looking at the examples or google “STL” together with “set” or “map” or “multi-map” etc.

<em> </em>

<strong>Requirements: </strong>

For this assignment you are to implement a C++ program that can read a text file and display any known words on the screen together with their frequency and position in the file. Below shows a snippet of what the output should look like:




<strong>                Word     Count   Position(s)                    a       7     22 65 87 96 130 148 165                  all       1     50                  and       9     19 70 125 134 138 157 177 247 261                  are       1     74                   as       2     169 214             automata       1     73                   be       1     99                begin       1     106              between       1     132                 cell       5     97 131 156 180 238             cellular       1     72               create       1     143               cursor       2     119 124                eight       1     171                every       2     155 237                first       2     20 110 </strong>







A “known” word is a word that is in the English dictionary which is defined by the words listed in the file named “dictionary.txt”.  The word “Positions” are determined by all the places where each word occurs in the data file. For example, in the above screen output, the word “first” occurred twice, at the 20<sup>th</sup> and 110<sup>th</sup> word position in the test data file.




A partially completed “WordStat” class is provided in “wordstat.h” and “wordstat.cpp”. A driver program is also provided in main.cpp. The file: “output.txt” shows the output your completed program should produce when run with redirected input from “input.txt”. You should do this assignment incrementally by completing the following steps.




<h1>Step 1  (2 mark)</h1>

Implement the ReadDictionary() and DisplayDictionary() public member function in the “wordstats” class in “wordstat.h &amp; “wordstat.cpp”. ReadDictionary should open “dictionary.txt” and read all the words (in lower case format) into the private “Dictionary” member:

<strong>set&lt;string&gt; Dictionary; </strong>

If you are unsure on using the STL set container, take a look at “08-set.cpp” in the examples folder.  DisplayDictionary() should display the first 20 words in the Dictionary on the screen. The screenshot below shows an example output of reading and displaying the dictionary.




<strong>Step-1 Reading and displaying dictionary </strong>

<strong> </strong>

<strong>25127 words read from dictionary. </strong>

<strong> </strong>

<strong>Displaying the first 20 words in the dictionary… </strong>

<strong>aarhus aaron ababa aback abacus … </strong>

<strong> </strong>

<strong>abbot abbott abbreviate abc abdicate abdomen  </strong>

<h1>Step 2  (2 mark)</h1>

Implement the ReadTextFile() public member function. This function should read the contents of the file named: “testdata.txt” into the “KnownWords” and “UnknownWords” data members of the “WordStats” class:

<strong> </strong>

<strong>WordMap KnownWords; </strong>

<strong>WordMap UnknownWords; </strong>




Please note that “WordMap” is typedefed in “wordstat.h” as:

<strong> </strong>

<strong>typedef map&lt;string, vector&lt;int&gt; &gt; WordMap; </strong>




Only “known” words should be put in the “KnownWords” WordMap. A “known” word is any word that is found in the Dictionary class member. Before attempting to find a word in the Dictionary, you should first preprocess the word by converting all characters to lower case and remove any non-alphabetic characters except for the punctuation marks: hyphen (-) and apostrophe (‘). You can add additional private member functions to class WordStats if you wish. Your output from step-2 should look something like this:




<strong>Step-2 Reading known wrods from text file: </strong>

<strong>89 known words read. </strong>

<strong>49 unknown words read. </strong>




If you are unsure on working with map containers, an example is provided in “08-map.cpp” in the example folder.

<strong>          </strong>

<h1>Step 3  (1 mark)</h1>

Implement the DisplayKnownWordStats(); public member function. This function should iterate the  “KnownWords” WordMap and display the word stats on the screen as shown on page 1.  If you are unsure on how to do this with a map look at “08-map.cpp” in the example folder.

<strong> </strong>

<h1>Step 4 (1 mark)</h1>

Implement the “DisplayUnknownWordStats()” public member function. This function should display the unknown words in the same format as step-3. Note: try to avoid duplicating code for this by declaring an additional private member function that is passed a WordMap by reference and called by both the display functions from step-3 and step-4.

<strong> </strong>

<h1>Step 5 (1 marks)</h1>

Implement the “DisplayMostFreqKnownWords()” public member function. This function should display the 10 most frequently occurring words in the “KnownWords” container. E.g.




<strong>Step-5 Displaying most frequent known words:       Word     Count        the      21       live      10         of       9        and       9         or       7         in       7          a       7         to       6         is       6       cell       5 </strong>

To do this declare a local multimap&lt;int,string&gt;; container. You will need to iterate the “KnownWords” container and insert the size of the vector (as the key) and the word into the local multimap. This multimap can then be iterated to display the 10 most frequent words on the screen.




<h1>Step 6 (1 mark)</h1>

Implement the “DisplayMostFreqUnknownWords()” public member function to display the 10 most frequently occurring words in the “UnknownWords” container. Again, try to avoid duplicate code by adding another private member function called by the display functions from setp-5 and 6.




<h1>Step 7 (2 marks)</h1>

Implement the “DisplayOriginalText()” public member function. To do this declare a local map&lt;int,string&gt;; container and do the same as you did with Step 6, except you should also iterate the vectors in the KnownWords and UnknownWords containers and add the &lt;position, word&gt; pair for all words and their positions. This will sort the words into their original text order based on the word position numbers. The screen output should look something like below.




<em>the game of life written by ian sharpe the game of life was invented by the mathematician john conway and first reached a wide public when it was written up in scientific american in 1970 or thereabouts in those days it was mostly played on squared paper nowadays computers take all the hard work out of this fascinating invention to some it’s nothing more than a toy to others it and related cellular automata are subjects for serious study in this implementation the screen is divided into a grid of cells 40 wide by 24 deep a cell may be live (red or dead (white) you begin by creating the first generation of live cells or seed . . .  </em>




<strong>     </strong>

<strong> </strong>

<strong>Submit: </strong>

Submit your files and the output produced when run (copy &amp; paste screen)  using the submit facility on UNIX as shown below:

<strong>$ submit -u login -c CSCI251 –a3 main.cpp wordstats.h wordstats.cpp output.txt </strong>

<strong> </strong>

<strong>where ‘login’ is your UNIX login ID  </strong>

Note: CSCI851 should also submit to –c CSCI251.

<strong> </strong>

<strong><u>To receive 2 marks for your demo, you should demonstrate step-1 and explain (or show) step-2  of</u></strong><strong> <u>your program in your week 9 lab class. Failure to do the demo on time without granted extension</u> <u>will result in a 1 mark deduction for each week late.</u> </strong>

<strong> </strong>

Deductions will be made for untidy work or for failing to comply with the submission instructions. Requests for alternative submission arrangements will only be considered before the due date. An extension of time for the assignment submission may be granted in certain circumstances.  Any request for an extension of the submission deadline must be made to the Subject Coordinator before the submission deadline. Supporting documentation must accompany the request for any extension.  <strong>Late assignment submissions without granted extension will be marked but the marks awarded will be reduced by 1 mark for each day late.</strong>  Assignments will not be accepted if more than four days late.


