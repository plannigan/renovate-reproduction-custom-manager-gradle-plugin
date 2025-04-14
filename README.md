# renovate-reproduction-custom-manager-gradle-plugin

## Current behavior

This project has a file used for documentation that includes the version of Kotlin being used. The goal is to have a
custom manager update this documentation file when the Kotlin Gradle plugin version is updated.

However, there is a failure to retrieve the versions for the dependency.

```
DEBUG: GET https://repo.maven.apache.org/maven2/org/jetbrains/kotlin/jvm/undefined/maven-metadata.xml = (code=ERR_NON_2XX_3XX_RESPONSE, statusCode=404 retryCount=0, duration=695)
DEBUG: Maven: error fetching versions for "org.jetbrains.kotlin.jvm": not-found
DEBUG: Failed to look up maven package org.jetbrains.kotlin.jvm
{
  "dependency": "org.jetbrains.kotlin.jvm"
  "packageFile": "docs.md"
}
```

Note the `undefined` in the URL being requested.

Renovate does create [an MR][update-mr] is created for the Gradle build file. But it notes that:

> Some dependencies could not be looked up. Check the warning logs for more information. 

## Expected behavior

The documentation file is update in the same MR that update the Gradle build file.

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.

[update-mr]: https://github.com/plannigan/renovate-reproduction-custom-manager-gradle-plugin/pull/1