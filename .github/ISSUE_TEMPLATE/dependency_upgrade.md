---
name: Dependency upgrade
about: Upgrading the version of a system dependency
title: 'Upgrade to [INSERT DEPENDENCY HERE] [INSERT VERSION NUMBER HERE]'
labels: maintenance
assignees: ''

---

- [ ] Add the new version to CircleCI
- [ ] Add the new version to .tool-versions
- [ ] Fix any failing tests or dependency issues caused by upgrade
- [ ] Provision staging box to use the new version
- [ ] Deploy code that works with the new version to staging
- [ ] Manually test on staging box with the new version
- [ ] Provision new boxes by running the playbook one server at as described in [Upgrading major versions of dependencies](https://github.com/pulibrary/pul-it-handbook/blob/main/services/upgrading_major_versions.md)
- [ ] Update this issue template with anything we need to keep in mind for the next upgrade
