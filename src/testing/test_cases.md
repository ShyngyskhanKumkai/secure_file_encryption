# Test Cases for Secure Messaging System

## Test Case 1 — User Registration
**Purpose:** verify account creation  
**Steps:**
1. Open registration page
2. Enter username + password
3. Click signup
**Expected:** user added to database  
**Actual:** works as expected  

---

## Test Case 2 — Login Authentication
**Purpose:** ensure login works  
**Steps:**
1. Enter valid credentials
2. Press login
**Expected:** redirected to dashboard  
**Actual:** OK  

---

## Test Case 3 — AES-128 Message Encryption
**Purpose:** verify encryption algorithm  
**Steps:**
1. Input: "hello world"
2. System encrypts using AES-128
**Expected:** ciphertext != plaintext  
**Actual:** OK  

---

## Test Case 4 — AES-128 Decryption
**Purpose:** verify decrypt()  
**Steps:**  
1. Take ciphertext  
2. Decrypt  
**Expected:** original text returned  
**Actual:** OK  

---

## Test Case 5 — Password Hashing (SHA-256)
**Purpose:** ensure correct hashing  
**Steps:**
1. Create password
2. Hash using SHA-256
**Expected:** string of length 64  
**Actual:** OK  

---

## Test Case 6 — Input Validation
**Purpose:** check that XSS/SQLI blocked  
**Steps:**
1. Try input `<script>`
2. Try `' OR 1=1`
**Expected:** rejected  
**Actual:** OK  

---

## Test Case 7 — API /encrypt route
**Purpose:** check API response  
**Steps:**
1. Send POST to `/encrypt`
2. Body: JSON {"text": "abc"}
**Expected:** {"ciphertext": "..."}  
**Actual:** OK  
