# The Problem


## Requirements

- Users have the ability to "request access" to "projects"
- "Projects" have their own permissions
- "Projects" can customize their permissions
- "Projects" can restrict access to their collection based on project roles

Notes:

- CWRC is the "client" in this case


## Islandora Capabilities

- XACML API requires use of either "users" or "roles" to determine permissions
- Drupal filter only sends "users" and "roles" to fedora


## Organic Groups Capabilities

- Groups have customizable permissions
- Users can request access to groups


## BUT

XACML doesn't understand group membership/roles...

Notes:

- No way to restrict permissionsons on repository objects based on group membership/roles


### Me at that moment
![I have no idea dog](http://i0.kym-cdn.com/photos/images/facebook/000/234/765/b7e.jpg)
