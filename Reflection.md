## Reflection

### Activity Description
For this activity I participated in the CyberQuests Spring 2026 challenge which involved analyzing packet capture files using Wireshark. The goal was to investigate network traffic identify scanning behavior determine open and closed ports
analyze industrial protocols and extract information such as authentication details from HTTP traffic. I completed all sections of the challenge by filtering packets following TCP streams an examining both decoded data and raw hex data to answer 
each question.

### Technical Decisions
Throughout the activity, I made several technical decisions to make analysis more efficient. I used Wireshark filters such as 
`tcp.port`, `tcp.flags.syn`, and `http`and others to isolate specific traffic. I also used `frame contains` to search for keywords like "Authorization," which helped me quickly
find authentication data. When analyzing login behavior I chose to follow TCP streams to view full conversations instead of relying only on packet summaries. For identifying patterns like counters
I compared multiple packets at the hex level to confirm consistent changes at specific offsets.

### Contributions
I completed this activity individually. All analysis, filtering, and interpretation of the packet captures were done by myself. I was responsible for identifying patterns, verifying answers, 
and documenting the results for each question.

### Quality Assessment
I would assess my participation as strong because I was able to complete the a decent amount of the challenge and understand how the network traffic worked instead of just guessing answers. 
I improved my ability to use Wireshark filters and learned how to analyze real-world protocols like EtherNet/IP and HTTP authentication. If I were to redo the activity
I would spend more time organizing my workflow earlier such as systematically checking each port and documenting findings as I go to avoid confusion . Overall
this activity helped me gain practical experience in network analysis and cybersecurity concepts. I feel more confident with how Wireshark works and how useful it is.
