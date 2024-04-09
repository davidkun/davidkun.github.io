---
title: about
tags:
- about-me
---

Up until recently, I worked at The [MITRE](https://www.mitre.org) Corporation, an organization that manages several federally funded research and development centers (FFRDCs). The team I was part of maintains and evolves a big data platform (primarily aviation data, weather, terrain, etc.), enabling analysts to answer complex questions about the national airspace.

The platform work mainly involved writing Java and working with Hadoop (plus Avro, Parquet, Spark, Crunch, Kafka, Flink, etc.). More recently, we began focusing on cloud migration, intelligent/automated operations, and data observability. When I did brief data science/analysis work, I'd use Python and sometimes Clojure.

I'm primarily interested in sustainable development practices, software quality, software testing, and reproducible research. The central theme of my work/career has been (and continues to be) a dedication to **continuous improvement**.

---

{{< details title="click to see full resume" open=false >}}
### Professional Experience

**Engineering Manager**, The MITRE Corporation `Sept 2022--April 2024`

* Leading the Big Data Engineering team in the Transportation Data Analytics department to operate and evolve our big data platform. Managing project allocations, helping with career goals, and mentoring junior developers (code reviews, pair programming).
* Created an automated ops service (Spring Boot) running on an OpenShift cluster (Helm, Kubernetes) for data recovery actions, data gap / schema change alerts, and syncing data/metadata from on-prem (Hadoop, HBase) to AWS (S3, DynamoDB). This decreased operating costs, increased data observability.
* Improved our hiring process (added structured questions and expectations, optimized interview pipeline to reject earlier) and streamlined the onboarding process (created a bootstrapped laptop setup script (Zsh), established a path to first day/week/month expectations for new hires).

**Lead Software Engineer**, The MITRE Corporation `April 2021--Sept 2022`

* Led a DevOps transformation for our Hadoop-based big data platform software (Java) and team. Sped up release process 3x by (1) porting from Maven to Gradle, (2) parallelizing test suites after categorizing by test size, (3) changing the architecture and dependency direction to decouple releases of sub-components, and (4) optimizing our build pipeline and Dockerfiles. Instrumented systems with metrics (Prometheus) and dashboards (Grafana). Formalized on-call responsibilities and hand-offs.
* Developed aviation analytics (Java, Apache Crunch on Hadoop) and analyzed/visualized the generated data (Python, Clojure) for data quality and demos/documentation.

**Sr. Modeling & Simulation Engineer**, The MITRE Corporation `April 2017--April 2021`

* Developed a near-real time Java app that streams radar data via Kafka from airports and detects potential risk via physics-based modeling and machine learning models ([news article link](https://www.mitre.org/news-insights/impact-story/aviation-safety-assessments-cover-new-ground)). Deployed the app into customer's AWS GovCloud (Ansible-based deployment, MSK for streaming, Kibana for ops). Events are ranked and published to a SQL database for FAA safety review.
* Developed a Java library to simulate (in fast-time) aircraft trajectories along specified procedures. The software generates results for a desktop app used by the FAA to assess "flyability" during procedure design. Tuned performance via benchmarking (JMH, with stats generated in CI/CD pipeline) and profiling (VisualVM). Validated against a GE Flight Management System (hardware-in-the-loop tests).

**Sr. Systems Engineer**, Rockwell Collins `June 2015--March 2017`

* Helped design and test the automatic Flight Control Systems for several aircraft.
* Wrote requirements, designed controllers (Matlab), and developed simulations tools (Python) for verifying an auto-land system (successful flight test in 2017).

**Sikorsky CH-53 Helicopter Technician**, Israeli Air Force `Aug 2006--Aug 2009`

* Worked on the CH-53 structural, mechanical, and hydraulic systems, led a team of 10+ soldiers, and trained recruits on inspections and repairs.


### Education

**Purdue University**, West Lafayette, IN

* `2015` -- M.S. Aerospace Engineering (3.94/4.00) _Guidance, Navigation, & Control_
* `2013` -- B.S. Aerospace Engineering (3.89/4.00) _Dynamics & Control, Aerodynamics_

### Skills

* **Java**, **Python**, Clojure, Bash
* Spring Boot, Apache [Kafka, HBase, Hadoop, Crunch], AWS [S3, MSK, DynamoDB], JUnit, Flask, seaborn, tox, pytest
* Git, Gradle, Docker, Kubernetes, Ansible, GitHub Actions, Gitlab CI/CD

{{< /details >}}