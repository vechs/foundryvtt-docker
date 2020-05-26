# foundryvtt-docker ⚔️🛡🐳 #

[![GitHub Build Status](https://github.com/felddy/foundryvtt-docker/workflows/build/badge.svg)](https://github.com/felddy/foundryvtt-docker/actions)
[![FoundryVTT Version: v0.6.0](https://img.shields.io/badge/foundry-v0.6.0-brightgreen?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAAAAXNSR0IArs4c6QAAAIRlWElmTU0AKgAAAAgABQESAAMAAAABAAEAAAEaAAUAAAABAAAASgEbAAUAAAABAAAAUgEoAAMAAAABAAIAAIdpAAQAAAABAAAAWgAAAAAAAABIAAAAAQAAAEgAAAABAAOgAQADAAAAAQABAACgAgAEAAAAAQAAAA6gAwAEAAAAAQAAAA4AAAAATspU+QAAAAlwSFlzAAALEwAACxMBAJqcGAAAAVlpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IlhNUCBDb3JlIDUuNC4wIj4KICAgPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICAgICAgPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIKICAgICAgICAgICAgeG1sbnM6dGlmZj0iaHR0cDovL25zLmFkb2JlLmNvbS90aWZmLzEuMC8iPgogICAgICAgICA8dGlmZjpPcmllbnRhdGlvbj4xPC90aWZmOk9yaWVudGF0aW9uPgogICAgICA8L3JkZjpEZXNjcmlwdGlvbj4KICAgPC9yZGY6UkRGPgo8L3g6eG1wbWV0YT4KTMInWQAAAiFJREFUKBVVks1rE1EUxc+d5tO0prZVSZsUhSBIPyC02ooWurJ0I7rQlRvdC/4N4h9gt7pyoRTswpWgILgQBIOIiC340VhbpC0Ek85MGmPmXc+baWpNGJg77/7uOffeB+z9FHB0FrH9eLwwqpOF0f34KrpsTicW+6L8KE8QhO/n8n1IOgtQHYZA+a/Ai9+Wd6v1g7liq5A2OjKSQNa9hkO4hAzOIylf6CHALk6hoWXsylPkfjyyApaJhVCxmERy5zLSuI7D8h1H5BWht1aBhS6wdI3pN7GabyuyS4JPrchzujmNjDxAVrrRL2PoxRSGxOfjssgEjkkJvVJBWu6h5M7YenvDoOO0OgicD4TPIKWbBG6xvwTaKCMwSU7hKxK6gt8mbsFIMaF5iDyjUg6iPnqc58higCr9fD4iTvWMziAmK2g73f/AADVWX0YXrlChirgOcqL3WXYBYpTfUuxzjkW30dI1C0ZW1RnjMopo4C56MIs6CgQrMER2cJoz9zjdO2iz17g2yZUjqzHWbuA4/ugiEz7DVRe/aLxmcvDQ5Cq+oWGWeDbAgiETXgArrVOFGzR0EkclxrVMcpfLgFThY5roe2yz95ZZkzcbj22+w2VG8Pz6Q/b5Gr6uM9mw04uo6ll4tOlhE8a8xNzGYihCJoT+u3I4kUIp6OM0X9CHHds8frbqsrXlh9CB62nj8L5a9Y4DHR/K68TgcHhoz607Qp34L72X0rdSdM+vAAAAAElFTkSuQmCC)](https://foundryvtt.com/releases/0.6.0)
[![Known Vulnerabilities](https://snyk.io/test/github/felddy/foundryvtt-docker/badge.svg)](https://snyk.io/test/github/felddy/foundryvtt-docker)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/felddy/foundryvtt-docker.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/felddy/foundryvtt-docker/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/felddy/foundryvtt-docker.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/felddy/foundryvtt-docker/context:python)
[![Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/felddy/foundryvtt-docker.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/felddy/foundryvtt-docker/context:javascript)

You can get a [FoundryVTT](https://foundryvtt.com) instance up and running in
minutes using this container.  This Docker container is designed to be secure,
reliable, compact, and simple to use.  It only requires that you provide the
credentials needed to download a Foundry release.

## Prerequisites ##

* A functioning [Docker](https://docs.docker.com/get-docker/) installation.
* The [`docker-compose`](https://docs.docker.com/compose/install/) tool.
* A [FoundryVTT](https://foundryvtt.com/auth/register/) account with a purchased
  software license.

## Building ##

1. Copy the project to your machine using the `Clone or download` button above
   or the command line:

    ```console
    git clone https://github.com/felddy/foundryvtt-docker.git
    cd foundryvtt-docker
    ```

1. Build the container using your FoundryVTT site credentials.  Your credentials
   are only used to download a Foundry release, and **are not stored** in the
   image:

    ```console
    docker-compose build \
    --build-arg USERNAME='your_username' \
    --build-arg PASSWORD='your_password'
    ```

See the [Cross-platform builds](#cross-platform-builds) instructions below for
additional build options.

## Running ##

A sample [`docker-compose.yml`](docker-compose.yml) file is included in this
repository.  Modify any configuration options as needed.  By default your
Foundry data will be stored in the `data` directory.  It is **strongly**
recommended that you **change the administrator password** in
`FOUNDRY_ADMIN_KEY`.

1. Start the container and detach:

    ```console
    docker-compose up --detach
    ```

1. Access the web application at:
[http://localhost:30000](http://localhost:30000).

If all goes well you should be prompted for your "License Key", the license
agreement, and then "admin access key" from the `docker-compose.yml` file.  If
you used the example file, the password is `atropos`.

## Updating ##

The Foundry "Update Software" tab is disabled by default in this container. To
upgrade to a new version of Foundry, update this repository to the latest
version and rebuild the image.

1. Stop the running container:

    ```console
    docker-compose down
    ```

1. Update to the latest release of this repository:

    ```console
    git pull
    ```

1. Follow the previous instructions for [building](#building) and
   [running](#running) the container above.

## Volumes ##

| Mount point | Purpose        |
|-------------|----------------|
| /data    | configuration, data, and log storage |

## Environment Variables ##

| Mount point  | Purpose | Default |
|--------------|---------|---------|
| TIMEZONE     | Container [TZ database name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List) | UTC |
| FOUNDRY_UID    | `uid` the daemon will be run under. | foundry |
| FOUNDRY_GID    | `gid` the deamon will be run under. | foundry |
| FOUNDRY_ADMIN_KEY | Admin password.  |  |
| FOUNDRY_AWS_CONFIG | An absolute or relative path that points to the [awsConfig.json](https://foundryvtt.com/article/aws-s3/) or `true` for AWS environment variable [credentials evaluation](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-credentials-node.html) usage | null |
| FOUNDRY_HOSTNAME | A custom hostname to use in place of the host machine's public IP address when displaying the address of the game session. This allows for reverse proxies or DNS servers to modify the public address. | null |
| FOUNDRY_NO_UPDATE | Prevent the application from being updated from the web interface.  The application code is immutable when running in a container.  See the [Updating](#updating) section for the steps needed to update this container. | true |
| FOUNDRY_PROXY_PORT | Inform the Foundry Server that the software is running behind a reverse proxy on some other port. This allows the invitation links created to the game to include the correct external port. | null |
| FOUNDRY_PROXY_SSL | Indicates whether the software is running behind a reverse proxy that uses SSL. This allows invitation links and A/V functionality to work as if the Foundry Server had SSL configured directly. | false |
| FOUNDRY_ROUTE_PREFIX | A string path which is appended to the base hostname to serve Foundry VTT content from a specific namespace. For example setting this to `demo` will result in data being served from `http://x.x.x.x:30000/demo/`. | null |
| FOUNDRY_SSL_CERT | An absolute or relative path that points towards a SSL certificate file which is used jointly with the sslKey option to enable SSL and https connections. If both options are provided, the server will start using HTTPS automatically. | null |
| FOUNDRY_SSL_KEY | An absolute or relative path that points towards a SSL key file which is used jointly with the sslCert option to enable SSL and https connections. If both options are provided, the server will start using HTTPS automatically. | null |
| FOUNDRY_UPDATE_CHANNEL | The update channel to subscribe to.  "alpha", "beta", or "release". | "release" |
| FOUNDRY_UPNP | Allow Universal Plug and Play to automatically request port forwarding for the Foundry VTT port to your local network address. | false |
| FOUNDRY_WORLD | The world startup at system start. | null |

## Cross-platform builds ##

To create images that are compatible with other platforms you can use the
[`buildx`](https://docs.docker.com/buildx/working-with-buildx/) feature of
Docker:

1. Create an new `Dockerfile` with `buildx` support:

    ```console
    ./buildx-dockerfile.sh
    ```

1. Build the image using `buildx`:

    ```console
    docker buildx build \
      --file Dockerfile-x \
      --platform linux/amd64 \
      --build-arg PASSWORD='your_password' \
      --build-arg USERNAME='your_username' \
      --build-arg VERSION=0.6.0 \
      --output type=docker \
      --tag felddy/foundryvtt:0.6.0 .
    ```

## Hosting behind Nginx with TLS ##

Below is an example configuration that will serve the FoundryVTT application at
a specific path.  In this example, the application container will be accessible
at `https://example.com/vtt`:

```nginx
server {
    listen 443 ssl http2 default_server;
    listen [::]:443 ssl http2 default_server;
    server_name example.com www.example.com;

    if ($host = www.example.com) {
        return 301 https://example.com$request_uri;
    }

    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
    ssl_trusted_certificate /etc/letsencrypt/live/example.com/chain.pem;

    add_header Access-Control-Allow-Origin https://example.com always;

    location /vtt {
        # FoundryVTT routePrefix = "vtt"

        proxy_http_version 1.1;
        access_log /var/log/nginx/upstream_log upstream_logging;

        proxy_read_timeout 90;
        proxy_set_header Connection "Upgrade";
        proxy_set_header Host $host;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Real-IP $remote_addr;

        proxy_pass http://localhost:30000;
    }
}

server {
    listen 80 default_server;
    listen [::]:80 default_server;
    server_name example.com www.example.com;
    return 301 https://example.com$request_uri;
}
```

## Debugging ##

There are a few helper arguments that can be used to diagnose container issues
in your environment.

| Purpose | Command |
|---------|---------|
| Drop into a shell in the container | `docker-compose run foundry --shell` |

## Contributing ##

We welcome contributions!  Please see [here](CONTRIBUTING.md) for
details.

## License ##

This project is in the worldwide [public domain](LICENSE).

This project is in the public domain within the United States, and
copyright and related rights in the work worldwide are waived through
the [CC0 1.0 Universal public domain
dedication](https://creativecommons.org/publicdomain/zero/1.0/).

All contributions to this project will be released under the CC0
dedication. By submitting a pull request, you are agreeing to comply
with this waiver of copyright interest.
