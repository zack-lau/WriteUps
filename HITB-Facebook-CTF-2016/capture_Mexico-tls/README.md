<b>Question:</b> Can you break TLS? [200PTS]<br>
<b>Note:</b> Flag doesn't start with flag{}<br>
<b>Category:</b> Crypto<br>
<b>File:</b> <a href="https://github.com/zack-lau/WriteUps/blob/master/HITB-Facebook-CTF-2016/capture_Mexico-tls/tls_16970cb3b09a9dd01f5b82449d9c1795.tar.gz">tls_16970cb3b09a9dd01f5b82449d9c1795.tar.gz</a>

<b>Introduction</b><br>
The goal of this question is to decrypt the TLS encrypted contents in the PCAP file (of course). The detailed techinical document for the techniques/tools used for answering the question are authored by <b>Marco Ortisi</b> (thank you very much indeed!) and here is his <a href="http://www.segfault.it/tools/Blackhat2016US-wp.pdf">white paper</a>.<br><br>
Since I only have access to the PCAP, I used the information from the passive approach discribed in Marco's white paper to determine whether there is a faulty signature to allow further actions to be done in attempt to obtain the private key.<br><br>
The steps in solving this question is simple as the required tools have been written by Marco. IMHO, it is important to understand why this attack works in this scenario and how it works. Therefore, I strongly recommend all readers of this write up spare some time to read the white paper produced by Marco. This attack works on products that are using RSA-CRT, but the fix is simple......disabling RSA-CRT!!!<br><br>
<b>Solution</b>
<ol>
<li type="1">Review and analyse the protocols in the PCAP file and it's TLS 1.2 in this PCAP file.</li>
<li type="1">Check whether all prerequisites are fulfilled for the attack.</li>
<li type="1">Split up the PCAP file using tcpflow by running:<br><b>tcpflow -r <i>&lt;PCAP file&gt;</i></b></li>
<li type="1">Run <b>ls -la</b> to make sure there are outputs in the directory.</li>
<li type="1">Go download the awesome tool written by Marco from <a href="http://www.segfault.it/tools/tools-latest.zip">here</a> and compile "piciolla".</li>
<li type="1">Compile "piciolla" and place the executable in the same directory of "piciolla.sh"</li>
<li type="1">Execute "piciolla.sh" with splited PCAP files folder path as parameter:<br><b>./piciolla.sh <i>&lt;Folder of splited PCAP files&gt;</i></b></li>
<li type="1">"piciolla" will start to analyse the packets.</li>
<li type="1">Results are placed in the <b>"results"</b>.</li>
<li type="1">Finally, use the private key in the <b>"results"</b> folder to decrypt the traffics in your favorite tools!</li>
</ol>
<b>References</b><br>
<a href="https://access.redhat.com/blogs/766093/posts/1976703"><i>Factoring RSA Keys With TLS Perfect Forward Secrecy</i>, Red Hat, 2015</a><br>
<a href="http://www.segfault.it/tools/Blackhat2016US-wp.pdf"><i>Recover a RSA private key from a TLS session with Perfect Forward Secrecy (White Paper)</i>, Marco Ortisi, 2016</a><br>

Please let me know if you have any questions.<br>
Email: <a href="mailto:zack@zack.idv.hk">zack@zack.idv.hk</a>
