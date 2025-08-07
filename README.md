# 🔍 What Happens When You Sign Into Outlook (Microsoft 365 Desktop App)?

Ever wondered what’s happening under the hood when you log into **Outlook** on your computer?  
Here’s the step-by-step breakdown — from authentication to offline mailbox storage.

---

## **Phase 1: Sign-In & Authentication**

1️⃣ **Enter Your Credentials**  
- Email: `you@company.com`  
- Password: Your account password.  
- If MFA (Multi-Factor Authentication) is enabled → Verify via app, SMS, or call.

2️⃣ **Validation by Azure AD**  
Your credentials are sent securely to **Azure Active Directory**, where Microsoft checks:  
- ✅ Are you a valid user?  
- ✅ Is your password correct?  
- ✅ Does your device/location meet company sign-in policies?

3️⃣ **Conditional Access Check (If Enabled)**  
Admins may enforce:  
- MFA for new devices  
- Blocking legacy apps  
- Location-based login restrictions  
- Time-based login rules

4️⃣ **Secure Token Issuance**  
Once validated, Azure AD issues a **sign-in token** → Outlook uses this to communicate with Microsoft 365 services without repeatedly asking for your password.

5️⃣ **Connection to Exchange Online**  
Outlook connects to **Exchange Online** to load your mailbox, calendar, and contacts.

---

## **Phase 2: Cached Exchange Mode & OST File**

If **Cached Exchange Mode** is ON (default for most desktop users):

6️⃣ **Creation of Local Mailbox Copy**  
- Outlook creates an **Offline Storage Table (OST)** file to improve performance and allow offline access.

7️⃣ **OST File Location**  

```plaintext
C:\Users\<YourUsername>\AppData\Local\Microsoft\Outlook\
