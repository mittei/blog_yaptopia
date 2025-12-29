+++
title = 'Demystifying AI for Laymen'
date = 2025-12-28T20:00:00+09:00
draft = true
tags = ['LLM']
+++

### Q: Does ChatGPT learn about me from our conversation? If I teach it stuff, does that knowledge stick?

Kind of yes and fundamentally no. LLMs don't automatically learn through conversation. The developer can decide to do additional training on LLMs, but that's a completely separate process from letting it converse with users. In this sense, LLMs are stateless.

### Q: But how does ChatGPT remember what I said two weeks ago?

When you ask something to ChatGPT, the entire conversation history is fed into the LLM. The LLM reads all the previous conversations plus your latest message at once and then generates a new message, which will be another message in the history. As I said, LLMs don't have any internal mechanism for memory that updates through interaction. It's the outer scaffolding system that keeps history, and it's a normal boring program with no AI.

All the LLM sees is previous messages in the *current chat*. When you open a new chat, you're literally starting a "clean-slate" conversation, because the LLM doesn't remember any previous conversations outside the current chat.

... Except ChatGPT has a feature called "memory", which complicates things a bit. It's another part of the scaffolding mechanism that share context about the user across chats. But it's just text data and it will be stored in an external storage. It works like this; First, the hidden prompt tells the LLM, basically, "Hey, if you learn something about the user that's worth saving, say 'Save \<info you want to save\>'."; The scaffolding system then sees this request and saves it into a storage shared by all chats of the user; When you start a new chat, these memories are injected into the prompt (hidden from the user). 
This feature reminds me of a movie I watched when I was small, called [博士の愛した数式](https://en.wikipedia.org/wiki/The_Housekeeper_and_the_Professor), where a mathematician who can only remember what he experienced in the last 80 minutes, tries to keep important information by sticking notes on his clothes.

There's also a newer similar feature called "chat history" that injects summaries of your previous conversations, how you prefer ChatGPT to respond, your job, location, interests, device, how long you use the app, favorite models, etc. in the prompt. See a more thorough explanation [here](https://simonwillison.net/2025/May/21/chatgpt-new-memory/#how-this-actually-works).

All these features are there to give you an illusion of ChatGPT gradually learning about and adapting to you. But the underlying model never changes. If you talk with GPT-4 now, it's literally the same model as it was when it was released in 2023. It hasn't learned any new info since then. Its knowledge is forever frozen. In this sense, LLMs are "snapshots" of whatever documents used during training.

Recent chatbots can access new info through web search, but it's still external data. It can't internalize what happened or was newly discovered after training. There's a difference between baked-in knowledge and ad-hoc retrieved information. Owning comprehensive English dictionaries doesn't mean you can write like Shakespeare. And a lot of people believe that's what's holding LLMs back from being useful agents in real-world tasks. They're incapable of continual learning.
