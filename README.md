# gitbucket-embedding-plugin

A GitBucket plugin to replace code link to snippet

This is still alpha ver.

## Screenshot

![screenshot](https://github.com/onukura/gitbucket-embedding-plugin/blob/assets/screenshot.png?raw=true)

## Install

1. Download *.jar from Releases.
2. Deploy it to `GITBUCKET_HOME/plugins`.
3. Restart GitBucket.

## Build from source

```sbt
sbt clean package
```

The built package is located at
`target/scala-2.13/gitbucket-embedding-plugin_2.13-{plugin-version}.jar`.

```sbt
sbt assembly
```

This makes the assembly package
`target/scala-2.13/gitbucket-embedding-plugin-{plugin-version}.jar`
for deployment.

## Supported link type

`http(s)://host/{owner}/{repository}/blob/{SHA}/{path/to/file}#L{StartLineNumber}-L{EndLineNumber}`

example1: `http://localhost:8080/root/gitbucket/blob/19f0431a3fb4a9c3560dbf9b1d74f2073da7708f/GitBucketCoreModuleSpec.scala#L5-L10`

example2: `http://localhost/root/gitbucket/blob/19f0431a3fb4a9c3560dbf9b1d74f2073da7708f/src/main/scala/GitBucketCoreModuleSpec.scala#L5-L10`

## Note

you better use link with sha, not branch name such as `master`. Because `master` changes by commits.

- Good url:  `http://localhost:8080/root/gitbucket/blob/19f0431a3fb4a9c3560dbf9b1d74f2073da7708f/GitBucketCoreModuleSpec.scala#L5-L10`
- Bad url: `http://localhost:8080/root/gitbucket/blob/master/GitBucketCoreModuleSpec.scala#L5-L10`

## Limitation

user name, repo name, branch name includes special character may not be processed.

## Version

Plugin version|GitBucket version
:---|:---
0.1.x |4.34.x -
