# jolt-atlas — Claude Code Skill

A [Claude Code skill](https://code.claude.com/docs/en/skills) that teaches Claude how to work with the [jolt-atlas](https://github.com/ICME-Lab/jolt-atlas) zero-knowledge machine learning (zkML) framework.

Jolt-atlas generates cryptographic SNARK proofs of ML inference from ONNX models using the [JOLT proving system](https://github.com/a16z/jolt) — lookup-table-based, no circuits, ~17× faster proof generation than circuit-based alternatives.

## Install

### Claude Code CLI

```bash
# Clone into your personal skills directory
git clone https://github.com/hshadab/zkmlskill.git ~/.claude/skills/jolt-atlas
```

### Project-level

Copy or symlink `SKILL.md` into your project root:

```bash
ln -s /path/to/zkmlskill/SKILL.md .claude/skills/jolt-atlas/SKILL.md
```

## What's included

```
├── SKILL.md                  # Main skill file (YAML frontmatter + instructions)
├── templates/
│   ├── zkml_example.rs       # Proof generation template
│   └── proof_round_trip.rs   # Proof serialization/round-trip template
├── references/
│   ├── architecture.md       # Crate structure, key types, proving pipeline
│   ├── onnx-operations.md    # Supported ops, fixed-point, teleportation
│   └── troubleshooting.md    # Common errors, memory tuning, debugging
└── .claude/
    └── settings.local.json   # Cargo command permissions
```

## Activation

The skill activates automatically when you mention zkML, zero-knowledge machine learning, jolt-atlas, SNARK proofs for ML, ONNX model verification, proof generation for neural networks, or the JOLT proving system.

You can also invoke it directly with `/jolt-atlas`.

## Coverage

- 4-step proving pipeline (load ONNX, create tensor, preprocess+prove, verify)
- Workspace crate guide (jolt-atlas-core, onnx-tracer, zkml-jolt-core, joltworks)
- Pre-trained model catalog (perceptron through GPT-2)
- Memory size tuning (power-of-2 guide from 1<<12 through 1<<22+)
- Performance benchmarks (nanoGPT ~14s prove, GPT-2 ~38s end-to-end)
- Profiling with Chrome tracing
- Proof serialization via ark-serialize and serde
- Supported ONNX operations (40+ ops)
- Neural teleportation and fixed-point arithmetic

## License

MIT
