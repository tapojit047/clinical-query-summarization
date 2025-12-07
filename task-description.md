# clinical-query-summarization
Summarization of Clinical Queries Using Extractive and Abstractive Approaches
Individual Project 1: Summarization of Clinical Queries
This is the same as the group project called "Summarization of Clinical Queries", but has fewer deliverables.

This is a text summarization project. We will not discuss summarization approaches in class, but this is a good primerLinks to an external site.. We will discuss some evaluation metrics. Note that there are two types of summaries: abstractive and extractive. In short, an extractive summary is a subset of the sentences in the original documents (that are deemed important), whereas an abstractive summary is a generated one.

Example:

Original Document

“Artificial intelligence (AI) is transforming industries by automating processes, improving efficiency, and enabling data-driven decision-making. Businesses across various sectors, including healthcare, finance, and manufacturing, are leveraging AI to gain a competitive edge. In healthcare, AI helps diagnose diseases more accurately and streamlines administrative tasks. In finance, AI-powered algorithms detect fraudulent transactions and optimize investment strategies. In manufacturing, AI enhances predictive maintenance, reducing downtime and costs. However, ethical concerns, such as bias in AI models and data privacy, continue to be challenges that need to be addressed.”

Extractive Summary

Artificial intelligence (AI) is transforming industries by automating processes, improving efficiency, and enabling data-driven decision-making. Businesses across various sectors, including healthcare, finance, and manufacturing, are leveraging AI to gain a competitive edge. However, ethical concerns, such as bias in AI models and data privacy, continue to be challenges that need to be addressed.

Abstractive Summary

Artificial intelligence (AI) is revolutionizing industries by enhancing automation, efficiency, and data-driven decision-making. Sectors like healthcare, finance, and manufacturing utilize AI for improved diagnostics, fraud detection, and predictive maintenance. Despite its advantages, ethical issues such as bias and data privacy remain significant challenges.

Task: Suppose you ask Google for a health-related issue, and multiple search results are returned. You might be interested in a concise summary of the text from the topmost document because that’s most important. This is called single-document summarization, which can be extractive or abstractive. However, different documents in the top-k results might bring in different perspectives, so you might be interested in a multi-document summary, which can be extractive or abstractive.

The aim of this project is to develop systems for either single or multi-document abstractive sumXXzzmaries. The group project expects you to produce four types of summaries: extractive single document, extractive multi-document, abstractive single document, and abstractive multi-document. This one, i.e., the individual one, expects you to produce one of the following two types of summaries: single-document abstractive and multi-document abstractive.

 

Dataset:  Download from this link.Links to an external site. There’s train, validation and test JSON files. Each entry in the JSON corresponds to a question, and looks like this:
Evaluation: This is a summarization project, so evaluation is very important. You will mostly follow the evaluation protocol mentioned in section 4 of this paperLinks to an external site., and we will also discuss some evaluation metrics.

Notes: This is a modification of task 2 from the MediQA2021 challengeLinks to an external site.. You can use any type of model you want, but you must fine-tune at least one model for each task – single/multi document abstractive summary.