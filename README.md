# Spatiotemporal-Traffic-Aware-Multi-Drone-Multi-Altitude-Delivery-Route-Optimization

## Project Description

This project presents a novel framework for optimizing delivery operations in dynamic urban environments using multiple drones operating across multiple altitude layers. The system addresses the challenges of traffic congestion, evolving delivery demand, airspace constraints, and route coordination by combining graph clustering, graph neural networks, and reinforcement learning.

The core idea is to partition delivery demands into congestion-resilient operational regions and enable drones to learn adaptive routing policies that respond to changing traffic conditions in real time.

Unlike traditional routing systems that rely on static demand partitioning or shortest-path heuristics, the proposed framework incorporates both spatial and temporal traffic information into the decision-making process, allowing drones to proactively avoid congested regions while maintaining efficient delivery performance.

## Key Features

* Multi-drone route optimization under dynamic traffic conditions
* Multi-altitude airspace representation and routing
* Congestion-aware demand partitioning
* Spatiotemporal graph modeling of urban environments
* Graph Neural Network (GNN)-based state representation
* Reinforcement Learning (RL)-based adaptive route planning
* Comprehensive benchmarking against classical search and optimization methods

## Proposed Methodology

The framework operates through four major stages:

### 1. Dynamic Demand Partitioning

Delivery requests are partitioned into operational regions before route planning.

To evaluate the effectiveness of the proposed clustering strategy, the following baseline clustering algorithms are considered:

* Mini-Batch K-Means
* DBSCAN
* OPTICS

The proposed clustering approach, **Congestion-Guided Residual Graph Clustering (CGRGC)**, partitions the network by prioritizing low-congestion connectivity and introducing highly congested connections only through controlled residual assignment.

### 2. Congestion-Guided Residual Graph Clustering (CGRGC)

CGRGC is a congestion-aware graph clustering framework designed for dynamic transportation networks.

The algorithm consists of three sequential phases:

#### Phase I: Primary Clustering

A congestion-filtered graph is constructed using only low-congestion edges. Initial clusters are formed exclusively from these reliable connections, creating stable and traffic-resilient operational zones.

#### Phase II: Neighborhood Absorption

Nodes that remain weakly assigned are incorporated into nearby clusters through graph-neighborhood expansion while preserving cluster coherence.

#### Phase III: Residual Assignment

Any remaining nodes are assigned to clusters using a minimum congestion-cost criterion, ensuring complete coverage of the delivery network.

This hierarchical strategy allows the system to construct clusters that reflect actual traffic conditions rather than purely geometric proximity.

### 3. Time-Expanded Graph Neural Network

The clustered delivery network is transformed into a time-expanded graph that captures both spatial structure and temporal traffic evolution.

The GNN learns latent representations using information such as:

* Delivery demand
* Network topology
* Traffic congestion
* Drone altitude level
* Temporal dynamics

These learned embeddings provide a compact representation of the operational state of the environment.

### 4. Reinforcement Learning-Based Route Optimization

The learned graph embeddings are supplied to a Reinforcement Learning agent responsible for route planning.

The agent dynamically selects:

* Delivery sequence
* Next waypoint
* Altitude transitions
* Route adjustments

based on current and predicted network conditions.

The objective is to maximize delivery efficiency while minimizing congestion exposure, travel cost, and energy consumption.

## Baseline Route Optimization Methods

The proposed framework is benchmarked against the following routing approaches:

* Prioritized A*
* Monte Carlo Tree Search (MCTS)
* Hill Climbing

These methods serve as reference models for evaluating the effectiveness of the proposed congestion-aware learning framework.

## Research Contributions

This project contributes:

* A novel congestion-aware graph clustering algorithm (CGRGC)
* Dynamic demand partitioning based on traffic conditions
* Integration of time-expanded graph neural networks for spatiotemporal representation learning
* Reinforcement learning for adaptive multi-drone routing
* Multi-altitude route planning under evolving traffic conditions
* Comparative evaluation against established clustering and routing baselines

## Applications

Potential applications include:

* Urban drone delivery systems
* Smart logistics networks
* Autonomous transportation systems
* Emergency response and medical delivery
* Supply chain optimization
* Smart city infrastructure

## Current Status

The project is currently under active development, focusing on the design and evaluation of congestion-aware clustering, spatiotemporal graph learning, and adaptive multi-drone route optimization in realistic urban environments.
