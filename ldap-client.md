# Centralized LDAP Authentication

## Felix Owusu Agyemang

---

## 1. Verification Screenshots

### Screenshot 1: Visibility Check (`getent passwd U01129692`)

![ Visibility Check (`getent passwd U01129692`)](getentpswd.png)


Proves the OS is pulling user data from the LDAP network.

---

### Screenshot 2: Identity Recognition (`id U01129692`)

![Identity Recognition (`id U01129692`)](id.png)


Confirms the mapping of numerical IDs to the directory objects.

---

### Screenshot 3: Evidence of Successful Login

![Evidence of Successful Login](login.png)

**Action:** `su - U01129692` followed by `whoami`,`pwd` and `id`

Displays the prompt change and the automatic creation of `/home/felix`.

---

