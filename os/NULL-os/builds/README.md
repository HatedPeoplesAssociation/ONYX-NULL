# NULL/OS Build Output

This directory is reserved for generated NULL/OS build artifacts.

---

# Important

Generated build files are not authoritative source.

Source belongs elsewhere in the repository.

---

# Possible Outputs

```text
kernel

boot images

system images

recovery images

package repositories

checksums

manifests

symbols
```

---

# Version Control

Most generated build files should not be committed directly to Git.

Release artifacts should normally be attached to versioned releases instead.

---

# Reproducibility

Published release artifacts should eventually include:

- version
- source commit
- SHA-256
- signature
- build manifest
- reproduction instructions
