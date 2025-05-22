# Model Context Protocol (MCP)

**MCP** is a lightweight framework that standardizes how ML models store and communicate their *context* — including training configuration, data lineage, hyperparameters, environment, and post-deployment metadata.

## 🚀 Features

- 🔍 Captures metadata during training
- 📦 Saves model + context in one archive
- 🧾 Auto-generates Model Cards
- 🔁 Reproducibility and audit support
- 🛡️ Governance-ready

## 📂 Components

- `context_builder.py`: Collects model context (dataset used, hyperparams, metrics, etc.)
- `mcp_protocol.py`: Defines how model context is stored, validated, and versioned
- `model_card_generator.py`: Converts context to readable format

## 💡 Sample Use-Case

```python
from mcp_protocol import MCP

mcp = MCP()
mcp.capture(model, X_train, y_train, config=training_config)
mcp.save("model_with_context.mcp")
