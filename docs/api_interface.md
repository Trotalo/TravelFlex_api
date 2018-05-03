# api interface

## network

network nodes, this is for client to know where to broadcast its transactions

###get

get direction of nodes

- url: ```/node_network```
- response: ```{"nodes": ["127.0.0.1:8000","127.0.0.1","168.192.0.12"]}```

# last_block

last block of chain, this to know the timestamp and the hash of last block to compose transaction information, timestamp is used to verify the time of data broadcast corresponds to the reality (proof of transaction was made during the time it is proclaimed to be made)

###get

get direction of nodes

- url: ```/last_block```
- response: ```{"last_block_hash": "last_block_hash", "block_info": {"timestamp":"YYYY-mm-dd_HH:MM:SS", "data":"data_of_block"}}```

## transaction

bitcoin transaction allows to create a transaction and see its state

###post

create transaction

- url: ```/transaction```
- body: ```{"source":"my_public_key", "destination":["destination1","destination2"], "values":["value1", "value2"], "signature":"data_signature", "timestamp":"YYYY-mm-dd_HH:MM:SS","last_block":"last_block_hash"}```
- response: ```{"submitted":"ok", "signature":"data_signature"}```

###get

get information of transaction

- url: ```/transaction/transaction_id```
- response: ```{{"source":"my_public_key", "destination":["destination1","destination2"], "values":["value1", "value2"], "signature":"data_signature", "timestamp":"YYYY-mm-dd_HH:MM:SS","last_block":"last_block_hash", "transaction_id":"transaction_id", "confirmations":"number of nodes confirmed the block where the transaction is"}}```
