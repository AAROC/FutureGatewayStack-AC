# FutureGatewayStack-AC

Ansible-Container playbooks for the [FutureGateway](https://github.com/FutureGateway).

# Variables

There are two variable files in `ansible` :

  * `vars.yml` : variables used in templating the container orchestration
  * `vars-fg-stack.yml` : variables used by the `main.yml` playbook which is run by ansible-container.

The former is used to template the containter orchestration and should contain variables related only to the deployment. For the deployment and configuration of the services, see the latter. This is loaded int the `stack` variable. 

# Containers and volumes

This builds three containers and one data volume. See `container.yml` for more information

  1. [![Docker Repository on Quay](https://quay.io/repository/aaroc/futuregatewaystack-ac-db/status "Docker Repository on Quay")](https://quay.io/repository/aaroc/futuregatewaystack-ac-db) `db` : The database container.
  1.  [![Docker Repository on Quay](https://quay.io/repository/aaroc/futuregatewaystack-ac-fgapiserver/status "Docker Repository on Quay")](https://quay.io/repository/aaroc/futuregatewaystack-ac-fgapiserver) `fgapiserver` : API server container.
  1. `db-data` : Derives from alpine, merely contains the persistent db volume.

# Building and running the containers

See the [Ansble Container documentation](https://docs.ansible.com/ansible-container/reference/index.html)

  * Building the containers: `ansible-container --var-file=vars.yml build`
  * Running the application : `ansible-container --var-file=vars.yml run -d` will start the applications and run them in background (detached) mode.

# Pushing images

We define two registries - docker hub and quay; quay is preferred.

To push the built images :

`ansible-container --var-file=vars.yml push --push-to=quay`
