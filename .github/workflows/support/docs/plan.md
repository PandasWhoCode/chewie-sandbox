# Sandbox Plan for Workflows

## Overview

The purpose of this document is to describe how the workflow 801-read-chewie-response.yaml
should be modified in order to make initial requests to chewie and to provide the calling
workflow with data from the outputs.

This workflow shouldn't change much - other than in name:

```yaml
name: "801: [CITR] Read Chewie Response"
```

Becomes

```yaml
name: "801: [CITR] Read Chewie Configuration Response"
```

We also need to add a new workflow to actually trigger chewie. This will be ```856-trigger-chewie.yaml``` and will be 
responsible for taking in the shape and timeout data necessary to trigger a chewie call, wait for response, and then pass
the responses back to the calling workflow.

`go-run-test.yaml` is the controller that will make calls to chewie both for the pre-configured calls and the over-the-network calls.
