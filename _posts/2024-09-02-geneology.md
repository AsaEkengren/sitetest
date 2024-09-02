---
title: "Family geneology"
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

{% capture mermaid_graph %}
graph TD;
    %% First Generation (Top row: Asa)
    A[Asa Francis Ekengren San Andrés<br>DOB: 1987-05-05<br>Birthplace: Jackson, Missouri, USA<br>DOD: -<br>Description: Loves technology and outdoor activities];
    %% Second Generation (Parents)
    A --> C[Neal Alvin Ekengren<br>DOB: 1957-11-28<br>Birthplace: Independence, Missouri, USA<br>DOD: -<br>Description: An engineer with a love for history];
    A --> D[Matilde San Andrés Pérez<br>DOB: 1954-11-07<br>Birthplace: Sabinas, Coahuila, Mexico<br>DOD: -<br>Description: A teacher and avid reader];
    %% Third Generation (Grandparents)
    C --> G[Gail Donna "Patsy" Baker<br>DOB: 1935-10-21<br>Birthplace: Chicago, Illinois<br>DOD: 2019-05-09<br>Death Place: Wichita, Kansas<br>Description: A dedicated nurse and community volunteer];
    C --> H[Alvin Francis Ekengren<br>DOB: 1932-12-16<br>Birthplace: Olathe, Kansas<br>DOD: 2019-01-01<br>Death Place: Wichita, Kansas<br>Description: A veteran and historian];
    D --> I[Pedro San Andrés Lavera<br>DOB: 1925-03-24<br>Birthplace: Tomelloso, Ciudad Real, España<br>DOD: 2020-08-17<br>Death Place: Cuernavaca, Morelos, México<br>Description: A retired lawyer and avid gardener];
    D --> J[Matilde Pérez Martínez<br>DOB: 1927-01-30<br>Birthplace: Tijola, Almeria, España<br>DOD: 2003-05-30<br>Death Place: Cuernavaca, Morelos, México<br>Description: A chef and community leader];
{% endcapture %}

{% include mermaid.html content=mermaid_graph %}
