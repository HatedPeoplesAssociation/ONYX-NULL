# ONYX-NULL Test Result Format

Use this format when documenting important ONYX-NULL test results.

---

# Test Identification

```text
Test ID:

Test Name:

Category:

Status:

Date:

Tester:
```

---

# Target

```text
Prototype:

Mainboard Revision:

Hardware Revision:

NULL/OS Version:

Kernel Version:

Firmware Versions:

Application Versions:
```

---

# Purpose

Describe the property being tested.

---

# Security / Privacy Relevance

Explain why this test matters.

---

# Equipment

```text
Computer:

Multimeter:

Oscilloscope:

Logic Analyzer:

Network Equipment:

Other:
```

---

# Setup

Document the exact test setup.

Diagrams are encouraged.

---

# Procedure

1. Step one.
2. Step two.
3. Step three.

The procedure should be precise enough for another person to repeat.

---

# Expected Result

Document the expected behavior before evaluating the result.

---

# Observed Result

Document what actually happened.

Include measurements where applicable.

---

# Evidence

Potential evidence:

```text
Logs:

Screenshots:

Packet Capture:

Photographs:

Measurements:

Hashes:
```

---

# Result

Use exactly one:

```text
PASS

FAIL

BLOCKED

INCONCLUSIVE
```

---

# Notes

Document unusual behavior or limitations.

---

# Related Issues

```text
Issue:

Pull Request:

Commit:
```

---

# Retest Required

```text
YES / NO
```

If yes, explain why.
