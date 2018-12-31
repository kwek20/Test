## Self-check answers


From [1-hello-world](1-hello-world.md), what does a node contain?

(a) Iota Tokens

(b) One view of the distributed ledger

(c) Neighbors

```
Answer:  (b) one view of the distributed ledger
```

From [2.1-send-hello](2.1-send-hello), which of these is a valid tryte string?
  
  (a)	123456789
  
  (b)	rbtRBTC9D9DCDQAEASBYBCCKX
  
  (c)	RBTC9D9DCDQAEASBYBCCKBFA 
  
  (d)	123ASDFasdf

```
Answer: (c) RBTC9D9DCDQAEASBYBCCKBFA

The tryte alphabet is: 9ABCDEFGHIJKLMNOPQRSTUVWXYZ

This is also written as: 9A-Z
```

From [2.1-send-hello](2.1-send-hello.md), which is a valid seed, assuming each is 81 trytes:

 (a)SENDER ONE 9999999999999999999999999999999999999999999999999999999999999999999999
 
 (b)SENDERSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS
 
 (c)SENDERsssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssss
 
 (d)1SENDERSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS

```
Answer: 

b)SENDERSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS

Spaces, numbers, and lowercase letters are not part of the tryte alphabet
```

From [4.send-tokens](4.send-tokens.md)

```
SEEDSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS Total Balance 46i (iota)

Deposit Address  ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSA  Balance 40i
Deposit Address  ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSB  Balance 1i
Deposit Address  ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSC  Balance 2i
Deposit Address  ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSD  Balance 3i
```

In the above example, which address is a deposit address?
 
(a)ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSA

(b)ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSB

(c)ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSC

(d)ADDRESSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSD

(e) All the above

```
Answer: (e) All the above

In this example, each address is a deposit address because each address contains iota tokens
```

From [4.send-tokens](4.send-tokens.md), how many transactions must be approved before a bundle is confirmed?

a)	1

b)	50%

c)	70%

d)	100%

```
Answer: d)	100%

Bundles are atomic meaning 100% of the transactions must be confirmed in order for the bundle to be processed
```

From [4.send-tokens](4.send-tokens.md), the _______ uses their ______ to send funds?
 
 (a) Sender, seed
 
 (b) Sender, address
 
 (c) Recipient, seed
 
 (d) Recipient, address

```
Answer:  (a) Sender, seed

The sender uses their seed to send funds
```

From [4.send-tokens](4.send-tokens.md), the _______ uses their ______ to receive funds?
 
 (a) Sender, seed
 
 (b) Sender, address
 
 (c) Recipient, seed
 
 (d) Recipient, address

```
Answer: (d) Recipient, address

The recipient uses their address to receive funds
```

From [4.send-tokens](4.send-tokens.md), funds are stored in the

(a) seed

(b) address

```
Answer: (b) address

Funds are stored in addresses
```

From [4.send-tokens](4.send-tokens.md), what should you always keep secret? 

a) seed 

b) address 

c) hash

```
Answer:  a) seed 

>Never share your seed
```

From [4.send-tokens](4.send-tokens.md), how many times should you use a deposit address? 

a) never 

b) as many as you want 

c) 1

```
Answer:  c) 1

Only use a deposit address once.  Otherwise, you make it easier for someone to decipher your secret key and steal your iota tokens
```

### Additional study questions

Which of the following can appear as 81-trytes or 90 characters? 

a) address 

b) bundle 

c) hash 

d) seed

```
Answer:  a) address 

The address is 81-trytes but a checksum is often added so it appears as a 90 character string.  Trinity wallet always uses the 
90 character string so users can easily differentiate between the seed and address.  This provides additional security so users 
remember to safeguard their 80-tryte seed and share their 90 character address
```

What should you use to keep track of addresses attached to a seed? 

a) Index 

b) Address 

c) Checksum 

```
Answer:  a) Index 

One seed many have many addresses.  Each address has a unique index starting at index 0 and incrementing by 1.  Addresses are 
processed in order of their index
```

How many addresses can be generated for a seed? 

a) 1 

b) As many as you need 

c) 2 

d) 100

