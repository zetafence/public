<h1 align="center">
    <img align="left" width="100" height="100" src="https://zetafence.com/images/logo.png" alt="Zetafence"/>
    <br />
    <p style="color: #808080; text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);">
    Zetafence Conception
    </p>
</h1>

<br/>

## Underlying Motivations 2022

Born out of frustration in designing modern Dev / SecOps workflows for brownfield & greenfield deployments.

- No elegant ways for operators to develop critical decision-making logic best suited for their needs. Operators should focus on workflow design, not how to enact them
- Alerting, logging primitives are basic today e.g. Slack app, Alert logs, Email, etc.
- Operators need better customization - filters, priorities, actions of what alerts are important to react faster
- Dependency evaluation requires sophisticated tools

Thus, Klig.io was born in 2022 primarily with the intention of easening Dev & DevSecOps.

## Summary of Zetafence Story

A quick summary of how Zetafence (originally Klig.io) was conceived, and developed.

- Graphical abstraction was perceived an important aspect from beginning
- Hypergraphs are equivalent to unveiling multiple dimensions of the same problem e.g. 2D vs 3D, and offered to reveal granular details that otherwise would create blindspots
- Blindspot detection in security is extremely important. This can be uniquely achieved through Hypergraph. An equivalent example is map application in NYC showing various connected points via roads, but tunnels offer a completely alternate and richer perspective
- Building out Hypergraph abstraction semantics enabled to change perspective of the problem domain, and observe existing problems in in a completely new way. For instance, viewing dependencies and relationships among Kubernetes resources such as ClusterRole to Deployment could be vastly enriched via Hypergraph representing ClusterRole to Deployments + Namespaces
- Set theory was favorably used to simplify Hypergraph relationship associations & simplifying them
- Building out Klig Mgmt plane using Hypergraph -> Build out resource control plane was refreshingly new. Typically they are built out the other way

<br/>Copyright (C)
    <a href="https://zetafence.com">
    <img align="center" width="85" src="https://img.shields.io/badge/Zetafence-8A2BE2" alt="Zetafence"/></a>
2024.
