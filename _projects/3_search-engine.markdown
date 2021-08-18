---
layout: page
title: 🔍 Search Engine
description: >
    Developed a search engine system in a team for a university catalogue and a corpus of Reuters articles. Implemented various search algorithms from the ground up, including live query completion, index construction, and query expansion.

stack: Python, NLTK, PySimpleGUI.
demo: https://www.youtube.com/watch?v=WBr91tTkfn4
repo: https://github.com/aethelind/minerva
img: /assets/img/search1.png #/assets/img/search.gif
importance: 3
category: work
---
## Introduction
For CSI4107 (Information Retrieval), I developed a search engine and various retrieval modules. This project was completed in a team of two.

The search engine was able to search over two distinct corpora: uOttawa courses catalogue, and Reuter's articles. Different models could be used to store the corpora, either a Vector Space model, or a Boolean model. As the user enters their query, live suggestions are fed to them to help complete their query. After sending a query, related topics are suggested for expansion.

## Demo
Below is a demonstration of the final application.

<div class="video-container"> 
<iframe src="https://www.youtube.com/embed/WBr91tTkfn4"  frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen class="yt-video"></iframe>

 </div>

<br>

## Modules


### Query completion module
This module leverages the work done in the bigram language module in an effort to provide explicit query completion suggestions to the user. Using the bigram index, we only save the top 3 words, which we then present to the user in the UI. The word suggestions appear in a separate widget, and clicking on them will add that term to your query (as well as to the query textbox).

### Global query expansion using WordNet
This module attempts to perform query expansion using an external source, WordNet. Thankfully, Python’s natural language toolkit provides a simple API for interacting with WordNet, so it was quite trivial to wire it into our project. We chose to give the user the option of applying the expansion for most cases. The only time we don’t is when the number of synonyms is large (> 10), since at that point we will sacrifice too much precision. We hypothesize that this provides the user’s with a good amount of insight into how their query is behaving while giving them the option to opt-out of this behaviour should they feel the need.
We also ensured that the expansion works using both the boolean and VSM model. Indeed, the terms are expanded before ever being transformed into a search expression.

### UI Improvements
While this was not a module, per se, it was still a lot of effort, as we had to accommodate a number of new workflows and elements. In particular, we had to create widgets for query expansion, as well as confirmation dialogs informing users of implicit expansions as well. We also needed a mechanism for users to provide relevance feedback, both declaring something relevant and undeclaring it, should the need arise. Finally, we needed to add the topic filtering selection box and the requisite logic to limit search results for Reuters articles when used.
