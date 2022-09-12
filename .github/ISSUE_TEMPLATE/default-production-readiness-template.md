---
name: Default production readiness template
about: Describe template for production readiness tasks
title: ''
labels: ''
assignees: ''

---

# Background
As part of the deployment to ORG, it is necessary to ensure that all of the activities are completed in order to ensure that APP is fully configured and ready for use in the REGIONS ENV environments.

# Requirement
## Productionisation and deployment
- [ ] Confirm application is deployable/deployed to both production environments.  
  - [ ] Deployments successful
  - [ ] canary and prod smoke test issues.  Shiva is looking at them.
- [ ] Review quotas for namespace allocation
- [ ] Review and update the application config (that is specific to summer)
  - [ ] Kafka
  - [ ] Cassandra
  - [ ] CQL migrate
  - [ ] other config
- [ ] Confirm cassandra connectivity,
  - [ ] Check healthcheck page
  - [ ] Check against [devops page](https://github.com/sky-uk/ovp-devops-inventory/blob/master/summer-prod-admin_inventory.json)
  - [ ] Check secrets / passwords.
    - [ ] validate cassandra credentials(https://sky.slack.com/archives/C0D2GDKT5/p1645107900194149)
  - [ ] Check use of SSL for connection
- [ ]  Check Kafka connectivity
  - [ ] Check kaas kafka secrets / kafka connectivity
- [ ] Verify build.gradle prod deployment config
- [ ] Check ingresses and gtms
  - [ ] Verify build.gradle prod ingresses
  - [ ] test ingresses [testing help](https://wiki.at.sky/pages/viewpage.action?spaceKey=ODO&title=Dev+GTM+Configuration)
- [ ] Smoke tests - ensure the test-runner works for the both production environments
- [ ] Raise card to enable continuous deployment https://github.com/sky-uk/lakitu/issues/1654
- [ ] Check extended nft runs correctly for summer

## Monitoring
- [ ] Verify metrics for DM are present in both summer Prometheus
- [ ] Review DM grafana dashboards
  - [ ] Ensure graphs have dropdown items for summer
  - [ ] Add support for new summer territories
    - Changed the graph to use territory variable based on the available metrics in the datasource.
- [ ] Admin dashboard check health
- [ ] Check summer [TOP](https://top-sum-prod.telemetry.nbcuott.com/) / kibana works for DM.

## Other
- [ ] Runbooks
- [ ] Check/Add bookmarks for summer
- [ ] Update [CD dashboard project](https://cd-dashboard.tools.cosmic.sky/) for summer
