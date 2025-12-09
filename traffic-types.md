# Traffic Types

### **1. Partially-Encrypted Traffic (PET)**

PET uses a **dual-phase encryption model** to keep data secure while still allowing RugPull validators to verify the performance and quality of the network.

#### **1.1 How PET Works**

* Traffic from the client to the validator is **encrypted**.
* The validator then performs a **TLS handshake** with the destination server.
* The validator re-encrypts and forwards the request using its own encryption keys.

This creates two secure channels:

1. **Client → Validator**
2. **Validator → Target Webserver**

#### **1.2 Benefits of PET**

PET allows the validator to:

* Measure node quality
* Validate bandwidth usage
* Prevent tampering across all routing segments
* Trace data lineage across the entire network

PET is essential for enforcing **proof of bandwidth** — a core requirement for fair reward allocation.

***

### **2. Fully-Encrypted Traffic (FET)**

FET is designed for users and applications that require **strict end-to-end privacy**, prioritizing confidentiality over validator analysis.

#### **2.1 How FET Works**

* Data is encrypted **from the client directly to the target server**.
* The validator acts only as a router — it cannot see request details, contents, or metadata.

#### **2.2 Benefits of FET**

* Highest level of privacy
* Ideal for sensitive or confidentiality-focused operations

#### **2.3 Trade-offs**

Because the validator cannot inspect or evaluate the session:

* It **cannot assess node quality**
* It **cannot verify traffic completeness or stability**
* Data reliability guarantees are lower
* FET traffic usually requires **higher gas usage** because it provides less utility to the network

This mode is most suitable when privacy is more important than validator-level verification.

***

### **3. Summary**

| Mode    | Encryption Level | Validator Visibility      | Reliability Guarantee | Gas Usage |
| ------- | ---------------- | ------------------------- | --------------------- | --------- |
| **PET** | Dual-phase       | Yes (bandwidth + quality) | High                  | Lower     |
| **FET** | End-to-end       | No                        | Medium–Low            | Higher    |
