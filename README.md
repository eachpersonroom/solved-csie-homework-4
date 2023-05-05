Download Link: https://assignmentchef.com/product/solved-csie-homework-4
<br>



<strong>Problem 1 – </strong><strong> Clique (Programming) </strong>

<strong>Problem Description</strong>

loves complicated things. Hence, in the graph theory, cliques are ’s favorite since they are the most complex structure within all simple graphs. One day,  found a new interesting game called “click clique” on a gaming website. The rule of the game is described as follows.

When the game starts, you are given a simple undirected graph <em>G </em>= (<em>V,E</em>). For each move, you can click a clique <em>C </em>of <em>G</em>, and it will remove those vertices and edges from the graph. That is, the graph will become the induced subgraph of <em>V </em><em>C </em>after the move. You can make arbitrary number of moves until the graph is empty. When the game ends (i.e. the graph becomes empty), you will receive stars according to the number of moves you make. Furthermore, you can receive full 3 stars only when you make the minimum number of moves. As a clique lover,  can’t bear to miss the full stars in the game. Thus,  comes and asks you for help. Given a simple graph, please tell  an optimal way to finish the game.

<strong>Input</strong>

The first line of the input contains an integer <em>T </em>indicating the number of testcases. For each testcase, the first line contains two integers <em>N,M </em>indicating the number of vertices and edges in the graph, respectively. The following <em>M </em>lines each contains two integers <em>u,v </em>describing the edges of the graph.

<ul>

 <li>1 ≤ <em>T </em>≤ 1000</li>

 <li>1 ≤ <em>N </em>≤ 80</li>

 <li></li>

</ul>

<h2>• 0 ≤ u,v &lt; N</h2>

<ul>

 <li>1 ≤ <em>C </em>≤ 800 where <em>C </em>is the number of maximal clique in the graph.</li>

 <li>It is guaranteed that the given graph is simple.</li>

 <li>Each test group will include its previous test groups.</li>

</ul>




<strong>Test Group 0 </strong>

<ul>

 <li>Sample Input</li>

</ul>

<strong>Test Group 1 </strong>

<ul>

 <li><em>n </em>≤ 7</li>

 <li><em>C </em>≤ 800</li>

</ul>

<strong>Test Group 2 </strong>

<ul>

 <li><em>n </em>≤ 14</li>

 <li>1 ≤ <em>C </em>≤ 100</li>

</ul>

<strong>Test Group 3 </strong>

<ul>

 <li><em>T </em>≤ 10</li>

 <li><em>n </em>≤ 50</li>

 <li><em>C </em>≤ 500</li>

</ul>

<strong>Test Group 4 </strong>

<ul>

 <li><em>T </em>≤ 3</li>

</ul>

<table width="643">

 <tbody>

  <tr>

   <td width="643"><strong>Output</strong>For each testcase, the first line output an integer <em>R</em>, which is the minimum number of moves needs to make.Then each of the following <em>R </em>lines output the vertices thatshould click in each move in the format of “<em>k v</em><sub>1 </sub><em>v</em><sub>2 </sub><em>… v<sub>k</sub></em>”, where <em>k </em>is the number of vertices in this move and {<em>v<sub>i</sub></em>} are the indices of these vertices. You can output {<em>v<sub>i</sub></em>} in any order.Note that the summation of <em>k </em>in each testcase should be equal to <em>N</em>. If there are multiple optimal solutions, you can output any of them.</td>

  </tr>

 </tbody>

</table>

<strong>Sample Input 1                             Sample Input 2</strong>

1                                                     2

6 6                                                   3 3

0 1                                                   1 2

<ul>

 <li>2 0 2</li>

 <li>2 0 1</li>

</ul>

1 3                                                   3 0

<h1><a name="_Toc38790"></a>3 4</h1>

4 5

<strong>Sample Output 2</strong>

<strong>Sample Output 1</strong>

<h1><a name="_Toc38791"></a>1</h1>

3 2 0 1

3                                                     3

3 0 1 2                                             1 2

<ul>

 <li>3 1 0</li>

 <li>4 5 1 1</li>

</ul>

<strong>Notes</strong>

A clique is defined as a complete subgraph. That is, a set <em>C </em>⊆ <em>V </em>and <em>u </em>6= <em>v</em>, (<em>u,v</em>) ∈ <em>E</em>.

<strong>Sample Input 3</strong>

2

<a href="#_Toc38790">4                                              2</a>

<a href="#_Toc38791">1                                              2</a>

<a href="#_Toc38792">0                                              2</a>




4 6

<h1><a name="_Toc38792"></a>0 1</h1>

<ul>

 <li>2</li>

 <li>3</li>

</ul>

0 3

<ul>

 <li>2</li>

 <li>3</li>

</ul>

<strong>Sample Output 3</strong>

3

<ul>

 <li>0 2</li>

</ul>

1 1

1 3

1

4 1 2 0 3

is a clique if and only if ∀<em>u,v </em>∈ <em>C</em>




A maximal clique is a clique that cannot be extended by adding any other vertex. That is, there is no proper superset of <em>C </em>which is also a clique. Formally speaking, a clique <em>C </em>is maximal if and only if @<em>C </em>⊂ <em>S </em>⊆ <em>V </em>such that <em>S </em>is a clique.

<strong>Hints</strong>

<ol>

 <li>std::bitset is a good data structure and it might be useful in this problem.</li>

 <li>You may want to use (integer) linear programming to solve this problem. Please see the following section to use the provided linear programming solver. (Of course, you are not forced to use it if you want to implement it by yourself.)</li>

 <li>You are welcome to use any heuristic method to solve this problem. Happy hacking.</li>

</ol>

<strong>Linear Programming Solver</strong>

The <a href="https://www.gnu.org/software/glpk/">GLPK (GNU Linear Programming Kit)</a><a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> package is intended for solving large-scale linear programming (LP), mixed integer programming (MIP), and other related problems. You can include the GLPK library (&lt;glpk.h&gt;) and use it in this problem. See <a href="http://most.ccib.rutgers.edu/glpk.pdf">GLPK Manual</a><a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> for more information about the usage.

There is also a packed version of the GLPK tools provided for you to use it easier. The full header file can be downloaded <a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/ypglpk.hpp">here</a><a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a>. You can include it by #include “ypglpk.hpp” in your solution.

There are three functions defined in the namespace “ypglpk”. You can follow the instruction below to use them. All the std::vector below are 0-based. Note that if the parameters violate the restriction, the behavior is undefined.

