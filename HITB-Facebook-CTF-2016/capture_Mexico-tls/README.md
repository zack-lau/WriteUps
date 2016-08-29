Question: Can you break TLS? [200PTS]<br>
Note: Flag doesn't start with flag{}<br>
Category: Crypto<br>
<a href="https://github.com/zack-lau/WriteUps/blob/master/HITB-Facebook-CTF-2016/capture_Mexico-tls/tls_16970cb3b09a9dd01f5b82449d9c1795.tar.gz">tls_16970cb3b09a9dd01f5b82449d9c1795.tar.gz</a> (original file is included in this folder)

<b>Introduction</b><br>
The goal for this question is to decrypt the TLS encrypted contents in the PCAP file (of course). The detailed techinical document for the techniques/tools used for answering the question are authored by <b>Marco Ortisi</b> (thank you very much indeed!) and here are his <a href="https://www.blackhat.com/docs/us-16/materials/us-16-Ortisi-Recover-A-RSA-Private-Key-From-A-TLS-Session-With-Perfect-Forward-Secrecy.pdf">presentation</a> and <a href="https://www.blackhat.com/docs/us-16/materials/us-16-Ortisi-Recover-A-RSA-Private-Key-From-A-TLS-Session-With-Perfect-Forward-Secrecy-wp.pdf">white paper</a>.<br><br>
Since I only have access to the PCAP, I used the information from the passive approach discribed in Marco's white paper to determine whether there is a faulty signature to allow further actions to be done in attempt to obtain the private key.<br><br>
<b>Solution</b><br>
<ul>
<li>Review and analyse the protocols in the PCAP file and it's TLS 1.2 in this PCAP file.<br>
</ul>
<br><br>
<b>References</b><br>
<a href="https://access.redhat.com/blogs/766093/posts/1976703"><i>Factoring RSA Keys With TLS Perfect Forward Secrecy</i>, Red Hat, 2015</a><br>
<a href="https://www.blackhat.com/docs/us-16/materials/us-16-Ortisi-Recover-A-RSA-Private-Key-From-A-TLS-Session-With-Perfect-Forward-Secrecy.pdf"><i>Recover a RSA private key from a TLS session with Perfect Forward Secrecy (Presentation)</i>, Marco Ortisi, 2016</a><br>
<a href="https://www.blackhat.com/docs/us-16/materials/us-16-Ortisi-Recover-A-RSA-Private-Key-From-A-TLS-Session-With-Perfect-Forward-Secrecy-wp.pdf"><i>Recover a RSA private key from a TLS session with Perfect Forward Secrecy (White Paper)</i>, Marco Ortisi, 2016</a><br>
