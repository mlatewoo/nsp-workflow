![NOKIA](https://raw.githubusercontent.com/nokia/nsp-workflow/master/logo.png)
# Nokia NSP Workflow Manager Blueprints
## MDC - Port Move 7x50

### Description

### Version
MDC Port Move 7x50 - version 1.0

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
* 7750 SR running SR OS 16.0.R4 (MD MODE)
* mdm-device-model-sros-16-0-r4/1.0.0.rel_10

### Installation
Download the workflow and then use the Workflow Manager workflow Import functionality to import the workflow into your WFM instance.

### Usage
The workflow can be initiated either via the WFM GUI or via the workflow management REST API The following parameters must be supplied

```
   "token_auth": The REST API Bearer token e.g. "YWRtaW46Tm9raWFOc3AxIQ=="
   "rest_gateway_host":  The IP address of the NSP REST gateway e.g.  "135.121.148.173"
   "ne1": The system address of the target node e.g. "92.168.96.39"
   "port1": The source port to copy e.g. "1/1/4"
   "port2": The destination port e.g. "1/1/2"
```

Additionally, the workflow may be initiated via the workflow management REST API

```
POST /wfm/api/v1/execution HTTP/1.1

{
    "workflow_id": "b0ceb995-b126-4798-b1e6-82db9bcfc9f7",
    "input": {
        "token_auth": "YWRtaW46Tm9raWFOc3AxIQ==",
        "rest_gateway_host": "135.121.148.173",
        "ne1": "92.168.96.39",
        "port1": "1/1/2",
        "port2": "1/1/4"
    },
    "params": {},
    "output": {}
}
```

### License
This project is licensed under the BSD-3 Clause License. See
[LICENSE.md](https://raw.githubusercontent.com/nokia/nsp-workflow/master/LICENSE.md) file for details.
