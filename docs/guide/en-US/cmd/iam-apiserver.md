## iam-apiserver

The IAM API server to validates and configures data for the api objects

### Synopsis

The IAM API server validates and configures data
for the api objects which include users, policies, secrets, and
others. The API Server services REST operations to do the api objects management.

Find more iam-apiserver information at:
    https://github.com/marmotedu/iam/blob/master/docs/admin/iam-apiserver.md

```
iam-apiserver [flags]
```

### Options

```
      --apiconfig string                              IAM APIServer config file.
      --feature.enable-metrics                        Enables metrics on the apiserver at /metrics (default true)
      --feature.profiling                             Enable profiling via web interface host:port/debug/pprof/ (default true)
      --grpc.bind-address string                      The IP address on which to serve the --grpc.bind-port(set to 0.0.0.0 for all IPv4 interfaces and :: for all IPv6 interfaces). (default "0.0.0.0")
      --grpc.bind-port int                            The port on which to serve unsecured, unauthenticated grpc access. It is assumed that firewall rules are set up such that this port is not reachable from outside of the deployed machine and that port 443 on the iam public address is proxied to this port. This is performed by nginx in the default setup. Set to zero to disable. (default 8081)
  -h, --help                                          help for iam-apiserver
      --insecure.bind-address string                  The IP address on which to serve the --insecure.bind-port (set to 0.0.0.0 for all IPv4 interfaces and :: for all IPv6 interfaces). (default "127.0.0.1")
      --insecure.bind-port int                        The port on which to serve unsecured, unauthenticated access. It is assumed that firewall rules are set up such that this port is not reachable from outside of the deployed machine and that port 443 on the iam public address is proxied to this port. This is performed by nginx in the default setup. Set to zero to disable. (default 8080)
      --jwt.key string                                Private key used to sign jwt token.
      --jwt.max-refresh duration                      This field allows clients to refresh their token until MaxRefresh has passed. (default 1h0m0s)
      --jwt.realm string                              Realm name to display to the user. (default "iam jwt")
      --jwt.timeout duration                          JWT token timeout. (default 1h0m0s)
      --log.disable-color                             Disable output ansi colors in plain format logs.
      --log.enable-caller                             Enable output of caller information in the log.
      --log.error-output-paths strings                Error output paths of log. (default [stderr])
      --log.format FORMAT                             Log output FORMAT, support plain or json format. (default "console")
      --log.level LEVEL                               Minimum log output LEVEL. (default "info")
      --log.output-paths strings                      Output paths of log. (default [stdout])
      --mysql.database string                         Database name for the server to use.
      --mysql.host string                             MySQL service host address. If left blank, the following related mysql options will be ignored. (default "127.0.0.1:3306")
      --mysql.log-mode                                Enable gorm debug mode.
      --mysql.max-connection-life-time duration       Maximum connection life time allowed to connecto to mysql. (default 10s)
      --mysql.max-idle-connections int                Maximum idle connections allowed to connect to mysql. (default 100)
      --mysql.max-open-connections int                Maximum open connections allowed to connect to mysql. (default 100)
      --mysql.password string                         Password for access to mysql, should be used pair with password.
      --mysql.username string                         Username for access to mysql service.
      --redis.addrs strings                           A set of redis address(format: 127.0.0.1:6379).
      --redis.database int                            By default, the database is 0. Setting the database is not supported with redis cluster. As such, if you have --redis.enable-cluster=true, then this value should be omitted or explicitly set to 0.
      --redis.enable-cluster                          If you are using Redis cluster, enable it here to enable the slots mode.
      --redis.host string                             Hostname of your Redis server. (default "127.0.0.1")
      --redis.master-name string                      The name of master redis instance.
      --redis.optimisation-max-active int             In order to not over commit connections to the Redis server, we may limit the total number of active connections to Redis. We recommend for production use to set this to around 4000. (default 4000)
      --redis.optimisation-max-idle int               This setting will configure how many connections are maintained in the pool when idle (no traffic). Set the --redis.optimisation-max-active to something large, we usually leave it at around 2000 for HA deployments. (default 2000)
      --redis.password string                         Optional auth password for Redis db.
      --redis.port int                                The port the Redis server is listening on. (default 6379)
      --redis.ssl-insecure-skip-verify                Allows usage of self-signed certificates when connecting to an encrypted Redis database.
      --redis.timeout int                             Timeout (in seconds) when connecting to redis service.
      --redis.use-ssl                                 If set, IAM will assume the connection to Redis is encrypted. (use with Redis providers that support in-transit encryption).
      --redis.username string                         Username for access to redis service.
      --secure.bind-address string                    The IP address on which to listen for the --secure.bind-port port. The associated interface(s) must be reachable by the rest of the engine, and by CLI/web clients. If blank, all interfaces will be used (0.0.0.0 for all IPv4 interfaces and :: for all IPv6 interfaces). (default "0.0.0.0")
      --secure.bind-port int                          The port on which to serve HTTPS with authentication and authorization. It cannot be switched off with 0. (default 8443)
      --secure.tls.cert-dir string                    The directory where the TLS certs are located. If --secure.tls.cert-key.cert-file and --secure.tls.cert-key.private-key-file are provided, this flag will be ignored. (default "/var/run/iam")
      --secure.tls.cert-key.cert-file string          File containing the default x509 Certificate for HTTPS. (CA cert, if any, concatenated after server cert).
      --secure.tls.cert-key.private-key-file string   File containing the default x509 private key matching --secure.tls.cert-key.cert-file.
      --secure.tls.pair-name string                   The name which will be used with --secure.tls.cert-dir to make a cert and key filenames. It becomes <cert-dir>/<pair-name>.crt and <cert-dir>/<pair-name>.key (default "iam")
      --server.healthz                                Add self readiness check and install /healthz router. (default true)
      --server.max-ping-count int                     The max number of ping attempts when server failed to startup. (default 3)
      --server.middlewares strings                    List of allowed middlewares for server, comma separated. If this list is empty default middlewares will be used. (default [recovery,secure,options,nocache,cors,requestid])
      --server.mode string                            Start the server in a specified server mode. Supported server mode: debug, test, release. (default "release")
      --version version[=true]                        Print version information and quit.
```

###### Auto generated by spf13/cobra on 29-Sep-2020