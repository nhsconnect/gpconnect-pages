---
title: Foundations release notes
keywords: foundations, release notes
tags: []
sidebar: foundations_sidebar
permalink: foundations_release_notes.html
summary: "Release notes for the various versions of the Foundations capability"
---

#### 1.0.0-rc.3 (Released: 06/10/2017)
- *Register a patient* - Additional fields in patient profile which are marked with Must-Support flag 
- [Foundations Design](foundations_design.html#definition-of-organisation-and-location-entities) - Added design decision to clarify how GP practice organisations and practice sites are represented in the FHIR Organization and Location resources
- *Foundation Resources*, *Register a patient* - Changed "Register a patient" response to use "gpconnect-searchset-bundle-1" profiled bundle resource rather than the "gpconnect-registerpatient-bundle-1" profiled bundle resource
- *Register a Patient* - registrationStatus extension element has been removed. Active status can be indicated through Patient.active element
- *Find a patient*, *Read a patient*, *Register a patient* - Update patient resource examples to conform to structured definition
- *Find a Location* - the API Use Case for "Find a Location" has been removed from the specification
- *Register a patient* - Added guidance on Register patient around consumer providing and storage expectations for patient telecom and address information

#### 1.0.0-rc.2 (Released: 08/09/2017)
- updated the system identifier URIs for Patient (https://fhir.nhs.uk/Id/nhs-number), Practitioner (https://fhir.nhs.uk/Id/sds-user-id), Organization (https://fhir.nhs.uk/Id/ods-organization-code) and Location (https://fhir.nhs.uk/Id/ods-site-code), this affects all the "Find" foundation API Use Cases. (Pages - development_fhir_operation_guidance.html, foundations_design.html, foundations_use_case_find_a_patient.html, foundations_use_case_find_a_practitioner.html, foundations_use_case_find_an_organisation.html, foundations_use_case_find_a_location.html)
- *Read Organization*, [Conformance Profile](foundations_use_case_get_the_fhir_conformance_profile.html), *Read Location*, *Register Patient* - Updated examples to conform to Care Connect profile uplifts
- [Glossary](overview_glossary.html#active-patient) - updated glossary to make definition of Active Patient clear, used in *Find a Patient* API Use Case
- *Register Patient* - Updated register patient example response to include the registration details extension

#### 1.0.0-rc.1 (Released: 01/09/2017)
- updated datalibrary to be capability specific, moving it to reside under the "Development" menu within the capability. This is to allow the Profiled FHIR Resources to be referenced per capability and updated independently. For foundations we have updated specification to reference FHIR profiles stored on FHIR reference server rather than those on the old DMS capability pack
- updated Api Use Case pages to make clear the expectations around the Fhir Resource Metadata Profile element, along with updates to examples to show new profile definitions
- added information around what GP Connect considers as an Active Patient and use of Active Patient within the "Find a patient" capability (Page - foundations_use_case_find_a_patient.html, overview_glossary.html)
- added additional information for "Register Patient" capability around re-activating inactive patients instead of registering new patient each time. (Page - foundations_use_case_register_a_patient.html)
- removed the Practitioner and Organization as mandatory resources within the response bundle for the "Register Patient" interaction (Page - foundations_use_case_register_a_patient.html)
- added clarification around the use of the "registrationDetails" extension for the "Register patient" interaction (Page - foundations_use_case_register_a_patient.html)
- removed ODS-Site-Code as a search parameter and identifier from the Organization resource for "Find Organization" and "Organization Read"

#### 1.0.0-beta.2 (Released: 11/08/2017)
- updated example conformance profile to include GP Connect profile information (Page - [Get the FHIR Conformance Statement](foundations_use_case_get_the_fhir_conformance_profile.html))
- clarified use of *Register a patient* API is only to support local-only temporary patient registrations to support federated appointment booking
- added additional clarification around use of identifiers for all foundation search capabilities (Pages - Find a practitioner, Find a patient, Find an organisation, Find a location)
- clarity on mandatory data items for *Register a patient* API
- moved VRead to out of scope (Pages - [Get the FHIR Conformance Statement, Common API Guidance](foundations_use_case_get_the_fhir_conformance_profile.html))
- added java example code to specification for Read capabilities (Pages - Read a practitioner, Read a patient, Read an organisation, Read a location)
- updated example code to bring in line with [FHIR Server Root URL format](development_fhir_api_guidance.html#fhir-api-versioning) guidance
- updates to *Register a patient* to include latest operation definition XML, and provide clarity on profiles used on response

#### 1.0.0-beta.1
- initial release of the Foundations capability pack on GitHub in early August 2016
  
#### 1.0.0-alpha.1
- initial release for feedback/comments as part of the late May 2016 release