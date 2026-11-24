# pfGuides

Guides associated with
[Patrick Freeland](https://www.linkedin.com/in/patrickfreeland/)
projects with <https://github.com/atniclimate/>.
This is a collaboration between Patrick [Brian Yandell](https://byandell.github.io/).

## DocumentTools Pages

The following pages were developed in
[DocumentTools](https://github.com/byandell/DocumentTools)
based on discussion with and repos of Patrick Freeland.

- [Build and Launch a Serverless Interactive Website](https://byandell.github.io/DocumentTools/github/serverless.html)
- [Harness for Document Content Analysis](https://byandell.github.io/DocumentTools/AI/harness.html#harness-for-document-content-analysis)

## Deployments

At present this only includes guides to how certain
repos are deployed to the web.
The primary prompt to Gemini 3.8 Flash in Antigravity was:

*Using <https://byandell.github.io/DocumentTools/github/serverless.html>, explain concisely how this repo gets deployed to produce
`https://atniclimate.github.io/[repo-name]/`. Avoid duplication of content. Use mermaid for any flowchart.*

Websites are `https://atniclimate.github.io/[repo-name]/`;
repositories are `https://github.com/atniclimate/[repo-name]/`;
documentation lives in `deploy/[repo-name].md`.

| Website | Documentation |
| --- | --- |
| [atni-task-force](https://atniclimate.github.io/atni-task-force/) | [atni-task-force.md](deploy/atni-task-force.md) |
| [climate-curriculum](https://atniclimate.github.io/climate-curriculum/) | [climate-curriculum.md](deploy/climate-curriculum.md) |
| [dynamic-drought-module](https://atniclimate.github.io/dynamic-drought-module/) | [dynamic-drought-module.md](deploy/dynamic-drought-module.md) |
| [policy-sentinel](https://atniclimate.github.io/policy-sentinel/) | [policy-sentinel.md](deploy/policy-sentinel.md) |
| [TERRA](https://atniclimate.github.io/TERRA/) | [TERRA.md](deploy/TERRA.md) |
| [TieredSovereignDataFramework](https://atniclimate.github.io/TieredSovereignDataFramework/) | [TieredSovereignDataFramework.md](deploy/TieredSovereignDataFramework.md) |

## Tribal Environmental Resilience and Resource Analytics (TERRA) Components

[TERRA](https://atniclimate.github.io/TERRA/)
is an umbrella summarizing status of (9) projects.
There is a package that will run on a laptop to visualize
progress across projects.

The Dynamic Drought Module and the Policy Sentinel are publicly available today. The nine applications are not yet connected to each other.
The [Tiered Sovereign Data Framework](https://atniclimate.github.io/TieredSovereignDataFramework/) is incorporated into all projects.

- [Dynamic Drought Module (DDM)](https://atniclimate.github.io/dynamic-drought-module/) ([source](https://github.com/atniclimate/dynamic-drought-module))
- [CAST and SHIELD](https://atniclimate.github.io/TERRA/#/apps/cast) ([source](https://github.com/atniclimate/CAST))
- [ATNI GeoBase](https://atniclimate.github.io/TERRA/#/apps/geobase/): will run on laptop
- [Land Use Analyzer](https://atniclimate.github.io/TERRA/#/apps/lua)
- [Policy Sentinel](https://atniclimate.github.io/policy-sentinel/) ([source](https://github.com/atniclimate/policy-sentinel))
- [TCR Policy Scanner](https://atniclimate.github.io/TERRA/#/apps/tcr)
- [Plan Assessor](https://atniclimate.github.io/TERRA/#/apps/plan)
- [ATNI ResIST](https://atniclimate.github.io/TERRA/#/apps/resist)
- [Community Navigator](https://atniclimate.github.io/TERRA/#/apps/navigator) ([source](https://github.com/atniclimate/community-connector))
