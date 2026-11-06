# Wazuh Server Deployment

## Server details

-   Hostname: `wazuh`
-   Operating system: Ubuntu Server 24.04.5 LTS
-   Server IPv4 address: `192.168.234.130`
-   Dashboard access: `https://192.168.234.130`
-   Wazuh agent version shown in the Endpoints view: `4.14.9`

## Deployment summary

The Wazuh server was deployed on an Ubuntu Server virtual machine. The
working dashboard was accessed over the lab network. The two endpoint
agents subsequently appeared in the Wazuh Endpoints view as active.

The supplied screenshots verify the server console, dashboard access,
and active endpoint connections. They do not include the original
installation terminal transcript or service-status output, so this
document does not reproduce unverified installation commands.

## Validation evidence

-   Dashboard accessible at the private server address:
    `01-wazuh-dashboard.png`
-   Both endpoint agents active: `02-active-agents.png`

## Operational notes

-   The dashboard in the supplied screenshots is accessed over HTTPS
    with a browser warning indicating a locally untrusted/self-signed
    certificate.
-   Keep the dashboard reachable only from the intended lab network.
-   Never commit dashboard passwords, private keys, API credentials, or
    certificates containing private keys.
