<h1>SmallCompiler</h1>
A C code compiler. 

<h2>Basics</h2>
In early october, I had an academic project to create a basic lexical scanner in C. I decided to expand on it for fun and create a baby compiler. When complete, my compiler will include lexical analysis, syntax analysis and semantic analysis. Currently, I'm working on the syntax analyzer. 

<h4>#Lexical Analyzer</h4>
<h6>summary:</h6>
-The lexical analyzer reads a file and decides if each 'token' (chunk of file) is valid. ie 'var' is valid but 23?adx.1 is not. Each token will make up elements of a token sequence which will be later checked for logical consistency by the syntax analyzer. 
The lexical analyzer works as a DFA. Each character triggers a transition. An accepting state occurs when a stream of aligning characters are followed by a space, new line, tab or EOF (end of file).<br>
-There are 11 different character types recognized: Whitespace, newline, alphabetic, 0, octal, decimal, division, multiplication, arithmetic(other), ascii(other), EOF and undefined(unrecognized symbols).<br> 
-The program begins by taking in data and parsing it into a matrix. That matrix determines the transitions in the lexical analyzer's DFA, as well as what action to take upon each transition (save the character and proceed or discard it and the stream). 

<h6>under construction:</h6>
-The lexical analyzer already knows what kind of token it's reading once it's finished-- it needs to store that in an array so the syntax analyzer can check if that sequence of tokens is logical  
-i.e.: symbol assignment number semicolon (x = 2;) is ok but number assignment symbol semicolon (2 = x;) is not <br>
<h6>known errors:</h6>
-It sometimes trips up on tab characters; I think there's two kinds of ways to tab so that's the reason? It's under investigation!<br>

<h4>#Syntax Analyzer</h4>
<h6>under construction:</h6>
I'd like to make this very similair to the lexical analyzer in that it's a DFA that transitions between states based on the token it's given. To start, I need to create another matrix of transitions triggered by tokens. 
