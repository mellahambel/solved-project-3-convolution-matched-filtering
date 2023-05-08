Download Link: https://assignmentchef.com/product/solved-project-3-convolution-matched-filtering
<br>
<strong>Introduction</strong>

The acquisition of a signal in a digital communications system requires the convergence of several signal processing technologies. The major receiver technologies are (1) ADCs, (2) timing recovery, (3) carrier recovery, (4) channel equalization, (5) signal detection, and (6) matched filtering (convolution).




<strong>Matched filtering</strong>




Practical receivers often estimate the transmitted signal by using a technique known as matched filtering. A receiver employing such a strategy possesses filters the received signal with a filter whose shape is “matched” to the transmitted signal’s pulse shape. Specifically the matched filter’s pulse shape is a time-reversed version of the transmit pulse shape. Thus, if the transmitted pulse shape <em>h(t) </em>is known to be:




<em>h(t) </em>for 0 ≤ <em>t </em>≤ <em>T</em>




then the matched filter’s response <em>h<sub>m</sub></em>(<em>t</em>) is:

<em> </em>

<em>h<sub>m</sub></em>(<em>t</em>) = <em>h</em>(<em>T–t</em>) for 0 ≤ <em>t </em>≤ <em>T</em>




Such processing provides two advantages. By filtering the received signal with a matched filter, only thoes frequencies contained in the transmitted signal’s spectrum are process while the remaining frequencies are ignored or nulled.  Therefore matched filters limit the amount of the noise that is passed on to subsequent receiver stages, maximizing the receiver’s SNR. A second advantage is that a matched filter correlates the received signal with the transmit pulse shape over the symbol period <em>T</em>. Such processing results in a correlation gain by integrating the received signal energy while averaging out the zero-mean AWGN.




An example of matched filtering is shown in Figure 1.




<table>

 <tbody>

  <tr>

   <td width="0"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>











































<table>

 <tbody>

  <tr>

   <td width="31">

    <table width="100%">

     <tbody>

      <tr>

       <td>1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Figure 1: Signal with and without noise (left) and their matched filter outcomes (right) measured at the end of each message period.




<strong>Spread Spectrum (Mitra)</strong>




Consider a multiuser <em>spread spectrum</em> communication system in which the transmitted data sequence is obtained by modulation a low-rate set of data <em>symbols</em> with a high-rate <em>spreading sequence</em>, typically chosen to be periodic pseudo-random sequence or orthogonal basis set (e,g,; Walsh functions).  The elements of the spreading sequence are called <em>chips</em>.  The number of chips per symbol is called the <em>processing gain</em> (denoted N).  The following N=5 example illustrates how the system works.




The data (symbols) to be transmitted is m[k] = { -1 -1 +1 +1 -1}




For each of 4-distinct users a binary-valued random spreading sequence, denoted s<sub>i</sub> (see below) is defined providing a processing gain N=5.




s<sub>1</sub>: { -1 +1 -1 +1 +1}:  user 1

s<sub>2</sub>: { -1 -1 -1  -1 +1}:   user 2

s<sub>3</sub>: { -1 +1 -1 -1 +1}:   user 3

s<sub>4</sub>: { +1 -1 -1 -1 +1}:   user 4




Generate an up-sampled N=5 data set of 5 symbols (note MATLAB indexing begins indexing with 1 not 0) based on m[k].

