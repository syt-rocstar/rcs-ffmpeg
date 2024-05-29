# Custom Rocstar ffmpeg docker image

## Usage

### Pull image

```bash
docker pull ghcr.io/syt-rocstar/rcs-ffmpeg:bookworm
```

### Create Docker compose file (example)

`/PATH/docker-compose.yml`

```
services:
  rcs-ffmpeg:
    image: rcs-ffmpeg:bookworm
    env_file: ./.env
    entrypoint: ${FFMPEG_CLI}
    restart: unless-stopped
```

### Create Environment file

`/PATH/.env`

```
FFMPEG_CLI={{ ffmpeg parameters to run }}
```

### Run container

`/PATH`

```bash
docker-compose -f docker-compose.yml up -d
```