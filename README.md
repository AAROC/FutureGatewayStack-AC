# FutureGatewayStack-AC

Ansible-Container playbooks for the [FutureGateway](https://github.com/FutureGateway).


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