<table>

 <tbody>

  <tr>

   <td width="52">

    <table width="100%">

     <tbody>

      <tr>

       <td>d[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="37">

    <table width="100%">

     <tbody>

      <tr>

       <td>-1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="37">

    <table width="100%">

     <tbody>

      <tr>

       <td>-1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="37">

    <table width="100%">

     <tbody>

      <tr>

       <td>-1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="34">

    <table width="100%">

     <tbody>

      <tr>

       <td>1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="34">

    <table width="100%">

     <tbody>

      <tr>

       <td>1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Figure 2:  Up-sampled (by 5) slow-rate data sequence m[k] to produce d[k]=[-1 -1 -1 -1 -1: -1 -1 -1 -1 -1: 1 1 1 1 1: 1 1 1 1 1: -1 -1 -1 -1 -1 ] for N=5 (nÎ[0,24]).




Suppose a message is intended for user 1.  The transmitter generates a high-rate spreading sequence S<sub>1</sub>[k] based on s<sub>1</sub>[k].

<table>

 <tbody>

  <tr>

   <td width="63">

    <table width="100%">

     <tbody>

      <tr>

       <td>s<sub>1</sub>[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="64">

    <table width="100%">

     <tbody>

      <tr>

       <td>s<sub>1</sub>[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="64">

    <table width="100%">

     <tbody>

      <tr>

       <td>s<sub>1</sub>[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="63">

    <table width="100%">

     <tbody>

      <tr>

       <td>s<sub>1</sub>[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="64">

    <table width="100%">

     <tbody>

      <tr>

       <td>s<sub>1</sub>[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="64">

    <table width="100%">

     <tbody>

      <tr>

       <td>S<sub>1</sub>[k]</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Figure 3: Periodic spreading sequence S<sub>1</sub>[k]=[-1 1 -1 1 1: -1 1 -1 1 1: -1 1 -1 1 : -1 1 -1 1 1: -1 1 -1 1 1 ] for user 1  (N=5) (nÎ[0,24]) based on s<sub>1</sub>[k] = [-1 1 -1 1 1].




Modulate the up sampled d[k] with S<sub>1</sub>[k] (i.e., d[k]*S<sub>1</sub>[k] ) using point-by-point multiplicative modulation.

Figure 4:  Product modulated sequence p[k]= d[k]*S<sub>1</sub>[k] =[1 -1 1 -1 -1: 1 -1 1 -1 -1: -1 1 -1 1 1: -1 1 -1 1 1: 1 -1 1 -1 -1] for intended user 1(N=5) (nÎ[0,24]) (i.e., d[k]*S<sub>1</sub>[k] )




Define the digital matched filter as the reverse image of s<sub>1</sub>[k] = [-1 1 -1 1 1], namely h<sub>1m</sub>[k] = [1 1 -1 1 -1 ].  That is, the matched filter is the reverse image of s<sub>1</sub>.  Convolve the received signal with the matched filter h<sub>1m</sub>[k].




<table>

 <tbody>

  <tr>

   <td width="37">

    <table width="100%">

     <tbody>

      <tr>

       <td>-1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="36">

    <table width="100%">

     <tbody>

      <tr>

       <td>1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="36">

    <table width="100%">

     <tbody>

      <tr>

       <td>1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="37">

    <table width="100%">

     <tbody>

      <tr>

       <td>-1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td width="36">

    <table width="100%">

     <tbody>

      <tr>

       <td>-1</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Figure 5:Output of the matched filter: y<sub>1</sub>[k] = [ 1 0 -1 2 -5: 3 -1 -1 3 -5: 1 -1 1 -1 5: -3 1 1 -3 5: -1 1 -1 1 -5] for user 1; (N=5) (nÎ[0,24])




Notice that at the end of each 5–sample periods (k=5, 10, 15, 20, 25), the matched filter achieves its maximal output value of ±5 corresponding to a processor gain of N=5.  Using a decision threshold ±4, for example, the original message m[k] = {-1 -1 +1 +1 -1} is recovered without error.  With noise present, a more careful threshold selection would be needed.




<strong>Project 3</strong>




Project 3 is an extension of the spread-spectrum N=5 example considered in the previous section.




Generate, using MATLAB:




<ul>

 <li>a 20 random symbol (±1 valued) low-rate data message m[k]. For N=5, the transmitted signal d[k] consists of 100 samples.</li>

 <li>a user #1 N=5 random spreading sequence S<sub>1</sub>[k]. That is, copy s<sub>1</sub>[k] 20 times to create a periodic  100-sample signal S<sub>1</sub>[k].</li>

 <li>a 100 sample product modulated signal p[k].</li>

</ul>




Perform the modulation and match filtering as practiced in the opening example.




Q1:  Using d[k] and S<sub>1</sub>[k] (message directed to user #1), generate the matched filter output and determine the bit error rate (BER) for a rationale choice of decision threshold.




Q2:  Repeat Q1 except use the matched filter for user #2.  Determine the bit error rate (BER) for a rationale choice of decision threshold.




Q3:  Add normal noise to the message d[k] for a SNR level of SNR = 0dB – verify.  Repeat the Q1 study and report. Determine the bit error rate (BER) for a rationale choice of decision threshold.







Due Oct.Oct.31, 2016

Same format as last project.