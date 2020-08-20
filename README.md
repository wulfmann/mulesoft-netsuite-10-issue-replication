# Mule Netsuite 10.0.1 Connector Search Issue Replication

This repo has an example project that shows an issue with the `10.0.x` Netsuite Connector.

This is a freshly created project from anypoint studio.

- Anypoint Studio Version: 7.6
- Mule Runtime Version: 4.3.0 EE

The code comes from [this mulesoft article](https://docs.mulesoft.com/netsuite-connector/10.0/netsuite-examples#customer-advanced-search).

## The error:

```text
Element               : ns-searchFlow/processors/0 @ ns-search:ns-search.xml:19 (Transform Message)
Element DSL           : <ee:transform doc:name="Transform Message" doc:id="46e4669e-a938-496b-badd-1bfb40016706">
<ee:message>
<ee:set-payload>%dw 2.0
output application/java
---
{
	columns: {
		basic: {
			dateCreated: [{
				customLabel: "Created"
			}],
			entityId: [{
				customLabel: "Entity Id"
			}],
			stage: [{
				customLabel: "Stage"
			}]
		}
	},
} as Object {
	class : "org.mule.module.netsuite.extension.api.CustomerSearchAdvanced"
}</ee:set-payload>
</ee:message>
</ee:transform>
Error type            : MULE:EXPRESSION
FlowStack             : at ns-searchFlow(ns-searchFlow/processors/0 @ ns-search:ns-search.xml:19 (Transform Message))

  (set debug level logging or '-Dmule.verbose.exceptions=true' for everything)
********************************************************************************
```

This issue is not present in `9.x` Netsuite Connector Versions.

## Setup

Make sure you add your netsuite token credentials to the `src/main/resources/application-dev.properties` file.

