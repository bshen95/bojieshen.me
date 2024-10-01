---
layout: archive
title: "Real-Time Public Transportation Routing"
permalink: /research/Transportation
author_profile: true
---

{% include base_path %}
<img src="https://bshen95.github.io/bojieshen.me/images/Trans.gif" title="Trans demo" style="float:right;width:300pt;height:200pt; padding-left:10px;"  alt="Trans demo"/>
Public transport journey planning is a critical part of modern urban transport systems, guiding millions of commuters daily. Instead of using a traditional graph model, journey planning relies on the timetable, which consists of connections representing public vehicle services between stops. These connections enable efficient route mapping across various modes of transport, such as buses, trains, trams, and subways. The journey planning process provides passengers with detailed guidance, helping them navigate from their starting point to their destination while optimizing various aspects of the journey, including arrival times, transfer points, and personal preferences. Similar to road networks, journey planning systems face challenges in large-scale deployments that require computing tens of thousands of journeys per second. As a result, effective algorithms must (i) find feasible journeys that follow the public transport timetable, (ii) optimize user objectives, and (iii) solve each problem quickly to ensure scalability.





## Transfer Connection Database
<img src="https://bshen95.github.io/bojieshen.me/images/TCD.pdf" title="TCDAlgorithm" style="float:left;width:250pt;height:300pt;padding-right:10px;" alt="TCDAlgorithm"/>
A journey typically consists of multiple scheduled public transport legs. The actual time required to transfer between these legs can substantially influence route planning. Therefore, we first properly model transfers by incorporating their exact costs. We then introduce a novel oracle-based routing algorithm that constructs an efficient oracle, called [Transfer Connections Database (TCD)[1]](https://bshen95.github.io/bojieshen.me/publications/Abu-AishaWHS24), considering the proposed transfer model. The database is leveraged online to quickly reconstruct the optimal journey in response to an earliest arrival time query. 
The figure on the left illustrates an example of a TCD. To build the oracle, stations are decomposed into neighborhood stations based on the footpaths connecting their stops. TCD then computes the first move table FT, where the rows represent origin neighborhood stations and the columns represent destination stations. Each cell FT[$$NS_o$$][$$s_d$$] contains a list of the first transfer connections for all optimal journeys from $$NS_o$$ to $$s_d$$. For example, the label ($$c_1$$, $$c_2$$) in FT[$$NS_3$$][$$s_2$$] is the first transfer connection of the journey J = <($$c_1$$, $$c_2$$), ($$c_5$$, $$c_5$$)> from $$NS_3$$ to $$s_2$$.
Our experimental results show that neglecting exact transfer costs often lead to either infeasible or suboptimal route plans. Furthermore, the findings highlight the efficiency of our algorithm TCD in handling queries, demonstrated by response times within mere microseconds.

