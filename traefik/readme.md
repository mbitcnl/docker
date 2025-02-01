# Traefik Reverse Proxy for Docker Swarm

This repository contains the configuration for Traefik v3 running on Docker Swarm with DNS challenge support.

## Features

- Latest Traefik v3 version
- Docker Swarm mode support (Community Edition)
- Automatic SSL certificate generation using DNS challenge
- Single replica deployment (Community Edition limitation)
- Automatic HTTP to HTTPS redirection

## Prerequisites

- Docker Swarm initialized
- DNS provider configured (for Let's Encrypt DNS challenge)
- Docker network created for Traefik

## Environment Variables

Create a `.env` file with the following variables:
