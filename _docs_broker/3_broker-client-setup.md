---
title: "Broker client"
---

The broker client is a web server which securely relays requests between Snyk's servers and your GitHub Enterprise. It needs to run on a network which has both outbound internet access and access to your GitHub Enterprise.

To set up and run a Snyk broker client:

1. Install snyk-broker

     `$ npm install -g snyk-broker`

2. Initialise the broker for use with Snyk

     `$ broker init snyk`

   This will generate two files:
     - ".env"        : the brokers configuration
     - "accept.json" : the rules used to filter the requests being proxied to and from the Snyk servers

3. Edit the ".env" file, providing the following details:

    | Variable name     | Description                                                                                                                                                                                                                         |
    |-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | BROKER_TOKEN      | Your unique broker token. This is displayed on the organisation settings page on [snyk.io](https://snyk.io). **This is a private token and must not be shared.**                                                                    |
    | GITHUB_TOKEN      | A GitHub Enterprise (or GitHub) personal access token for the user that Snyk will use to access your repositories.                                                                                                                  |
    | GITHUB            | The host (and port if necessary) of your private GitHub server.                                                                                                                                                                     |
    | GITHUB_API        | The url to the api of your private GitHub server.                                                                                                                                                                                   |
    | GITHUB_RAW        | The url to access raw contents of files in git repos on your private GitHub server                                                                                                                                                  |
    | BROKER_CLIENT_URL | The url that your broker *client* is accessible at, which will be used for GitHub webhooks that notify Snyk of relevant changes to your repositories                                                                                |
    | CA_CERT           | (optional) Path to the Certificate Authority root certificate that was used to sign your GitHub Enterprise's TLS certificate. Only needed if your GitHub Enterprise uses a TLS certificate signed by a custom Certificate Authority |

   The .env file itself is optional, all of these details may be provided to the broker as environment variables.

   Note: The .env file is generated with defaults appropriate for use with GitHub Enterprise. It also includes instructions for values to use with github.com.

4. Start the broker

    `$ broker client`

   The broker can be started in debugging mode with:

    `$ broker client --verbose`

   Note: your BROKER_TOKEN will be output on stdout when the broker is started with `--verbose`.

Alternatively, the broker can also be installed as part of a private npm package. See [https://github.com/Snyk/broker-snyk-client-example](https://github.com/Snyk/broker-snyk-client-example) for an example of this.
