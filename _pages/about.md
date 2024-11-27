---
permalink: /
title: "Bojie Shen"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
I am a postdoctoral research fellow in the Urban Computing Lab at Monash University. I received my Ph.D. from the Faculty of Information Technology at Monash University, under the supervision of Associate Professor Muhammad Aamir Cheema, Associate Professor Daniel Harabor, and Professor Peter Stuckey. I also hold a Bachelor of Software Engineering (with Honors) from the same institution. My research interests encompass a variety of topics related to transportation and optimization, including heuristic search, multi-agent pathfinding, and electric vehicle routing.

* Check out my **publications** [here](https://bshen95.github.io/bojieshen.me/publications/).
* Check out my **CV** [here](https://bshen95.github.io/bojieshen.me/files/bojieCV.pdf).

## News
* [2024/11] My doctoral dissertation was honored with the [CORE Australasian Distinguished Doctoral Dissertation Award](https://acsw.core.edu.au/speaker/bojie-shen). Furthermore, I have been invited to present a talk at the [2025 Australasian Computer Science Week](https://acsw.core.edu.au), scheduled from February 10–14 at the University of Queensland, Brisbane. Please join me at the conference!


## Research
Pathfinding queries are one of the most ubiquitous practical uses of computing, which involve navigating an agent or groups of agents from the source locations to their destination locations in a shared environment. These queries are critical to numerous real-world applications, such as path planning in video games, route optimization in GPS navigation systems, multi-robot coordination in automated warehouses, drone swarm management, and etc., These efforts have led to numerous advances and optimisations over the past decades. The majority of attention is on finding paths that: (i) meet domain-specific constraints (e.g., avoiding obstacles, avoiding collisions with other agents, etc.); (ii) are of reasonable quality (e.g., minimal distance, minimal travel time, etc.); and (iii) as efficient as possible in terms of response time and computational resources (e.g., memory and preprocessing time). My research focuses on developing efficient algorithms to solve pathfinding queries and related planning tasks across various application domains, including games, road networks, warehouses, and more.




<style>
.flex-container {
    display: flex;
}

.is-flex-wrap {
  flex-wrap: wrap;
}

.flex-child{
    padding:.75rem;
    min-width:300px;
    flex: 1;
    margin-right: 20px;
    margin-top: 20px;
}

.card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  padding: 0.75rem;
  flex-direction: column;
  max-width: 100%;
  border-radius: 5px;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.2);
}

.image {
    position: relative;
    width: 250px;
    margin-top: 1.0em;
    margin-left: auto;
    margin-right: auto;
}

.image__title {
    font-size: 1em;
    font-weight: bold;
    text-align: center;
    margin-top: 1.0em;
}

.image__img {
    display: block;
    width: 300px;
    height: 200px;
}
.image__description {
    margin-top: 0.25em;
    margin-left: 0.25em;
    margin-right: 0.25em;
    text-align: center;
    font-size: 0.8em;
    font-weight: normal
}

.image__overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    color: #ffffff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    opacity: 0;
    transition: opacity 0.25s;
}

.image__overlay--blur {
    backdrop-filter: blur(5px);
}

.image__overlay > * {
    transform: translateY(20px);
    transition: transform 0.25s;
}

.image__overlay:hover {
    opacity: 1;
}

.image__overlay:hover > * {
    transform: translateY(0);
}
</style>


<div class="flex-container is-flex-wrap">
    <!-- Euclidean -->
    <div class="flex-child card">
        <a href="https://bshen95.github.io/bojieshen.me/research/Euclidean">
            <p class="image__title"> Euclidean Pathfinding for Games </p>
            <div class="image">
                <img class="image__img" src="https://bshen95.github.io/bojieshen.me/images/polyanya.gif" alt="Euclidean" />
                <div class="image__overlay image__overlay--blur">
                    <p class="image__description">
                        We develop efficient algorithms to solve pathfinding and planning task in Euclidean plane for games.
                    </p>
                </div>
            </div>
        </a>
    </div>
    <!-- road network -->
    <div class="flex-child card">
        <a href="https://bshen95.github.io/bojieshen.me/research/roadnetwork">
            <p class="image__title"> Path Planning in Road Network </p>
            <div class="image">
                <img class="image__img" src="https://bshen95.github.io/bojieshen.me/images/roadNetwork.gif" alt="roadNetwork" />
                <div class="image__overlay image__overlay--blur">
                    <p class="image__description">
                       In road networks, we design efficient algorithms for pathfinding in navigation software and for solving other location-based services in spatial databases.
                    </p>
                </div>
            </div>
        </a>
    </div>
    <!-- warehouse -->
    <div class="flex-child card">
        <a href="https://bshen95.github.io/bojieshen.me/research/MAPF">
            <p class="image__title"> Multi-Agent Path Finding for Automated Warehouse </p>
            <div class="image">
                <img class="image__img" src="https://bshen95.github.io/bojieshen.me/images/MAPF.gif" alt="Robotic Arms">
                <div class="image__overlay image__overlay--blur">
                    <p class="image__description">
                        We address the core challenges of the Multi-Agent Path Finding (MAPF) problem and develop efficient algorithms to solve complex MAPF instances.
                    </p>
                </div>
            </div>
        </a>
    </div>
    <!-- traffic -->
    <div class="flex-child card">
        <a href="https://bshen95.github.io/bojieshen.me/research/Transportation">
            <p class="image__title">Real-Time Public Transportation Routing  </p>
            <div class="image">
                <img class="image__img" src="https://bshen95.github.io/bojieshen.me/images/Trans.gif" alt="Railway Planning">
                <div class="image__overlay image__overlay--blur">
                    <p class="image__description">
                        We develop efficient algorithms to find optimal journeys for users, accounting for transfers, and design algorithms to handle delays that may occur in real-time transportation systems.
                    </p>
                </div>
            </div>
        </a>
    </div>

    <!-- drones -->
    <!-- <div class="flex-child card">
        <a href="/research/drones/">
            <p class="image__title"> Planning for Complex Robot Teams </p>
            <div class="image">
                <img class="image__img" src="/images/drone_side.gif" alt="Drones">
                <div class="image__overlay image__overlay--blur">
                    <p class="image__description">
                        We generalize MAPF algorithms to coordinate teams of
                        heterogeneous and nonholonomic robots
                        by considering various practical constraints from robotics.
                    </p>
                </div>
            </div>
        </a>
    </div> -->
    <!-- others -->
    <!--
    <div class="flex-child card">
        <p class="image__title"> Other Projects </p>
        <div class="image">
            <a href="https://jiaoyangli.me/research/others/">
                <img class="image__img" src="https://jiaoyangli.me/images/3d-fastmap.png" alt="FastMap">
                <div class="image__overlay image__overlay--blur">
                    <p class="image__description">
                        We perform other planning and search related projects,
                        such as graph embeddings, multi-agent meeting problems, etc.
                    </p>
                </div>
            </a>
        </div>
    </div>
    -->
</div>