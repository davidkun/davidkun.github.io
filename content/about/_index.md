---
title: about
tags:
- about-me
---

I started out as an aerospace engineer (designed and tested autopilot, autoland, and flight guidance control laws) and eventually grew into the software developer role. At [MITRE](https://www.mitre.org), I worked on aviation research software (e.g., aircraft trajectory simulation engine, near-real time airport risk detection application, and a big data platform for aviation research). 

Nowadays, I develop software apps in support of the [Spatial Audio](https://www.ceva-ip.com/product/ceva-realspace/) business unit at [Ceva](https://www.ceva-ip.com). Over the years, I went from writing (primarily) Python, to Java, and now back to Python. I've enjoyed [dabbling with Clojure](https://github.com/davidkun/clojure-exercises) outside of work and would love to one day get paid to write Clojure.

I'm interested in sustainable development practices, team culture, software quality/testing, and reproducible research. My overarching focus has been on **continuous improvement**.

---

{{< details title="click to see full resume" open=false >}}
### Professional Experience

**Sr. Software Developer**, Ceva `April 2024--present`

* Developing a Python application for visualizing and comparing head-related transfer functions (HRTFs). Implementing published algorithms (and developing new ones) and visualizing similarity metrics with Bokeh. The application is quickly growing to support new Spatial Audio business needs.

**Engineering Manager**, The MITRE Corporation `Sept 2022--April 2024`

* Led the Big Data Engineering team in the Transportation Data Analytics department to operate and evolve our big data platform. Managed project allocations, helped with career goals, and mentored junior staff (code reviews, pair programming).
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