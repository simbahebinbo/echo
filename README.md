# Echo

An example libp2p project that uses a Kademlia DHT for peer discovery and performs rpc calls. You can read about this project at [ldej.nl/post/building-an-echo-application-with-libp2p](https://ldej.nl/post/building-an-echo-application-with-libp2p/).

## How to run

```shell
$ git clone git@github.com:ldej/echo.git
$ go run .
2021/01/20 12:56:42 Host ID: QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz
2021/01/20 12:56:42 Connect to me on:
2021/01/20 12:56:42   /ip4/192.168.1.8/tcp/45363/p2p/QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz
2021/01/20 12:56:42   /ip4/127.0.0.1/tcp/45363/p2p/QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz

$ # open a second terminal
$ go run . -peer /ip4/192.168.1.8/tcp/45363/p2p/QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz
2021/01/20 12:57:45 Host ID: QmSP59U51bSsERKobDE4CyrChJ4uSWv6RV1kiAs51DLLRF
2021/01/20 12:57:45 Connect to me on:
2021/01/20 12:57:45   /ip4/192.168.1.8/tcp/39957/p2p/QmSP59U51bSsERKobDE4CyrChJ4uSWv6RV1kiAs51DLLRF
2021/01/20 12:57:45   /ip4/127.0.0.1/tcp/39957/p2p/QmSP59U51bSsERKobDE4CyrChJ4uSWv6RV1kiAs51DLLRF
2021/01/20 12:57:45 Connection established with bootstrap node: "{QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz: [/ip4/192.168.1.8/tcp/45363]}"

$ # open a third terminal
$ go run . -peer /ip4/192.168.1.8/tcp/45363/p2p/QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz
2021/01/20 12:59:06 Host ID: QmPLsZDrgPLFie9PkvrdBbiMa8C5W9eKjZ429kimkP2SB8
2021/01/20 12:59:06 Connect to me on:
2021/01/20 12:59:06   /ip4/192.168.1.8/tcp/42967/p2p/QmPLsZDrgPLFie9PkvrdBbiMa8C5W9eKjZ429kimkP2SB8
2021/01/20 12:59:06   /ip4/127.0.0.1/tcp/42967/p2p/QmPLsZDrgPLFie9PkvrdBbiMa8C5W9eKjZ429kimkP2SB8
2021/01/20 12:57:45 Connection established with bootstrap node: "{QmNpf6rQUFFTR9syqLASvzTsfDdBaUYvu3QkgVMXodyJUz: [/ip4/192.168.1.8/tcp/45363]}"
```

Each node sends a message to all peers every second, and each peer responds with an echo message.



```shell
$ go build
```

```shell

# open a first terminal
$ ./telephone                                      
2024/06/18 17:28:05 Host ID: QmNn9FPZXj1o5wAm5aekkmHSE19YU65zAYZARuk3aPnmuD
2024/06/18 17:28:05 Connect to me on:
2024/06/18 17:28:05   /ip4/192.168.8.6/tcp/64129/p2p/QmNn9FPZXj1o5wAm5aekkmHSE19YU65zAYZARuk3aPnmuD
2024/06/18 17:28:05   /ip4/127.0.0.1/tcp/64129/p2p/QmNn9FPZXj1o5wAm5aekkmHSE19YU65zAYZARuk3aPnmuD

# open a second terminal
$ ./telephone -peer /ip4/192.168.8.6/tcp/64129/p2p/QmNn9FPZXj1o5wAm5aekkmHSE19YU65zAYZARuk3aPnmuD
2024/06/18 17:29:46 Host ID: QmT2SGPb6TaVvcqE1Ukxq2Wgbhw942jLJ1yawuQ11XmXUq
2024/06/18 17:29:46 Connect to me on:
2024/06/18 17:29:46   /ip4/192.168.8.6/tcp/64185/p2p/QmT2SGPb6TaVvcqE1Ukxq2Wgbhw942jLJ1yawuQ11XmXUq
2024/06/18 17:29:46   /ip4/127.0.0.1/tcp/64185/p2p/QmT2SGPb6TaVvcqE1Ukxq2Wgbhw942jLJ1yawuQ11XmXUq
2024/06/18 17:29:46 Connection established with bootstrap node: "{QmNn9FPZXj1o5wAm5aekkmHSE19YU65zAYZARuk3aPnmuD: [/ip4/192.168.8.6/tcp/64129]}"
```
