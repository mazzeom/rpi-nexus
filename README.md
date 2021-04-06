# Nexus for raspberry pi

## Usage

### Build

```bash
docker build . -f Dockerfile.arm64v8 -t dlgmltjr0925/nexus3:arm64v8-3.30.0-01
```

### Upload

```bash
docker login # docker hub login
docker push dlgmltjr0925/nexus3:arm64v8-3.30.0-01
```

### Run

#### simple

```bash
docker run -d --name nexus3 -p 8081:8081 dlgmltjr0925/nexus3:arm64v8-3.30.0-01
```

#### Persistence storage

```bash
docker run -d --name nexus3 -p 8081:8081 \
  -v {YOUR_DIR}:/opt/nexus/sonatype-work/nexus3 \ # <-- change YOUR_DIR to your data dir
  dlgmltjr0925/nexus3:arm64v8-3.30.0-01
```
