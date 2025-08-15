# LLMConsent Standards

![Version](https://img.shields.io/badge/version-v1.0.0-blue)
![License](https://img.shields.io/badge/license-CC--BY--4.0-green)
![Status](https://img.shields.io/badge/status-active-success)

Open standards for decentralized AI consent management and data sovereignty.

## Overview

LLMConsent is an open protocol that establishes standards for managing consent between humans and AI systems. Like HTTP or TCP/IP, it provides a common language for AI systems to request permissions, manage data usage rights, and ensure user sovereignty over their data and AI representations.

### Key Principles

- **Decentralized**: No single entity controls the protocol
- **User Sovereign**: Users own and control their data and AI representations
- **Interoperable**: Any AI system can implement the standards
- **Verifiable**: Cryptographic proofs ensure consent authenticity
- **Economic**: Built-in compensation mechanisms for data providers

## Current Standards

### Core Standards (v1.0)

| Standard | Title | Status | Description |
|----------|-------|--------|-------------|
| [LCS-001](core/LCS-001.md) | Core Consent Standard | Final | Blockchain-based consent tokens for AI training and inference |
| [LCS-002](core/LCS-002.md) | Digital Twin Standard | Draft | User-owned persistent AI models and representations |
| [LCS-003](core/LCS-003.md) | Agent Permission Standard | Draft | Capability-based security for AI agent actions |
| [LCS-004](core/LCS-004.md) | Memory Sharing Standard | Draft | Secure memory pools for multi-agent collaboration |

### Extension Standards

Extensions are community-proposed standards that build on core functionality. See [extensions/README.md](extensions/README.md) for proposal guidelines.

## Quick Start

### For AI Developers

Implement LLMConsent in your AI system:

```solidity
// Check user consent before training
function trainModel(bytes32 dataHash) {
    require(
        llmConsent.checkConsent(msg.sender, dataHash, PERMISSION_TRAIN),
        "Training consent required"
    );
    // Proceed with training
}
```

### For Users

Grant consent for your data:

```javascript
// Grant inference-only consent
const consent = await llmConsent.grantConsent({
    dataHash: myDataHash,
    permissions: PERMISSION_INFER,
    duration: 86400, // 24 hours
    compensation: 0.001 // ETH per use
});
```

### For Platforms

Integrate the consent layer:

```python
# Verify consent before processing
def process_request(user_data):
    if not llm_consent.verify(user_data.hash, Permission.INFERENCE):
        raise ConsentRequired("User consent needed")
    return ai_model.process(user_data)
```

## Implementations

### Official Implementations

- [llmconsent-solidity](https://github.com/llmconsent/llmconsent-solidity) - Smart contracts (Ethereum/EVM)
- [llmconsent-py](https://github.com/llmconsent/llmconsent-py) - Python SDK
- [llmconsent-js](https://github.com/llmconsent/llmconsent-js) - JavaScript/TypeScript SDK

### Community Implementations

- Coming soon...

### Adoption Status

| Platform | Status | Standard Version | Notes |
|----------|--------|-----------------|--------|
| Example AI | Testing | v1.0.0 | Pilot program |
| Data Platform | Planning | v1.0.0 | Q2 2025 launch |

## Governance

LLMConsent is governed by an open community process:

- **Proposals**: Anyone can propose standards via LCP (LLMConsent Proposals)
- **Review**: Community review and feedback period
- **Approval**: Standards approved by rough consensus
- **Implementation**: Reference implementations required

See [CHARTER.md](CHARTER.md) for full governance details.

## Contributing

We welcome contributions! Please see:

- [PROCESS.md](PROCESS.md) - How to propose new standards
- [GitHub Issues](https://github.com/llmconsent/standards/issues) - Report issues or suggest improvements
- [Discussions](https://github.com/llmconsent/standards/discussions) - Community discussions

## Versioning

LLMConsent follows semantic versioning:

- **Major**: Breaking changes to core standards
- **Minor**: New features, backwards compatible
- **Patch**: Clarifications and fixes

Current version: **v1.0.0**

See [VERSIONS.md](VERSIONS.md) for version history.

## Resources

### Documentation
- [Standards Process](PROCESS.md)
- [Governance Charter](CHARTER.md)
- [Version History](VERSIONS.md)

### Community
- Website: [llmconsent.org](https://llmconsent.org)
- Discord: [Join our community](https://discord.gg/c2tjrZKcbR)
- Twitter: [@llmconsent](https://twitter.com/llmconsent)

### Technical
- [GitHub Repository](https://github.com/llmconsent/standards)
- [Reference Implementation](https://github.com/llmconsent/reference)
- [Test Suite](https://github.com/llmconsent/tests)

## License

All LLMConsent standards are licensed under [Creative Commons Attribution 4.0 International (CC-BY-4.0)](LICENSE).

## Contact

- **Author**: Subhadip Mitra
- **Email**: contact@subhadipmitra.com
- **Organization**: LLMConsent Standards Working Group

---

*LLMConsent - Building the consent layer for AI*