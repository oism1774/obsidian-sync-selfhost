# Obsidian Selfhosted LiveSync (Powered by CoachDB)

This repository contains a Dockerized setup for CouchDB, specifically optimized for use with the Obsidian Self-hosted LiveSync plugin. It provides a private, secure, and fast alternative to Obsidian Sync.
🚀 Quick Start
1. Prerequisites

  * Docker and Docker Compose installed on your machine or server.
  * Obsidian with the Self-hosted LiveSync plugin installed.

2. Deployment

Clone this repository and spin up the container:
`git clone https://github.com/oism1774/obsidian_sync_selfhost
cd obsidian_sync_selfhost
docker compose up -d`

Once running, the CouchDB management interface will be available at: http://localhost:5984/_utils/

3. CouchDB Initial Setup

You will need to Enable CORS in CouchDB settings for sync to work:
  1) Login to CoachDB using the credentials used in your docker config file
  2) Go to Settings -> CORS
  3) Enable CORS

4. Obsidian Plugin Setup

   To be able to sync your obsidian you should enable Comminity Plugins and install "Self-hosted LiveSync" plugin
   Open the plugin settings in Obsidian and enter:

    * URL: http://<YOUR_SERVER_IP>:5984
    * Username/Password: Your Docker credentials.
    * Database name: Name the database, where your data will be stored.

   # Security Note

For remote access, it is highly recommended to use a Cloudflare Tunnel or a Reverse Proxy
(like Nginx or Traefik) with an SSL certificate. Do not expose port 5984 directly to the internet without encryption.
