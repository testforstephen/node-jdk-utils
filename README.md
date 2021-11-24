# node-jdk-utils

A collection of Java related utils.

## Installation
```bash
npm i jdk-utils
```

## Usage

### findJavaRuntime

Find Java runtime from all possible locations on your machine.
Covering:
* `JAVA_HOME`.
* JDK-like paths from `PATH`.
* SDKMAN installation location.
* Links specified in jEnv.
* Platform-specific conventional installation location:
  * Linux: `/usr/lib/jvm`
  * macOS: `/Library/Java/JavaVirtualMachines`
  * Windows: JDK-like folders under `%ProgramFiles%` and `%LocalAppData%`,


callback-style

```ts
require("jdk-utils").findRuntimes().then(console.log)
/*
[{
    homedir: '/home/username/.sdkman/candidates/java/17.0.1-ms',
  }, {
    homedir: '/usr/lib/jvm/java-11-openjdk-amd64',
  },
...
]
*/
```

promise-style
```ts
import { findRuntimes } from "jdk-utils";
await findRuntimes({checkJavac: true, withVersion: true});
/*
[{
    homedir: '/home/yanzh/.sdkman/candidates/java/17.0.1-ms',
    hasJavac: true,
    version: { java_version: '17.0.1', major: 17 }
  }, {
    homedir: '/usr/lib/jvm/java-11-openjdk-amd64',
    hasJavac: true,
    version: { java_version: '11.0.7', major: 11 }
  },
...
]
*/
```

