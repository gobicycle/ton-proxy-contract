# Ton proxy contract

Smart contract for forwarding internal messages.
Sends body refs of incoming internal message as internal message with mode = 128+32
(forwards all TONs from balance and self-destroy).
Incoming internal message must contain init.

## Contract data cell scheme

`data owner:MsgAddressInt subwallet_id:uint32 = Data;`

## Use cases

### Jetton deposits control

You can use one wallet to create multiple Jetton deposits. 
A proxy contract is created for each Jetton wallet as its owner. 
Then we can manage multiple Jetton wallets by sending messages to proxy contracts.
