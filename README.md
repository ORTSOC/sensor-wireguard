ansible-vpn-client
=========

Deploys a Wireguard VPN client, to connect to a Wireguard VPN server.

Requirements
------------

- Debian 10
- sudo
- ssh

## Variables
* `vpn_client_internal_address`: self-chosen address for the sensor in the internal wireguard network
* `vpn_client_private_key`: the server address for the client in base64, base generated with `wg genkey`
* `vpn_server_addr`: the normally accessible server IP that can be connected to.
* `vpn_server_port`: the port to connect to the server over.
* `vpn_server_public_key`: the public key for the server.
* `cidr_allow_list`: a list of items in CIDR format that gives access to certain items in the VPN IP space.

## Example Config

```yml
# local client config
vpn_client_internal_address: 11.11.11.5
vpn_client_private_key: aaaaaaaaaaaaaa=

# config for the server to connect to
vpn_server_addr: my.server
vpn_server_public_key: bbbbbbbbbbbbb=
vpn_server_port: 51820

# list of CIDR items that we will try to connect to over the VPN IP space.
cidr_allow_list:
  - 11.11.11.0/24
  - 11.11.10.1/32
```

License
-------

GPL3

Author Information
------------------

ORTSOC
