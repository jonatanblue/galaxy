# Install

This document describes how to install the dependencies and deploy Galaxy.

## Mac OS X

Requires **Docker for Mac**.

1. Install pre-requisites

    pip install ansible-container

2. Verify volume paths

On Docker for Mac you need to configure Docker to treat `~/.` and '/galaxy' as a shared folders.

Alternatively you can change the directories in `develop.yml` to something you have already shared:

    galaxy_log_dir: "/tmp/.galaxy/logs"
    galaxy_config_path: "/tmp/.galaxy/config"
    galaxy_project_dir: "/tmp/galaxy"

3. Remove `pyinotify` from `requirements.txt` as it cannot be installed on Mac OS.

4. Build containers

This takes a **really long time** (over 25 min on a MacBook Pro with Intel Core i5 and 8 GB RAM).

    make build

5. Run containers

    make run

6. Play

You can now access Galaxy in your browser:

    http://localhost:8000
