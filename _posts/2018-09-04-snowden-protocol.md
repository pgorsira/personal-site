---
layout: post
title:  "Snowden Protocol: Leak-Resistant Conversations via Asymmetric Cryptocurrency Stake"
date:   2018-09-04 23:19:37 -0700
categories: projects
---

<div class="project-showcase">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/N9ccPElJaVA?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

Snowden Protocol is an experimental effort to add a penalty to leaking secure information. Two parties set up a ”conversation” instance through an [Ethereum smart contract](https://kovan.etherscan.io/address/0x8ef1bcb14d3d2b7da87090f658aef0a6b9846da8#code){:target="_blank"} and define the following parameters: 

- how much each party needs to deposit at the beginning of the conversation 
- how much each party receives at the end of a “successful” conversation (one where messages haven’t leaked for a certain amount of blocks)

Note that these parameter values can be different for each party to represent asymmetric relationships (sometimes one party works for the other, sometimes one party has secrets and the other is listening, etc). 

As each party sends messages, they also hash the message and post the digest to the contract. If a message leaks through any channel, the victim of the leak can post the original plaintext to the contract (since the message has been leaked, it’s figured to be as good as public anyway). The contract verifies that this plaintext matches one of the previously sent digests and if so “slashes” the leaker’s deposit as penalty per the original terms. 

<!-- There are definitely a few issues in the design of the mechanisms here in terms of actual production usage of something like this but for a hackathon I think the concept is pretty neat. -->

Snowden Protocol [won the grand prize](https://twitter.com/sendwyre/status/1031358410707484672){:target="_blank"} at the 2018 unBlock (MakerDAO/Wyre) hackathon.
