Dockerfile for GitBucket
====

This image is based on [the `openjdk` official alpine-based image](https://hub.docker.com/_/openjdk)

How To Use
----

To quickly run, do:

```$ docker run -d -p 8080:8080 -p 29418:29418 -v ${PWD}/gitbucket 190ikp/gitbucket```

All data in GitBucket is mounted on `~/gitbucket`.

Then go to `http://localhost:8080/` and log in with ID: **root** / Pass: **root**.

To access the git repository over SSH (default: `29418`), check this setting:

- GitBucket > Administration > System Settings > SSH access

Options
----

You can use some environment variables such as:

Environment variable | Value | Example
----|----|----
`GITBUCKET_DB_URL`, `GITBUCKET_DB_USER`, `GITBUCKET_DB_PASSWORD` | to use external database (MySQL, PostgreSQL) | `jdbc:postgresql://db/gitbucket`, `user`, `password`
`GITBUCKET_CERT` | for LDAP Authentication | `/path/to/your/cacert.pem`
`GITBUCKET_EXTRA_DEPS` | to install dependencies required by GitBucket plugins | `git procps`
`JAVA_OPTS` | JavaVM options | `-Xmx1g`
`GITBUCKET_OPTS` | GitBucket options | `--host=example.com`

For more infomation, visit: [here](https://github.com/gitbucket/gitbucket/)

Gitbucket's License
----

visit [here](https://github.com/gitbucket/gitbucket/blob/master/LICENSE)