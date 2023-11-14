# Vulnmap Node.js runtime agent 

Use this package as a library in your application to monitor your dependencies and to learn how the vulnerable functions of the dependencies are invoked in your deployments.

# Quick start
```js
require('@khulnasoft/nodejs-runtime-agent')({ projectId: <Your-Project-ID> });
```

# Supported Node.js versions

The Node.js Runtime Agent is tested on Node 8 and Node 10.
Other versions are unsupported.

# How to
```js
require('@khulnasoft/nodejs-runtime-agent')(config);
```

The `config` object supports the following options:

| Key                | Type      | Default value                            | Purpose                                                                 |
|--------------------|-----------|------------------------------------------|-------------------------------------------------------------------------|
| `projectId`        | `String`  |                           | The Vulnmap project ID that matches your application.                         |
| `enable`           | `Boolean` | `true`                    | Set to `false` to disable the agent.                                    |

Advanced `config` options:

| Key                  | Type      | Default value                                               | Purpose                                                                                    |
|----------------------|-----------|-------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| `beaconIntervalMs`   | `Number`  | `60000`                   | Report frequency in milliseconds.                                                          |
| `snapshotIntervalMs` | `Number`  | `3600000`                 | Snapshot retrieval frequency in milliseconds.                                              |
| `flushOnExit`        | `Boolean` | `true`                    | Set to `false` to prevent the agent from flushing its data before exiting. `true` is useful especially for short-lived environments.   |

# Demo

There is a
[self-contained demo named node-woof](https://github.com/khulnasoft-lab/node-woof#node-woof),
which you can clone and run. It will guide you through the setup of the project on
your machine.

# Development
`npm start` brings up an http server that invokes a vulnerable function
on startup and for every request.
