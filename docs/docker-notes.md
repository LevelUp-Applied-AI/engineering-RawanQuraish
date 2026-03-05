# Docker Notes — Day 9

## Docker Version
docker version
Client:
 Version:           29.2.1
 API version:       1.53
 Go version:        go1.25.6
 Git commit:        a5c7197
 Built:             Mon Feb  2 17:20:16 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.63.0 (220185)
 Engine:
  Version:          29.2.1
  API version:      1.53 (minimum version 1.44)
  Go version:       go1.25.6
  Git commit:       6bc6209
  Built:            Mon Feb  2 17:17:24 2026
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v2.2.1
  GitCommit:        dea7da592f5d1d2b7755e3a161be07f43fad8f75
 runc:
  Version:          1.3.4
  GitCommit:        v1.3.4-0-gd6d73eb8
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0

## Hello World Test

Command:
docker run hello-world

Output:
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/


 ## Startup Logs

Command:
docker logs pg-prework

Output:
The files belonging to this database system will be owned by user "postgres".
This user must also own the server process.

The database cluster will be initialized with locale "en_US.utf8".
The default database encoding has accordingly been set to "UTF8".
The default text search configuration will be set to "english".

Data page checksums are disabled.

fixing permissions on existing directory /var/lib/postgresql/data ... ok
creating subdirectories ... ok
selecting dynamic shared memory implementation ... posix
selecting default max_connections ... 100
selecting default shared_buffers ... 128MB
selecting default time zone ... UTC
creating configuration files ... ok
running bootstrap script ... ok
sh: locale: not found
2026-03-05 07:28:18.365 UTC [33] WARNING:  no usable system locales were found
performing post-bootstrap initialization ... ok
syncing data to disk ... ok


Success. You can now start the database server using:

    pg_ctl -D /var/lib/postgresql/data -l logfile start

initdb: warning: enabling "trust" authentication for local connections
initdb: hint: You can change this by editing pg_hba.conf or using the option -A, or --auth-local and --auth-host, the next time you run initdb.
waiting for server to start....2026-03-05 07:28:19.947 UTC [39] LOG:  starting PostgreSQL 15.17 on x86_64-pc-linux-musl, compiled by gcc (Alpine 15.2.0) 15.2.0, 64-bit
2026-03-05 07:28:19.956 UTC [39] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
2026-03-05 07:28:20.001 UTC [42] LOG:  database system was shut down at 2026-03-05 07:28:18 UTC
2026-03-05 07:28:20.013 UTC [39] LOG:  database system is ready to accept connections
 done
server started

/usr/local/bin/docker-entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*

waiting for server to shut down....2026-03-05 07:28:20.154 UTC [39] LOG:  received fast shutdown request
2026-03-05 07:28:20.168 UTC [39] LOG:  aborting any active transactions
2026-03-05 07:28:20.173 UTC [39] LOG:  background worker "logical replication launcher" (PID 45) exited with exit code 1
2026-03-05 07:28:20.173 UTC [40] LOG:  shutting down
2026-03-05 07:28:20.184 UTC [40] LOG:  checkpoint starting: shutdown immediate
2026-03-05 07:28:20.254 UTC [40] LOG:  checkpoint complete: wrote 3 buffers (0.0%); 0 WAL file(s) added, 0 removed, 0 recycled; write=0.023 s, sync=0.011 s, total=0.082 s; sync files=2, longest=0.006 s, average=0.006 s; distance=0 kB, estimate=0 kB
2026-03-05 07:28:20.260 UTC [39] LOG:  database system is shut down
 done
server stopped

PostgreSQL init process complete; ready for start up.

2026-03-05 07:28:20.424 UTC [1] LOG:  starting PostgreSQL 15.17 on x86_64-pc-linux-musl, compiled by gcc (Alpine 15.2.0) 15.2.0, 64-bit
2026-03-05 07:28:20.424 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
2026-03-05 07:28:20.424 UTC [1] LOG:  listening on IPv6 address "::", port 5432
2026-03-05 07:28:20.444 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
2026-03-05 07:28:20.466 UTC [53] LOG:  database system was shut down at 2026-03-05 07:28:20 UTC
2026-03-05 07:28:20.484 UTC [1] LOG:  database system is ready to accept connections


## Stop Command

Command:
docker stop pg-prework

Output:
pg-prework


## Restart Command

Command:
docker restart pg-prework

Output:
pg-prework
