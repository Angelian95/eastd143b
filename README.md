# EASTD143B (Spring 2026)

Quarto website for the course.

## Local preview

```bash
quarto preview
```

## Publishing

GitHub Actions publishes the site to GitHub Pages on pushes to the `2026` branch.

## Soft password gate

This repo includes a **client-side** (not strong security) password gate.

1. Choose a password (do **not** commit the plaintext password).
2. Compute SHA-256 hash:

```bash
python3 -c "import hashlib; print(hashlib.sha256(b'YOUR_PASSWORD').hexdigest())"
```

3. Replace `__REPLACE_ME__` in:
- `auth.html` (EXPECTED_HASH)
- `_includes/auth-check.html` (expected)

After that, users must enter the password once per browser (stored in `localStorage`).
