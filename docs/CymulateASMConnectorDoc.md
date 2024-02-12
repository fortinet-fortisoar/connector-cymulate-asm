## About the connector
The Cymulate Exposure Management and Security Validation Platform provides the technology for exposure
discovery, validation, and prioritization with business insights and intelligence. This simplifies security leaders’ risk
and resilience to emergent threats and a rapidly changing attack surface. With a complete view of the security
posture and business risks, the Cymulate platform gives security leaders the data they need to define the scope for cyber initiatives, successfully mobilize mitigations, and continuously assess security operations performance. 
<p>This document provides information about the Cymulate ASM Connector, which facilitates automated interactions, with a Cymulate ASM server using FortiSOAR&trade; playbooks. Add the Cymulate ASM Connector as a step in FortiSOAR&trade; playbooks and perform automated operations with Cymulate ASM.</p>

### Version information

Connector Version: 1.0.0


Authored By: Fortinet

Certified: No
## Installing the connector
<p>Use the <strong>Content Hub</strong> to install the connector. For the detailed procedure to install a connector, click <a href="https://docs.fortinet.com/document/fortisoar/0.0.0/installing-a-connector/1/installing-a-connector" target="_top">here</a>.</p><p>You can also use the <code>yum</code> command as a root user to install the connector:</p>
<pre>yum install cyops-connector-cymulate-asm</pre>

## Prerequisites to configuring the connector
- You must have the credentials of Cymulate ASM server to which you will connect and perform automated operations.
- The FortiSOAR&trade; server should have outbound connectivity to port 443 on the Cymulate ASM server.

## Minimum Permissions Required
- Not applicable

## Configuring the connector
For the procedure to configure a connector, click [here](https://docs.fortinet.com/document/fortisoar/0.0.0/configuring-a-connector/1/configuring-a-connector)
### Configuration parameters
<p>In FortiSOAR&trade;, on the Connectors page, click the <strong>Cymulate ASM</strong> connector row (if you are in the <strong>Grid</strong> view on the Connectors page) and in the <strong>Configurations</strong> tab enter the required configuration details:</p>
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Server URL</td><td>Specify the Cymulate server URL to connect and perform the automated operations.
</td>
</tr><tr><td>Secret Key</td><td>Specify the Secret Key of the API Application already created in the Cymulate Server.
</td>
</tr><tr><td>Verify SSL</td><td>Specifies whether the SSL certificate for the server is to be verified or not. <br/>By default, this option is set to True.</td></tr>
</tbody></table>

## Actions supported by the connector
The following automated operations can be included in playbooks and you can also use the annotations to access operations:
<table border=1><thead><tr><th>Function</th><th>Description</th><th>Annotation and Category</th></tr></thead><tbody><tr><td>Create Internal Assessment</td><td>Create a specific Internal ASM assessment in Cymulate ASM.</td><td>create_internal_assessment <br/>Investigation</td></tr>
<tr><td>Get Assessment List</td><td>Retrieve the ASM assessment history within the date range provided. If a date range is not provided, the response will retrieve the history from the last 30 days.</td><td>get_assessment_list <br/>Investigation</td></tr>
<tr><td>Get Findings List For Latest Assessment</td><td>Retrieve all findings generated in the latest ASM assessment from Cymulate ASM.</td><td>get_findings_list_for_latest_assessment <br/>Investigation</td></tr>
<tr><td>Get Findings List By Assessment ID</td><td>Retrieve all findings generated in a specific ASM assessment from Cymulate ASM.</td><td>get_findings_list_by_assessment_id <br/>Investigation</td></tr>
<tr><td>Get Assets List For Latest Assessment</td><td>Retrieve a list of assets from the latest assessment from Cymulate ASM.</td><td>get_assets_list_for_latest_assessment <br/>Investigation</td></tr>
<tr><td>Get Assets List By Assessment ID</td><td>Retrieve a list of assets for a specific assessment from Cymulate ASM.</td><td>get_assets_list_by_assessment_id <br/>Investigation</td></tr>
<tr><td>Get Internal Assessment List</td><td>Retrieve Internal ASM assessments from Cymulate ASM.</td><td>get_internal_assessment_list <br/>Investigation</td></tr>
<tr><td>Get Internal Assessment By ID</td><td>Retrieve a specific Internal ASM assessment from Cymulate ASM.</td><td>get_internal_assessment_by_id <br/>Investigation</td></tr>
<tr><td>Delete Internal Assessment By ID</td><td>Delete a specific Internal ASM assessment from Cymulate ASM.</td><td>delete_internal_assessment_by_id <br/>Investigation</td></tr>
</tbody></table>

### operation: Create Internal Assessment
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Assessment Name</td><td>Specify the name of the assessment.
</td></tr><tr><td>Assessment Description</td><td>Specify the description of the assessment.
</td></tr><tr><td>Agent Name</td><td>Specify the agent name.
</td></tr><tr><td>Profile Name</td><td>Specify the profile name.
</td></tr><tr><td>Platforms</td><td>Specify the platforms for example Azure, Active Directory, AWS, GCP you can specify multiple platforms as comma-separated values.
</td></tr><tr><td>Crown Jewels</td><td>Specify the crown jewels (Important resources on which to create assessment).
</td></tr><tr><td>Schedule For</td><td>(Optional) Specify the time at which assessment should be triggered.
</td></tr><tr><td>Schedule Loop</td><td>Specify the frequency for triggering the assessment eg: one-time.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Get Assessment List
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>From Date</td><td>(Optional) Specify the date from where to fetch assessments.
</td></tr><tr><td>To Date</td><td>(Optional) Specify the date until which assessments should be fetched.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Get Findings List For Latest Assessment
#### Input parameters
None.
#### Output

 The output contains a non-dictionary value.
### operation: Get Findings List By Assessment ID
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Assessment ID</td><td>Specify the assessment ID to fetch its findings.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Get Assets List For Latest Assessment
#### Input parameters
None.
#### Output

 The output contains a non-dictionary value.
### operation: Get Assets List By Assessment ID
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Assessment ID</td><td>Specify the assessment ID to fetch its assets.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Get Internal Assessment List
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Offset</td><td>Specify the number of records to skip.
</td></tr><tr><td>Limit</td><td>Specify the limit of how many items to get (min - 1000, max - 10000) - Default = 100.
</td></tr></tbody></table>
#### Output

 The output contains a non-dictionary value.
### operation: Get Internal Assessment By ID
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Assessment ID</td><td>Specify the assessment ID for which you want to fetch the details from Cymulate ASM.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Delete Internal Assessment By ID
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Assessment ID</td><td>Specify the assessment ID which you want to delete from Cymulate ASM.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
## Included playbooks
The `Sample - cymulate-asm - 1.0.0` playbook collection comes bundled with the Cymulate ASM connector. These playbooks contain steps using which you can perform all supported actions. You can see bundled playbooks in the **Automation** > **Playbooks** section in FortiSOAR&trade; after importing the Cymulate ASM connector.

- Create Internal Assessment
- Delete Internal Assessment By ID
- Get Assessment List
- Get Assets List By Assessment ID
- Get Assets List For Latest Assessment
- Get Findings List By Assessment ID
- Get Findings List For Latest Assessment
- Get Internal Assessment By ID
- Get Internal Assessment List

**Note**: If you are planning to use any of the sample playbooks in your environment, ensure that you clone those playbooks and move them to a different collection since the sample playbook collection gets deleted during connector upgrade and delete.
