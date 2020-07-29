#Introduction
This example demonstrates the applicability of the the following user guides in an simple use case.
<ul>
<li> Coverage Requirements discovery (CRD)</li>
<li> Document Templates and Rules(DTR)</li>
<li> Prior Authorization Support(PAS) </li>
</ul>

For the purpose of demonstration, the [guidelines](UHC-Cardiology.pdf) published by United Health Care to physicians in 2018 have been taken as reference.

It should be noted that these are for demonstration purposes only and should not be used in production.

United Health Care neither approved nor endorsed these guidelines. These are taken from publicly available content over internet and the publisher of this document is not responsible for the accuracy of the contents of this document.

The sections below describe various files available in this example. 

## Order sign CDS Hook invocation
The file  [Order Sign Input](Order-sign-Input.json) gives an example of how an order sign CDS hook is invoked from the EHR workflow.
It contacts the payer to check if prior authorization or additional documentation is necessary to perform a Stress Echo cardiogram with a CPT code of 93350.
The payer system returns back a CARD with information about the prior authorization and also the information about the Questionnaire template to be filled in.

## Questionnaire Information
The file [Stress Echo Cardiogram questionnaire](StressEchoCardiography.json) gives the information about the questionnaire to be filled in when submitting the prior authorization request.
This questionnaire will have reference to a library of CQL files that would help in prepopulating this questionnaire when being executed through a smart app or a native application

## Library File

The file [Library Stress Echo Cardiogram](Library-StressEchoCardiography.json) has references to CQL file to prepopulate and also the datarequirements to execute in case the CQL executor does not have access to EHR FHIR resources.

## CQL files

The files [StressEchoCardiography.cql](StressEchoCardiography.cql) and [StressEchoCommon.cql](StressEchoCommon.cql) has the logic to prepopulate the questionnaires and also gather the information needed by the payer.

## Example data in EHR

Example of data generated by extracting it from EHR, filling the questionnaire is given as [PASExample.json](PASExample.json)
This is submitted to the Claim/$submit operation in the PAS Endpoint.

## X12 files

As there are license requirements in using X12, the X12 278 request generated by the intermediary and X12 278 response generated by the payer are not included.

If you already comply with X12 licensing agreements, please send an email to sreekanth.puram@mettles.com to get access to the X12 files associated with this example.


