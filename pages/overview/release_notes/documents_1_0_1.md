---
title: GP Connect API - Access Document 1.0.1-beta release notes
keywords: GP Connect, release notes
tags: [release]
sidebar: overview_sidebar
permalink: overview_release_notes_documents_1_0_1.html
summary: "GP Connect API - Access Document 1.0.1-beta released on 5th November 2019"
toc: false
---

{% include warning.html content="The seperate Access Document specification was merged into the GP Connect API specification at [GP Connect API 1.5.0](overview_release_notes_1_5_0.html#access-document). This page contains a release note from when the Access Document specification was versioned and published independently." %}

## Introduction ##

The GP Connect API - Access Document 1.0.1-beta contains an update to the Access Document document capability following external review.   This specification is being published separately to the other capabilities and looks purely at documents.

### API guidance ###

**Affects**&nbsp; Core

**Description:**

- An example has been added to the `[PROVIDER_ROUTING_SEGMENT]` in service root URL to clarify how it should be used.

**Pages changed:**

- [General API Guidance](development_general_api_guidance.html#service-root-url-versioning)

### Capability statement updates ###

**Affects**&nbsp; Access Documents

**Description:**&nbsp;

- The version number in the `CapabilityStatement.version` has been updated to 1.0.1

### API ###

**Affects**&nbsp; Access Document

**Tickets:** [#858](https://github.com/nhsconnect/gpconnect/issues/858), [#871](https://github.com/nhsconnect/gpconnect/issues/871), [#872](https://github.com/nhsconnect/gpconnect/issues/872), [#870](https://github.com/nhsconnect/gpconnect/issues/870)

**Description:**

- custodian has been removed for the search parameters
- clarification has been added to the include parameters
- The created, facility, author and type search parameters have been relaxed to **MAY** be included instead of **SHOULD**
- update request to indicate that the `subject` search parameter uses the FHIR logical id.
- guidance added on how `created` search parameter should be matched when `DocumentReference.created` doesn't exist
- added guidance on how to use the created search parameter to represent a period
- updated description of MasterIdentifier

**Pages changed:**

- [Search for a patient's documents](access_documents_development_search_patient_documents.html)
- [Retrieve a patient's documents](access_documents_development_retrieve_patient_documents.html)
- [Consumer sessions illustrated](access_documents_development_api_session.html)

### Documents Guidance and DocumentReference Profile ###

**Affects**&nbsp; Access Document

**Tickets:** [#881](https://github.com/nhsconnect/gpconnect/issues/881), [#880](https://github.com/nhsconnect/gpconnect/issues/880), [#879](https://github.com/nhsconnect/gpconnect/issues/879), [#884](https://github.com/nhsconnect/gpconnect/issues/884), [#853](https://github.com/nhsconnect/gpconnect/issues/853), [#852](https://github.com/nhsconnect/gpconnect/issues/852)

**Description:**

- guidance has been added for unfiled documents
- guidance has been added for sensitive documents
- list of white listed documents has been removed
- end user jobs in value proposition diagram has been updated
- content.attachment.data field moved to 'Elements not in use' section of DocumentReference profile

**Pages changed:**

- [Documents guidance](access_documents_development_documents_guidance.html)
- [DocumentReference](access_documents_development_documentreference.html)

### Update to query documents example ###

**Affects**&nbsp; Access Document

**Description:**

- patient has been added into the returned bundle

**Pages changed:**

- [Documents FHIR examples](access_documents_development_fhir_examples_documents.html)