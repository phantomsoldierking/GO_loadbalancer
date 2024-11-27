# Simple Reverse Proxy Load Balancer

## Description

This project implements a simple HTTP reverse proxy load balancer in Go. The load balancer distributes incoming HTTP requests to a list of backend servers using a round-robin strategy. It forwards the requests to one of the available backend servers based on the round-robin count, ensuring that requests are distributed evenly across the servers.

The load balancer also ensures that only healthy servers (i.e., those marked as "alive") are used for proxying requests. This simple implementation assumes all backend servers are always alive for the sake of simplicity, but it could be extended to include health checks.

This is useful for scaling applications by distributing traffic across multiple backend services.

## Features

- **Round-robin load balancing**: Distributes requests evenly among backend servers.
- **Reverse proxy**: Forwards client requests to backend servers.
- **Simple HTTP server**: The load balancer itself serves on a configurable port.
- **Configurable backend servers**: You can add multiple backend servers to balance traffic between them.

## How It Works

1. The load balancer listens on a specific port (default is `localhost:8000`).
2. Incoming HTTP requests are forwarded to one of the backend servers.
3. The backend servers are configured as `https://www.facebook.com`, `https://www.bing.com`, and `https://www.duckduckgo.com` in this example, but can be customized to any valid URLs.
4. The load balancer uses a round-robin strategy to distribute requests across the backend servers.
5. When the backend server is determined, the request is forwarded to that server using a reverse proxy.

## Running the Application

1. Clone the repository:
   ```bash
   git clone https://github.com/phantomsoldierking/GO_loadbalancer.git
   cd GO_loadbalancer
