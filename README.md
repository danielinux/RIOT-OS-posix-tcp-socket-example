# Posix sockets: TCP client/server example

This example shows how to use TCP with POSIX sockets


## License

This example is distributed under the terms of GNU LGPLv2.1.

## SOCK vs. Socket

This example is configured to use POSIX sockets (over LWIP).


## Fast configuration (Between RIOT instances)

### Prepare the bridge interface linking two tuntap

```bash
    ./../../dist/tools/tapsetup/tapsetup --create 2
```

## Testing

### Run the server
```bash
$ make all; PORT=tap1 make term
> ip
```
*copy the server address*

```bash
> tcps
```
### Run the client
```bash
$ PORT=tap0 make term
> tcpc <IPv6's server address[%netif]>
```

### Testing against host endpoints

Riot-to-host can be tested against netcat

## Boards

Boards that due to insufficient memory are not able to support LWIP, which is required for this example, are included
in the `BOARD_INSUFFICIENT_MEMORY`.
