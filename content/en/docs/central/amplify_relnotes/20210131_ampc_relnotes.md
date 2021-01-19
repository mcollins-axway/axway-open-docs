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

The AMPLIFY Central CLI includes the following enhancements:  

* ADD ENHANCEMENTS HERE

### AMPLIFY Central WebUI

The AMPLIFY Central WebUI is used by both the API providers and consumers to manage and consume APIs.

The AMPLIFY Central WebUI includes the following enhancements:  

* ADD ENHANCEMENTS HERE

### Mesh governance

AMPLIFY Central mesh governance enables you to govern and manage your APIs, public and private services, along with the hybrid environments where they are located.

Mesh governance includes the following enhancements: 

* ADD ENHANCEMENTS HERE

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

* Mesh governance alpha Discovery Agents:

    * The alpha Discovery Agents do not work with the Mesh Traceability Agent.