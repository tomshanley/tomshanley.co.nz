---
title: "Sankey charts with circular links"
date: 2019-12-23T15:44:46+06:00
type: portfolio
image: "images/projects/sankey.jpg"
category: ["TOOLS"]
project_images: ["images/projects/sankey.jpg"]
---

I've been developing improvements to the [D3 sankey library](https://github.com/d3/d3-sankey), so that it can handle circular links. Circular links are really common when analysing exceptions to business processes or how people navigate around websites and apps. The current D3 sankey library only allows linking one direction, and does not work if a link is addeded which creates a loop in the network.

My [version of the library](https://github.com/tomshanley/d3-sankey-circular) allows for circular links, and in addition, attempts to draw those links to avoid overlaps. This version has since been used by many companies looking to analyse their complex data and networks, including Netflix and University of California, Berkeley. Also, the [Plotly JS](https://plotly.com/javascript/) incorporated my sankey library into their base application.

Since its release I have been investigating improvements to the layout, including the handling of graphs with multiple long links, stabilising the layout when new nodes or links are added, and allowing users to dictate the order in which the nodes are drawn on screen.

Trying to optimise the various functions has been hard, as the inner-workings are often opaque as to the layout they return at every stage of the process.

Prototypes of these changes are demonstrated in the following Observable notebooks, along with a description of how the inner workings of layout algorithm works

* https://observablehq.com/@tomshanley/sankey-circular-deconstructed
* https://observablehq.com/@tomshanley/sankey-circular-deconstructed-part-2-manual-scaling

Have a play with the parameters to see how it affects the final chart:

<iframe width="100%" height="1085" frameborder="0"
  src="https://observablehq.com/embed/@tomshanley/sankey-circular-deconstructed-part-2-manual-scaling?cell=viewof+chooseData&cell=finalGraph&cell=viewof+sankeyParameters&cell=viewof+virtualLinkType"></iframe>

