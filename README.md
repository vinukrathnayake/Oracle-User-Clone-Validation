# 🔍 User Clone Validation - Oracle SQL Script

This script validates the cloning accuracy of Oracle database users by comparing role privileges, system privileges, and table privileges between a **source user** (CLONE_FROM_USER) and a **target user** (NEW_USER).

---

## 📋 Script Overview

The script performs the following comparisons:

- ✅ Role Privileges (`DBA_ROLE_PRIVS`)
- ✅ System Privileges (`DBA_SYS_PRIVS`)
- ✅ Table Privileges (`DBA_TAB_PRIVS`)

It ensures that the newly created user has been cloned correctly with all corresponding privileges from the original user.

---

## 📌 Variables

This script uses substitution variables:

| Variable         | Description                             |
|------------------|-----------------------------------------|
| `NEW_USER`       | Username of the target (cloned) user    |
| `CLONE_FROM_USER`| Username of the original source user    |

You will be prompted to input these values when executing the script.

---

## ⚙️ How to Run

1. Connect to the Oracle database using `sqlplus`:
   ```bash
   sqlplus sys@YOUR_DB as sysdba
   ```

2. Execute the script:
   ```bash
   @userclone-validation.sql
   ```

3. You will be prompted to enter values for:
   - `NEW_USER`
   - `CLONE_FROM_USER`

4. The script will output the count of privileges for each user to verify whether they match.

---

## 📦 Output Example

```
Role Privileges    - Source: 5, Clone: 5
System Privileges  - Source: 12, Clone: 12
Table Privileges   - Source: 20, Clone: 20
```

Matching numbers indicate successful privilege cloning.

---

## 🔐 Requirements

- Oracle Database access with DBA privileges
- `DBA_ROLE_PRIVS`, `DBA_SYS_PRIVS`, and `DBA_TAB_PRIVS` views must be accessible

---

## ✍️ Author Notes

Use this script after performing a manual or automated user clone operation to ensure privilege parity between the original and new user.

---

## 🪪 License

This script is distributed under the MIT License. Use freely with attribution.

---
