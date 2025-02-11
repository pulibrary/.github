---
name: Production readiness audit
about: Evaluate an application for adherence to production application expectations
title: '[Application] Production readiness audit'
labels: ''
assignees: ''

---
PUL IT has put together a [checklist for production applications](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md).

The work of this ticket is to go through the checklist and evaluate which of the criteria an application meets, and to create tickets for any criteria which an application does not meet.

## Infrastructure
  - [ ] All environments can be fully build using a playbook in [Princeton Ansible](https://github.com/pulibrary/princeton_ansible) ([Infrastructure as Code](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#infrastructure-as-code))
  - [ ] There is only one application on the server ([One Application Per Server](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#one-application-per-server))
  - [ ] There is a staging environment ([Staging Environment](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#staging-environment))
  - [ ] There are at least two servers per environment ([Minimum 2 Servers Per Environment](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#minimum-2-servers-per-environment))
  - [ ] Can be deployed with a single command (probably via capistrano) ([Low Barrier to Deployment](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#low-barrier-to-deployment))
  - [ ] Backup and Restore
    - [ ] [List services here, e.g. Database, Solr]
      - [ ] There is a documented process for backup and restore
      - [ ] We have practiced backup and restore
  - [ ] Solr index uses a replication factor of 3 ([Index Replication](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#index-replication))

## Security
  - [ ] Main dependencies (Ruby, PHP, etc.) are under support ([Use Dependencies Under Support](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#use-dependencies-under-support))
  - [ ] Automatic dependency checking for upstream dependencies (e.g. Dependabot) ([Use Dependencies Under Support](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#use-dependencies-under-support))
  - [ ] Web ports are only accessible to the load balancer, not the world ([Firewall](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#firewall))
  - [ ] Secrets are in Ansible Vault ([Secrets Management](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#secrets-management))
  - [ ] We use OIT supported Single Sign-On for users to authenticate ([Single Sign-on for Authentication / Authorization](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#single-sign-on-for-authentication--authorization))

## Monitoring
  - [ ] Alerts are set up in Datadog, CheckMK, or Honeybadger (CheckMK preferred over Datadog) ([Alerts Requiring Response](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#alerts-requiring-response))
  - [ ] There are not many false alarms with the alerts ([Alerts Requiring Response](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#alerts-requiring-response))
  - [ ] We store metrics on the state of the system, either in Datadog, CheckMK, or Honeybadger (CheckMK preferred over Datadog) ([Diagnostic Metrics](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#diagnostic-metrics))

## User Interfaces
  - [ ] WCAG AA Compliant ([WCAG AA Compliance](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#wcag-aa-compliance))
  - [ ] WCAG Compliance covered by CI ([WCAG AA Compliance](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#wcag-aa-compliance))
  - [ ] Gathers Web Analytics that measure the goals and success criteria of that application ([Web Analytics](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#web-analytics))

## Code Practices
  - [ ] Main branch is deployable ([Main Branch Always Deployable](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#main-branch-always-deployable))
  - [ ] There are automated tests that run on pull requests and merges to main ([Automated Tests](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#automated-tests))
  - [ ] Code coverage is measured and displayed in README ([Code Coverage](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#code-coverage))
  - [ ] [Code review required for merge to main](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#code-review-required-for-merge-to-main)
  - [ ] Application is configured via Environment Variables, preferably set up via Princeton Ansible ([Configuration via Environment Variables](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#configuration-via-environment-variables))
  - [ ] There is a README with access to [documentation](https://github.com/pulibrary/pul-it-handbook/blob/main/norms/production_application_checklist.md#documentation) that includes
    - [ ] What the application is for
    - [ ] How to run the application
    - [ ] How to deploy the application
    - [ ] How to run the application's tests
    - [ ] Any other activities a developer would likely want to know about
