---
title: Events
keywords: usecase, structured
tags: [usecase, structured] 
sidebar: accessrecord_structured_sidebar
permalink: accessrecord_usecase_3.28.html
summary: "Use case for events"
---

**Use Case Name:**

A professional user of the Local Care Record ('Care professional') needs to review a patient's GP Practice information relating to Events:

  - details of Encounters
  - details of Referrals
  - details of Admissions

**Brief description:**

A patient is admitted to hospital and the clinician responsible for the care of that patient in the hospital needs to review their care history, recorded encounters, referrals and admissions from the GP Practice Clinical System, to assist in determining the appropriate care provision and support. They have access to the Local Care Record (LCR), which shares clinical information relevant to the direct care of their patient from a variety of local hospital, community and GP organisations.

**Use case justification:**

Currently, when a Patient's record is viewed in the LCR, their encounters, referrals and admissions from the GP Practice Clinical System are presented as a static HTML view from a 3<sup>rd</sup>-party supplier, which is rigid and not in keeping with the needs of professionals, the design of the system's UI, nor is it the preferred strategy for sharing of patient information within the LCR landscape. Electronically consuming the FHIR-compliant profiles for a patient's encounters, referrals and admissions from their GP Practice Clinical System will allow the LCR to:

  - share this data in a manner which is congruent and consistent with all other care partners
  - present the data in a manner which is appropriate for the care setting
  - share more relevant data, pertinent to the role of the professional involved and improve care delivery
  - present the data in a uniform and streamlined interface
  - provider a higher quality user experience
  - provide a higher fidelity audit record

**Primary Actors:**

- care professionals
- clinicians
- LCR Subsystem

**Secondary actors:**

- patient

**Triggers:**

- at the point of direct care, during a consultation or care delivery setting, the professional / clinician is discussing the medical history with their Patient.

**Pre-Conditions:**

  - patient has been admitted onto the Hospital's Patient Administration System (PAS) and has gone through identification including retrieving their NHS Number
  - the Clinician has been advised by the local Hospital's system that their patient has information available within the LCR
  - the Clinician is logged into, and has a valid session with, the LCR
  - the Clinician has relevant access and permission to view the patient's details in the LCR
  - the patient has been registered within the GP Practice Clinical System and has data available for sharing with other clinical systems
    N.B. If no such data is available, it will not be possible to initiate the basic flow
  - the GP Practice Clinical System exists within the Spine Security Proxy (SSP)

**Post conditions:**

  - **On Success:**
    
      - the patient's recorded encounters, referrals and admissions are taken from the GP Practice Clinical System and presented in the LCR

  - **Guaranteed:**
    
      - access and data returned is recorded for auditing purposes

**Basic flow with alternative and exception flows:**

<table>
<thead>
<tr class="header">
<th width="10%"><strong>Step</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>Step 1</td>
<td>Clinician requests the 'Encounters, Referrals and Admissions' for the Patient using the LCR interface.</td>
</tr>
<tr class="odd">
<td>Step 2</td>
<td>The LCR identifies the Patient's GP Practice end point using PDS/SDS lookup</td>
</tr>
<tr class="even">
<td>Step 3</td>
<td>The LCR requests the Patient's 'Encounters Referrals and Admissions' from their registered GP Practice.</td>
</tr>
<tr class="odd">
<td>Step 4</td>
<td>Spine Security Proxy (SSP) checks organisation to organisation sharing agreement exists between requesting organisation (LCR) and the Patients registered GP Practice, and that the interaction (for example,  Get Encounters Referrals and Admissions) is part of the sharing agreement</td>
</tr>
<tr class="even">
<td>Step 5</td>
<td>GP Practice Clinical System checks Patient permissions and consent to share</td>
</tr>
<tr class="odd">
<td>Step 6</td>
<td>The LCR receives the 'Encounters, Referrals and Admissions' via the GP Connect service and presents the results to the Clinician within the LCR user interface (UI).
<p>The following information is returned and presented in the LCR UI, as a minimum, for all Encounters and Admissions:</p>
<ul>
<li><p>Brief Summary of the Encounter/Admission</p></li>
<li><p>Status of the Encounter/Admission (for example,  planned/in-progress/finished)</p></li>
<li><p>Type of Encounter/Admission (for example,  inpatient/outpatient/ambulatory)</p></li>
<li><p>Urgency of the Encounter/Admission</p></li>
<li><p>Related Referral information, if available</p></li>
<li><p>Clinician(s) involved</p></li>
<li><p>Start and end time</p></li>
<li><p>Reason for the Encounter/Admission</p></li>
<li><p>Related Diagnosis information, if available</p></li>
<li><p>Any related hospital information, if available.</p></li>
</ul>
<p>The following information is returned and presented in the LCR UI, as a minimum, for all Referrals:</p>
<ul>
<li><p>Summary of the Referral</p></li>
<li><p>Status of the Referral (for example,  active/suspended/cancelled)</p></li>
<li><p>Type of Referral</p></li>
<li><p>Urgency of the Referral</p></li>
<li><p>Originating Encounter/Admission (if available)</p></li>
<li><p>Service requested</p></li>
<li><p>Proposed date and time for service</p></li>
<li><p>Requestor of the service</p></li>
<li><p>The clinical speciality that the Referral is requested for</p></li>
<li><p>Reason for Referral</p></li>
<li><p>Additional supporting information</p></li>
<li><p>Comments and notes relating to the Referral</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Step 7</td>
<td>The Clinician then reviews the information presented and determines the best course of action in response to the information. This may involve requesting additional data sets from GP Connect to supplement the data already presented within this list.</td>
</tr>
<tr class="odd">
<td><b>Exceptions</b></td>
<td></td>
</tr>
<tr class="even">
<td>Step 4a</td>
<td>SSP sharing agreement between 'to' organisation and 'from' organisation doesn't exist.</td>
</tr>
<tr class="odd">
<td>Step 4b</td>
<td>Exception is reported in LCR user interface; user is directed to contact local Service Desk for resolution.</td>
</tr>
<tr class="even">
<td>Step 5a</td>
<td>The patient has not consented to the sharing of medical data from the GP Practice.</td>
</tr>
<tr class="odd">
<td>Step 5b</td>
<td>Exception is reported in the LCR user interface.</td>
</tr>
<tr class="even">
<td>Step 6a</td>
<td>A logic or integration exception occurs in the retrieval of data</td>
</tr>
<tr class="odd">
<td>Step 6b</td>
<td>Exception is reported in the LCR user interface and is logged within the LCR's exception tracing database; user is directed to contact local Service Desk for resolution.</td>
</tr>
</tbody>
</table>

**Use Case Diagram:**