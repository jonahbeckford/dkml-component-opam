# staging-opam

The ocamlrun component is a standalone distribution of OCaml containing
just `ocamlrun` and the OCaml Stdlib.

The staging-opam component makes available the Opam binaries (`opam`, `opam-installer`
and on Windows `opam-putenv`) in the staging-files directory.

These are components that can be used with [dkml-install-api](https://diskuv.github.io/dkml-install-api/index.html)
to generate installers.

## dkml-component-staging-opam

### Executables

> `%{dkml-component-staging-opam:share-abi}%/bin/opam`

> `%{dkml-component-staging-opam:share-abi}%/bin/opam-installer`

> `%{dkml-component-staging-opam:share-abi}%/bin/opam-putenv`

If you need to copy these from staging to the end-user's installation prefix, you should copy
the entire `%{dkml-component-staging-opam:share}%/bin` directory as it may contain DLLs
and shared libraries necessary for its operation.

On Windows the binaries will end with `.exe`.

### Documentation

> `%{dkml-component-staging-opam:share-generic}%/man/man1`

Man pages.

### Usage

FIRST, add a dependency to your .opam file:

```ocaml
depends: [
  "dkml-component-staging-opam"   {>= "2.1.0"}
  # ...
]
```

SECOND, add the package to your currently selected Opam switch:

```bash
opam install dkml-component-staging-opam
# Alternatively, if on Windows and you have Diskuv OCaml, then:
#   with-dkml opam install dkml-component-staging-opam
```

Be prepared to **wait several minutes** while one or more Opam is being
compiled for your machine.

## Contributing

See [the Contributors section of dkml-install-api](https://github.com/diskuv/dkml-install-api/blob/main/contributors/README.md).

## Status

[![Syntax check](https://github.com/diskuv/dkml-component-opam/actions/workflows/syntax.yml/badge.svg)](https://github.com/diskuv/dkml-component-opam/actions/workflows/syntax.yml)

| Status                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![Asset tests](https://github.com/diskuv/dkml-component-opam/actions/workflows/asset.yml/badge.svg)](https://github.com/diskuv/dkml-component-opam/actions/workflows/asset.yml)    |
| [![Syntax check](https://github.com/diskuv/dkml-component-opam/actions/workflows/syntax.yml/badge.svg)](https://github.com/diskuv/dkml-component-opam/actions/workflows/syntax.yml) |
