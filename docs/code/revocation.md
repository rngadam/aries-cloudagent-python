# Revocation

## Registry creation

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/models/issuer_rev_reg_record.py#L187

This is done by dependency injection of an Issuer class:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/revocation/models/issuer_rev_reg_record.py#L199

The default was IndyCredxIssuer:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/indy/credx/issuer.py#L43

bound in the AskarProfile:

https://github.com/rngadam/aries-cloudagent-python/blob/15af464c6cba617b6352b8e82d6eea3a1c8f11d0/aries_cloudagent/askar/profile.py#L120-L125

but now is from the anoncreds-rs Python module?

