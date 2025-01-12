---
---

# i8degrees-dockerfiles

Base repository root for my Docker infrastructure. This is one of the major *platform management subsystems* that I maintain for my **Syn Net** LAN. Ideally, I would like to see every last project that I have worked on over my entire life, but this is unlikely to occur, at least any time soon. The number of pre-Docker projects **far** outnumbers any reasonable time estimate and goes as far back as thirty (30) years -- OR MORE -- in time. In theory, this should not be problematic, but I am somewhat hesitant to even saying that this is a remotely decent use of my time. Time shall tell...

## usage

### deps

- any filesystem with a multi-host, concurrent **R/W** architecture (GlusterFS, GFS, AWS S3, CephFS, *...*)
  * `zfs` is **NOT** multi-host capable *per se* without either using the snapshot replication feature across two or more separate (physical) **pools** at some interval of `+1min` units -- this is not suitable for *all* workload types, but is likely to be good enough for general use. Note that two or more physical hosts must be allocated for this (VM images for testing is OK, though!) You also are more than likely going to want the multipath features of `zfs` as opposed to doing so in pure hardware (like we did in the 90s).
- [rclone: Integration with Docker Volumes](https://rclone.org/docker/#getting-started)

### hier

- [GitHub profile](https://github.com/i8degrees-dockerfiles/.github)
  - [archivebox](https://github.com/i8degrees-dockerfiles/archivebox.git)
  - [ntfy](https://github.com/i8degrees-dockerfiles/ntfy.git)
  - [traefik](https://github.com/i8degrees-dockerfiles/traefik.git)
  - [templates](https://github.com/i8degrees-dockerfiles/templates.git)
  - [plex](https://github.com/i8degrees-dockerfiles/plex.git)
  - **WIP** This list is a work in progress and does not represent everything acccessible

## Reference Documents

1. [STUB]()

# TODO

- [ ] The repository visibility is presently **private** for security reasons. As soon as I iron out how exactly we are going to handle the integration and environment handling of sensitive bits, we can implement these here and then re-mark the repositories here as **public**.
  1. I believe that by seperating the sensitive bits inside `compose.yml` and `.env` files into their own private `.env.secrets` file shall resolve **99%** of our issue; this is the method I shall be employing initially.
  2. The first repository to go live -- **public** -- is [plex](https://github.com/i8degrees-dockerfiles/plex.git).
  3. Somewhat unrelated to, but directly applicable here is the fact that I am concurrently testing the use of (Docker Swarm](https://docs.docker.com/engine/swarm/) for all of my containers here. Once unlocked, this engine offers support for [Docker Secrets](https://docs.docker.com/engine/swarm/secrets/). I anticipate that any [unresolved issues][1] will be gracefully resolved once this new infrastructure piece is in motion. I am expecting this item to not be anywhere near completion for roughly **six** months from now, best case scenario.
