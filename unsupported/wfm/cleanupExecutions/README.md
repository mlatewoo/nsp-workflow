![NOKIA](https://raw.githubusercontent.com/nokia/nsp-workflow/master/logo.png)
# Nokia NSP Workflow Manager Blueprints
## Workflow Manager - Cleanup Executions

### Description
This workflow will remove execution results from the Workflow Manager. The execution results for deletion are selected based on the created_at attribute.

### Version
WFM Cleanup Executions - version 1.0

### Support level
Unsupported, use at your own risk!

### History
|Version|Author|Date      |Comments     |
|-------|------|----------|-------------|
|   1.0 |  ML  |2019-01-28|first version|

### Prerequisites
Nokia NSP with Workflow Manager

### Tested with
* Nokia NSP 18.12

### Installation
Download the workflow and then use the Workflow Manager workflow Import functionality to import the workflow into your WFM instance.

### Usage
The workflow can be initiated either via the WFM GUI or via the workflow management REST API The following parameters must be supplied

```
   "token_auth": The REST API Bearer token e.g. "YWRtaW46Tm9raWFOc3AxIQ=="
   "rest_gateway_host":  The IP address of the NSP REST gateway e.g.  "1.2.3.4"
   "fromDate": The date string used to selected the executions to delete in YYYY-MM-DD HH:MM:SS format e.g. "2018-11-12%2021:10:03"
   "workFlowName": The workflow to delete executiions for e.g. "telemetryTest"
   "function": Delete partial or full executions e.g. "partial"
```
Additionally, the workflow may be initiated via the workflow management REST API

```
POST /wfm/api/v1/execution HTTP/1.1

{
    "workflow_id": "b0ceb995-b126-4798-b1e6-82db9bcfc9f7",
    "input": {
        "token_auth": "YWRtaW46Tm9raWFOc3AxIQ==",
        "rest_gateway_host": "1.2.3.4",
        "fromDate": "2018-11-12%2021:10:03",
        "workFlowName": "telemetryTest",
        "function": "partial"
    },
    "params": {},
    "output": {}
}
```
### License
This project is licensed under the BSD-3 Clause License. See
[LICENSE.md](https://raw.githubusercontent.com/nokia/nsp-workflow/master/LICENSE.md) file for details.
