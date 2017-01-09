# FutureGatewayStack-AC

Ansible-Container playbooks for the [FutureGateway](https://github.com/FutureGateway).


# Containers and volumes

This builds three containers and one data volume. See `container.yml` for more information

  1. [![Docker Repository on Quay](https://quay.io/repository/aaroc/futuregatewaystack-ac-db/status "Docker Repository on Quay")](https://quay.io/repository/aaroc/futuregatewaystack-ac-db) `db` : The database container.
  1.  [![Docker Repository on Quay](https://quay.io/repository/aaroc/futuregatewaystack-ac-fgapiserver/status "Docker Repository on Quay")](https://quay.io/repository/aaroc/futuregatewaystack-ac-fgapiserver) `fgapiserver` : API server container.
  1. `db-data` : Derives from alpine, merely contains the persistent db volume
