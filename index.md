<img src="img/MillionLLMs_vanGogh_style.webp" />

# Overview

The Million LLM Track envisions a world in which information is served to users by the means of Large Language Models (LLMs). Imagine for instance Wikipedia, NY Times, Reddit, Elsevier, and all content providers offering information to users by the means of LLMs, which have been trained on proprietary material. We envision LLMs that cite and offer the original texts from which their knowledge is derived and others that simply return responses without references; we envision LLMs that are cooperative providing access to embeddings and internal weights and others that are simply returning a textual answer; we envision LLMs that are free to query and others that are associated with a certain cost model. We envision the existence of millions of such LLMs, each one having a certain expertise (sometimes overlapping). A user's information need can be satisfied by combining the output of few LLMs, but most LLMs are not experts on the subject matter.

In such a digital world there is a need for an LLM agent (a meta-LLM) that can query and combine the answers of the expert LLMs. However, querying all LLMs is prohibitively expensive. Therefore, one needs a search engine that given a user's question it retrieves those LLMs that are expert on the matter and can offer the most relevant answers. Therefore, upon a user's question the LLM agent should decide which LLMs should it question so that it obtains the right answer to the user's query and at the same time minimizes costs.

The problem bears similarities to the distributed information retrieval (DIR), federated search (FS), and meta-search, where a meta search engine needs to query and combine results from multiple search engines accessing different collections. One of the key differences is that collecting statistics of the underlying collection in the case of DIR/FS was a simpler endeavour since queried search engines would return thousands of results and therefore statistics were more reliable. In the case of LLMs, answers are much shorter.

With this proposal we invite the IR community to examine the problem of selecting LLMs to query, building the appropriate evaluation framework, and building a community around the problem.

# Motivation and Challenges

## Evaluation of searching LLMs

Here we propose a specific simulation and evaluation framework however many of the assumptions we make are not reflecting reality. How far are they from reality and how could we best evaluate search engines of LLMs is a challenge itself. 

## Quantifying the expertise of LLMs

The work in distributed IR pivoted on the fact that statistics for the underlying collection can be obtained by querying each search engine and obtaining hundred or thousands of results per query. In our setup it is likely that an LLM will only respond with a paragraph (if not a short factual answer) and in the best case a couple of references. Understanding the expertise of each LLM is a challenge.

## Developing methods to rank LLM

Even with a good understanding of each LLM expertise it is not clear how these LLMs should be ranked and what is optimal for the LLM agent that will combine their answers. In this year track we do not examine it --- we focus on the ranking of LLMs --- however this is also a challenge we can examine in future versions of the track.

## Combining multiple LLM answers into a single answer

There is limited work on combining the answers of multiple LLMs and therefore this is an open scientific question.

# Organizers

<table>
  <tr>
    <td><img src="img/kanoulas.jpeg" style="height:130px;border-radius:50%" alt="Evangelos Kanoulas"></td>
    <td><img src="img/eustratiadis.jpeg" style="height:130px;border-radius:50%" alt="Panagiotis Eustratiadis"></td>
    <td><img src="img/sanderson.jpeg" style="height:130px;border-radius:50%" alt="Mark Sanderson"></td>
    <td><img src="img/callan.jpeg" style="height:130px;border-radius:50%" alt="Jamie Callan"></td>
  </tr>
  <tr>
    <td>
      <div class="name">Evangelos Kanoulas</div>
      <div class="affiliation">University of Amsterdam, The Netherlands</div>
    </td>
    <td>
      <div class="name">Panagiotis Eustratiadis</div>
      <div class="affiliation">University of Amsterdam, The Netherlands</div>
    </td>
    <td>
      <div class="name">Mark Sanderson</div>
      <div class="affiliation">RMIT University, Australia</div>
    </td>
    <td>
      <div class="name">Jamie Callan</div>
      <div class="affiliation">Carnegie Mellon University, USA</div>
    </td>
  </tr>
</table>