```
Answer:  b) As many as you need 

One seed may have multiple addresses.  Be mindful, having many addresses requires more processing time to compute the total seed 
balance.  You may want to use multiple seeds and select an optimum number of addresses per seed to meet your needs.
```

Where is the balance stored? 

a) Seed 

b) Address 

c) A and B

```
Answer:  b) Address 

Iota tokens are stored in addresses.  A seed balance is the summary of all the associated addresses
```

What happens when two transactions are sent simultaneously? 

a)	Error message

b)	Account overdrawn message

c)	First TX confirms but second remains pending

d)	API fails

```
Answer:  c)	First TX confirms but second remains pending

The first TX processed by a node will confirm but the second TX remains pending.  This prevents a double spend situation where the 
same tokens are used twice
```

What is a double spend? 

a) Paying twice what the item is worth 

b) Paying two people 

c) Attempting to spend funds twice 

d) Using two distributed ledgers

```
Answer:  c) Attempting to spend funds twice 

Because the ledger is distributed, trustworthiness occurs through consensus.  However, a user may purposefully or inadvertently
attempt to spend the same funds twice.  This is called "double spend".  Iota uses special security to help prevent a double-spend.
```

What does the signatureMessageFragment contain?

(a) User-defined message

(b) Signature

(c) 9's

(d) All of the above

