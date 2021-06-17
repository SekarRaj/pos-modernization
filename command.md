## Capture HTTP traffic loopback interface
```sh
tshark -i lo0  -w lo.pcap 

tshark -r lo.pcap -V

tshark -r lo.pcap -V -Y  http.response

tshark -r lo.pcap -Y http.request -T fields -e http.host

tshark -r lo.pcap -Y http.request -T fields -e http.host -e http.user_agent -e http.request.uri

tshark -r lo.pcap -Y http.request -T fields -e http.host -e http.user_agent 

tshark -r lo.pcap -Y http.request -T fields -e http.host -e http.user_agent -e http.request.uri.query

tshark -r lo.pcap -Y http.request -T fields -e http.host -e http.user_agent -e http.request.uri 

tshark -r lo.pcap -Y http.request
```

## Start deno server

```sh
deno run --allow-net --unstable server.ts
```

## Mac List interfaces 
```sh
ifconfig 

ifconfig | pcregrep -M -o '^[^\t:]+(?=:([^\n]|\n\t)*status: active)'
```