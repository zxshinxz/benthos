---
title: sample
type: processor
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/processor/sample.go
-->


DEPRECATED: This processor is now deprecated, and the new
[bloblang processor](/docs/components/processors/bloblang) should be used
instead.

```yaml
# Config fields, showing default values
sample:
  retain: 10
  seed: 0
```

Retains a pseudo-randomly sampled percentage of message batches (0 to 100) and
drops all others. The random seed is static in order to sample
deterministically, but can be set in config to allow parallel samples that are
unique.

## Fields

### `retain`

The percentage of messages to keep.


Type: `number`  
Default: `10`  

### `seed`

A seed for pseudo-random sampling.


Type: `number`  
Default: `0`  


