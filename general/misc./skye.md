# Skye

Skye is our cherished chat bot made to help answer commonly asked server questions, but she can do a bit of casual interaction too!

<div align="center">

<img src="../../.gitbook/assets/skye.png" alt="">

</div>

### Technical

Skye works by comparing the similarity of public chat messages to a library of overgrowing inputs & outputs known as conversational nodes with their own thresholds. If your message is similar enough to a conversational node and satisfies its minimum similarity threshold, Skye sends a random response from the that node's collection of responses. For fine tuning, some nodes require you to start or end your message with Skye, while others do not (ex. saying "hello" should not trigger Skye's response without addressing Skye, whereas a specific server question should trigger Skye's response regardless). Once you have interacted with Skye, all conversational nodes temporarily lose their requirement (if present) for you to start or end with Skye for a more natural dialogue. For long responses, Skye will break it down into multiple messages, each with a dynamically determined delay based on the length of the last portion of the response Skye sent for a natural reading speed. To prevent abuse, most nodes have per-player and or global cooldowns, and Skye will reject answering another question while actively replying to a different question.\
\
As of 9/3/23, Skye has 145 conversational nodes!
