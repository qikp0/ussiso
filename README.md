# ussiso

ussiso is a project that provides unofficial, signed, CentOS Stream ISO images.

It stands for:

- **u**noffical
- **s**igned
- **s**tream
- **iso**

## Downloading

Use [nightly.link](https://nightly.link/qikp0/ussiso/workflows/build/main?preview) or the Actions tab (requires a GitHub account). In some cases, the Actions tab may be necessary.

## Verifying

Import the public key:

```sh
gpg --keyserver pgpkeys.eu --recv-keys fb5b374e69deb706a2855ad65ecdb0bf323c7fae
```

Then download the `hash` artifact, and extract it.

Verify the signature of the hash:

```sh
gpg --verify hash.txt.asc
```

You should see `Good signature`.

Then verify the hash itself:

```sh
sha256sum -c hash.txt.asc
```

## Why?

CentOS doesn't sign their ISO images anymore, this project offers separate infrastructure that signs the ISO image.
