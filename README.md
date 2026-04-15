# Welcome Robot & Security Robot Documentation

## Table of Contents

1. [Introduction](#1-introduction)
2. [Chapter 1 – Welcoming Robot (Reception)](#chapter-1--welcoming-robot-reception)
3. [Chapter 2 – Security Robot (Surveillance & Alert)](#chapter-2--security-robot-surveillance--alert)
4. [Privacy & Data Retention](#3-privacy--data-retention-both-robots)
5. [Troubleshooting](#4-troubleshooting)
6. [Support Contacts](#5-support-contacts)

---

## 1. Introduction

This facility uses **two separate autonomous robots** with distinct roles:

| Robot | Location | Primary function |
|-------|----------|------------------|
| **Welcoming Robot** | Main reception area | Greet visitors, provide information, answer questions |
| **Security Robot** | Hallways, restricted zones, entrances | Detect unknown persons, monitor behavior, trigger visual and sound alerts |

> **Important:** The two robots do not share real-time data except for basic face recognition logs. The Welcoming Robot does **not** trigger security alerts. The Security Robot does **not** give directions or company information.

---

# Chapter 1 – Welcoming Robot (Reception)

## 1.1 Overview

The **Welcoming Robot** is designed to assist visitors and employees at the main reception. It provides a friendly, personalized experience without any security alert functions.

## 1.2 Hardware & Interface

- **Camera:** Face detection only (no continuous surveillance)
- **Screen:** Touchscreen for displaying text information
- **Microphone & Speaker:** Voice interaction
- **Local database:** Stores names, interests, departments, certifications, international recognitions

## 1.3 Face Detection – Important Notes

- The robot detects your face to recognize you.
- **Hats** can reduce detection accuracy. Please remove your hat if the robot does not recognize you.
- Glasses do **not** affect accuracy.
- Poor lighting may also reduce accuracy.

## 1.4 Known Visitor Experience

**Condition:** Your face is pre-registered in the Welcoming Robot's database.

| Step | Description |
|------|-------------|
| 1 | Robot detects your face and identifies you |
| 2 | Robot greets you: *"Good morning [Name], welcome back."* |
| 3 | Robot checks your recorded interests |
| 4 | Robot offers: *"There is a new innovation report. Would you like to see it?"* |
| 5 | You can ask questions (see table below) |
| 6 | All interactions are logged (date, time, requests) |

### Available queries for known visitors:

| You ask | Robot response |
|---------|----------------|
| *"Where is the R&D department?"* | Gives **voice directions only** (no map): *"The R&D department is on the second floor, third door on the left."* |
| *"Where is the HR department?"* | *"HR is on the first floor, straight ahead past the coffee machine."* |
| *"Tell me about innovation history"* | Recites company milestones (e.g., *"In 2022, we launched our first AI logistics platform..."*) |
| *"I am looking for a job"* | Lists open positions and offers to send details by email |

## 1.5 Unknown Visitor Experience (Welcoming Robot Only)

If your face is **not** in the Welcoming Robot's database:

| Step | Description |
|------|-------------|
| 1 | Robot detects an unknown face |
| 2 | Robot remains polite: *"Hello, you seem new. How can I help you?"* |
| 3 | Robot provides basic information (directions, company facts) |
| 4 | Robot **does not** trigger any security alert |
| 5 | Robot **does not** save snapshots for security purposes |

> ✅ The Welcoming Robot is **not a security device**. Unknown visitors receive normal assistance.

## 1.6 Language & Voice Interaction

The Welcoming Robot automatically detects your language.

**Supported languages:** English, French, Spanish, German

### Voice commands:

| You say | Robot response |
|---------|----------------|
| *"I don't see"* | Repeats the last message more slowly |
| *"Repeat that"* | Repeats the last information |
| *"Speak slower"* | Reduces speaking speed |
| *"Show me on screen"* | Displays text information on the touchscreen |

## 1.7 Innovation History

The Welcoming Robot contains a full timeline of company innovations.

**To access:** Say *"Tell me about innovation history"*

**Example output:**  
> *"In 2022, we launched our first AI-driven logistics platform. In 2024, we received the International Innovation Award. In 2025, we opened our R&D center in Singapore."*

---

# Chapter 2 – Security Robot (Surveillance & Alert)

## 2.1 Overview

The **Security Robot** is deployed in hallways, near restricted zones, and at secondary entrances. Its only mission is **security**: detect unknown persons, monitor behavior, and trigger visual and sound alerts. It **does not** provide directions, company information, or job assistance.

## 2.2 Hardware & Interface

- **Camera:** Continuous face detection and recording
- **No touchscreen** – voice interaction only (limited)
- **Microphone & Speaker:** Basic voice responses
- **Sounder:** Can emit an audible alert tone
- **Security backend:** Saves snapshots and logs events

## 2.3 Face Detection – Important Notes

- The robot continuously scans for faces.
- **Hats** can reduce detection accuracy. The robot may ask you to remove your hat.
- Glasses do **not** affect accuracy.
- If a face cannot be detected after 10 seconds, the robot logs a "hidden face" event.

## 2.4 Known Visitor Experience (Security Robot)

**Condition:** Your face is pre-registered in the Security Robot's database.

| Step | Description |
|------|-------------|
| 1 | Robot detects your face and identifies you as authorized |
| 2 | Robot **does not** say "access granted" |
| 3 | Robot treats you like an **unknown visitor** by default (see section 2.5) |
| 4 | However, because you are known, the robot's behavior is **less aggressive** |
| 5 | Robot logs your presence (date, time, location) |
| 6 | No sound alert is triggered |

> **Important:** Even known visitors are treated similarly to unknown visitors. The only difference is the **absence of aggressive behavior and sound alert**.

## 2.5 Unknown Visitor Experience (Security Robot)

**Condition:** Your face is **not** in the Security Robot's database.

### Step-by-step flow:

| Step | Description |
|------|-------------|
| 1 | Robot detects an unknown face |
| 2 | Robot says: *"Hello. Please identify yourself to reception."* |
| 3 | Robot starts **continuous snapshot capture** (1 image per second) |
| 4 | Robot observes visible behavior (see below) |
| 5 | If behavior is normal → no alert, but presence is logged |
| 6 | (If behavior is suspicious → robot becomes more aggressive and triggers a sound alert) |

### Suspicious behavior definition:

- Turning face away from camera repeatedly
- Staying more than 60 seconds without moving toward an authorized area
- Trying to cover or hit the camera
- Entering a restricted zone
- Not responding to the robot's voice commands

### Aggressive behavior (unknown + suspicious):

| Action | Description |
|--------|-------------|
| 1 | Robot raises its voice: *"Security has been alerted. Stay still."* |
| 2 | Robot emits a **loud sound alert** (audible tone) |
| 3 | Security team receives an **email** and **internal notification** |
| 4 | A **snapshot** of the unknown person is saved |
| 5 | The robot continues recording until security arrives |

### Normal behavior (unknown but compliant):

| Action | Description |
|--------|-------------|
| 1 | Robot says: *"Please go to the reception desk to register."* |
| 2 | Robot logs the presence but does not trigger a sound alert |
| 3 | No aggressive tone is used |

---

## 3. Privacy & Data Retention (Both Robots)

- **Facial data** is stored locally on each robot separately.
- **Welcoming Robot data** is not shared with the Security Robot (except for basic name/face registration if explicitly configured).
- **Voice recordings** are not saved; only transcribed text is logged (Welcoming Robot only).
- You may request deletion of your data by contacting privacy@company.com.

---

## 4. Troubleshooting

| Problem | Robot involved | Likely cause | Solution |
|---------|----------------|--------------|----------|
| Robot does not recognize me | Welcoming | Hat or poor lighting | Remove hat, stand in better light |
| Robot does not recognize me | Security | Hat or poor lighting | Remove hat, stand still for 5 seconds |
| Welcoming Robot gives wrong directions | Welcoming | Database error | Contact support.tech@company.com |
| Security Robot triggers sound alert for no reason | Security | Fast movement or hat | No action needed; security will verify |
| Security Robot does not speak | Security | Volume too low | Contact security team |
| Welcoming Robot does not answer | Welcoming | Microphone blocked | Check that nothing covers the top |

---

## 5. Support Contacts

| Issue type | Robot | Contact | Response time |
|------------|-------|---------|----------------|
| Technical malfunction | Welcoming | support.tech@company.com | 4 hours |
| Technical malfunction | Security | security.tech@company.com | 2 hours |
| Database update request | Both | hr.database@company.com | 24 hours |
| Privacy / data removal | Both | privacy@company.com | 48 hours |
| Emergency (robot blocking exit) | Both | Call security desk: 555-0199 | Immediate |

---

## End of Documentation