std::pair&lt;double,std::vector&lt;double&gt;&gt; linear_programming( const std::vector&lt;std::vector&lt;double&gt;&gt; &amp;A,

const std::vector&lt;double&gt; &amp;b, const std::vector&lt;double&gt; &amp;c);

<ul>

 <li>The function linear_programming(A,b,c) is used to solve the standard linear programming problem.</li>

 <li>Parameters: <em>A </em>∈ R<em><sup>m</sup></em><sup>×<em>n</em></sup><em>,b </em>∈ R<em><sup>m</sup>,c </em>∈ R<em><sup>n </sup></em>where <em>n </em>is the number of structural variables and <em>m </em>is the number of constraints.</li>

 <li>Targets: Maximize <em>c </em> <em>x </em>subject to <em>Ax </em>≤ <em>b,x </em>∈ R<em><sup>n</sup></em>.</li>

 <li>Return value: pair of (optimal value <em>c </em> <em>x</em><sup>∗</sup>, optimal vector <em>x</em><sup>∗</sup>). If the solution is infeasible or unbounded, the return value is (negative infinity -ypglpk::INF, empty vector vector&lt;double&gt;()).</li>

</ul>

std::pair&lt;double,std::vector&lt;double&gt;&gt; mixed_integer_linear_programming( const std::vector&lt;std::vector&lt;double&gt;&gt; &amp;A, const std::vector&lt;double&gt; &amp;b, const std::vector&lt;double&gt; &amp;c, const std::vector&lt;bool&gt; &amp;isint);

<ul>

 <li>The function mixed_integer_linear_programming(A,b,c,isint) is used to solve the mixed integer linear programming problem, which can restrict some structural variables to be integers.</li>

 <li>Parameters: <em>A </em>∈ R<em><sup>m</sup></em><sup>×<em>n</em></sup><em>,b </em>∈ R<em><sup>m</sup>,c </em>∈ R<em><sup>n</sup>,</em>isint ∈ {<em>true,false</em>}<em><sup>n </sup></em>where <em>n </em>is the number of structural variables and <em>m </em>is the number of constraints.</li>

 <li>Targets: Maximize <em>c </em> <em>x </em>subject to <em>Ax </em>≤ <em>b,x </em>∈ R<em><sup>n</sup></em>, and ∀<em>i </em>with isint<em><sub>i </sub></em>= <em>true,x<sub>i </sub></em>∈ Z.</li>

 <li>Return value: pair of (optimal value <em>c </em> <em>x</em><sup>∗</sup>, optimal vector <em>x</em><sup>∗</sup>). If the solution is infeasible or unbounded, the return value is (negative infinity -ypglpk::INF, empty vector vector&lt;double&gt;()).</li>

 <li>The function set_output(output) is used to set whether GLPK to output verbose information about the (MI)LP solver.</li>

 <li>The default setting is output=false. You may enable it to debug your code with more information about the constraints and the solver. <strong>However, please do not set it to </strong>true <strong>when you submit to the judge; otherwise, you will certainly get </strong>Wrong Answer <strong>verdict due to the unexpected output.</strong></li>

</ul>

<strong>Local Testing</strong>

<a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/example.cpp">Here</a><a href="#_ftn4" name="_ftnref4"><sup>[4]</sup></a> is a simple example code to demonstrate how to use the provided header file. It should be able to be compiled and run successfully on the judge (although you will receive Wrong Answer).

The installed GLPK version on the judge system is 5.0. (The version of the GLPK package does not affect the correctness. It only affects the performance in some cases since the later version might have better presolver and branching strategy.)

For CSIE students, you are highly recommended to run the program on the CSIE workstation, as there is already an installed GLPK 5.0 package for you. You can simply put your source code and the given header file together and compile them with the command below Compilation.

Otherwise, to compile and run the GLPK library successfully, please refer to the Appendix GLPK

Installation to install it.

<strong>Compilation</strong>

After having an environment with installed GLPK package, you can compile the provided codes (or your source code) by adding the additional linker argument -lglpk to the compilation command. <strong>Note that the order of the arguments is essential. The linker argument should be put after the source code. </strong>For example (assume that the filename of the source code is “example.cpp”):

<strong>Demonstration</strong>

You can try to compile and run the provided example program to ensure there is no problem with the package. Below is a script to download the provided files, compile them, and run the program. (Note that the compilation command and the execution command might differ if you built the package from source by yourself. See the Appendix GLPK Installation for more information.)

curl -o example.cpp ’https://www.csie.ntu.edu.tw/~giver/ADA/hw4/example.cpp’ curl -o ypglpk.hpp ’https://www.csie.ntu.edu.tw/~giver/ADA/hw4/ypglpk.hpp’ g++ -std=c++17 -O2 -oexample example.cpp -lglpk -Wall

./example

And the expected output of the program execution should be like figure 1.

Sample output of the example.cpp program

<strong>Problem 2 – </strong><strong> Game (Programming)</strong>

This task has unusual time limit and submission quota. Please read the notes carefully.

<strong>Problem Description</strong>

King  loves to play board games. He is especially good at playing Connect4.

The following figure shows an example game:

is a nice person, <strong>he will always let you move first</strong>. Additionally, since King                                                                                                                                                                         is

very busy, he can’t pay full attention to the games. Sometimes, he will make a random move instead of using his strong mind. Given these advantages, can you defeat King ?

<strong>Scoring</strong>

There are multiple test groups. In each test group, there are two parameters, a probability <em>p </em>and a threshold <em>thres</em>. For each testcase within the test group, you will play <strong>100 games </strong>of Connect4 against King . When it’s King ’s turn, he has a probability <em>p </em>to make the decision using his strong mind. Otherwise, he will make a random move (each valid column has the same chance to be chosen).

Suppose that you got <em>x </em>wins and <em>y </em>ties out of all 100 games in a single testcase, your score <em>score </em>is defined as 2<em>x</em>+<em>y</em>. That is, <strong>each win gives you two points, while each tie gives you a single point</strong>. You will get <strong>Accepted </strong>iff <em>score </em>≥ <em>thres</em>.

<strong>Test Group 0 </strong>

<ul>

 <li>King always drops his piece in the leftmost valid column.</li>

 <li><em>thres </em>= 190</li>

</ul>

<strong>Test Group 1                                     Test Group 2 (10 %) Test Group 3 (10 %) Test Group 4 </strong>

