## 🔑 AWS Identity & Access Management (IAM) — Builder Lab

> **Summary:** Completed the **AWS IAM Builder Lab**. Explored pre-created IAM users/groups, inspected and tested policies, assigned users to role-based groups, validated sign-in via the account/alias URL, and observed how permissions impact access to AWS services.

---

## 🎯 Objective
Understand and demonstrate **foundational IAM concepts**—users, groups, policies, and sign-in—by applying and testing **least-privilege, role-based access control (RBAC)** in a practical lab scenario.

---

## 🛠️ Environment
- **Platform:** AWS Management Console (Builder Lab sandbox)
- **Service:** AWS Identity and Access Management (IAM)
- **Scope:** No production resources, lab-only pre-provisioned users/groups/policies

---

## 🚀 Workflow

### 1) Explore Pre-Created IAM Entities
- Reviewed **Users** (e.g., lab-created identities) and their current **Group** memberships.
- Confirmed there were **no direct policies** attached to users (best practice: use groups).
- Inspected **Groups** to see which **managed policies** (AWS-managed / customer-managed) were attached.

**Why it matters:** Centralizing permissions on groups simplifies audits, revocation, and least-privilege maintenance.

---

### 2) Inspect IAM Policies on Groups
- Opened attached policies to review **JSON statements**:
  - `Effect`, `Action`, `Resource`, optional `Condition`
- Identified whether policies granted **read-only**, **power-user**, or **service-specific** capabilities.

**Key concept:** Policies are **deny-by-default**; only explicitly allowed actions on specific resources are permitted (unless an explicit deny applies).

---

### 3) Apply RBAC via Group Assignments
- Followed a **real-world scenario**: placed users into groups that align with their job function (e.g., “Read Only Amazon S3”, “View, Start, Stop Amazon EC2 Instances”).
- Verified users inherited the group’s policies (no user-specific policy sprawl).

**Outcome:** Users received only the capabilities required for their role—supporting **least privilege**.

---

### 4) Locate & Use IAM Sign-In URL
- Retrieved the **IAM sign-in URL** (account alias or account ID URL).
- Tested login using a lab user to validate the **end-user experience** and confirm the correct account context.

**Why it matters:** Using the right sign-in URL reduces cross-account confusion and supports **auditable access**.

---

### 5) Validate Policy Effects (Positive & Negative Tests)
- As a lab user with restricted permissions, attempted to:
  - **Access allowed services** (confirmed success).
  - **Access restricted services** (confirmed **AccessDenied** / permissions error).
- Confirmed that group policy changes **take effect** on next authorization evaluation.

**Takeaway:** Hands-on testing proves your RBAC design works as intended.

---

## ✅ Outcome
- Implemented **role-based access** using **groups + managed policies**.
- Demonstrated **least privilege** by granting only the actions needed.
- Validated **sign-in flow** and observed **policy enforcement** through positive/negative tests.
- Built a foundation to extend into MFA, permission boundaries, and SCPs (in orgs) later.

---

## 🧩 Skills Demonstrated
- IAM **users, groups, policies**, and **policy evaluation** model
- **RBAC** design and **least-privilege** enforcement
- Reading and reasoning about **IAM policy JSON**
- Practical validation via **AWS Console sign-in** and **service access tests**

