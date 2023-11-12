# Delete

The `delete` operation allows you to specify resources that should be deleted from the Kubernetes cluster before a particular test step is executed.

The full structure of the `Delete` is documented [here](../../apis/chainsaw.v1alpha1.md#chainsaw-kyverno-io-v1alpha1-Delete).

## Usage in `Test`

Below is an example of using `delete` in a `Test` resource.

!!! example

    ```yaml
    apiVersion: chainsaw.kyverno.io/v1alpha1
    kind: Test
    metadata:
      name: example
    spec:
      steps:
      - try:
        # ...
        - delete:
            apiVersion: v1
            kind: Pod
            namespace: default
            name: my-test-pod
        # ...
    ```

## Usage in `TestStep`

Below is an example of using `delete` in a `TestStep` resource.

!!! example

    ```yaml
    apiVersion: chainsaw.kyverno.io/v1alpha1
    kind: TestStep
    metadata:
      name: example
    spec:
      try:
      # ...
      - delete:
          apiVersion: v1
          kind: Pod
          namespace: default
          name: my-test-pod
      # ...
    ```