<ul>

 <li><em>p </em>= 0<em>.</em>0 <em>p </em>= 0<em>.</em>5                 • <em>p </em>= 0<em>.</em>5                 • <em>p </em>= 0<em>.</em>7</li>

 <li><em>thres </em>= 150 <em>thres </em>= 120      • <em>thres </em>= 170      • <em>thres </em>= 110</li>

</ul>

<strong>Test Group 5 (15 %)                                  Test Group 6 (15 %)                               Test Group 7 (25 %)</strong>

<ul>

 <li><em>p </em>= 0<em>.</em>85 <em>p </em>= 0<em>.</em>85              • <em>p </em>= 0<em>.</em>85</li>

 <li><em>thres </em>= 110 <em>thres </em>= 140      • <em>thres </em>= 170</li>

</ul>

<strong>Implementation details</strong>

First of all, <strong>the columns are numbered from </strong>0 <strong>to </strong>6. You need to implement the following procedure:

int decide(int yp_move)

In each game, decide(-1) will be called first. You should return the first move (index of the column) you want to make. Every subsequent call of the function denotes that King placed his piece in column yp move. You should return the next move you want to make.

It is guaranteed that the game hasn’t finished yet when yp move 6= -1. However, there are multiple games within a single testcase. <strong>Please properly reset all your variables whenever </strong>decide(-1) <strong>is called.</strong>

<strong>Local testing tool &amp; Template</strong>

We’ve provided a local testing tool for you. The tool will connect to our sever (<strong>so it needs network connectivity</strong>) and play against the <strong>exactly same </strong>strategy on the judge (i.e., King ). So <strong>please submit your solution to the judge only if it runs correctly at local.</strong>

Please download <a href="http://w.csie.org/~b08902107/ADA/connect4_public.zip">connect4</a> <a href="http://w.csie.org/~b08902107/ADA/connect4_public.zip">public.zip</a><a href="#_ftn5" name="_ftnref5"><sup>[5]</sup></a>, which contains the following two files:

connect4.cpp

This is the template file for you to work on. This is also the file you should submit for this problem. <strong>You can pass Test Group 0 by submitting this file without any modifications. </strong>You can (and should) include any header you need on your own. Feel free to use global variables.

connect4.h

This is the local testing tool. We already included this file in your solution. You should directly compile connect4.cpp. It’s recommended to add -std=c++17 and -O2 flag when compiling locally. <strong>For Windows users, you need to append </strong>-lws2 32 <strong>to the compiler option.</strong>

It will ask for <em>p </em>and the number of games you want it to repeat. It is encouraged to take a look at the tool and change it as you like. Feel free to borrow any code from the tool.

Additionally, there are two “switches” located at the very beginning of this tool:

<ul>

 <li>CONNECT4 DEBUG: The tool will output the state of the game board if this flag is defined.</li>

 <li>CONNECT4 INTERACTIVE: The tool will let you (instead of King ) play with your own code if this flag is defined.</li>

</ul>

<strong>About the execution time</strong>

The local testing tool will help you measure the total time it takes to run your code on your computer (not including King ’s thinking time). King  will spend approximately 3 seconds per testcase on the judge. However, beware that the execution time might change a lot on the judge. It’s a good idea to run the same code locally and on the judge once and take the time difference as a reference. The time limit to this problem should be more than enough.

<strong>Notes</strong>

<ol>

 <li>The time limit for this problem is <strong>40 seconds per testcase </strong>(100 games). However, <strong>you can only submit 5 times per day</strong>.</li>

 <li>Do not write your own main function and do not try to interact with stdin and stdout.</li>

 <li>Feel free to use any random number generators. However, it’s encouraged to use a fixed seed so that your judge verdict can be deterministic.</li>

 <li>The judge uses a fixed random seed, so you should get the same verdict (Accept or Wrong Answer) if you submit the same deterministic code twice. (Note that this does not hold for local testing tool, as it uses a different seed for every new invocation.)</li>

 <li>Do not try to steal any data from the grader. Similar behavior will be regarded as cheating and will receive heavy penalties. If you find weird behavior from the grading or the local test tool, please contact TA.</li>

</ol>

<strong>Hints</strong>

<ol>

 <li>It is important to examine why your code loses.</li>

 <li>It might be easier to debug by playing with your own code (see the instruction above on how to do this).</li>

 <li>This is an open question, we don’t have a model solution. You can use your imagination to come up with some good strategies.</li>

 <li>You can ask TAs for some additional hints if you don’t have any idea. However, we can’t really debug your ideas for you.</li>

 <li>You can also come to play with TAs if you like.</li>

</ol>

<strong>Problem 3 – </strong><strong> Record (Programming)</strong>

<strong>Problem Description</strong>

As a competitive programming athlete,has participated in <em>N </em>contests, and the <em>i</em><sup>th </sup>contest has a unique ID <em>i</em>. However,            knows that he got score <em>s<sub>i </sub></em>in the <em>i</em><sup>th </sup>contest and feels slightly dissatisfied with those results. Due to his self-esteem,wants to let his scores become <strong>increasing </strong>over time by concealing some of the contest records.

, who is the enemy of , would like to interfere him. Since  is a great time traveler, he will travel to the past and do one of the following operations many times:

<ol>

 <li>Convinceto participate in an extra contest.</li>

 <li>Convincenot to participate in a contest.</li>

</ol>

Notice thatmay perform the operations at any time. Any operation will not affect the scores of other contests, you don’t need to worry about the Butterfly Effect.

entrusts you, his assistant, to perform the concealment. Unfortunately, doesn’t want to tell you the exact scores of each contest. You can only ask him many times about “whether the score of the <em>a</em><sup>th </sup>contest is less than the <em>b</em><sup>th </sup>contest”, but not too many because       is busy. You also need to keep updating the concealment afterhas done any operation.

Oh,  does not care about minimizing the number of concealed contests. <strong>will accept any approximate solution that is at most twice as many as the minimum.</strong>

<strong>Implementation details</strong>

Include “ada-hw4-p3.h” in the first line of your code, and then you should implement the following procedures:

