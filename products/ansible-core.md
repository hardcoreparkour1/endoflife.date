---
title: Ansible-core
category: framework
iconSlug: ansible
permalink: /ansible-core
versionCommand: ansible --version
releasePolicyLink: https://docs.ansible.com/ansible-core/devel/reference_appendices/release_and_maintenance.html
changelogTemplate: https://github.com/ansible/ansible/blob/stable-__RELEASE_CYCLE__/changelogs/CHANGELOG-v__RELEASE_CYCLE__.rst
releaseDateColumn: true
activeSupportColumn: false
eolColumn: Supported

auto:
-   git: https://github.com/ansible/ansible.git

releases:
-   releaseCycle: "2.14"
    releaseDate: 2022-11-07
    eol: 2024-05-31
    latest: "2.14.3"
    latestReleaseDate: 2023-02-27
    pythonVersionsControlNode: 3.9 - 3.11
    pythonVersionsManagedNode: 2.7 or 3.5 - 3.11

-   releaseCycle: "2.13"
    releaseDate: 2022-05-16
    eol: 2023-11-30
    latest: "2.13.8"
    latestReleaseDate: 2023-02-27
    pythonVersionsControlNode: 3.8 - 3.10
    pythonVersionsManagedNode: 2.7 or 3.5 - 3.10

-   releaseCycle: "2.12"
    releaseDate: 2021-11-08
    eol: 2023-05-31
    latest: "2.12.10"
    latestReleaseDate: 2022-10-11
    pythonVersionsControlNode: 3.8 - 3.10
    pythonVersionsManagedNode: 2.6 - 2.7 or 3.5 - 3.10

-   releaseCycle: "2.11"
    releaseDate: 2021-04-26
    eol: 2022-11-07
    latest: "2.11.12"
    latestReleaseDate: 2022-05-23
    pythonVersionsControlNode: 2.7 or 3.5 - 3.9
    pythonVersionsManagedNode: 2.6 - 2.7 or 3.5 - 3.9

-   releaseCycle: "2.10"
    releaseDate: 2020-08-13
    eol: 2022-05-23
    latest: "2.10.17"
    latestReleaseDate: 2022-01-31
    pythonVersionsControlNode: 2.7 or 3.5
    pythonVersionsManagedNode: 2.6 or 3.5

-   releaseCycle: "2.9"
    releaseDate: 2019-10-31
    eol: 2022-05-23
    latest: "2.9.27"
    latestReleaseDate: 2021-10-11
    pythonVersionsControlNode: 2.7 or 3.5
    pythonVersionsManagedNode: 2.6 or 3.5

---

> [Ansible](https://www.ansible.com/) is an open-source software provisioning, configuration
> management and application-deployment tool enabling infrastructure as code. It runs on many
> Unix-like systems, and can configure both Unix-like systems and Microsoft Windows.

The `ansible-core` package has a graduated maintenance structure that extends to three major
releases. For detailed information, see Ansible [Releases and maintenance](https://docs.ansible.com/ansible/devel/reference_appendices/release_and_maintenance.html).

See the [ansible-core Roadmap](https://docs.ansible.com/ansible-core/devel/roadmap/ansible_core_roadmap_index.html)
for upcoming release details.

## [Python Compatibility](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#node-requirement-summary)

{% include table.html
labels="ansible-core,Control node Python,Managed node Python"
fields="releaseCycle,pythonVersionsControlNode,pythonVersionsManagedNode"
types="string,string,string"
rows=page.releases %}
  
