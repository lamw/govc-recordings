# Community Repository of govc vSphere Inventory Recordings

- [Community Repository of govc vSphere Inventory Recordings](#community-repository-of-govc-vsphere-inventory-recordings)
  - [Description](#description)
  - [Usage](#usage)
  - [Contributions](#contributions)
  - [Recordings](#recordings)

## Description

A collection of VMware Community saved vSphere Inventory Recordings using the [govc](https://github.com/vmware/govmomi/tree/master/govc) utility. For more details, please refer to this [blog post](https://www.virtuallyghetto.com/2021/01/record-and-replay-vsphere-inventory-using-govc-and-vcsim.html).

## Usage

Download or clone this repository and then use the [vcsim](https://github.com/vmware/govmomi/tree/master/vcsim) utility to load a specific recording.

```
$GOPATH/bin/vcsim -load vcsim-vcsa.primp-industries.local
export GOVC_URL=https://user:pass@127.0.0.1:8989/sdk GOVC_SIM_PID=34680
```

## Contributions

To contribute your vSphere Inventory to this repository.

**Step 1** - Run the following command to set your vSphere endpoint

```
export GOVC_URL=https://your-vcenter-hostname-or-ip/sdk
export GOVC_USERNAME=your-vcenter-username
export GOVC_PASSWORD=your-vcenter-password
export GOVC_INSECURE=1
```

**Step 2** - Save your recording, run the govc `object.save` command:

```
$GOPATH/bin/govc object.save

Saved 111 total objects to "vcsim-vcsa.primp-industries.local", including:
ClusterComputeResource: 3
Datastore: 3
DistributedVirtualPortgroup: 4
Folder: 11
HostDatastoreBrowser: 3
HostDatastoreSystem: 2
HostNetworkSystem: 2
HostSystem: 2
HostVirtualNicManager: 2
ResourcePool: 6
Task: 2
VirtualMachine: 20
```

**Step 3** - Create a README.md file inside of the saved vSphere Inventory directory that contains the text output from the `object.save` govc command. See [README.md](vcsim-vcsa.primp-industries.local/README.md) for an example and this will help users understand the inventory configuration

**Step 4** - Create a Github pull request that includes the following:

* i. Saved vSphere Inventory directory

* ii. Update the table below with your contributions

## Recordings

| Submitter     | Date     | Version                                | Directory                                                                                      |
|---------------|----------|----------------------------------------|------------------------------------------------------------------------------------------------|
| William Lam   | 01/02/21 | VMware Cloud on AWS 1.13               | [vcsim-vcenter.sddc-35-167-62-16.vmwarevmc.com](vcsim-vcenter.sddc-35-167-62-16.vmwarevmc.com) |
| William Lam   | 01/02/21 | vSphere 7.0 Update 1c (Build 17327586) | [vcsim-vcsa.primp-industries.local](vcsim-vcsa.primp-industries.local)                         |
| Timo Sugliani | 01/06/21 | vSphere 6.7 Update 3  (Build 17138064) | [vcsim-vc01.rax.lab](vcsim-vc01.rax.lab)                                                       |
| Romain Decker | 01/07/21 | vSphere 7.0 Update 1c (Build 17327586) | [vcsim-vcsa01-z67.sddc.lab](vcsim-vcsa01-z67.sddc.lab)                                         |
