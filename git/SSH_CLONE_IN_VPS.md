
## 1️⃣ Check if SSH key already exists on VPS

```bash
ls ~/.ssh
```

If you see files like:

* `id_rsa` & `id_rsa.pub` **or**
* `id_ed25519` & `id_ed25519.pub`

👉 you can **skip to Step 4**.

If not, continue.

---

## 2️⃣ Generate SSH key on the VPS

**Recommended (modern & secure):**

```bash
ssh-keygen -t ed25519 -C "vps"
```

Press **Enter** for:

* file location
* passphrase (optional but recommended)

This creates:

```
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

---

## 3️⃣ Add the public key to GitHub / GitLab

Copy the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

### On GitHub:

1. GitHub → **Settings**
2. **SSH and GPG keys**
3. **New SSH key**
4. Paste key
5. Title: `VPS - DigitalOcean`
6. Save

---

## 4️⃣ Test SSH connection

```bash
ssh -T git@github.com
```

Expected output:

```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

⚠️ First time → type **yes** when asked.

---

## 5️⃣ Clone the repository (SSH URL only)

Go to your project directory:

```bash
cd /var/www
# or
cd ~
```

Clone using **SSH**, NOT HTTPS:

```bash
git clone git@github.com:USERNAME/REPO_NAME.git
```

Example:

```bash
git clone git@github.com:Siddu-06-0405/timetable-rvitm.git
```

---
