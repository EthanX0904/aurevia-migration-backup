# Aurevia Migration Backup (encrypted)

Encrypted backup chunks of the Aurevia/OpenClaw migration package.

**Do NOT upload the decryption password here.**

## Restore steps

```bash
# 1. download all chunk-XX files into one folder
# 2. rejoin:
cat chunk-* > migrate-enc.bin
# 3. decrypt (you need the password, ask the owner):
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -pass pass:YOUR_PASSWORD \
  -in migrate-enc.bin -out migrate-home-FULL-20260821.tar.gz
# 4. extract with 7-Zip / WinRAR / tar
```

Windows PowerShell version:

```powershell
cmd /c "copy /b chunk-* migrate-enc.bin"
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -pass pass:YOUR_PASSWORD -in migrate-enc.bin -out migrate-home-FULL-20260821.tar.gz
```

Created 2026-08-21. Chunks: 8 (90MB each, last 38MB).
