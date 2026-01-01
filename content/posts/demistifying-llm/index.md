+++
title = 'Demystifying AI for Laymen'
date = 2025-12-28T20:00:00+09:00
draft = false
tags = ['LLM']
+++

### Q: Does ChatGPT learn about me from our conversation? If I teach it stuff, does that knowledge stick?

Kind of yes but fundamentally no. LLMs don't automatically learn through conversation. The developer can decide to do additional training on LLMs, but that's a completely separate process from letting it converse with users.

When using an LLM (opposed to training), LLM is essentially a next word predictor, which is implemented as a gigantic math expression. Given input text (i.e. the prompt), it spits out a word that would likely to come next. The outer program operating the LLM repeatedly runs this process, appending the predicted word to the end of the input text every time, until the LLM outputs a special symbol signaling the end of text. The LLM's neural connections (which is what encodes knowledge and intelligence) never change in this process.

### Q: But how does ChatGPT remember what I said two weeks ago?

When you ask something to ChatGPT, the entire conversation history is fed into the LLM. The LLM reads all the previous conversations plus your latest message at once and then generates a new message, which will be another message in the history. LLMs don't have any internal mechanism for memory that updates through interaction. It's the outer scaffolding system that keeps history, and it's a normal boring program with no AI.

All the LLM sees is previous messages in the *current chat*. When you open a new chat, you're literally starting a "clean-slate" conversation, because the LLM now doesn't see any previous conversations.

... Except that's not quite true. ChatGPT has a feature called "memory", which complicates things a bit. It's another part of the scaffolding mechanism that share context about the user across chats. But it's just text data stored like any other normal data on your computer. It basically works like this; First the hidden prompt (i.e. system prompt) tells the LLM, basically, "Hey, if you learn something about the user that's worth saving, say 'Save \<info you want to save\>'."; The scaffolding system then sees this request and saves it into a storage that's shared by all chats of the user; When you start a new chat, these memories are injected into the prompt (hidden from the user). This way, the LLM can directly *see* those memories in the prompt and use them when generating answers.

This feature reminds me of a movie I watched when I was small, called [博士の愛した数式](https://en.wikipedia.org/wiki/The_Housekeeper_and_the_Professor), where a mathematician who can only remember what he experienced in the last 80 minutes, tries to keep important information by sticking notes on his clothes.

There's also a newer feature called "chat history" that injects more comprehensive information, such as summaries of your previous conversations, how you prefer ChatGPT to respond, your job, location, interests, device, time you spend on the app, favorite models. See a more thorough explanation [here](https://simonwillison.net/2025/May/21/chatgpt-new-memory/#how-this-actually-works).

All these features are there to give you an illusion of ChatGPT gradually learning about and adapting to you. But the underlying model never changes (until OpenAI releases a new model and you switch to it). If you talk with GPT-4 now, it's literally the same model as it was when it was released in 2023. It hasn't learned any new info since then. Its knowledge is forever frozen. In this sense, LLMs are "snapshots" of whatever documents used during training.

Recent chatbots can access new info through web search, but it's still external data. It can't internalize what happened or was newly discovered after training. And that matters because there's a difference between baked-in knowledge and ad-hoc retrieved information. Owning comprehensive English dictionaries doesn't mean you can write like Shakespeare. And some people believe that's what's holding LLMs back from being competitive agents to the point of replacing a lot of human workers. They're incapable of continual learning.
