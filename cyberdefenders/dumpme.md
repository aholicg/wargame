// this is still a draft
// todo: full wu+scenario
Q6: to show connection related to the sus process:
`$ vol -f Triage-Memory.mem windows.netscan | grep "3496"`

Q7: 
`$ vol -f Triage-Memory.mem windows.dlllist | grep "VCRUNTIME140"`

Q8: download vol2 :)
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 procdump -p 3496 -D dump`

Q9: 
`$ vol2  --profile=Win7SP1x64 -f Triage-Memory.mem hashdump`
standard Windows password hash string

Q10: 
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 vadinfo | grep -A 5 "0xfffffa800577ba10"`
Q11:
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 vadinfo | grep -A 5 "Start 0x00000000033c0000 End 0x00000000033dffff"`

Q12: 
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 cmdline -p 5116 (pid of wscript.exe)`

Q13:
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 timeliner | grep "2019-03-07 23:06:58"`

Q14:
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 memdump --dump-dir=./dump/ -p 3032 (PID of notepad.exe)`
`$ strings -e l 3032.dmp | grep -E "[A-Za-z0-9]{4}<[A-Za-z0-9]{7}_[A-Za-z0-9]{2}_[A-Za-z0-9]{4}>"`

Q15: 
`$ vol2 -f Triage-Memory.mem --profile=Win7SP1x64 mftparser | grep -A 20 "59045"`

Q16: nó là cái 3496 dm
