## Revocation notification

### Message type:

https://github.com/rngadam/aries-cloudagent-python/blob/e3f3466f2fb0b2f68c827796083aff3e77a6e8af/aries_cloudagent/protocols/revocation_notification/v2_0/message_types.py#L15

### Protocol:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/messages/revoke.py#L16

### Schema

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/messages/revoke.py#L42

### Handler (receiving revoke messages)

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/handlers/revoke_handler.py#L9

Emits a webhook (if configured for revocation.monitor_notification):

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/handlers/revoke_handler.py#L28-L37

Emits a websocket:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/handlers/revoke_handler.py#L40-L48
