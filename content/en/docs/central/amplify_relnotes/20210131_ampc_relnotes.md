---
title: AMPLIFY Central January 2021 Release Notes
linktitle: AMPLIFY Central January 2021
weight: 90
description: AMPLIFY Central enables the user to manage their provider /
  consumer view. For more information, see the AMPLIFY Central documentation.
---
## New features and enhancements

The following new features and enhancements are available in this update.

### AMPLIFY Central CLI

The AMPLIFY Central CLI is a package for managing AMPLIFY Central resources with a DevOps approach to API Management.

AMPLIFY Central CLI version 0.6.0 is now available on NPM (<https://www.npmjs.com/package/@axway/amplify-central-cli/v/0.6.0>)

The CLI extension is compatible **only** with the AMPLIFY CLI **version 1.4** (<https://www.npmjs.com/package/@axway/amplify-cli/v/1.4.0>)

**This is not yet compatible with the Axway CLI**.

The AMPLIFY Central CLI includes the following enhancements:  

* installation of Azure agents
* Providers can use new resource shortnames to access resources (use `amplify central get` to view list resource shortnames)
* Providers can remove previously configure parameters using the interactive mode of the Central CLI (use `amplify central config unset <key>`)
* Providers can view a list of multiple resource tables (use `amplify central get apis, apisr, apisi –s <scopename>`)

### AMPLIFY Central WebUI

The AMPLIFY Central WebUI is used by both the API providers and consumers to manage and consume APIs.

The AMPLIFY Central WebUI includes the following enhancements:  

* View the agents connected to an environment in environment detail page
* Improved Provider UX of API Service List and Details page:

    * Providers can view the user who made the last modification from the list of API Service versions.
    * Providers can search/sort on the Endpoints and Catalog Item list tables.
    * Providers can add new API Services from the UI.

### Axway Edge Gateway / AWS / Azure Agents

To provide better visibility into your mutli-type gateway eco system, two sets of agents are provided. These agents collect data from the Gateway (API / traffic) and exposes it in AMPLIFY Central, providing you with a global vision of your eco system from a single interface.

The agents include the following enhancements:

* Azure gateway support

### Mesh governance

AMPLIFY Central mesh governance enables you to govern and manage your APIs, public and private services, along with the hybrid environments where they are located.

Mesh governance includes the following enhancements:

* The Mesh Governance open beta has been updated to use helm3 and Kubernetes 1.16.
* The Mesh Traceability Agent has been updated to allow API transaction header logging to be globally enabled or disabled with an option passed to it on deployment. This will affect all API transactions visible in the API Observer.
* The Mesh Traceability Agent has been updated to allow a set of header redaction rules to be passed to it on deployment. The rules apply globally to all transaction logging and provide options for path, query parameter and header filtering. Request and response headers may be separately managed to selectively redacted or entirely removed from the results visible in the API Observer.
* Both of these options are applied using the mesh agent helm deployment step and are documented in Step 4 of the full mesh client and cluster setup instructions here: [https://github.com/Axway/Setup-Amplify-Mesh-Governance/wiki/Step-4.-Create-an-Amplify-Central-environment-and-connect-your-Kubernetes-cluster-to-it](https://github.com/Axway/Setup-Amplify-Mesh-Governance/wiki/Step-4.-Create-an-Amplify-Central-environment-and-connect-your-Kubernetes-cluster-to-it)

Redeploying with helm to change either of these options will cause the mesh agent to restart.

## Fixed issues

The following issues were fixed in this version of AMPLIFY Central:

* Previously, Now,

## Known limitations

This version of AMPLIFY Central has the following limitations:

* API Observer:

    * Users that are assigned the Consumer role cannot see their subscription usage on the API Observer screen.  

* Axway Edge Gateway Agents:

    * Discovery Agent only discovers APIs having PassThrough, API Key and Oauth security.
    * Discovery Agent cannot expose discovered APIs in multiple teams, so the organization structure on API Manager is lost in Central. As a result, the API provider must create the team in AMPLIFY Platform and share the API within appropriate teams.
    * Discovery Agent cannot detect that an API has been renamed. Consequently, you will see both the old API and the new API on AMPLIFY Central.
    * Discovery Agent does not handle frontend API deletion. Consequently, the Unified Catalog API is out of sync.
    * Traceability Agent is not working in an externally managed topology deployment.

* AWS Gateway agents:

    * Discovery Agent is working with only one AWS Region (the one used when installing the agent).
    * Discovery Agent does not associate the usage plan and API when a subscriber chooses a usage plan that is not already linked to the chosen API.

* Azure agents:

    * Discovery Agent is not managing revision and version yet
    * Traceability agent is not reporting the App usage traffic

* Mesh governance alpha Discovery Agents:

    * The alpha Discovery Agents do not work with the Mesh Traceability Agent.
