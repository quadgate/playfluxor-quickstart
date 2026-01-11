PlayFluxor QuickstartPlayFluxor – Reactive Go platform inspired by Vert.x. Fast, simple, high-performance.Quick Start (2 mins)bash

git clone https://github.com/quadgate/playfluxor-quickstart.git
cd playfluxor-quickstart
go run .

Server: http://localhost:8080  
Dashboard: http://localhost:8080/dashboard (realtime metrics)

Benchmarkbash

# Expect 100k–200k+ RPS on M1/M2
wrk -t8 -c1000 -d60s http://localhost:8080/ping

Featuresfasthttp server (ultra-fast)  
Realtime dashboard (goroutines, memory, GC, queue)  
Zero external deps – single binary

Next StepsExplore main.go  
Full repo: https://github.com/quadgate/playfluxor (coming soon)  
Site: https://quadgate.io

MIT License – Built with  by Fluxor team  Happy benchmarking! 

