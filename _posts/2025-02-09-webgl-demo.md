---
title: WebGL demo
date: February 8, 2025 8:36 PM
categories:
  - graphic
tags:
  - webgl2
  - demo
  - graphic
description: Test embed graphic project
toc: true
comments: true
math: false
---

# Demo

<div style="left: 0; width: 100%; position:relative; aspect-ratio: 3/1;">
<p class="codepen" data-height="600" data-default-tab="result" data-slug-hash="LEYPGeK" data-pen-title="Untitled" data-user="gamer2810" style="height: 600px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/gamer2810/pen/LEYPGeK">
  Untitled</a> by K3K (<a href="https://codepen.io/gamer2810">@gamer2810</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://public.codepenassets.com/embed/index.js"></script>
</div>
# Description

The above project demonstrates how to set up a basic OpenGL application, in this case using WebGL.

It includes:

- The main JS function that handles rendering.
- The rendering program setup and shader binding using WebGL.
- Vertex Shader written in GLSL.
- Fragment Shader written in GLSL.

# Spherical demo

<div class="slidecontainer">
  How many points do you want?<br>
  <input type="range" min="10" max="100" value="50" class="slider" id="myRange"><span id="rangeValue"></span>
</div>
<svg width="960" height="600"></svg>

<script src="https://d3js.org/d3.v5.min.js"></script>
<script src="https://unpkg.com/d3-delaunay@5"></script>
<script src="https://unpkg.com/d3-geo-voronoi@1.5"></script>

<script>
  const phi = (1 + Math.sqrt(5)) / 2;
let pointCount = 50;
const slider = document.getElementById("myRange");
var sliderValue = document.getElementById("rangeValue");
const svg = d3.select("svg");
let projection = d3.geoOrthographic();
let path = d3.geoPath().projection(projection);

function generatePoints(count) {
  return Array.from({ length: count }, (_, i) => {
    const [x, y] = [i / phi, i / count];
    return {
      type: "Point",
      coordinates: [(x * 360) % 360, (Math.acos(2 * y - 1) / Math.PI) * 180 - 90],
    };
  });
}

function updateVisualization() {
  const features = generatePoints(pointCount);
  const points = { type: "FeatureCollection", features };
  const v = d3.geoVoronoi()(points);

  // Compute colors based on triangle centroids
  const triangles = v.triangles().features;

  // Define a custom Siri-inspired gradient scale
  const colorScale = d3.scaleSequential(d3.interpolateRgbBasis([
    "#5E5CE6", // Deep purple-blue
    "#BF5AF2", // Vibrant pink-purple
    "#FF2D55"  // Apple’s signature red-pink
  ])).domain([-90, 90]); // Latitude range

  // Update triangles with gradient color
  svg.select(".triangles")
    .selectAll("path")
    .data(triangles)
    .join("path")
    .attr("d", path)
    .attr("fill", d => {
      const centroid = d3.geoCentroid(d);
      return colorScale(centroid[1]); // Use latitude for color
    });

  // Update sites
  svg.select(".sites")
    .selectAll("path")
    .data(points.features)
    .join("path")
    .attr("d", path);
}

// Initialize SVG content
svg.append("path")
  .attr("id", "sphere")
  .datum({ type: "Sphere" })
  .attr("d", path);

svg.append("g").attr("class", "triangles");
svg.append("g").attr("class", "sites");

// Update when slider changes
sliderValue.innerHTML = slider.value;
slider.addEventListener("input", function () {
  pointCount = Number(slider.value);
  sliderValue.innerHTML = slider.value;
  updateVisualization();
});

// Start visualization
updateVisualization();

// Animation loop
d3.interval((elapsed) => {
  projection.rotate([elapsed / 150, 0]);
  svg.selectAll("path").attr("d", path);
}, 50);

</script>

# References

[WebGL2 Fundamentals](https://webgl2fundamentals.org/webgl/lessons/webgl-fundamentals.html)
