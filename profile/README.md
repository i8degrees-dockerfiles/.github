---
---

# i8degrees-dockerfiles

Base directory path for my Docker infrastructure files.

## usage

```shell
```

1. [rclone: Integration with Docker Volumes](https://rclone.org/docker/#getting-started)

## TODO

- [ ] The repository visibility is presently **private** for security reasons. As soon as I iron out how exactly we are going to handle the integration and environment handling of sensitive bits, we can implement these here and then re-mark the repositories here as **public**.
  1. I believe that by seperating the sensitive bits inside `compose.yml` and `.env` files into their own private `.env.secrets` file shall resolve **99%** of our issue; this is the method I shall be employing initially.
  2. The first repository to go live -- **public** -- is [plex](https://github.com/i8degrees-dockerfiles/plex.git).
  3. Somewhat unrelated to, but directly applicable here is the fact that I am concurrently testing the use of (Docker Swarm](https://docs.docker.com/engine/swarm/) for all of my containers here. Once unlocked, this engine offers support for [Docker Secrets](https://docs.docker.com/engine/swarm/secrets/). I anticipate that any [unresolved issues][1] will be gracefully resolved once this new infrastructure piece is in motion. I am expecting this item to not be anywhere near completion for roughly **six** months from now, best case scenario.
