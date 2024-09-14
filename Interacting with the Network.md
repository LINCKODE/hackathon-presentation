The nodes on the Qubic network communicate using a custom Peer to Peer TCP protocol.
This protocol is not very straight forward to implement into projects, so created an Integration layer, which allows everyone to interact with the network using simple HTTP requests.

The integration layer is composed from a couple of services, which serve different types of information.
# The Archiver service
The Qubic network performs a weekly reset to make space for new transactions, thus the previous state is lost.
The Archiver service is responsible for storing all the transaction and tick information in order to serve it as needed.

Endpoint documentation: https://qubic.github.io/integration/Partners/qubic-rpc-doc.html
Github: https://github.com/qubic/go-archiver
## Fetching service status
Endpoint: `/v1/status`
CLI example: `curl https://rpc.qubic.org/v1/status`
## Fetching tick information
Endpoint: `/v1/ticks/{tick_number}/tick-data`
CLI example: `curl https://rpc.qubic.org/v1/ticks/15885608/tick-data`
## Fetching tick transactions
Endpoint: `/v1/ticks/{tick_number}/transactions`
CLI example: `curl https://rpc.qubic.org/v1/15885608/transactions`
## Fetching transaction information
Endpoint: `/v1/transactions/{tx_id}`
CLI example: `curl https://rpc.qubic.org/v1/rcldxnmsmnjxobnpgboocdowbjqbojsuigxtybetvetrozzpbpgdrrgakwlf`
### Transaction status
Endpoint: `/v1/tx-status/{tx_id}`
CLI example: `curl https://rpc.qubic.org/v1/tx-status/rcldxnmsmnjxobnpgboocdowbjqbojsuigxtybetvetrozzpbpgdrrgakwlf`
### Identity transactions
Endpoint: `/v1/identities/{identity}/transfer-transactions?startTick={start}&endTick={end}`
CLI example: `curl https:rpc.qubic.org/v1/identities/KKSPOZZECAQGNCFCGQFDYZZGUBPAQBHLUTIMBCAKGADRFSAIOYOQNLTDGVUA/transfer-transactions?startTick=15880608&endTick=15885608`
## Fetching the latest network tick
Endpoint: `/v1/latestTick`
CLI example: `curl https://rpc.qubic.org/v1/latestTick`
# The HTTP service 
The HTTP service acts as a proxy to the Qubic network, allowing for querying live information and broadcasting transactions to the network.
Endpoint documentation: https://qubic.github.io/integration/Partners/qubic-rpc-doc.html?urls.primaryName=Qubic%20RPC%20Live%20Tree
Github: https://github.com/qubic/qubic-http
## Fetching identity balance
Endpoint: `/v1/balances/{identity}`
CLI example: `curl https://rpc.qubic.org/v1/balances/KKSPOZZECAQGNCFCGQFDYZZGUBPAQBHLUTIMBCAKGADRFSAIOYOQNLTDGVUA`
## Broadcasting transactions
Endpoint: `/v1/broadcast-transaction`
 > No example for now

# The Stats service
The Stats service is able to provide miscellaneous information, such as the current price of Qubic, circulating supply, market cap and more, as well as the rich-list.
Endpoint documentation: https://qubic.github.io/integration/Partners/qubic-rpc-doc.html?urls.primaryName=Qubic%20Stats%20API
Github: https://github.com/qubic/qubic-stats-service
## Fetching the latest information
Endpoint: `/v1/latest-stats`
CLI example: `curl https://rpc.qubic.org/v1/latest-stats`
## Fetching the rich list
Endpoint: `/v1/rich-list?pageSize={page_size}`
CLI example: `curl https://rpc.qubic.org/v1/rich-list?pageSize=100`

# QX
Endpoint documentation: https://qubic.github.io/go-qubic/swagger/index.html#/QxService
Github: https://github.com/qubic/go-qubic
