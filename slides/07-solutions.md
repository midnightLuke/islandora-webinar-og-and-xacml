# Solutions


## Continue Using "Global" Roles

- **PRO**: Islandora loves those
- **CON**: Roles table already unwieldy
- **CON**: XACML Editor already confusing enough
- **CON**: Permissions are always global
- **CON**: No "pre-built" solutions


## Modify Drupal Filter and XACML API for OG

- **PRO**: Provide tight integration with Organic Groups
- **CON**: Need to maintain these ourselves
- **CON**: No in-house Java devs
- **CON**: No in-house expertise in XACML

Notes:

- And we were only hired to do the "interface"


## Map "OG" Roles to "Global" Roles

- **PRO**: Provides functionality while using default XACML API
- **PRO**: Works with default OG
- **PRO**: Transparent to end user
- **PRO**: OG has solid API to build this
- **CON**: Would need to modify a number of forms to hide new "global" roles
- **CON**: Requires modifying XACML editor to fake "group" roles

Notes:

- Selected this one for ability to do the work in-house
- Allowed us to use things like "og_context" when browsing repository
