# Capture-K8s 🚀

Capture-K8s is a tool to capture details and logs from Kubernetes clusters. 

It can capture information about specified resources and logs from pods within specific namespaces and provides a flexible configuration file.

The ouput from capture-k8s tool is stored in current directory as folder with name `capture-TIMESTAMP`



#### TOC

- [Usage ✨](#usage-✨)
- [Options 🛠️](#options-🛠️)
- [Examples 🌐](#examples-🌐)
- [Installation 🚚](#installation-🚚)
- [Default Configuration ⚙️](#default-configuration-⚙️)
- [Custom config 🔧✨](#🔧✨)



## Usage ✨

Run the `capture.sh` script to capture Kubernetes resources and logs.

```bash
capture-k8s [OPTIONS] [NAMESPACE1 NAMESPACE2 ...]
```

### Options 🛠️

- `-h, --help`: Display help information.
- `-f, --config FILE`: Specify the configuration file (default: config.yaml).
- `--kubeconfig FILE`: Specify the kubeconfig file for fetching logs.
- `--log-all-pods`: Override logAllPods from config.yaml and capture logs for all pods.

### Examples 🌐

1. Capture resources and logs based on the default configuration:

   ```bash
   capture-k8s
   ```

2. Capture resources and logs using a custom configuration file:

   ```bash
   capture-k8s -f custom-config.yaml
   ```

3. Capture resources and logs for specific namespaces:

   ```bash
   capture-k8s namespace1 namespace2
   ```

4. Override logAllPods from the configuration and capture logs for all pods:

   ```bash
   capture-k8s --log-all-pods
   ```

For more information, use the `-h` or `--help` option:

```bash
capture-k8s -h
```



## Installation 🚚

1. Clone the repository:

   ```bash
   git clone https://github.com/parthyadav3105/capture-k8s.git
   ```

2. Navigate to the tool directory:

   ```bash
   cd capture-k8s
   ```

3. Make the script executable:

   ```bash
   chmod +x capture-k8s
   ```



## Default Configuration ⚙️

The tool uses a configuration file (`config.yaml` or `-f myconf.yaml`) to specify the namespaces, resources, log selectors, and other options. If `config.yaml` does not exists then the default configuration used is as follows:

```yaml
namespaces:
  - default

resources:
  - configmaps
  - nodes
  - pvc
  - pv
  - pods
  - secrets
  - services
  - crds
  - daemonsets
  - deployments
  - replicasets
  - statefulsets
  - cronjobs
  - jobs
  - ingresses
  - networkpolicies
  - clusterrolebindings
  - clusterroles
  - rolebindings
  - roles
  - storageclasses
  - volumeattachments

logAllPods: true
```

#### 🔧✨

You can customize the configuration file based on your requirements and pass using flag `-f` or `--config`. 

