Download Link: https://assignmentchef.com/product/solved-cs10c-assignment1-simple-data-compression
<br>
Huffman coding is used to compress data. The idea is straightforward: represent more common longer strings with shorter ones via a basic translation matrix. The translation matrix is easily computed from the data itself by counting and sorting by frequency

For example, in a well-known corpus used in Natural Language Processing called the “Brown” corpus (see nltk.org), the top-20 most frequent tokens, which are words or punctuation marks are listed below associated with frequency and code. The word “and” for example requires writing three characters. However, if I encoded it differently, say, using the word “5” (yes, I called “5” a word on purpose), then I save having to write two extra characters! Note, the word “and” is so frequent, I save those two extra characters many times over!

<table width="183">

 <tbody>

  <tr>

   <td colspan="2" width="144">Token Frequency</td>

   <td width="39">Code</td>

  </tr>

  <tr>

   <td width="48">the</td>

   <td width="96">62713</td>

   <td width="39">1</td>

  </tr>

  <tr>

   <td width="48">,</td>

   <td width="96">58334</td>

   <td width="39">2</td>

  </tr>

  <tr>

   <td width="48">.</td>

   <td width="96">49346</td>

   <td width="39">3</td>

  </tr>

  <tr>

   <td width="48">of</td>

   <td width="96">36080</td>

   <td width="39">4</td>

  </tr>

  <tr>

   <td width="48">and</td>

   <td width="96">27932</td>

   <td width="39">5</td>

  </tr>

  <tr>

   <td width="48">to</td>

   <td width="96">25732</td>

   <td width="39">6</td>

  </tr>

  <tr>

   <td width="48">a</td>

   <td width="96">21881</td>

   <td width="39">7</td>

  </tr>

  <tr>

   <td width="48">in</td>

   <td width="96">19536</td>

   <td width="39">8</td>

  </tr>

  <tr>

   <td width="48">that</td>

   <td width="96">10237</td>

   <td width="39">9</td>

  </tr>

  <tr>

   <td width="48">is</td>

   <td width="96">10011</td>

   <td width="39">10</td>

  </tr>

  <tr>

   <td width="48">was</td>

   <td width="96">9777</td>

   <td width="39">11</td>

  </tr>

  <tr>

   <td width="48">for</td>

   <td width="96">8841</td>

   <td width="39">12</td>

  </tr>

  <tr>

   <td width="48">“</td>

   <td width="96">8837</td>

   <td width="39">13</td>

  </tr>

  <tr>

   <td width="48">”</td>

   <td width="96">8789</td>

   <td width="39">14</td>

  </tr>

  <tr>

   <td width="48">The</td>

   <td width="96">7258</td>

   <td width="39">15</td>

  </tr>

  <tr>

   <td width="48">with</td>

   <td width="96">7012</td>

   <td width="39">16</td>

  </tr>

  <tr>

   <td width="48">it</td>

   <td width="96">6723</td>

   <td width="39">17</td>

  </tr>

  <tr>

   <td width="48">as</td>

   <td width="96">6706</td>

   <td width="39">18</td>

  </tr>

  <tr>

   <td width="48">he</td>

   <td width="96">6566</td>

   <td width="39">19</td>

  </tr>

  <tr>

   <td width="48">his</td>

   <td width="96">6466</td>

   <td width="39">20</td>

  </tr>

 </tbody>

</table>

So the steps of Huffman coding are relatively straightforward:

<ol>

 <li>Pass through the data once, collecting a list of token-frequency counts.</li>

 <li>Sort the token-frequency counts by frequency, in descending order.</li>

 <li>Assign codes to tokens using a simple counter, for example by incrementing over the integers; this is just to keep things simple.</li>

 <li>Store the new mapping (token -&gt; code) in a hashtable called “encoder”.</li>

 <li>Store the reverse mapping (code -&gt; token) in a hashtable called “decoder”.</li>

 <li>Pass through the data a second time. This time, replace all tokens with their codes.</li>

</ol>

Now, be amazed at how much you’ve shrunk your data!

<strong>Delivery Notes</strong>:​

<ul>

 <li>Implement your own hashtable from scratch, you are not allowed to use existing hash table libraries.</li>

 <li>To be useful, your output should include the coded data as well as the decoder (code -&gt; token) mapping file.</li>

</ul>

Now GZIP all that and watch it shrink immensely!