<ul>

 <li>This procedure is called exactly once, and should return a single array <em>D</em>. The elements of the returned array should form a subset of 0 to <em>N </em>− 1 in any order, describing the IDs of contests you want to conceal. An empty array is also valid when you don’t want to conceal any contest.</li>

 <li><em>p</em>: position of the inserted contest. After the insertion, the <em>id</em><sup>th </sup>contest will have position <em>p</em>, and the original contests whose positions are greater than or equal to <em>p </em>will be increased by one.</li>

 <li><em>id</em>: the ID of the inserted contest.</li>

 <li>This procedure should return a single array <em>D</em>. The elements of array should form a subset of the current contest <strong>ID </strong>list (after the insertion) in any order, describing the IDs of contests you want to conceal. An empty array is also valid when you don’t want to conceal any contest.</li>

 <li><em>p</em>: position of the removed contest. After the deletion, the contest having position <em>p </em>will be removed, and the original contests whose positions are greater than <em>p </em>will be decreased by one.</li>

 <li>This procedure should return a single array <em>D</em>. The elements of array should form a subset of the current contest <strong>ID </strong>list (after the removal) in any order, describing the IDs of contests you want to conceal. An empty array is also valid when you don’t want to conceal any contest.</li>

</ul>

The above procedures can make calls to the following procedure:

<ul>

 <li><em>a</em>: the first contest’s ID you want to compare.</li>

 <li><em>b</em>: the second contest’s ID you want to compare. Both the the compared contests should exist (a removed contest is regarded as disappeared). And <em>a </em>6= <em>b</em>.</li>

 <li>The procedure returns true if the <em>a</em><sup>th </sup>contest’s score is less than the <em>b</em><sup>th </sup>contest’s score. Otherwise, it will return false.</li>

 <li>The grading program will record the number of calls of this procedure, which is relate to the condition of getting Accepted.</li>

 <li>The time complexity of the procedure is <em>O</em>(1).</li>

</ul>

<strong>Examples</strong>

This procedure may call compare(0, 1) which (in this scenario) returns true. It may then call compare(1, 2), which returns false.

At this point, there is sufficient information to conclude that we should conceal at least one contest. So, the procedure init can return [2] and get Accepted.

Notice that we can return an answer having twice of the minimum answer size. Hence, if the procedure init returns [1<em>,</em>2], it can also get Accepted.

After that, the procedure insert may be called in the following way:

score of it is 3. The contest ID list is [0<em>,</em>3<em>,</em>1<em>,</em>2] and the contest score list is [1<em>,</em>3<em>,</em>4<em>,</em>2] now.

This procedure may call compare(3, 1) which returns true. At this point, there is sufficient information to conclude that we can conceal only one contest. So, the procedure insert can return [2] and get Accepted.

Continue, the procedure remove may be called in the following way:

At this point, there is sufficient information to conclude that we don’t need to conceal any contest. So, the procedure remove can return [] and get Accepted.

Notice that returning any non-empty array cannot get Accepted since the minimum answer size is 0.

<strong>Constraints</strong>

Let the number of calls of insert and remove be <em>P </em>and <em>Q</em>, respectively. Then:

<ul>

 <li>1 ≤ <em>N </em>≤ 2000</li>

 <li>0 ≤ <em>P,Q </em>≤ 1000</li>

</ul>

For each call to insert, let <em>L </em>be the current length of the array:

<h2>• 0 ≤ p ≤ L</h2>

<ul>

 <li><em>id </em>= <em>N </em>+ <em>i </em>− 1 in the <em>i</em><sup>th </sup>call of insert</li>

</ul>

For each call to remove, let <em>L </em>be the current length of the array:




<h2>• 0 ≤ p &lt; L</h2>

<strong>Test Group 0 (0 %)</strong>

<ul>

 <li>Sample Input.</li>

</ul>

<strong>Test Group 1 (20 %)</strong>

<ul>

 <li>No additional constraint.</li>

</ul>

<strong>Test Group 2 (20 %)</strong>

<ul>

 <li>For the call of init, procedure compare can be called at most <em>N </em>− 1 times.</li>

 <li><em>P </em>= <em>Q </em>= 0.</li>

</ul>

<strong>Test Group 3 (30 %)</strong>

<ul>

 <li>For the call of init, procedure compare can be called at most <em>N </em>− 1 times.</li>

 <li>For each call of insert, procedure compare can be called at most 30 times.</li>

 <li><em>Q </em>= 0.</li>

</ul>

<strong>Test Group 4 (30 %)</strong>

<ul>

 <li>For the call of init, procedure compare can be called at most <em>N </em>− 1 times.</li>

 <li>For each call of insert, procedure compare can be called at most 2 times.</li>

 <li>For each call of remove, procedure compare can be called at most 2 times.</li>

</ul>




<strong>Sample grader</strong>

Download <a href="http://w.csie.org/~b08902103/ADA/ada-hw4-p3.zip">“ada-hw4-p3.zip”</a><a href="#_ftn6" name="_ftnref6"><sup>[6]</sup></a>, extract and put them in the same directory of your code. Compile your code with the following command, assuming that your code is named ada-hw4-p3.cpp:

g++ -O2 -std=c++17 grader.cpp ada-hw4-p3.cpp -o ada-hw4-p3

We also have provided sample code (ada-hw4-p3.cpp), sample compile scripts (compile cpp.sh for Linux and Mac OS, compile cpp.bat for Windows) in the zip file.

The sample grader reads an array <em>s </em>of 32-bits unsigned integers indicating the scores of contests 0 to <em>N </em>− 1 and <em>Q </em>operations. The sample grader reads input in the following format:

<ul>

 <li>line 1: <em>N Q</em></li>

 <li>line 2: <em>s</em>[0] <em>s</em>[1] <em>… s</em>[<em>n </em>− 1]</li>

 <li>line 3 + <em>i</em>(0 ≤ <em>i &lt; Q</em>): operation[<em>i</em>]: could be of the following two types:

  <ul>

   <li>insert <em>p s</em>: Insert a contest with score <em>s </em>at position <em>p</em>. The contest’s ID will automatically become <em>N </em>+ <em>j </em>− 1 at the <em>j</em><sup>th </sup>call of insert.</li>

   <li>remove <em>p</em>: Remove the contest at position <em>p</em>.</li>

  </ul></li>

</ul>

The output of sample grader is in the following format:

<ul>

 <li>line 1: <em>choice</em><sub>init </sub>(<em>t</em>)</li>

 <li>line 2 + <em>i</em>(0 ≤ <em>i &lt; Q</em>): <em>choice<sub>i </sub></em>(<em>t</em>)</li>

</ul>

, where:

<ul>

 <li><em>choice</em><sub>init</sub>: Choice returned by init.</li>

 <li><em>choice<sub>i</sub></em>: Choice returned by operation[<em>i</em>].</li>

 <li><em>t</em>: the number of calls of the procedure compare.</li>

