---
layout: archive
title: "Euclidean Pathfinding for Games"
permalink: /research/Euclidean
author_profile: true
---

{% include base_path %}

<img src="https://bshen95.github.io/bojieshen.me/images/polyanya.gif" title="Euclidean demo" style="float:right;width:200pt;padding-left:10px;"  alt="Euclidean demo"/>
In computer games, the environment is typically represented as a two-dimensional plane which contains polygonal obstacles that must be avoided by virtual characters. During a game, players navigate their characters around the map, which is facilitated by solving a range of pathfinding queries. Pathfinding is also required as part of higher-level decision-making for non-player characters (NPCs), such as build planning and combat planning. In each of these cases, it is desirable to find direct and detour-free paths because virtual characters need to appear intelligent to human observers. Yet this apparently simple task is surprisingly complicated because games occur in real-time, they often involve a large number of player and non-player characters, and because there are only limited CPU and memory resources available for pathfinding (the bulk of computational resources are assigned to other higher-priority tasks such as graphics, networking and so on). Effective algorithms in this space are ones that compute paths which are: (i) obstacle avoiding; (ii) as short as possible; and (iii) computed as fast as possible.



## End Point Search
<img src="https://bshen95.github.io/bojieshen.me/images/EPS.pdf" title="EPSAlgorithm" style="float:left;width:250pt;padding-right:10px;" alt="EPSAlgorithm"/>
[End Point Search (EPS) [1]](/publications/ShenCHS20) leverages ideas from two recent works: Polyanya, a mesh-based ESPP planner which we use to represent and reason about the environment, and Compressed Path Databases (CPD), a speedup technique for pathfinding on grids and spatial networks, which we exploit to efficiently compute candidate paths. EPS is a two-phase algorithm where during the offline phase, we preprocess the input mesh to extract a graph of co-visible points. We then preprocess the graph to create a CPD which can be used to efficiently extract optimal paths between any pair of graph vertices u and v.
During the online phase, Polyanya connects the start and target points to the co-visible graph. The CPD then proceeds to identify candidate paths: from each of the m outgoing successors of the start point to each of the n incoming successors of the target node.
In a range of experiments and empirical comparisons we show that: (i) the auxiliary data structures required by EPS are cheap to build and store; (ii) for optimal search, the new algorithm is faster than a range of recent pathfinding algorithms, with speedups ranging from several factors to over one order of magnitude; (iii) for anytime search, where feasible so- lutions are needed fast, we report even better performance. 


<img src="https://bshen95.github.io/bojieshen.me/images/CPE.pdf" title="CPEAlgorithm" style="float:left;width:250pt;padding-right:10px;" alt="CPEAlgorithm"/>
 Building on the principles of EPS, [Centroid Path Extraction (CPE) [2]](/publications/ShenCHS22) extends the CPD such that it computes and compresses first move data of a larger number of selected candidate nodes covering every point in the Euclidean space.
CPE is an ultra-fast bounded suboptimal pathfinding algorithm that is completely search-free, simultaneously fast, and returns a path within a fixed bound of the optimal solution.
In a range of empirical results, we show that: (i) our approach outperforms a range of optimal and suboptimal pathfinding algorithms proposed in the literature; (ii) our approach demonstrates excellent path quality, better than all existing suboptimal pathfinding algorithms; and (iii) the approach offers flexibility by allowing a trade-off between the preprocessing cost (space and time) and the suboptimality bound.



## Euclidean Hub Labelling
<img src="https://bshen95.github.io/bojieshen.me/images/EHL.pdf" title="EHLAlgorithm" style="float:left;width:300pt;padding-right:10px;" alt="EHLAlgorithm"/>
[Euclidean Hub Labelling (EHL) [3]](/publications/DuSC23) exploits Hub Labeling, the leading shortest path approach for graphs such as road networks. During the preprocessing phase, EHL constructs a visibility graph on the convex vertices of the polygonal obstacles and precomputes the hub labeling on this graph. The precomputed hub labels of each vertex are then copied to each grid cell of a uniform grid that is visible from the vertex. During the online phase, EHL considers the labels stored in the grid cells containing the start and target, respectively. These labels are joined to obtain the shortest path via a merge-join process. We compare EHL against Polyanya and EPS, the two state-of-the-art algorithms. Our results indicate that EHL provides 1-2 orders of magnitude faster query performance compared to Polyanya and EPS.
<!-- at the expense of larger preprocessing time and memory. -->

<!-- 
Although EHL outperforms existing techniques by 1-2 orders of magnitude in runtime efficiency, this improvement comes at the cost of significant memory overhead, requiring up to tens of gigabytes of storage on large maps. This can limit its applicability in memory-constrained environments, such as mobile phones or smaller devices. Additionally, EHL’s memory usage is only apparent after index construction, and while it offers a memory-runtime tradeoff, it does not fully optimize memory utilization.
Therefore, we further introduce an improved version of EHL, called [EHL* [4]](https://arxiv.org/pdf/2408.11341), which overcomes these limitations. A key contribution of EHL* is its ability to create an index that adheres to a specified memory budget while optimizing query runtime performance. Moreover, EHL* can leverage pre-known query distributions to further enhance runtime efficiency. Our results show that EHL* can reduce memory usage by up to 10-20 times without much impact on query runtime performance compared to EHL, making it a highly effective solution for optimal pathfinding in memory-constrained environments.
The figure below illustrates how EHL* merges grid cells into larger regions to reduce the memory budget to 5%. The merged regions are shown in different colors for various query sets on the arena map. -->
Although EHL achieves 1-2 orders of magnitude better runtime efficiency than existing techniques, it requires up to tens of gigabytes of storage, limiting its use in memory-constrained environments. Additionally, its memory usage is only known after index construction and isn't fully optimized. To address these issues, we introduce [EHL* [4]](https://arxiv.org/pdf/2408.11341), which adheres to a set memory budget while optimizing query performance. EHL* can reduce memory usage by 10-20 times with minimal impact on runtime. The figure below shows how EHL* merges grid cells into larger regions, reducing the memory budget to 5%.
<img src="https://bshen95.github.io/bojieshen.me/images/EHLStar.pdf" title="EHLStarAlgorithm" style="float:left;width:1000pt;padding-right:10px;padding-top:20px;padding-bottom:40px" alt="EHLStarAlgorithm"/>



## Other Location-based Service Queries
- [Efficient Keyword k Nearest Neighbors](https://bshen95.github.io/bojieshen.me/publications/DuSC23/): Video games feature a dynamic environment where locations of objects (e.g., characters, equipment, weapons, vehicles etc.) frequently change within the game world. We propose a simple lightweight index, called Grid Tree, to store objects and their associated textual data. Our index can be efficiently updated with the underlying updates such as object movements, and supports a variety of object search queries, including k nearest neighbors (returning the k closest objects), keyword k nearest neighbors (returning the k closest objects that satisfy query keywords), and several other variants.
 <!-- Our extensive experimental study, conducted on standard game maps benchmarks and real-world keywords, demonstrates that our approach has up to 2 orders of magnitude faster update times for moving objects compared to state-of-the-art approaches such as navigation mesh and IR-tree. At the same time, query performance of our approach is similar to or better than that of IR-tree and up to two orders of magnitude faster than the other competitor.  -->
