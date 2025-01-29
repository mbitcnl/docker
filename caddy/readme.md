# Caddy in Docker Swarm - Testing Notes

## Overview
This repository contains my testing experience with Caddy server as a reverse proxy in a Docker Swarm environment.

## Current Status
⚠️ **Not Production Ready**

After several days of testing Caddy in a Docker Swarm environment, I have concluded that the setup is not yet stable enough for production use.

## Testing Period
- Environment: Docker Swarm
- Duration: Multiple days
- Purpose: Stability evaluation

## Deployment Configuration
- Running in global mode with 3 replicas
- NFS backend for shared storage
- Image: lucaslorentz/caddy-docker-proxy:2.9.1 (Caddy with Docker plugin)

### Container Configuration Attempts
- Implemented various healthcheck configurations
- Tested different container restart policies
- Experienced random container crashes despite configuration tweaks

### NFS Mount Configuration
```bash
nfs4 rw,relatime,vers=4.2,rsize=1048576,wsize=1048576,hard,proto=tcp,timeo=600,retrans=2,sec=sys,local_lock=all
```

### NFS Configuration Details
- Version: NFSv4.2
- Read/Write buffer sizes: 1MB (1048576 bytes)
- Protocol: TCP
- Timeout: 600 seconds
- Retransmission attempts: 2
- Security: sys
- Locking: local_lock=all
- Mount options: hard mount, relative timing

## Key Findings
- The implementation shows promise but requires further testing
- Stability issues were encountered during the testing period
- Random container crashes occurred frequently
- Container health checks and restart policies did not resolve stability issues
- Not recommended for production deployment at this time
- NFS backend configuration requires further optimization

## Future Considerations
- Further testing and configuration optimization may be needed before considering production deployment
- Investigation needed into root cause of random container crashes
- Alternative container configurations may need to be explored

---
*Note: This documentation reflects personal testing experience and may not represent all possible deployment scenarios.*