</ul>

All of the choices will be printed in the following format:

<h2>• k c[0] c[1] … c[k − 1]</h2>

Where <em>k </em>is the size of the choice and array <em>c </em>is the content of the choice.

Note:

<ul>

 <li>The sample grader will not help you judge the correctness of your answer except the format error.</li>

 <li>The sample grader will fail if it tries to compare two contests with the same score.</li>

</ul>

<strong>Sample Input 1                                                        Sample Output 1</strong>

3 2                                                                                2 1 2 (2)

1 4 2                                                                             1 2 (1)

insert 1 3                                                                     0 (0)

remove 3

<strong>Sample Input 2                                                        Sample Output 2</strong>

3 3                                                                                3 0 1 2 (2)

3 2 1                                                                              3 0 1 2 (2)

insert 1 4                                                                       3 0 1 2 (2)

insert 2 5                                                                      1 1 (2)

remove 3

<strong>Sample Input 3                                                        Sample Output 3</strong>

6 6                                                                               0 (5)

1 5 6 7 9 10                                                                   1 6 (1)

insert 1 8                                                                      2 7 6 (0)

insert 1 3                                                                      2 6 8 (2)

insert 6 4                                                                      2 6 8 (2)

remove 4                                                                      2 6 8 (2)

remove 7                                                                      1 6 (0)

remove 5

<strong>Hint</strong>

<ol>

 <li>Try to reduce this problem to the <strong>minimum vertex cover </strong>problem, which has a 2-approximation algorithm as taught in class.</li>

 <li>Do not write your own main function, and do not try to interact with stdin and stdout.</li>

 <li>Feel free to use global variables.</li>

 <li>Do not try to use complex data structures to maintain your array. Since the data size is small, you can spend linear time inserting or removing any element.</li>

 <li>All you need to return are the IDs of the contests, not the positions.</li>

 <li>For those who aren’t familiar with std::vector, take a look at the <a href="https://en.cppreference.com/w/cpp/container/vector">document</a><a href="https://en.cppreference.com/w/cpp/container/vector">.</a></li>

 <li>Do not try to steal any data from the grader. Similar behavior will be regarded as cheating and will receive heavy penalties. If you find weird behavior from the grading, please contact TA.</li>

</ol>

<strong>Problem 4 – </strong><strong> Ring (Programming) (13 points)</strong>

<strong>Problem Description</strong>

Under the rule of King , people live from hand to mouth in the kingdom of . In the time of crisis, people rose to rebel and used a ring to seal King .

To ensure everyone’s safety, people decided to divide the ring into <em>M </em>segments and hide them at the end of the earth to prevent from resurrecting and slaughtering the people.

This ring is decorated by <em>N </em>symbols, and each can be represented by a value <em>a</em><sub>1</sub><em>,a</em><sub>2</sub><em>,</em>··· <em>,a<sub>N</sub></em>, in counterclockwise order. After dividing the ring into <em>M </em>segments (each consisting of some consecutive symbols), we can calculate each segment’s risk value as follows.

Suppose the symbols within a segment can be represented as <em>b</em><sub>1</sub><em>,b</em><sub>2</sub><em>,</em>··· <em>,b<sub>k</sub></em>, the risk value of this segment will be

<em>k               k</em>−1                                <em>k</em>−2

<h2>                       X                 X                                   X</h2>

<em>b</em><em>i </em>−            |<em>b</em><em>i</em>+1 − <em>b</em><em>i</em>| +                 <em>b</em><em>i</em>+1 × ((<em>b</em><em>i </em>&amp; <em>b</em><em>i</em>+1) ⊕ (<em>b</em><em>i</em>+1 | <em>b</em><em>i</em>+2) ⊕ (<em>b</em><em>i </em>+ <em>b</em><em>i</em>+2))

<em>i</em>=1              <em>i</em>=1                                 <em>i</em>=1

, where <em>x </em>&amp; <em>y </em>means applying bitwise AND operation, <em>x </em>| <em>y </em>means applying bitwise OR operation, and <em>x </em>⊕ <em>y </em>means applying bitwise XOR operation to numbers <em>x </em>and <em>y</em>.

To reduce the risk, you want to minimize the sum of the risk values of the <em>M </em>segments. How should you divide the <em>M </em>segments?

<strong>Input</strong>

The first line contains two integers <em>N,M</em>, representing the number of symbols on the ring and the number of segments to be divided.

The following contains <em>N </em>space-separated integers <em>a</em><sub>1</sub><em>,a</em><sub>2</sub><em>,</em>···<em>a<sub>N</sub></em>, indicating the symbols on the

<table width="524">

 <tbody>

  <tr>

   <td width="176">ring.•   2 ≤ <em>M </em>≤ <em>N </em>≤ 1000•   0 ≤ <em>a<sub>i </sub></em>≤ 10<sup>5</sup></td>

   <td width="348"> </td>

  </tr>

  <tr>

   <td width="176"><strong>Test Group 0 (0 %)</strong>•   Sample Input.<strong>Test Group 1 (20 %)</strong>•   <em>N </em>≤ 25.</td>

   <td width="348"><strong>Test Group 2 (30 %)</strong>•   <em>N </em>≤ 100<strong>Test Group 3 (50 %)</strong>•   No additional constraint.</td>

  </tr>

 </tbody>

</table>

<strong>Output</strong>

Please print an integer representing the smallest sum of risk values of the <em>M </em>segments.

<strong>Sample Input 1                                                        Sample Output 1</strong>

5 2                                                                             14

1 2 3 4 5

<strong>Sample Input 2                                                        Sample Output 2</strong>

5 3                                                                             10

1 2 3 4 5

<strong>Sample Input 3                                                        Sample Output 3</strong>

5 5                                                                             15

1 2 3 4 5

<strong>Hint</strong>

<ul>

 <li>The risk-value function has no specific meaning and you don’t have to focus on it.</li>

 <li>You can check this <a href="https://www.csie.ntu.edu.tw/~b07902133/ADA2021-HW4-RiskValue.cpp">sample code</a> to see how to calculate the risk value.</li>

</ul>

<strong>Problem 5 – </strong><strong> NPC &amp; Reduction (Hand-Written) (30 points)</strong>

First, here present some interesting problems. The definitions are given below:

<strong>JoJo’s Bizarre Adventure Problem (JJBAP)</strong>

