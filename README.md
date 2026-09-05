# Peppol BIS Billing 3.0 & EN 16931 E-Invoice Engine — Python SDK

[![PyPI version](https://img.shields.io/pypi/v/stanzaapi-peppol-validator.svg)](https://pypi.org/project/stanzaapi-peppol-validator/)
[![Python Versions](https://img.shields.io/pypi/pyversions/stanzaapi-peppol-validator.svg)](https://pypi.org/project/stanzaapi-peppol-validator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> Sub-5ms Peppol BIS Billing 3.0 & EN 16931 e-invoice validation and XML-to-JSON parsing supporting OASIS UBL 2.1 and UN/CEFACT CII.

Official, zero-dependency Python 3.8+ client library for **Peppol BIS Billing 3.0 & EN 16931 E-Invoice Engine**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Intended for enterprise data pipelines, backend verification, and sub-5ms edge compute.

* 🌐 **Live Web Playground:** [Test your inputs online](https://stanzaapi.com/tools/peppol-validator)
* 📚 **API Documentation:** [View full schema on Stanza](https://stanzaapi.com/tools/peppol-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

```bash
pip install stanzaapi-peppol-validator
```

---

## 🚀 Quickstart

```python
import os
from stanzaapi_peppol_validator import PeppolValidatorClient

# Initialize client (api_key optional for local evaluation)
client = PeppolValidatorClient(
    api_key=os.getenv("STANZA_API_KEY")
)

# Execute deterministic validation
response = client.validate("<Invoice xmlns=\"urn:oasis:names:specification:ubl:schema:xsd:Invoice-2\">...</Invoice>")

if response.get("success"):
    print("Verification Success:", response["data"])
else:
    print("Validation Error:", response.get("error"), response.get("code"))
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "profile": "urn:fdc:peppol.eu:2017:poacc:billing:01:1.0",
    "invoice_number": "INV-2026-001"
  }
}
```

---

## ⚙️ Client Options

| Parameter | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `api_key` | `Optional[str]` | `os.getenv("STANZA_API_KEY")` | Your [Stanza API Key](https://stanzaapi.com). Required for production quotas. |
| `base_url` | `Optional[str]` | `"https://stanzaapi.com"` | API endpoint base URL. Custom endpoints supported for VPC enclaves. |
| `timeout` | `int` | `15` | Request timeout in seconds. |


---

## 🔗 Useful Links

* [Peppol BIS Billing 3.0 & EN 16931 E-Invoice Engine Interactive Sandbox](https://stanzaapi.com/tools/peppol-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/stanzaapi/peppol-validator-python)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).
