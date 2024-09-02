---
title: "Family Geneology"
date: 2024-09-02
excerpt: "How I got here"
categories:
  - article
tags:
  - geneology
toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: "fas fa-file-alt"

---


<button onclick="toggleSection('section1')">Toggle Section 1</button>
<div id="section1" style="display:none;">
{% include mermaid.html content="
  graph TD;
    A-->B;
    B-->C;
    C-->D;
" %}