Given a sequence of integers S = (<em>a</em><sub>1</sub><em>,</em>··· <em>,a<sub>n</sub></em>) with cardinality <em>n </em>and an integer <em>T</em>. The <em>JoJo’s Bizarre Adventure Problem </em>seeks whether there is a subsequence of S whose sum equals <em>T</em>. This problem is known to be NP-complete.

<strong>Quintessential Quintuplets Problem (QQP)</strong>

Given a sequence of non-negative integers S = (<em>a</em><sub>1</sub><em>,</em>··· <em>,a<sub>n</sub></em>) with cardinality <em>n </em>and. The <em>Quintessential Quintuplets Problem </em>seeks whether there is a subsequence of S whose sum equals <em>U/</em>2.

<strong>Dragon Ball Problem (DBP)</strong>

Given a collection of <em>n </em>balls B with weights <em>a</em><sub>1</sub><em>,</em>··· <em>,a<sub>n </sub></em>kilograms respectively, with constraint that <em>a<sub>i </sub></em>∈ [0<em>,</em>1], i.e., a single ball’s weight is at most 1 kilogram and at least 0 kilogram (yes, <em>a<sub>i </sub></em>may be 0, to make the following problem simpler). The <em>Dragon Ball Problem </em>seeks to partition balls into a minimum number of bins such that all the bins weigh at most 1 kilogram.

Recall that if problem <em>Y </em>can be reduced to problem <em>X </em>in polynomial time, we denote this by <em>Y </em>≤<em><sub>p </sub>X</em>. It also means that <em>X </em>is at least as hard as <em>Y </em>because if you solve <em>X</em>, you solve <em>Y </em>. An immediate corollary is the transitivity of “≤<em><sub>p</sub></em>”, i.e. if <em>Z </em>≤<em><sub>p </sub>Y </em>and <em>Y </em>≤<em><sub>p </sub>X </em>then we will have <em>Z </em>≤<em><sub>p </sub>X</em>.

<strong>Reminder: </strong>It is good to practice how to write down proofs properly. <strong>Do not use pseudocode to explain how your algorithm works. </strong>Also, keep your proof and algorithm as readable as possible. If you want to make sure whether you can get full credit with your solution, you are encouraged to contact TAs via email or discuss with TAs during TA hours.

You may assume the transitivity of “≤<em><sub>p</sub></em>” and the NP-completeness of <em>JJBAP </em>in the following problems.

For each “show that <em>Y </em>≤<em><sub>p </sub>X</em>”, please

<ul>

 <li>Show the correctness of your reduction. In particular, if <em>Y </em>and <em>X </em>are decision problems, <em>f </em>is a transformation between the instances of <em>Y </em>and those of <em>X</em>, <em>L </em>is an instance of <em>Y </em>and <em>f</em>(<em>L</em>) is an instance of <em>X</em>, you need to show that the answer to <em>L </em>is “yes” if and only if the answer to <em>f</em>(<em>L</em>) is “yes”.</li>

 <li>Provide a polynomial-time reduction algorithm for <em>f </em>and briefly explain why your algorithm meets the time requirement. In particular, if <em>f </em>is your transformation, explain why it takes polynomial time to complete the transformation. This can be done within two sentences in the following problems. If your reduction algorithm is too complicated to explain in one or two sentences, it is probably wrong.</li>

</ul>

Here begins the problem section:

<ol>

 <li><strong>(6 points) </strong>Consider a variant of <em>JJBAP</em>: given a sequence of <strong>non-negative </strong>integers S = (<em>a</em><sub>1</sub><em>,</em>·· <em>,a<sub>n</sub></em>) with cardinality <em>n </em>and an integer <em>T</em>, and determine whether there is a subsequence of S whose sum equals <em>T</em>. Let’s denote this problem <em>JJBAP</em><sub>+</sub>.</li>

</ol>

In fact, <em>JJBAP </em>and <em>JJBAP</em><sub>+ </sub>are equivalent with respect to polynomial-time reduction, i.e., <em>JJBAP</em><sub>+ </sub>≤<em><sub>p </sub>JJBAP </em>and <em>JJBAP </em>≤<em><sub>p </sub>JJBAP</em><sub>+</sub>. An immediate consequence is that <em>JJBAP</em><sub>+ </sub>is also NP-complete. It is straightforward to see that <em>JJBAP</em><sub>+ </sub>≤<em><sub>p </sub>JJBAP</em>. Please show <strong>the other direction</strong>.

<strong>Hint: </strong>you wish the transformed <em>a<sub>i </sub></em>are all non-negative, so you can solve <em>JJBAP </em>by solving <em>JJBAP</em><sub>+ </sub>given the transformed problem instance. Let <em>L </em>= (<em>a</em><sub>1</sub><em>,</em>··· <em>,a<sub>n</sub></em>;<em>T</em>) be an instance of <em>JJBAP</em>, then consider a transformation <em>f </em>from instances of <em>JJBAP </em>to those of <em>JJBAP</em><sub>+</sub>, in the sense that

<em>n K</em>’s

How do you choose <em>K</em>? And, when do you need to do the transformation? Don’t forget to justify that the answer to the problem instance <em>L </em>is “yes” if and only if the answer to <em>f</em>(<em>L</em>) is “yes”.

<strong>More Hint: </strong>This problem is considered to be tricky. −min<em>a<sub>i </sub></em>is not a good enough choice for <em>K</em>. Absolute value and its triangle inequality may be useful for this problem.

<ol start="2">

 <li><strong>(0 points) </strong>Show that <em>JJBAP </em>≤<em><sub>p </sub>QQP </em>using the result in the previous problem. Mimic the proof given in the lecture slides. This problem is just an extra exercise for you and will not be graded.</li>

</ol>

<strong>Hint: </strong>add some integers to the original problem instance.

<ol start="3">

 <li><strong>(6 points) </strong><span style="text-decoration: line-through;">Show that <em>QQP </em>≤<em><sub>p </sub>DBP</em>. </span>Write down the corresponding decision problem of <em>DBP </em>and let’s call this problem <em>DDBP</em>. Show that <em>QQP </em>≤<em><sub>p </sub>DDBP</em>, and deduce that <em>QQP </em>≤<em><sub>p </sub>DBP</em>.</li>

 <li><strong>(3 points) </strong>Briefly explain why <em>QQP </em>and <em><span style="text-decoration: line-through;">DBP </span></em><em>DDBP </em>are both NP. Deduce that <em>QQP </em>and <em><span style="text-decoration: line-through;">DBP </span></em><em>DDBP </em>are NP-complete from the previous results.</li>

 <li><strong>(6 points) </strong>If <em>P </em>6= <em>NP</em>, show that there is no polynomial time (3 )-approximation for <em>DBP</em>, where <em>&gt; </em>0 is any small positive number.</li>

