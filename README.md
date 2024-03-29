# Kubernetes `kubectl` Output Formatting Guide

Understanding how to format the output of `kubectl` commands can significantly improve your productivity and insights when working with Kubernetes. By default, `kubectl` commands return information in a human-readable plain-text format. However, you can customize this output format to better suit your needs using the `-o` (output) flag.

## Using the `-o` Flag

The `-o` flag allows you to specify the format of the command's output. Here's the general usage pattern:

```bash
kubectl [command] [TYPE] [NAME] -o <output_format>


Here are some of the commonly used formats:

-o jsonOutput a JSON formatted API object.

-o namePrint only the resource name and nothing else.

-o wideOutput in the plain-text format with any additional information.

-o yamlOutput a YAML formatted API object.

Here are some useful examples:

#Output with JSON format:

master $ kubectl create namespace test-123 --dry-run -o json
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-123",
        "creationTimestamp": null
    },
    "spec": {},
    "status": {}
}


#Output with YAML format:

master $ kubectl create namespace test-123 --dry-run -o yaml
apiVersion: v1
kind: Namespace
metadata:
  creationTimestamp: null
  name: test-123
spec: {}
status: {}


Output with wide (additional details):

Probably the most common format used to print additional details about the object:

master $ kubectl get pods -o wide

|   Name   | READY    | STATUS   | RESTARTS  | AGE   | IP       | NODE  | 
|----------|----------|----------|-----------|-------|----------|-------|
| busybox  | 1/1      | Running  |   0       |  3m39s| 10.36.0.2| node01| 
| ningx    | 1/1      | Running  |   0       |  7m32s| 10.44.0.1| node03|
| redis    | 1/1      | Running  |   0       |  3m59s| 10.36.0.1| node01|


