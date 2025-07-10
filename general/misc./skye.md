# Skye

Skye is our cherished chat bot made to help answer commonly asked server questions, but can also do a bit of casual chatting too! Skye was officially released on the server on 3/28/20, but has since been updated many times and become a lot smarter.

<figure><img src="../../.gitbook/assets/92E7C53F-1942-4790-8316-CE2C826C63FA.png" alt=""><figcaption></figcaption></figure>

While Skye is generating a response, you will see "Skye is thinking...", "Skye is replying...", and "Skye finished replying" action bar notifications (as well as "Response failed" if an issue occurs). Additionally, you will see chat notifications when Skye begins and stops focusing on your messages. These notifications makes interactions smoother and gives you a better sense of Skye's state by giving you real-time confirmations.

If you're actively chatting and have Skye's focus, but need to message another player and don't want Skye to interrupt, you can now simply ask Skye to unfocus (by either asking fully, or just writing 'unfocus'). You can also start your message with "**`.!`**" for Skye to ignore it, but not unfocus from you. This helps prevent Skye from replying when unwanted.

## Technical

Skye works by comparing the similarity of public chat messages to a local Q\&A library of prewritten potential questions and and answers related to the server. Each Q\&A node is equip with unique settings and thresholds, and if your message is similar enough to the nodes inputs and satisfies its requirements, Skye sends an answer from the that node. If your message doesn't match any nodes, Skye queries a fine tuned LLM to generate a conversational response.\
\
To make Skye less intrusive out of the blue, some nodes require you to start or end your message with "Skye", while others do not (ex. saying "hello" should not trigger Skye's response without addressing Skye, whereas a specific server question should trigger Skye's response regardless). Once you have interacted with Skye (unless the node is specified as an end of conversation), most other nodes temporarily lose their requirement if present for you to start or end with Skye for a more natural dialogue. This is referred to as 'focusing' on to players messages. In LLM queries, Skye can dynamically include special tokens to dictate and control focus based on the context and conversation flow.\
\
For longer responses, Skye will break the content down into multiple messages, each with a dynamic delay based on the length of the last sent portion of response for a natural reading speed. This creates  a more natural feeling interaction and prevents a huge wall of text immediately appearing in chat.

For very large responses, Skye will send one message and tunicate it with a \[..hover to see full message..] hoverable that shows the full response. This is to prevent Skye flooding chat with a bunch of messages in big replies.\
\
To prevent abuse, most nodes have per-player and or global cooldowns, and Skye will reject answering another question while actively replying to a different question. Skye has numerous checks and limits in place to prevent misuse or reverse engineering.

As of 5/24, Skye received a major v5 update that leverages a fine tuned large language model for general dialogue in addition to the Q\&A library (previously referred to as the conversational library), now refined specifically for server knowledge and Q\&A instead of also including some conversational inputs and outputs. This hybrid approach keeps costs manageable and significantly enhances Skye's conversational abilities. Now, when chatting with Skye, if your input doesn't match any Q\&A conversational nodes, Skye queries the LLM to generate a response. Our long term goal for Skye is to fully integrate AI to answer both server questions and general conversation. However, currently the costs associated with a fully AI fledged Skye are too high.

As of 3/25, Skye was updated to v5.8, which introduced new experimental features like periodic chat participation and retainment of a small rolling context window including public chat messages, level up, deaths, etc. to provide more contextual responses and engage across LLM sessions from users.

You can choose to permanently opt-out of Skye usage & AI processing using the **/skyoptout** command.
