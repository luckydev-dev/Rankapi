# RankApi

Paper 1.21.11 plugin that allows your website to grant LuckPerms ranks through an HTTP API.

## Build

Open GitHub Codespaces and run:

```bash
mvn clean package
```

Jar output:

```text
target/Rankapi-1.1.jar
```

## Configuration

Set `api.server-name` in `plugins/RankApi/config.yml` to the server identifier
used by your API. The plugin requests pending orders using:

```text
GET /api/plugin/orders?pending=true&server=servername
```

The configured server name is URL-encoded before it is sent. Leave it blank
only when connecting to an API that does not support server-specific orders.

## API

POST:

```text
http://SERVER_IP:8080/grant-rank
```

JSON:

```json
{
  "secret":"CHANGE_THIS_SECRET",
  "player":"Steve",
  "rank":"vip"
}
```

Allowed ranks:

- vip
- mvp
- legend

Change them inside RankApiPlugin.java.