</ol>

The following problems will guide you to give an example that “small additional restrictions may change a problem a lot”.

We say a collection of balls B suffices (<em>c,m</em>)<em>-Kuan’s first condition </em>if each ball in B is at least <em>c </em>kilogram and there are only <em>m </em>different types of weights in B for some <em>c &gt; </em>0 and <em>m </em>∈ N. Fix <em>c </em>and <em>m</em>, and we call the <em>DBP </em>problem with (<em>c,m</em>)-Kuan’s first condition as (<em>c,m</em>)-Kuan’s <em>DBP</em>. Here you will show that (<em>c,m</em>)-Kuan’s <em>DBP </em><span style="text-decoration: line-through;">is in the complexity class <em>P </em></span>can be solved in polynomial time.

<ol start="6">

 <li><strong>(3 points) </strong>For example, there are 5 balls which weigh <em>π/</em>4, 1/2, 1/2, 1/3, 1/4 respectively, then there are totally 9 choices of the balls to form a valid content of a single bin. The content of a single bin may be one of the following form:</li>

</ol>

<ul>

 <li>{}, i.e., it’s an empty bin.</li>

</ul>

<h2>• {π/4}</h2>

<ul>

 <li>{1<em>/</em>2}</li>

 <li>{1<em>/</em>3}</li>

 <li>{1<em>/</em>4}</li>

 <li>{1<em>/</em>2<em>,</em>1<em>/</em>2}</li>

 <li>{1<em>/</em>2<em>,</em>1<em>/</em>3}</li>

 <li>{1<em>/</em>2<em>,</em>1<em>/</em>4}</li>

 <li>{1<em>/</em>3<em>,</em>1<em>/</em>4}</li>

</ul>

Note that {<em>π/</em>4<em>,</em>1<em>/</em>2<em>,</em>1<em>/</em>4}, {1<em>/</em>2<em>,</em>1<em>/</em>2<em>,</em>1<em>/</em>3} and {1<em>/</em>2<em>,</em>1<em>/</em>3<em>,</em>1<em>/</em>4} are not valid contents of a single bin, since they all exceed the weight limit.

Find an upper bound of “the number of choices of the balls that form a valid content of a single bin”, and represent it with <em>m </em>and <em>c</em>. Your answer should be an integer independent of <em>n</em>.

<strong>Hint: </strong>Consider the number of combinations. Note that there may be balls with identical weights, especially as <em>n </em>→ ∞.

<ol start="7">

 <li><strong>(3 points) </strong>Denote the upper bound you found in the previous problem as <em>M</em>. Now given <em>k </em>indistinguishable bins, you can compute the number of ways to put all the balls inside these <em>k </em>bins, denote this number Γ(<em>k</em>). Show that Γ(<em>k</em>) is bounded-above by <em>C<sub>M</sub>k<sup>M </sup></em>for some <em>C<sub>M</sub></em>, which is a positive constant independent of choice of <em>k </em>and may depend on <em>M</em>. You can either “justify the existence of <em>C<sub>M</sub></em>” or “write down your favorite <em>C<sub>M </sub></em>and simply explain why your <em>C<sub>M </sub></em>meets the requirement”. Again, the sum of weight of the content in any single bin should not exceed 1 kilogram.</li>

</ol>

<strong>Remark: </strong>In fact, it is equivalent to show Γ(<em>k</em>) = <em>O</em>(<em>k<sup>M</sup></em>) with respect to the variable <em>k</em>. If you use this fact, you also need to write down the reason why they are equivalent.

<ol start="8">

 <li><strong>(3 points) </strong>Based on the previous results, provide an <em>O</em>(<em>n<sup>M</sup></em><sup>+1</sup>) time algorithm for (<em>c,m</em>)-Kuan’s <em>DBP</em><span style="text-decoration: line-through;">, where <em>L </em>is some non-negative integer independent of <em>n</em></span>. Analyze the time complexity of your algorithm and justify the asymptotic bound rigorously as you did in Homework #1. Deduce that <span style="text-decoration: line-through;">(<em>c,m</em>)-Kuan’s <em>DBP </em></span>(<em>c,m</em>)-Kuan’s <em>DDBP</em>, the decision version of (<em>c,m</em>)-Kuan’s <em>DBP</em>, is in the complexity class <em>P</em>.</li>

</ol>

(<em>c,m</em>)-Kuan’s second condition: You should go to bed at 0037

<strong>Problem 6 – </strong><strong> Merry Christmas (Hand-Written) (20 points)</strong>

<em>Please see the class slides for the definition of the </em><em>Traveling Salesman Problem (TSP) and what it means to have a </em><em>TSP whose edge costs satisfy the triangle inequality.</em>

In class, Ada has learned a 2-approximation algorithm using <strong>Minimum Spanning Tree (MST) algorithms </strong>to solve <strong>TSP </strong>on a graph <strong>G </strong>whose edge costs satisfy the triangle inequality. Now, Ada wants to design a better algorithm with a smaller approximation ratio. Can you help?

<ol>

 <li>(2pt) Describe the sufficient and necessary condition for <em>G </em>to contain an Eulerian cycle.</li>

 <li>(4pt) Given that <em>T </em>is a tree and <em>V </em><sup>0 </sup>= {vertex <em>v </em>with odd degree |∀<em>v </em>∈ <em>T</em>}, prove that |<em>V </em><sup>0</sup>| is</li>

</ol>

even.

In graph theory, a perfect matching in a graph is a matching that covers every vertex of the graph. More formally, given a graph <em>G </em>= (<em>V,E</em>), a perfect matching in <em>G </em>is a subset <em>M </em>of <em>E</em>, such that every vertex in V is adjacent to exactly one edge in <em>M</em>.

