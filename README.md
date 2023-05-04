Download Link: https://assignmentchef.com/product/solved-csci-3104-assignment-4
<br>
<ol>

 <li>Recall that Huffman’s algorithm takes as input a vector <em>f </em>of length <em>n</em>, containing the frequencies of the input symbol set <em>C </em>and returns a Huffman encoding tree. We can make the process of encoding real strings faster by instead returning a <em>codebook</em>, which is a dictionary ADT <em>T </em>that contains <em>n </em>key-value pairs (<em>x<sub>i</sub>,y<sub>i</sub></em>), where <em>x<sub>i </sub></em>∈ <em>C </em>and <em>y<sub>i </sub></em>is the Huffman binary encoding of <em>x<sub>i</sub></em>. Let <em>T</em>(<em>x<sub>i</sub></em>) = <em>y<sub>i</sub></em>. Hence, the encoding of <em>x </em>= <em>x</em><sub>1</sub><em>x</em><sub>2</sub><em>x</em><sub>3 </sub><em>…x<sub>l </sub></em>is simply <em>y </em>= <em>T</em>(<em>x</em><sub>1</sub>)<em>T</em>(<em>x</em><sub>2</sub>)<em>T</em>(<em>x</em><sub>3</sub>)<em>…T</em>(<em>x<sub>l</sub></em>).</li>

</ol>

In this problem, you will implement and apply three functions: (i) strToFreq, (ii) huffmanEncode, and (iii) encodeStr.

<ol>

 <li>Implement the three functions, i.e. strToFreq, huffmanEncode, encodeStr, <strong>from scratch</strong>. For Huffman’s algorithm, use a min-heap as a priority queue. Within this priority queue, ties should be broken uniformly at random.</li>

 <li>What is the running time of the call y = encodeStr(x, huffmanEncode(strToFreq(x)))? Justify your answer using asymptotic analysis.</li>

 <li>Pick your favorite quote, poem, or piece of text that has length <em>l &gt; </em>500 characters (not too long either, for simplicity). Given that <em>ASCII </em>characters are usually represented using 8 bits, how many bits are required to represent the entire text?</li>

 <li>Claude Shannon famously proved that the lower bound on the number of encoded bits per input symbol for a prefix-free binary encoding of a string <em>x </em>is given by the entropy function, defined as</li>

</ol>

where <em>f<sub>i </sub></em>is the frequency in <em>x </em>of the <em>i</em>th symbol in <em>C</em>, and <em>l </em>is the length of <em>x</em>. Because we take log<sub>2</sub>, <em>H </em>has units of <em>bits</em>. Using this equation, compute (i) the predicted number of bits per symbol needed to optimally encode the text you chose in part (c), and (ii) the predicted number of bits needed to encode the entire text you chose.

<ol>

 <li>Now use your Huffman encoder from part (a) to encode your text and report the number of bits in the encoded string. Compare this number to the lower bound obtained in part (d) and comment on the comparison.</li>

</ol>

<ol start="2">

 <li>Here, you will modify and then use your Huffman encoder from part (1) to perform a numerical experiment to show that your encoder uses O(<em>n</em>log<em>n</em>) time on an input of size <em>n</em>. The deliverables here are (i) a nice figure showing this result and (ii) a brief description of how you modified your code and ran your experiment.</li>

</ol>

First, implement a new function makeHuffmanInput, which takes an argument <em>n</em>, the size of the symbol set <em>C</em>, and returns a vector of counts <em>f </em>of length <em>n</em>, in which each <em>f<sub>i </sub></em>is a positive integer chosen uniformly at random from the interval [1<em>,</em>100]. Second, modify your huffmanEncode function by adding measurement code that counts the number of atomic operations it performs before returning.