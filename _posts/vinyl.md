---
title: "My Vinyl Collection"
date: 2024-09-14
excerpt: "Wax on a shelf"
categories:
  - post
tags:
  - music
---

# My Vinyl Collection

This is an interactive sunburst chart of my vinyl collection, organized by artist and album. Click on the artists to zoom in and explore the albums.

<div id="chart" style="max-width: 960px; height: 960px; margin: auto;"></div>

<script src="https://d3js.org/d3.v6.min.js"></script>

<script>
    const width = 932;
    const radius = width / 6;

    const arc = d3.arc()
        .startAngle(d => d.x0)
        .endAngle(d => d.x1)
        .padAngle(d => Math.min((d.x1 - d.x0) / 2, 0.005))
        .padRadius(radius * 1.5)
        .innerRadius(d => d.y0 * radius)
        .outerRadius(d => Math.max(d.y0 * radius, d.y1 * radius - 1));

    const partition = data => {
        const root = d3.hierarchy(data)
            .sum(d => d.children ? 0 : 1)
            .sort((a, b) => b.value - a.value);
        return d3.partition()
            .size([2 * Math.PI, root.height + 1])
            (root);
    };

    function arcVisible(d) {
        return d.y1 <= 3 && d.y0 >= 1 && d.x1 > d.x0;
    }

    d3.json("https://your-github-repo/assets/discogs_d3_hierarchy.json").then(data => {
        const root = partition(data);
        root.each(d => d.current = d);

        const svg = d3.select("#chart")
            .append("svg")
            .attr("viewBox", [0, 0, width, width])
            .style("font", "10px sans-serif");

        const g = svg.append("g")
            .attr("transform", `translate(${width / 2},${width / 2})`);

        const path = g.append("g")
            .selectAll("path")
            .data(root.descendants().slice(1))
            .join("path")
            .attr("fill", d => { while (d.depth > 1) d = d.parent; return d3.interpolateRainbow(d.x0); })
            .attr("fill-opacity", d => arcVisible(d.current) ? (d.children ? 0.6 : 0.4) : 0)
            .attr("d", d => arc(d.current));

        path.filter(d => d.children)
            .style("cursor", "pointer")
            .on("click", clicked);

        function clicked(event, p) {
            root.each(d => d.target = {
                x0: Math.max(0, Math.min(1, (d.x0 - p.x0) / (p.x1 - p.x0))) * 2 * Math.PI,
                x1: Math.max(0, Math.min(1, (d.x1 - p.x0) / (p.x1 - p.x0))) * 2 * Math.PI,
                y0: Math.max(0, d.y0 - p.depth),
                y1: Math.max(0, d.y1 - p.depth)
            });

            const t = g.transition().duration(750);

            path.transition(t)
                .tween("data", d => {
                    const i = d3.interpolate(d.current, d.target);
                    return t => d.current = i(t);
                })
                .filter(function(d) { return +this.getAttribute("fill-opacity") || arcVisible(d.target); })
                .attr("fill-opacity", d => arcVisible(d.target) ? (d.children ? 0.6 : 0.4) : 0)
                .attrTween("d", d => () => arc(d.current));
        }
    });
</script>