```
Answer:  (d) All of the above

Example of signatureMessageFragment containing a signature:

  signatureMessageFragment: 'MJELJJJRTPNZZMSRRRQKXOAZVKLWKEKMYTAYCUHJNQZ9OZQLXUG
BDZKWFKKYVTHHHQYBRJJH9VMELOSUZ9YOCPYCKOPUYUYFXPCPBTYKJCRLDNCF9HQTN9UFB9PBUSKKGGG
NICZIGZONGPHTGTWMDUOKRLQIFPQWUXPNAFXMW99QQJTANHVHZEJAQJNRAWESSZEFSVRDWYGFPMDHCVO
ITOCO9CWKXBAJEFFCQAUEPC9LNH9D9VBVGJEALB9UYL9RCZQAKPQOVNWBODJAIIQDODPMHWLQYIXTFWN
TTDIT9FRWBSYHCLJTEVTHYLSUBIBQGULCHURXPOHOTJJJLTWRLVFDKOICTHI9EGUGQTUZWCGWVWYZLQQ
ZKZKUXZHTTCBNQJLP9YOUDXOXXRX9EHMQCVTQVJQVM9XAGJY9YDGHYAOEHPP9LPTTDXUDUDWZDALKYHV
WOTGJKBECTFUYVAFEGPIKLYYSQKIXHJXDZ9HFPTEJPLNULHDCOVNRVVAHEOFNHFQKGSOEHX9XISDYNDR
CNQWWITMKXHDGBQVBTRI9VICNFJRPWPBCVUYYLLEZY9CVPGQHGCXUWTWQXLUJRUGGXDWOWQIZQWRCDPI
DNNAQWRRKVJAPBDQQXAHEURIBNUWTNRIEVVW9SDFEJZ9FDZMAJCMXTRBSJLERPOLWNUCNSDFPLZMYQJP
KILLW9PGSFCOOMXEPBKCTCKKHCEGRUFZQVSMEDDTDQEPZGZVZJLNTYYSAYBXQJVVUFUDLMPFOKELAYRL
9LAKGRTSACVIRVDGNDHVMENNCDNSRFNNVGZDMLZKRHTYJFLPEFNXWAZDLOMWMBJXYLOLBDOHBRZYO9GZ
LKPYWMMWBGIIRRRX9FJBJXNMKDGRACUTKQ9FPPNZSUEKRCXFZRWXPBFMCDRMHKRIWGUXZVEMCHXMCSNE
SMU9CUQPVGGQRIJCBXSOKGLWLQJY9FWDTBGLAKXJCRPPBLNLLJPQRQTAIECEKITWNASIRVHD9NJZHRLU
NIGKACVWIHEMIKZASWWCAIBUCREYCVEFTCBWXLDUMWPABRVUVATEYDQUIUQESWXFKKQEXS9VCZHJHHUP
LPRFTAHFYMROSZYBZGYHUBVIK9KSYG9YADAPUFZGWYAXQCILNFUGWKKXRXUFTBQIXMGVXLICOAUEQSNV
SLQMGDGRFHGQTYHGUHBHAOPM9IQJHILOIFWS9PMQQMYAJYCWXCZCPZBCJAPRHMHJOWIWXGTJZIQNTHEJ
KCFVADRPCBQTZMXUNLHOQBUFW9ZWNQESEDP9KWWXAMLRYMAYBWKLYRHEMYBF9MYLXGDRFUKFVTNICXNS
XKCESPUOBFIWVEPASPBFLJNDI9BGPVMWXYMBKXNYSBZTWXBIEPHJKZEAUBAIVUJ9ICMSXJ99XSWMAQIN
SZ9CFGIDLXOWWXLZ9FWMBXVDHBDERYADDGJZVZF9BHUJVNAISINEG9NQFQHRAY9AFFLTQJSNWF9SJSON
XTUBWEQ9IAZDEUVENNYT9X9HEVUBPEP9EC99WYIFGPESFQO9KEJQJR9UZSJE9IJPRZQ9FLBNH9UB9VQU
JVNXEWHUBRZM9MDHTMIFYDLRJPBMWFIAGNWSVTFBVWRVCKATWLZDTTY99D9L9QHANEOKADAGOMODCAZU
PRICDYYTIGCWKFVYKALWVHIVKTCQYVQSSHCVZKYOHABNIGD9XZAJKTVI9MQGMU9OPPQGRZZCYMQARDYP
KIPMVGUGRVHCHXCLZ9WDDNYRQKKUNFCORXIPUXRFVBXCCGPXJKCTBQBMUGFMC9BYV9QSPGBYXSJFYBPY
DMDZSMBKQYDCMA9OVNEQQKWDQFNIQWLYUYPJZ9CHQKOACVGISWYAFGWLFSSBKIIGN9OEVYJLEUTEBRGE
MOVPUB9XHOFJVRAD9TJHSHJKMYSIBWDRDHHHSOQVMAHLWR9UIWCJDBGT9QK9UHOGKWPIFAZFOGW9DVHL
EBUEGHAPNNADUNMFTUIVHCZGNBWDOVSKHSEACNAZBK9MMBSCGTBFYYLDEYAIORQYCWKBDUPMUEZEWVCA
BPVGTVRIATQRJGSHIJZALIODNKGQONXFUVJYIOKTRKTHYUPUZWMTXWYSMFN9BNIAPCKDJPSFELFYFZYV
INLSAJCSVLGRNH9JDSHVRVTNXDNAEP9DDZNC9OQTUOQKABMPJFXHISAC',

Example of a blank signatureMessageFragment:

  signatureMessageFragment: '999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999999999999999999999999999
99999999999999999999999999999999999999999999999999999999',

Example of signatureMessageFragment containing a message converted to trytes:

signatureMessageFragment: 'SBYBCCKBEAFCCDFDZCGDWCCDDDEAXCGDEAHDCDDDFA99999999999999999999999999999999999999999999999999999999999...',

If the TX requires a signature, then the `signatureMessageFragment` contains this signature.  Otherwise, the `signatureMessageFragment`
is blank (shown as all 9's) or contains a user-defined message padded with 9's.
```

Which of the following would generate the first address?
 
(a) ```  .getNewAddress(hash, { index: 1, total: 1 })```

(b) ```  .getNewAddress(bundle, { seed: 1, address: 1 })```

(c) ```  .getNewAddress(seed, { index: 1, total: 0 })```

(d) ```  .getNewAddress(seed, { index: 0, total: 1 })```

```
Answer:  (d) ```  .getNewAddress(seed, { index: 0, total: 1 })```

In order to generate an address, you need a seed.  So options (a) and (b) are incorrect.  (a) attempts to use a hash.  
(b) attempts to use a bundle.  
The parameters in option (c) are backwards.  It would not be useful to generate zero addresses.

Option (d) is correct.  Choose index zero and a total of one address to be generated.  These parameters can be used to generate
the first address for a given seed.
```

The balance can be checked for one address

(a) True

(b) False

```
(a) True

Iota tokens are stored in addresses.  The balance can be checked for one or more addresses.  In order to get the total balance of 
all addresses in a seed, summarize the balances of all associated addresses
```

