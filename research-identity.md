# Felix Owusu Agyemang

## Identity & Policy Management Research

This research explores the evolution of Identity Providers (IdP), the transition to phish-resistant MFA, and the emerging security challenges of 2026.

---

## 1. Enterprise Identity Provider (IdP): Microsoft Entra ID
As organizations move away from traditional on-premises silos, Entra ID serves as the centralized "Source of Truth" for modern enterprise ecosystems.

* **Platform Name:** Microsoft Entra ID
* **Controlling Vendor:** Microsoft
* **Description:** The cloud-native evolution of Azure AD. It acts as a comprehensive Identity-as-a-Service (IDaaS) platform, managing access to M365, cloud infrastructure, and thousands of SaaS applications through single sign-on (SSO).
* **Official Link:** [Microsoft Entra ID](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id)
* **Implementation Dependencies:** * An active Azure/M365 tenant.
    * **Entra Connect** for hybrid environments requiring synchronization with on-premises Active Directory Domain Services (AD DS).
* **Cost to Implement (Pricing Model):**
    * **Free/Bundled:** Included with business-tier M365 subscriptions.
    * **Premium P1 (~$6/user/month):** Necessary for critical features like Conditional Access and Application Proxy.
    * **Premium P2 (~$9/user/month):** Required for high-level risk-based automation, Identity Protection, and PIM (Privileged Identity Management).
* **Scalability:** Engineered for global scale, capable of managing hundreds of thousands of users per tenant with high availability.
* **Administrator Implementation Needs:** * Verification of custom domains via DNS records.
    * Configuration of Enterprise Applications via SAML or OIDC.
    * Setting up Security Groups and sync scopes.
* **Policy & Access Management:** Managed primarily through **Conditional Access Policies**. These allow admins to enforce granular "If-Then" rules based on user location, device health, and login risk.
* **Account Configuration:** Includes User Principal Name (UPN) mapping, attribute synchronization, and the configuration of Self-Service Password Reset (SSPR).

---

## 2. MFA & Verification: Hardware-Based (YubiKeys)
With the rise of sophisticated phishing and session hijacking, hardware-based FIDO2 keys have become the industry gold standard for high-assurance security.

* **Common Platforms:** YubiKey 5 Series / Security Key Series (Yubico).
* **Description:** Physical cryptographic devices that require a "touch" to authenticate. They prevent remote attacks by ensuring that the user is physically present at the device being accessed.
* **Official Link:** [Yubico](https://www.yubico.com/)
* **Implementation Dependencies:** * Browsers or Operating Systems supporting **WebAuthn/FIDO2**.
    * A backend IdP (like Entra ID or Okta) that supports external security keys.
* **Cost to Implement:**
    * **Device Hardware:** Typically ranges from **$25 to $95** per key. 
    * **Logistics:** Organizations must factor in the cost of providing two keys per user (one primary, one backup) and the overhead of shipping keys to remote staff.
    * **Readers:** Most modern workstations have built-in USB/NFC support; however, legacy systems may require external USB-C or Lightning adapters.
* **The "Human" Factor:** Unlike SMS or App-based TOTP, hardware keys cannot be tricked by fake login sites (phishing), as the key will only communicate with the legitimate, registered domain.

---

## 3. 2026 Trend: Deepfake Defense (Liveness Detection)
As generative AI makes "Face ID" and voice verification easier to spoof, the industry is shifting toward "Liveness Detection" to prove a user is a real human in real-time.

* **Category:** Deepfake Defense / Continuous Verification.
* **The Concern:** Attackers use Generative Adversarial Networks (GANs) to create highly realistic video and audio in real-time. These "Deepfakes" can be used to impersonate executives during video calls or bypass automated biometric identity checks.
* **Exploitation Methods:** * **Virtual Camera Injection:** Attackers use software to feed AI-generated video into a meeting or verification app instead of a physical webcam feed.
    * **Presentation Attacks:** Using high-resolution screens or realistic physical masks to fool standard facial recognition.
* **The Response (Prevention):** * **Active Liveness:** Requiring users to perform a random, unpredictable action (e.g., "Look at the blue circle as it moves").
    * **Passive Liveness:** AI-driven analysis of micro-textures, skin blood flow (rPPG), and corneal reflections that are not yet replicable by digital screens or AI.
    * **Hardware-Bound Identity:** Moving the "trust" away from just the face and toward the secure enclave/TPM of a physical device, ensuring the biometric check is tied to a specific piece of hardware.

---