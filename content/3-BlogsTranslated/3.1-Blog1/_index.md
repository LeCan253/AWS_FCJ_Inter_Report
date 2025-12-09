---
title: "Blog 1"
date: 2025-09-30
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Navigating the Windows 10 to 11 Migration for Amazon WorkSpaces Personal

**Author:** Dan Garibay
**Date:** 03/05/2025
**Category:** Amazon WorkSpaces • Desktop Streaming • End-User Computing • Technical Guide

---

## 1. Introduction

Windows 10 Enterprise will reach **End-of-Support (EOS)** on **October 14, 2025**, forcing end-user computing administrators to migrate to Windows 11 to remain a supported operating system. This article provides guidance on migrating to Windows 11 using the **BYOL (Bring Your Own License)** model for Amazon WorkSpaces Personal.

Customers using Windows 10 BYOL on **WorkSpaces Pools** only need to migrate to the new image because the environment is stateless.

---

## 2. Scope of application

Guidelines for customers:

- Running or planning to run Windows workloads under the BYOL model.

- Not applicable to WorkSpaces bundles with Windows licenses.

- Not applicable to **Windows 10 LTSC 2019/2021**.

---

## 3. When Windows 10 EOS – What changes?

- Existing Windows 10 WorkSpaces **still work**.

- WorkSpaces can still be created from old **custom bundles**.

- New Windows 10 images cannot be imported**.

- Windows 11 requires **TPM + UEFI Secure Boot**, so direct upgrade is not possible — a new WorkSpace must be created.

---

## 4. Preparation before Migration

- Backup all data from drive **C:** (this drive will be erased).

- WorkSpace must exist for **≥ 12 hours** to ensure a snapshot has been created.

- Data after the last snapshot is **not retained**.

- Users must be **fully logged out** while migration is in progress.

- WorkSpaces must be in the following states: **AVAILABLE**, **STOPPED**, or **ERROR**.

- Recommended:
- **Amazon FSx**
- **ProfileUnity**
- **Microsoft FSLogix**
- Ensure there are enough **IP addresses** for new WorkSpaces.

- If using script → migrate in batch **≤ 25 WorkSpaces**.

---

## 5. Option 1: WorkSpaces Migration API (Recommended)

### Advantages
- Simple and fast.

- No need to create additional infrastructure → **no cost**.

- Users keep the same **Registration Code**.

### Disadvantages
- **No rollback** → **one-way** process.
- Cannot recover missing data on C: drive.

### Steps
1. Import Windows 11 BYOL image.

2. Create Windows 11 WorkSpace from image.
3. Install management agent and security agents.
4. Create **custom image + bundle**.
5. Run WorkSpace test to check.
6. Migrate users in small groups.

---

## 6. Option 2: Create new Windows 11 BYOL infrastructure

### Advantages
- Allows running Windows 10 & 11 in parallel → **with rollback**.

- Flexible, easy to control and test.
- Users have time to migrate data themselves.

### Disadvantages
- More complicated and resource-intensive.
- There may be additional costs due to running two environments in parallel.

### Steps
1. Import Windows 11 BYOL image.
2. Create Windows 11 WorkSpace in new **AD Connector**.
3. Apply necessary configuration + install security agent.
4. Create **custom image & bundle**.
5. Launch Windows 11 WorkSpaces for users.
6. Provide new **registration code**, instruct users to migrate data themselves.
7. Delete old Windows 10 BYOL WorkSpaces.
8. Clean up:

- Directory Services
- Unused VPC
- AD computer objects

---

## 7. Conclusion

This article presents two methods for migrating from Windows 10 to Windows 11 on Amazon WorkSpaces Personal:

- **Migration API** – fast, simple, low cost but no rollback.

- **Build new infrastructure** – flexible, secure, supports rollback but more complex and expensive.

Whichever method you choose, **careful planning**, data backup, and proper user profile management will ensure a **smooth and secure** transition to Windows 11.

---

## 8. About the author

**Dan Garibay**
Senior Solutions Architect – AWS End User Compute
Expertise: EC2, Microsoft, Linux
Joined AWS in 2016, was a Senior Support Engineer and Technical Account Manager.
