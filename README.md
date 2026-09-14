# HUNTD (Web & Mobile) - Comprehensive Manual Testing Portfolio

## 📌 Project Overview
This repository contains the end-to-end functional manual testing artifacts and execution histories for the **HUNTD ecosystem, spanning both Web and Mobile platforms**. The main objective of this project was to establish quality assurance gates, validate platform-specific user acceptance criteria, and perform rigorous cross-platform defect management across multiple distinct test cycles.

---

## 🛠️ Tools & Methodologies Used
* **Test Management:** TestRail (Test case design, multi-run execution tracking, and metrics)
* **Defect Management:** Jira (Bug lifecycle tracking and reporting)
* **Frameworks & Methodologies:** Agile (Scrum/Kanban), Software Testing Life Cycle (STLC)
* **Testing Types:** Functional Web/Mobile Testing, Smoke Testing, Regression Testing, Black-Box Testing (Boundary Value Analysis & Equivalence Partitioning)

---

## 📊 Testing Artifacts & Deliverables

### 📋 1. Core Test Cases Datasets
The structural manual test suites designed for both environments can be viewed interactively in your browser without downloading:
* 🌐 **[Click here to view the Web Test Cases Suite](./huntd__web%20%281%29.csv)**
* 📱 **[Click here to view the Mobile Test Cases Suite](./huntd__mobile.csv)**

### 🔍 2. Execution History & Test Runs (CSV Format)
Access the live execution sheets tracking real results directly from our TestRail test cycles:
* 🧪 **[Test Run 1: Smoke Test - Web (100% Passed)](./test_run_1__smoke_test__web.csv)**
* 🧪 **[Test Run 2: Full Regression - Web (89% Passed)](./test_run_2__full_regression__web.csv)**
* 🧪 **[Test Run 4: Full Execution - Mobile MVP (88% Passed)](./test_run_4__full_execution__mobile_mvp.csv)**

---

## 📈 Key Project Metrics & Test Runs
The metrics below reflect the exact real-world results tracked within TestRail across the project life cycle:

### 🌐 1. Test Run 1: Smoke Test - Web
* **Objective:** Validate critical workflows and core paths of the Web system.
* **Total Executions:** 31 Test Cases
* **Status:** **100% Passed** (0 Defects Found) — Build verified as stable for deeper testing.

### 🌐 2. Test Run 2: Full Regression - Web
* **Objective:** Comprehensive 100% regression round covering all web environments and edge cases.
* **Total Executions:** 584 Test Cases
* **Passed:** 519 Test Cases (89% Pass Rate)
* **Failed:** 65 Functional Defects (11% Failure Rate) — Mapped and logged into Jira.

### 📱 3. Test Run 4: Full Execution - Mobile MVP
* **Objective:** Strict validation of native application core subset features (MVP scope restriction).
* **Total Executions:** 8 Test Cases
* **Passed:** 7 Test Cases (88% Pass Rate)
* **Failed:** 1 Critical Bug (13% Failure Rate) — Mobile chat communication input block.

---

## 🐛 Defect Reporting Standard (Jira Pattern)
To maintain top-tier industry standards, defects identified during execution cycles were documented in Jira using a rigorous technical format. Below are explicit engineering reports showcasing the logging standards for both platforms:

### 🌐 1. WEB PLATFORM EXAMPLE (From Test Run 2: Full Regression)
#### 🛑 BUG-001: Password field accepts 2 characters instead of 8-character minimum

* **Preconditions:**
  1. The user is on the HUNTD Web registration or password setup page.
  2. No active session is running in the current browser tab.

* **Steps to Reproduce:**
  1. Click on the "New Password" input field.
  2. Type a short password with only 2 characters (e.g., `12`).
  3. Click the form submission or "Save/Create" button.

* **Expected Result:**
  The system must reject the form, trigger an error, and display a validation message: *"Password must be at least 8 characters long"*.

* **Actual Result:**
  The system bypasses validation, accepts the 2-character input, and successfully processes the form request without any warnings.

* **Environment of Testing:**
  * **OS:** Windows 11 Home
  * **Browser:** Google Chrome (Latest Version)
  * **Resolution:** 1920x1080 (Desktop Viewport)

* **Priority:** High

* **Evidence:** [Link to Screenshot/Video Workflow](https://imgur.com/a/uVNfP9v)
---

### 📱 2. MOBILE PLATFORM EXAMPLE (From Test Run 4: Mobile MVP)
#### 🛑 BUG-MOB-001: Chat communication input field does not accept accented vowels

* **Preconditions:**
  1. The native mobile application is installed and opened.
  2. The user is logged into the application.
  3. The user has accessed the communication feature and opened an active chat conversation.

* **Steps to Reproduce:**
  1. Tap on the chat text input field to open the device's keyboard.
  2. Attempt to type words that contain accented vowels (e.g., "não", "você", "pensei", "avô").
  3. Observe the characters displayed within the input field.

* **Expected Result:**
  The text input field must accept and render all characters normally, including Portuguese accented vowels (á, é, í, ó, ú, â, ê, ô, ã, õ), matching standard text input behavior.

* **Actual Result:**
  The input field fails to combine dead keys/accents with vowels, preventing users from typing accented words correctly. It only accepts uncombined special characters isolated (e.g., typing results in "~", "^", or just "ç").

* **Environment of Testing:**
  * **Device:** Emulated Android Device (Medium Phone)
  * **OS:** Android 14.0 (API 34)
  * **Browser:** Google Chrome Mobile (inside the emulator)
  * **App Version:** N/A (Production Build 2026 / MVP Web)

* **Priority:** Medium

* **Evidence:** [Link to Screenshot/Video Workflow](https://imgur.com/a/cZu96Ds)
