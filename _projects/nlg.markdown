---
layout: page
title: 🗣 NLG from Structured Data 
description: >
    Used Neural Machine Translation (NMT) to map structured data to plain English verbalizations. The application of such a model is to make large databases of structured, machine readable data (such as DBPedia) more accessible.


stack: Python, NLTK, OpenNMT, GloVe.
demo: 
repo: 
img: /assets/img/nlg-code.png #/assets/img/nlg.png
importance: 40
category: work
---

## Abstract
Semantic knowledge graphs are an increasingly popular way to store structured data in a machine-readable format online. The information stored in these knowledge bases can be made more accessible with tools that can provide human-readable translations of subsets of this data. The WebNLG Challenge (2017) provides a novel dataset to train a model to generate text from structured data. The dataset consists of data derived from DBPedia, a semantic knowledge base, paired with human-written verbalizations of subsets of this data. This paper explores the use of a Natural Language Translation model trained using a long short-term memory recurrent neural network architecture to provide human-readable translations of the DBPedia data.

## Introduction
Data-to-text generation is a subtask in Natural Language Generation (NLG) that focuses on the transformation of structured data to natural language. The input in a data-to-text task may come in various forms including databases of records, spreadsheets, and expert system knowledge bases (Puduppully et al., 2019). The WebNLG Challenge (2017) presents a task involving the summarization of structured data. A dataset is provided which consists of sets of structured data mapped to natural language text summaries. The structured data was extracted from DBPedia (an online, machine- readable knowledge base), and the text summaries of the extracted data were written by human volunteers. The WebNLG Challenge was organized by research labs from the Universit​é de Lorraine and the University of Edinburgh.

The generation system created for this task can be seen as a microplanner​. Microplanning is a complex choice problem involving several subtasks. These subtasks include ​referring expressionngeneration (generating contextually appropriate references to entities in the data), ​aggregation (merging words or sentences together), lexicalisation (choosing words), surface realisation (creating actual text in human language) and sentence segmentation (Gardent et al, 2017). In essence, microplanners flesh out the linguistic content of an event in data.

The motivation behind this task is to increase the accessibility of large knowledge bases. The structured data is encoded as Resource Description Framework (RDF) triples, a widely used data structure in the semantic web. As its name indicates, a triple is a set of three entities that codifies a statement about semantic data in the form of a subject–predicate–object expression. A natural language generation system that can translate this data into structured text makes it more accessible to the general public because it fleshes out the linguistic context of the data. Additionally, a robust system could expand natural language texts that have missing information by elaborating on
unmentioned facts which are present in the knowledge base.

**Problem Statement.**
The goal of my research was to create a system which takes as an input semantic data and produces as an output a summary of this data in natural language. The following paper will explain the chosen approach to natural language translation and compare this approach to those from the WebNLG challenge.

**Related literature.**
The WebNLG Challenge was initiated in 2017 due to the lack of existing research into data-to-text generation models for knowledge graphs and RDF triple data. Part of the reason for this was a lack of datasets with many verbalizations.
