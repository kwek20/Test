## 6-zmq-listen.js - listening for transactions

This tutorial shows how to use a tool called ZMQ to listen for transactions.  You can listen for all transactions or transactions for a specific address


## Step-by-step explanation of 6-zmq-listen.js

Import zeromq and call is "zmq".  Open the DevNet ZMQ port, 5556.

```

///////////////////////////////
// Listen to live transactions
///////////////////////////////

let zmq = require('zeromq')
let sock = zmq.socket('sub')

// Connect to the devnet node's ZMQ port
sock.connect('tcp://zmq.devnet.iota.org:5556')
```

Instructions are printed to the console for listening to all transactions or entering the command to listen to transactions for a specific address

```
// Check if there is no command line argument
if (!process.argv[2]) {
  // Prompt user to add an address to the commmand line
  console.log('Watching all TXs on the node')
  console.log('---------------------')
  console.log('Note: If you want to watch an address for TXs use this:')
  console.log('node 6-zmq-listen.js AHSAK..99WS')

  // Subscribe to any TX coming in to the node
  sock.subscribe('tx')
} else {
  console.log('Watching for transactions to this address: ' + process.argv[2])
  console.log(
    'Remember to send a TX to this address & be patient it can take 30 seconds for the TX appear.'
  )
  // Subscribe to the address passed via the CLI
  sock.subscribe(process.argv[2])
}
```

A switch statement is used for selecting which type of transaction to monitor.  Case "TX" displays transactions.  Case process.argv[2] displays the specific transaction requested from the CLI.

```
sock.on('message', msg => {
  const data = msg.toString().split(' ') // Split to get topic & data
  switch (
    data[0] // Use index 0 to match topic
  ) {
    case 'tx': // Display any TX coming in.
      console.log(`I'm a TX!`, data)
      break
    case process.argv[2]: // Use the command line argument to subscribe.
      console.log(`I'm the TX you are looking for!`, data)
      break
  }
})
```

RESULT

In this example, we are watching all the transactions.

```
C:\Users\Nelson\NODE\workshop>node 6-zmq-listen.js

Watching all TXs on the node
```

Here is the note showing how to watch transactions for a specific address

```
---------------------
Note: If you want to watch an address for TXs use this:
node 6-zmq-listen.js AHSAK..99WS
```

Here is one sample transaction:  

```
I'm a TX! [ 'tx',
  'QAIHGF9SOBNH9RJRVNOEJTNIMLJCD9YWKJBMY9HXOKZLMAFCIFNPXZEETFMUCHIJKTRACUNYZKCEF
K999',
  'EQQFCZBIHRHWPXKMTOLMYUYPCN9XLMJPYZVFJSAY9FQHCCLWTOLLUGKKMXYFDBOOYFBLBI9WUEILG
ECYM',
  '0',
  'LHEXB9999999999999999999999',
  '1545619370',
  '0',
  '1',
  'WGHZMPWFJBTRVQASXLFLIWWGSQEQMQCQEBTVABEVAOPVIFNNWGYLRX9GECXWZXHMPA9FTKNONUFCI
AU9Y',
  'ERMDCTEZMQK9FBIGPVLIMUNRWWLAXABZMSSECQORLQMUIEVUJJFRARVI9KXTMLTV9QXNFNIB9FEKO
I999',
  'OXBBHFCMNVGFRIGTJ9CUG9J9JEVZNBRHTWEMRRGWFQ9DMCYQWHTANWATVKADAZX9FKJFVOGQABGMZ
K999',
  '1545619370868',
  'LHEXB9999999999999999999999' ]
```

