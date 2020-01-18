---
title: mqtt
type: input
---

Subscribe to topics on MQTT brokers.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
input:
  mqtt:
    urls:
    - tcp://localhost:1883
    topics:
    - benthos_topic
    client_id: benthos_input
```

</TabItem>
<TabItem value="advanced">

```yaml
input:
  mqtt:
    urls:
    - tcp://localhost:1883
    topics:
    - benthos_topic
    client_id: benthos_input
    qos: 1
    clean_session: true
    user: ""
    password: ""
```

</TabItem>
</Tabs>

### Metadata

This input adds the following metadata fields to each message:

``` text
- mqtt_duplicate
- mqtt_qos
- mqtt_retained
- mqtt_topic
- mqtt_message_id
```

You can access these metadata fields using
[function interpolation](/docs/configuration/interpolation#metadata).

## Fields

### `urls`

`array` A list of URLs to connect to. If an item of the list contains commas it will be expanded into multiple URLs.

### `topics`

`array` A list of topics to consume from.

### `client_id`

`string` An identifier for the client connection.

### `qos`

`number` The level of delivery guarantee to enforce.

Options are: `0`, `1`, `2`.

### `clean_session`

`bool` Set whether the connection is non-persistent.

### `user`

`string` A username to assume for the connection.

### `password`

`string` A password to provide for the connection.

