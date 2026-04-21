# Centralized Directory Management (OpenLDAP)

## Felix Owusu Agyemang

## 1. LDIF File Explanations

* **`structure.ldif`**: This file creates the Organizational Units (OUs) which serve as the directory's folder structure. I created a `People` OU for user accounts and a `Groups` OU for departmental organization.
* **`users.ldif`**: This file defines the individual user objects. It includes specific attributes like `uidNumber`, `gidNumber`, and `homeDirectory` so that the directory can be used for Linux system authentication.

---

## 2. Implementation Results

### Screenshot 1: Directory OUs
The output below confirms the successful creation of the **People** and **Groups** Organizational Units.

![LDAP Structure Output](../Identity/structure.png)

### Screenshot 2: User Verification
The output below shows my specific user account (`U01129692`) successfully added and searchable within the directory.

![LDAP User Output](../Identity/user.png)

---
