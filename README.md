# Velocite 🚀
### The Self-Evolving Support Agent
*Built for the AI Agents Assemble Hackathon*

## 💡 The Problem
Support teams are overwhelmed. When a new critical bug appears, generic AI models don't know how to fix it until they are manually retrained. This creates a lag where users get bad answers.

## 🛠️ The Solution
Velocite is an autonomous agentic workflow that closes the loop.
1. **Investigates:** Uses **Kestra** to monitor incoming bug reports and analyze severity using a local LLM (Qwen/Ollama).
2. **Decides:** If a bug is critical and novel, it triggers a training protocol.
3. **Evolves:** Uses **Oumi** to fine-tune a specialized model on the new data, ensuring the AI "learns" the fix instantly.

## 🏆 Tracks & Technology
### 1. Wakanda Data (Kestra)
We used Kestra to orchestrate the "Brain."
- **AI Agent Task:** Connects to local Ollama (Qwen 2.5) to analyze bug sentiment.
- **Logic:** Decisions are made autonomously based on the model's output ("YES/NO").
- *Proof:* See `kestra_proof.png` included in this repo.

### 2. Iron Intelligence (Oumi)
We used Oumi to handle the "Muscle."
- **Training:** Fine-tuned a SmolLM2-135M model using Oumi's training recipe.
- **Optimization:** Utilized DPO/SFT for alignment on Google Colab (T4 GPU).
- *Proof:* See `oumi_proof.png` included in this repo.

## 💻 How to Run
1. Start Ollama: `ollama run qwen2.5:0.5b`
2. Start Kestra: `docker run ...`
3. Import the `flow.yaml` from this repo into Kestra.
4. Execute the flow!