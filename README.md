# Copyparty Deploy

Deploy [copyparty](https://github.com/9001/copyparty) file server to Dokploy.

## Setup

1. Edit `config/copyparty.conf` and change the admin password:
   ```
   admin: changeme  →  admin: your-secure-password
   ```

2. Push this repo to GitHub/GitLab

3. In Dokploy:
   - Create a new **Compose** application
   - Connect to your Git repo
   - Deploy

4. Configure your domain/proxy in Dokploy to route to port `3923`

## Configuration

Edit `config/copyparty.conf` to customize:

- **Accounts**: Add users in `[accounts]` section
- **Permissions**: Modify `accs:` in volume sections
- **Features**: Uncomment options in `[global]`

See [copyparty docs](https://github.com/9001/copyparty#readme) for full configuration options.

## Docker Images

Available images (in `docker-compose.yml`):

| Image | Size | Features |
|-------|------|----------|
| `copyparty/min` | 20 MB | Base server |
| `copyparty/im` | 25 MB | + image thumbnails |
| `copyparty/ac` | 56 MB | + ffmpeg (video/audio) ← **default** |
| `copyparty/iv` | 73 MB | + vips (faster thumbnails) |
| `copyparty/dj` | 104 MB | + BPM/key detection |
