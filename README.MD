PlayFluxor QuickstartPlayFluxor is a reactive Go platform inspired by Vert.x, built for speed, simplicity, and high-performance IO-bound workloads.
This quickstart repo lets you get up and running in under 2 minutes to experience PlayFluxor’s core features:Ultra-high performance HTTP server (fasthttp-based)  
Realtime observability dashboard  
Zero-leak IO-bound worker pool  
Basic resilience metrics (goroutines, memory alloc, queue length, etc.)

PrerequisitesGo 1.22+  
(Optional) wrk for benchmarking:  bash

brew install wrk          # macOS
sudo apt install wrk      # Ubuntu

Quick Start (2 minutes)Clone the repo

bash

git clone https://github.com/quadgate/playfluxor-quickstart.git
cd playfluxor-quickstart

Run the server

bash

go run .

Server starts on http://localhost:8080  
Dashboard available at http://localhost:8080/dashboard (realtime metrics)

Open browser & enjoyGo to http://localhost:8080/dashboard  
You’ll see live stats: goroutines, memory allocated, alloc rate, GC cycles, queue length, etc.

Test performance (optional but recommended)

bash

# Simple benchmark (expect 100k–200k+ RPS on M1/M2 Mac)
wrk -t8 -c1000 -d60s http://localhost:8080/ping

# Or heavier test
wrk -t12 -c5000 -d30s http://localhost:8080/ping

Expected output on M1/M2 MacBook:

Running 30s test @ http://localhost:8080/ping
  12 threads and 5000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.20ms    1.50ms   80ms   95%
    Req/Sec    40.00k    5.00k   60.00k   85%
  1,200,000+ requests in 30s, ~150MB read
Requests/sec:  ~140,000+ RPS

Features in this QuickstartHTTP Server: fasthttp for raw speed  
/ping: Minimal endpoint for benchmarking  
/dashboard: Realtime observability (goroutines, memory, GC, queue metrics)  
Zero external dependencies — single binary deploy

Next StepsExplore the code  main.go: Server setup & routes  
dashboard/: Realtime metrics rendering

Scale it up  Add your IO-bound tasks (DB queries, external APIs) using the built-in worker pool  
Integrate Fluxor core modules (from main repo)

Want more?  Full PlayFluxor repo (coming soon): https://github.com/quadgate/playfluxor  
Official site: https://quadgate.io / https://gofluxor.com  
Join the waitlist or contribute!

LicenseMIT – feel free to use, modify, and build upon.Built with  by the Fluxor team
Questions? Issues? PRs welcome!  Happy coding & benchmarking! 

