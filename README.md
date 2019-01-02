## Dockerfile for Rust, Rocket web app development

### Sample `docker-compose.yml`

```
version: '3'

services:
  web:
    image: bhboruff/rrweb
    ports:
      - "80:8000"
    volumes:
      - .:/code/app
    command: sh -c "cd app && cargo-watch watch -x run"
```

Your [rocket](https://rocket.rs/) web app will be available at `http://localhost` on the default port `80`.

Changes to your local code will be detected by `cargo-watch` and rebuilt. It may take a small amount of time
for the rebuild to complete. Then refresh your browser.