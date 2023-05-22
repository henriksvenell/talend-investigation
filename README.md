# Talend

Uses:

- Pendo
- Launch darkly
- scim (read more about)

## SCIM

### api/v1/scim/me

Returns info about the user:

- Applications assigned
- Email and display names
- List of entitlements:
- Roles
- Metadata

### api/v2/scim/accounts/current

### api/v1/iam-server/application-details

Gets URL to the assigned applications

### api/v1/scim/Users

### api/v1/scim/Groups

## Infra

### api/user

### api/v1/streams-cloud-agents

## Datastore

### api/v1/datastores

Lists available data stores

### api/v1/datastores/:id

## Dataset

- One dataset per table, for excel files there will be multiple datasets.
- Extended [classification](./dataset/classification.md) information
- Statistics ~ the same but Talend have variance + [medcouple](https://en.wikipedia.org/wiki/Medcouple)

### api/v1/datasets

### api/v1/datasets/:id/attributes

### api/v1/datasets/:id/metadata

### api/v1/dataset-samples/:id

### api/v1/datasets/trust-score/composite-history

## Metadata

### api/v1/facets

### api/v1/crawlers

### api/v1/semantic/categories

### api/v1/rules

## Data preparation

### api/export/formats/preparations/:id

### api/preparations/:id/content

### api/v2/preparations/:id/steps/:stepId

### api/preparations/:id/steps/:stepId/columns/:columnId/statistics

### transform/preparations/functions/mapping

### transform/preparations/:id/runs

### transform/preparations/:id/columns/mapping-tck

### transform/preparations/:id/rowmetadata/validity

### tacokit/:id/functions

## Streams/Pipeline

### [api/v1/streams/:id](./streams/streams-id.json)

Information on the current pipeline

<img src="./images/pipeline.png" height="300">

This example uses:

- 2 datasets as inputs from 2 different datastores
- Produces 1 dataset

Payload:

- List of datasets (3)
- List of datastores (2)
- Runtime metrics
- Pipelines
  - Components - list of the nodes with graphicalAttributes
    - source - local storage
    - source - datastore-connector
    - processor - left outer join
    - sink - local storage
  - Ports - incomming and outgoing endpoints to the nodes
  - Steps - edges between the nodes
    - sourceId - source port
    - targetId - target port

### api/v1/streams/:id/processors

Information on the current processors

<img src="./images/processors.png" height="600">

### api/v1/streams/pipelines/:id/previews/:previewId/ports/:portId/schema
