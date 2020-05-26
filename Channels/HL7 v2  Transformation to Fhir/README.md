# fhir-integration-channels
  This channel is a tool for generating Converting HL7 messages into Fhir Transaction Bundle resource. These channel requires HL7 message format as templateid in custom metadata and HL7 message as input. To generate fhir resource , send a template id  to this channel with the following format:

template_id : [messageType]_[eventType]
Ex:  template_id : ADT_A01

  The channel will return Fhir resource in response. You can view this response within Mirth by selecting the source connector for a 
message and clicking the Response radio button.

  The channel contains second destination to send the generated fhir resource to fhir server. For This you have to import another channel Fhir R4 Server Resource Sender Channel present in the same repository.and this channel required fhir base url and Authorization token in custom metadata. 
 
Ex: fhir_base_url : https://fhir-api-r4.collabkare.com/collabkare10/data
    token : eyJhbGciOiJIUzI1NiIsImprdSI6Imh0dHBzOi8vdWFhLmNvbGxhYmthcmUuY29tL3VhYS90b2tlbl9rZXlzIiwia2lkIjoibGVnYWN5LXRva2VuLWtleSIsInR5cCI6IkpXVCJ9


  The second channel will return Fhir server output in response. You can view this response within Mirth by selecting the source connector for a message and clicking the Response radio button.


The currently supported Template id's with its event type.:

ADT_A01 - Admit / visit notification
ADT_A02 - Transfer a patient
ADT_A03 - Discharge/end visit
ADT_A04 - Register a patient
ADT_A05 - Pre-admit a patient
ADT_A06 - Change an outpatient to an inpatient
ADT_A07 - Change an inpatient to an outpatient
ADT_A08 - Update patient information
ADT_A13 - Cancel discharge / end visit
ADT_A14 - Pending admit
ADT_A28 - Add person information

SIU_S12 - Notification of new appointment booking
SIU_S13 - Notification of appointment rescheduling
SIU_S14 - Notification of appointment modification
SIU_S15 - Notification of appointment cancellation
SIU_S26 - Notification that patient did not show up for scheduled appointment

SRM_S01 - Request new appointment booking
SRM_S02 - Request appointment rescheduling
SRM_S03 - Request appointment modification
SRM_S04 - Request appointment deletion

MDM_T01 - Original document notification
MDM_T02 - Original document notification and content

ORU_R01 - Observation Message

ORM_O01 - Order Message

