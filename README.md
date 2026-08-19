# Cybersecurity Incident Report — Summary

A travel agency's website went down, giving customers and employees connection timeout errors. Investigation of the traffic logs traced the cause to a **SYN flood Denial-of-Service (DoS) attack** — a suspicious source IP (`203.0.113.0`) was sending repeated SYN requests to the web server, overwhelming its capacity to respond.

**How it works:** Normal connections use a TCP three-way handshake — the client sends a SYN, the server replies with a SYN-ACK, and the client finishes with an ACK. In this attack, the flood of SYN requests filled the server's connection backlog queue faster than it could process them, so real users' connection attempts were rejected and they received error pages instead.