<ol start="3">

 <li>(6pt) Let <em>V </em><sup>0 </sup>⊆ <em>V </em>, such that |<em>V </em><sup>0</sup>| is even, and let <em>M </em>be a minimum cost perfect matching on <em>V </em><sup>0</sup>. Prove that <em>cost</em>(<em>M</em>) ≤ <em>OPT/</em>(this OPT is the TSP problem’s OPT)</li>

 <li>(8pt) Given a function <strong>Oracle </strong>which can find a minimum cost perfect matching of <em>V </em>in polynomial time, please design a 3/2-approximation algorithm to solve this problem and show that

  <ul>

   <li>It is 3/2-approximation.</li>

   <li>The time complexity of your algorithm is polynomial.</li>

  </ul></li>

</ol>

<strong>Appendix</strong>

<strong>GLPK Installation</strong>

For some common Linux distributions or MacOS (you may need to install <a href="https://brew.sh/index_zh-tw">Homebrew</a><a href="#_ftn7" name="_ftnref7"><sup>[7]</sup></a> using the installation command in its official website) user, you may install the GLPK package from their official package repositories. For example:

<strong>Note that for MacOS users that uses GNU g++ instead of clang++ (default g++), and install the GLPK package from Homebrew</strong>, since the GNU g++ does not use the system’s library that includes the installed GLPK package, you may need to provide additional compilation arguments to specify the path to find the GLPK package. For example, you may try to use the below compilation command (assume your g++ is GNU g++):

For Windows user, you may install the GLPK package from <a href="https://www.cygwin.com/">Cygwin</a><a href="#_ftn8" name="_ftnref8"><sup>[8]</sup></a>:

<ol>

 <li>Download the <a href="https://www.cygwin.com/setup-x86_64.exe">Cygwin installer</a><a href="#_ftn9" name="_ftnref9"><sup>[9]</sup></a> and execute the installer. Below assume you install the cygwin at the default directory C:cygwin64.</li>

 <li>Follow the default installation settings to download from an arbitrary mirror.</li>

 <li>At the package selection page, change the view to “Full” and install the following package:

  <ul>

   <li>Search for g++ and select the package gcc-g++ package with version 10.2.0-1.</li>

   <li>Search for glpk and select both package glpk and libglpk-devel with version 5.0-1.</li>

  </ul></li>

 <li>After the installation, copy the source code and the header file to the C:cygwin64home</li>

 <li>Run the C:cygwin64Cygwin batch file, and you should see a terminal (simple linux shell).</li>

 <li>Type ls into the terminal and you should see the files you put in the previous step (step 4).</li>

 <li>At last, you can simply run the compilation command described above to compile your program, and run it with ./example</li>

</ol>

For other Unix-based operating systems which are able to run curl, tar, gcc, g++, make commands, you can use the following script to build and install GLPK package from source:

curl -o glpk-5.0.tar.gz https://ftp.gnu.org/gnu/glpk/glpk-5.0.tar.gz tar -xzvf glpk-5.0.tar.gz &amp;&amp; cd glpk-5.0 ./configure &amp;&amp; make &amp;&amp; sudo make install

# cd to the directory that contains your source codes and the given header g++ -std=c++17 -O2 -oexample example.cpp -lglpk -Wall

LD_LIBRARY_PATH=/usr/local/lib ./example

# you can use ‘sudo make uninstall‘ command in the glpk-5.0 directory

# to uninstall the GLPK package

Moreover, if you do not have root access (or do not want to install the package globally, you can use the following script to install it in a rootless location:

# assume your current working directory is $HOME,

# the glpk package will be installed at $HOME/glpk-5.0/build curl -o glpk-5.0.tar.gz https://ftp.gnu.org/gnu/glpk/glpk-5.0.tar.gz tar -xzvf glpk-5.0.tar.gz &amp;&amp; cd glpk-5.0

./configure –prefix=$PWD/build &amp;&amp; make &amp;&amp; make install

# cd to the directory that contains your source codes and the given header g++ -std=c++17 -O2 -oexample example.cpp -I $HOME/glpk-5.0/build/include 

-L $HOME/glpk-5.0/build/lib -lglpk -Wall

LD_LIBRARY_PATH=$HOME/glpk-5.0/build/lib ./example

If you still have any problem with the GLPK package or failed to compile or run the programs locally, feel free to email TAs for help as soon as possible. Besides, to let us figure out the problem sooner, please provides the environment (operating system), the problem detail you encountered, and maybe some screenshot or error message you saw when you are asking for help.

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="https://www.gnu.org/software/glpk/">https://www.gnu.org/software/glpk/</a>

<a href="#_ftnref2" name="_ftn2">[2]</a> <a href="http://most.ccib.rutgers.edu/glpk.pdf">http://most.ccib.rutgers.edu/glpk.pdf</a>

<a href="#_ftnref3" name="_ftn3">[3]</a> <a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/ypglpk.hpp">http://www.csie.ntu.edu.tw/</a><a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/ypglpk.hpp">~</a><a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/ypglpk.hpp">giver/ADA/hw4/ypglpk.hpp</a>

<a href="#_ftnref4" name="_ftn4">[4]</a> <a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/example.cpp">http://www.csie.ntu.edu.tw/</a><a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/example.cpp">~</a><a href="http://www.csie.ntu.edu.tw/~giver/ADA/hw4/example.cpp">giver/ADA/hw4/example.cpp</a>

<a href="#_ftnref5" name="_ftn5">[5]</a> <a href="http://w.csie.org/~b08902107/ADA/connect4_public.zip">http://w.csie.org/</a><a href="http://w.csie.org/~b08902107/ADA/connect4_public.zip">∼</a><a href="http://w.csie.org/~b08902107/ADA/connect4_public.zip">b08902107/ADA/connect4</a> <a href="http://w.csie.org/~b08902107/ADA/connect4_public.zip">public.zip</a>

<a href="#_ftnref6" name="_ftn6">[6]</a> <a href="http://w.csie.org/~b08902103/ADA/ada-hw4-p3.zip">http://w.csie.org/</a><a href="http://w.csie.org/~b08902103/ADA/ada-hw4-p3.zip">∼</a><a href="http://w.csie.org/~b08902103/ADA/ada-hw4-p3.zip">b08902103/ADA/ada-hw4-p3.zip</a>

<a href="#_ftnref7" name="_ftn7">[7]</a> <a href="https://brew.sh/index_zh-tw">https://brew.sh/index_zh-tw</a>

<a href="#_ftnref8" name="_ftn8">[8]</a> <a href="https://www.cygwin.com/">https://www.cygwin.com/</a>

<a href="#_ftnref9" name="_ftn9">[9]</a> <a href="https://www.cygwin.com/setup-x86_64.exe">https://www.cygwin.com/setup-x86_64.exe</a>