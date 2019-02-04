molecule-example
=========

Example role for testing molecule with docker and the three major cloud providers.

Requirements
============

molecule
------------
Installation instructions for molecule can be found [here](https://molecule.readthedocs.io/en/latest/installation.html)

Docker
------------
* Have docker installed on your local machine and `docker-py` should be installed via `pip`

GCE
------------
* Have a project setup in GCP
* Setup a [service account](https://cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances)
* Export your project id, service account email, and path to credentials as the following env variables `GCE_PROJECT_ID`, `GCE_SERVICE_ACCOUNT_EMAIL`, `GCE_CREDENTIALS_FILE`. These are the environment variables the molecule playbooks will look to for creating and destroying your testing  
* Ensure you have your [SSH key setup for GCE](https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys#project-wide) 

EC2
------------
* Set default region by exporting EC2_REGION (ex: export EC2_REGION=us-west-2)
* Set AMI and Subnet ID in `molecule.yml`

Running Tests
===========

Docker
-----------
`molecule test -s default`

GCE
----------
`molecule test -s gce`

EC2
----------
`molecule test -s aws`
