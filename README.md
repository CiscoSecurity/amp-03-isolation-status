[![Gitter chat](https://img.shields.io/badge/gitter-join%20chat-brightgreen.svg)](https://gitter.im/CiscoSecurity/AMP-for-Endpoints "Gitter chat")

### AMP for Endpoint Endpoint Isolation Status:
This collection of scripts have the basic logic for gathering connector GUIDs based on different isolation status. Each script will query [/v1/computers](https://api-docs.amp.cisco.com/api_actions/details?api_action=GET+%2Fv1%2Fcomputers&api_host=api.amp.cisco.com&api_resource=Computer&api_version=v1) endpoint and page through the results. If there are connectors found that meet a given criteria the GUIDs will be written to disk.

- **get_connectors_supporting_isolation.py**
Returns connectors that support isolation meaning that they have a connector installed that supports the endpoint isolation and have a policy with isolation enabled

- **get_connectors_that_can_be_isolated.py**
Returns connectors that support isolation and have a current status of ```not_isolated``` meaning they are not currently isolated, isolation can be started, and they are not in a transitional state

- **get_isolated_connectors.py**
Returns connectors that support isolation and have a current status of ```isolated``` meaning they are currently isolated, isolation can be stopped, and they are not in a transitional state

- **get_connectors_in_transition.py**
Returns connectors that support isolation and have a current status of ```pending_start``` or ```pending_stop``` meaning they are in a transitional state

### Before using you must update the following:
- amp_client_id
- amp_api_key

### Usage:
```
python get_connectors_supporting_isolation.py
```

### Example script output:
```
Connectors found: 13
Connectors found: 11
Total connectors found that support isolation: 24

Writing connector GUIDs to connectors_supporting_isolaiton.txt
```
