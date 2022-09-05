---
name: Default Banana scaler deployment template
about: Template for new Banana scaler deployments
title: ''
labels: ''
assignees: ''

---

<!--
    1. Add labels
    2. Add milestone
    3. If you want the card to be on the board now add the project `Stratos`
    4. Fill in issue template below
-->

## Prerequisites
- Application-to-scale deployment
- Stubbed-NFT banana scaler deployment (For int-nft)
- INT-NFT banana scaler deployment (For Prod)


### Details

Promote banana dynamic pod scaling to stubbed-nft / int-nft / production.

Core Wiki Horizontal Auto Scaling Reference:
https://core-docs.dev.ce.eu-central-1-aws.npottdc.sky/docs/tenant-wiki/how-to/horizontal-pod-autoscaling/#setup-the-banana-scaler-deployment

### Check list for going to the next environment in the pipeline: stubbed-nft -> int-nft -> prod
- [ ] Confirm application is suitable for autoscaling.
- [ ] Prove application scales linearly.
- [ ] Confirm performance tests do not burst.
- [ ] Confirm app prometheus is externally monitored.

### Tasks

- [ ] Defuzz
- [ ] Update core-platform-config resource allocation if required - ** stubbed-nft/int-nft/Prod in both regions
- [ ] Deploy updated pod resource allocation and number XX pods (cpu 000m; memory;  000Mi ; jvm heap initial and max 000Mi) (get numbers from NFT engineer)
- [ ] Ensure extra quota is added and maxSurge is configured.
- [ ] Ensure replicas removed from deployment. https://core-docs.dev.ce.eu-central-1-aws.npottdc.sky/docs/tenant-wiki/how-to/horizontal-pod-autoscaling/#changes-to-application-deployment
- [ ] Banana scaler query recording rules added to prometheus in both regions: (example: #1427)
- [ ] Update prometheus scrape interval to 10 seconds in both regions: (example: #1424)
- [ ] (stubbed-nft) Deploy banana scaler to stubbed-nft
- [ ] (int-nft) Deploy banana scaler to int-nft
- [ ] (int-nft) Review banana scaler behaving in stubbed-nft as expected
- [ ] (prod) Review banana scaler behaving in int-nft as expected
- [ ] (prod) Deploy banana scaler to production (min and max replicas should be set the same)
    - Canary config: https://core-docs.dev.ce.eu-central-1-aws.npottdc.sky/docs/tenant-wiki/how-to/horizontal-pod-autoscaling/#canary-deployments
    - Banana scaler read me: https://github.com/sky-uk/banana-scaler/blob/master/scaler/README.md
- [ ] (prod) Confirm banana scaler is monitored and alerting is in place. https://core-docs.dev.ce.eu-central-1-aws.npottdc.sky/docs/tenant-wiki/how-to/horizontal-pod-autoscaling/#alerting
    - See example for PCS [here](https://stratos-pc-prometheus-external.int-nft.ce.us-west-2-aws.npskooniedc.com/rules#./banana-scaler.rule)
- [ ] (prod) Once alerting is in place, update the min replica count.
- [ ] Wiki documentation
- [ ] Demo

#### Acceptance Criteria

#### Developer info
