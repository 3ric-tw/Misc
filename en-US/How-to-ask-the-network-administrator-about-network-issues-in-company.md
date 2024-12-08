# How to ask the IT support / network administrator about network issues in company

In the corporate environment, we often encounter a common issue: network failures. These can manifest as inability to connect to the company's intranet or external networks.

As an Infrastructure Engineer, I've faced numerous such problems, ranging from "My computer can't connect to the internal company website" to "I can't access our partner's website." Even after transitioning to a software-centric company with highly skilled software engineers, their approach to seeking help for network issues remained simplistic: "My test machine can't access the internet."

These situations often required me to spend considerable time inquiring about users' network configurations and specific circumstances. I gradually realized that the most time-consuming aspect of troubleshooting wasn't the actual problem-solving, but rather gathering information from users to diagnose the issue.

Consequently, I decided to write this guide on how to accurately describe "network connectivity issues." This approach can reduce unnecessary back-and-forth communication and improve the efficiency of troubleshooting.

## Stop Telling IT support / Network Administrator "The Network Is Down"

Imagine you're standing on a street in an unfamiliar city, and all you can say to passersby is, "I'm lost!" What would be the result? You'd likely be met with bewildered looks.

```
You: "Excuse me, I'm lost."
Passerby: "Uh... where are you trying to go? Are you driving or walking?"

You: "I don't know, I'm just lost!"
Passerby: (Internal monologue: How am I supposed to help you? Am I supposed to read your mind?)
```

Similarly, when you encounter a network problem and only say "The network is down," you're not providing IT support / Network Administrator with any actionable information for troubleshooting. They won't know where to start.

```
You: "The network is down on my test machine."
IT support / Network Administrator: (Internal monologue: Here we go again...) "Um, what specifically isn't working? What are you trying to connect to? How are you trying to connect?"

You: "It's just not working! You're in IT, shouldn't you know?"
IT support / Network Administrator: (Internal monologue: I guess I need to be psychic...)
```

## The Three Essentials of Network Troubleshooting: Source, Destination, and Port (Mode of Transport)

Just like asking for directions, reporting network issues follows a standard format. Let's examine these three essential elements:

<img width="404" alt="截圖 2024-12-08 12 04 59" src="https://github.com/user-attachments/assets/2d8c71ab-e448-493a-b54a-fe41079f9237">

### 1. Source: Where are you now?
- This is your computer's IP address, essentially your home address in the network world.
- How to find it:
   - Windows: Open Command Prompt, type `ipconfig`
   - Linux/Mac: Open Terminal, type `ifconfig` or `ip addr`

### 2. Destination: Where do you want to go?
- This is the URL or IP address you're trying to connect to, like your intended destination.

### 3. Port: How do you plan to get there?
- This represents the network protocol and port number you're using, analogous to your chosen mode of transportation (walking, driving, cycling, etc.).
- Common Ports:
   - Web: 80 (HTTP) or 443 (HTTPS)
   - Email: 25 (SMTP) or 110 (POP3)
   - Remote Access: 22 (SSH) or 3389 (RDP)

## Next time you encounter a network issue, try communicating like this:

```
You:
Hello, I'm YYY from the XX department, and I'm currently experiencing a network connectivity issue:
- Source IP: 10.1.10.100, Netmask: 255.255.255.0, GateWay: 10.1.10.254, DNS: 10.1.10.254
- Destination: intranet.company.com
- Protocol: TCP 443
- Symptom: The webpage is stuck loading. Can you help me identify the problem?

IT support / Network Administrator:
Based on the information you provided, we've confirmed that machines in your subnet (10.1.10.0/24) are currently restricted from accessing intranet.company.com due to company policy. However, if your manager approves, we can grant you access. Please submit a request through the ZZ system with your manager's approval, and we'll be able to open up access for you.


You:
- Source IP: 10.200.10.100, Netmask: 255.255.255.0, GateWay: 10.200.10.254, DNS: 10.200.10.25
- Destination: 10.0.0.50
- Protocol: TCP 22
- Symptom: The command 'ssh user@10.0.0.50' is unresponsive and hangs. Can you help me identify the issue?

IT support / Network Administrator:
We've reviewed the information you provided. Your test machine (10.200.10.100) should have default SSH access to 10.0.0.50. It appears there might be an issue with our routing or firewall. We're currently investigating and will notify you once it's resolved so you can try again.
```

Isn't that straightforward? You've provided:
1. Source: Your computer's IP
2. Destination: The server's URL/IP
3. Mode of Transport: Protocol and Port

With this basic information, IT support / Network Administrator can perform initial troubleshooting and respond to your issue more quickly.

## Conclusion

A well-described problem can significantly improve the speed and efficiency of problem-solving. Try this method the next time you encounter a network issue. You'll find that not only will your problem be resolved faster, but you'll also build a better relationship with IT support / Network Administrator (they'll appreciate you providing this information upfront).
