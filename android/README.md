# uniffi generated Nimbus bindings
This directory contains the build script that compiles the Nimbus SDK and generates its kotlin
bindings

## Prerequisites
- `uniffi-bindgen`: The library uses [`uniffi`](https://mozilla.github.io/uniffi-rs) to generate Kotlin bindings
  for the Rust `experiments` crate, so you will need to install the `uniffi-bindgen` tool via
  `cargo install uniffi_bindgen`.
- Android Studio: It is preferred you use Android Studio to build the project

## How to use
The bindings are meant to be consumed elsewhere. In order to consume them, you would publish 
this project and consume it from a different project.


### Publishing locally
You can publish this library to `mavenLocal` using
```shell script
./gradlew publishToMavenLocal
```


You should then be able to import it in other projects locally from the `mavenLocal()` repository

### How to consume
The consuming libraries will be consuming the generated bindings directly

You can view what the high level API looks like by checking out the [idl](../experiments/src/nimbus.idl).
`uniffi` ensures that the generated library matches the idl.

## How to modify
The generated bindings will depend on the [idl](../experiments/src/nimbus.idl) file,
if you'd like to modify the api, follow the following steps:
- Modify the [idl](../experiments/src/nimbus.idl) file
- Modify the [Rust code](../experiments/src) to reflect the changes to the idl file

After those steps, when building this project the bindings will be autogenerated
