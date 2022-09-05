---
name: Default application deployment template
about: Template for new deployments of applications
title: ''
labels: planning
assignees: ''

---

<!--
    1. Add labels
    2. Add milestone
    3. If you want the card to be on the board now add the project `Stratos`
    4. Fill in issue template below
-->

## Prerequisites
- Stubbed-NFT sign-off
- CI setup
- Common metrics are generated
- Common alerts are setup

### Details

Deploy ** APP ** to ** ORG ** ** ENV **


### Tasks

#### Dev
- [ ] Defuzz
- [ ] Setup downstreams dependencies
- [ ] Namespace quota (app and injector quotas) request to core team
- [ ] Kafka certs request with Kaas team, if applicable
- [ ] Setup DB (DB setup instructions : https://wiki.at.sky/display/ODO/Cassandra+buildout)
- [ ] update schema migrator
- [ ] Deploy app to Region 1 (plus stubbed nft mocks)
- [ ] Deploy app to Region 2 (plus stubbed nft mocks)
- [ ] pipeline updates
- [ ] add stratline calls to cd-scripts
- [ ] Ingress & gtm setup
- [ ] Tops logging setup
- [ ] Prometheus deployment
- [ ] Add GPC uptime checks. [wiki](https://github.com/sky-uk/aieng-global-ott-uptime-service)
- [ ] Add OPSView/Pulsar check for the app
- [ ] Make sure if an alert is triggered we are calling spark (monitoring project)
- [ ] Add/check application in Stardust (https://github.com/sky-uk/ovp-stardust)
- [ ] Wiki documentation
- [ ] Add deployment links to bookmarks (logs, prometheus and grafana if available)


#### QA
- [ ] Setup and run Integration Tests
- [ ] configure prod deployment tests

#### Acceptance criteria
- [ ] Info endpoint showing OK

#### Extra information
