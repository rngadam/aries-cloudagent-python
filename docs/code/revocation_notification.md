## Revocation notification

### Message type:

https://github.com/rngadam/aries-cloudagent-python/blob/e3f3466f2fb0b2f68c827796083aff3e77a6e8af/aries_cloudagent/protocols/revocation_notification/v2_0/message_types.py#L15

### Protocol:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/messages/revoke.py#L16

### Schema

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/messages/revoke.py#L42

### Revocation

within the route revoke:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/routes.py#L503-L512

revoke_credential is called:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/routes.py#L569-L580

RevocationManager.revoke_credential

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/manager.py#L196-L202

notification sent:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/util.py#L62-L69

### Sending a revoke notification

Revocation message is presented in the to_message:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/models/rev_notification_record.py#L120

every revocation record is turned into a revocation message:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/routes.py#L51-L60

if revocation.notify is true:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/routes.py#L36

this event handler subscribes to revocation_published_event here:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/routes.py#L22-L25

### Handler (receiving revoke messages)

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/handlers/revoke_handler.py#L9

Emits a webhook (if configured for revocation.monitor_notification):

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/handlers/revoke_handler.py#L28-L37

Emits an event:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/protocols/revocation_notification/v2_0/handlers/revoke_handler.py#L40-L48

