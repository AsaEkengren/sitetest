---
title: "Family Genealogy"
date: 2024-09-02
excerpt: "How I got here"
categories:
  - article
tags:
  - genealogy
---

{% capture mermaid_graph %}
graph TD;
    A[Asa Francis Ekengren San Andrés<br>b. May 5, 1987 in Jackson, Missouri, USA];
    A --> C[Neal Alvin Ekengren<br>b. Nov 28, 1957 in Independence, Missouri, USA];
    A --> D[Matilde San Andrés Pérez<br>b. Nov 7, 1954 in Sabinas, Coahuila, Mexico];
    C --> G[Gail Donna 'Patsy' Baker<br>b. Oct 21, 1935 in Chicago, Illinois, USA<br>d. May 9, 2019 in Wichita, Kansas, USA];
    C --> H[Alvin Francis Ekengren<br>b. Dec 16, 1932 in Olathe, Kansas, USA<br>d. Jan 1, 2019 in Wichita, Kansas, USA];
    D --> I[Pedro San Andrés Lavera<br>b. Mar 24, 1925 in Tomelloso, Ciudad Real, España<br>d. Aug 17, 2020 in Cuernavaca, Morelos, México];
    D --> J[Matilde Pérez Martínez<br>b. Jan 30, 1927 in Tijola, Almeria, España<br>d. May 30, 2003 in Cuernavaca, Morelos, México];
    H --> L[Alvin Francis Ekengren<br>b. Aug 28, 1907 in Olathe, Kansas, USA<br>d. May 20, 1992 in Olathe, Kansas, USA];
    H --> M[Geneva Laverne Randall<br>b. Oct 17, 1909 in Wichita, Kansas, USA<br>d. Sep 21, 1970 in Clay County, Missouri, USA];
    G --> N[Cornelius Isaac Baker<br>b. 1904 in Leslie, Todd, Minnesota, USA<br>d. Aug 4, 1984 in Osakis, Douglas, Minnesota, USA];
    G --> O[Elmera Carrie Pollei<br>b. May 2, 1908 in New Ulm, Brown, Minnesota, USA<br>d. Oct 15, 1968 in Knoxville, Tennessee, USA];
    I --> P[Bonifacio San Andrés López<br>b. Apr 11, 1898 in Consuegra, Toledo, España<br>d. Apr 1969 in Torreón, Coahuila, México];
    I --> Q[Purificación Lavera Mulás<br>b. 1898 in Peñaranda de Bracamonte, Salamanca, España<br>d. 1922 in Peñaranda de Bracamonte, Salamanca, España];
{% endcapture %}

{% include mermaid.html content=mermaid_graph %}
