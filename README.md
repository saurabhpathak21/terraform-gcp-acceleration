Compute Instance
This module is used to create compute instances (and only compute instances) using google_compute_instance_from_template, with no instance groups.

Usage
See the simple for a usage example.

Testing
Inputs
Name	Description	Type	Default	Required
access_config	Access configurations, i.e. IPs via which the VM instance can be accessed via the Internet.	
list(object({
    nat_ip       = string
    network_tier = string
  }))
[]	no
add_hostname_suffix	Adds a suffix to the hostname	bool	true	no
alias_ip_ranges	(Optional) An array of alias IP ranges for this network interface. Can only be specified for network interfaces on subnet-mode networks.	
list(object({
    ip_cidr_range         = string
    subnetwork_range_name = string
  }))
[]	no
deletion_protection	Enable deletion protection on this instance. Note: you must disable deletion protection before removing the resource, or the instance cannot be deleted and the Terraform run will not complete successfully.	bool	false	no
hostname	Hostname of instances	string	""	no
hostname_suffix_separator	Separator character to compose hostname when add_hostname_suffix is set to true.	string	"-"	no
instance_template	Instance template self_link used to create compute instances	string	n/a	yes
ipv6_access_config	IPv6 access configurations. Currently a max of 1 IPv6 access configuration is supported. If not specified, the instance will have no external IPv6 Internet access.	
list(object({
    network_tier = string
  }))
[]	no
network	Network to deploy to. Only one of network or subnetwork should be specified.	string	""	no
num_instances	Number of instances to create. This value is ignored if static_ips is provided.	number	"1"	no
region	Region where the instances should be created.	string	null	no
resource_policies	(Optional) A list of short names or self_links of resource policies to attach to the instance. Modifying this list will cause the instance to recreate. Currently a max of 1 resource policy is supported.	list(string)	[]	no
static_ips	List of static IPs for VM instances	list(string)	[]	no
subnetwork	Subnet to deploy to. Only one of network or subnetwork should be specified.	string	""	no
subnetwork_project	The project that subnetwork belongs to	string	""	no
zone	Zone where the instances should be created. If not specified, instances will be spread across available zones in the region.	string	null	no
Outputs
Name	Description
available_zones	List of available zones in region
instances_details	List of all details for compute instances
instances_self_links	List of self-links for compute instances