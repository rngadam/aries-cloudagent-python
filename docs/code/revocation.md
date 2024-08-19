# Revocation

## aries_cloudagent/revocation/routes.py

Registered events for init, endorsed and entry:

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/routes.py#L1544-L1557

...but where are these events created?


## Registry init aries_cloudagent/revocation/indy.py:init_issuer_registry

Entry point in routes for registry init event:

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/routes.py#L1560-L1561

init notification sent from here:

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/indy.py#L102-L109

the init notification receiver here:

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/util.py#L18-L34


## Registry creation

aries_cloudagent/revocation/models/revocation_registry.py

Max registry size is between 4 and 32768 records

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/models/revocation_registry.py#L21-L25

The registry is generated in generate_registry:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/models/issuer_rev_reg_record.py#L187

This is done by dependency injection of an Issuer class:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/models/issuer_rev_reg_record.py#L199

The default was IndyCredxIssuer:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/indy/credx/issuer.py#L43

bound in the AskarProfile:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/askar/profile.py#L120-L125

but now is from the anoncreds-rs Python module?

## registry is full or decommissionned

when an existing registry is set to state FULL or DECOMMISSIONED in aries_cloudagent/revocation/indy.py:_set_registry_status, a new registry is created:

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/indy.py#L160-L165

this triggers a REVOCATION_REG_INIT_EVENT in aries_cloudagent/revocation/indy.py:init_issuer_registry that is handled in aries_cloudagent/revocation/routes.py:on_revocation_registry_init_event

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/routes.py#L1639-L1647

which itself may call init_issuer_registry again:

https://github.com/rngadam/aries-cloudagent-python/blob/3cb976de06c2c184d0f42df9decf4c88143ff221/aries_cloudagent/revocation/routes.py#L1639-L1647