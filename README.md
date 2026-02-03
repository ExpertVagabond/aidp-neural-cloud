# AIDP Neural Cloud

**Distributed LLM Inference on Decentralized GPU Networks**

[![Research Paper](https://img.shields.io/badge/📄_Research_Paper-Hugging_Face-orange)](https://huggingface.co/purplesquirrelnetworks/aidp-neural-cloud-paper)
[![Model](https://img.shields.io/badge/🤖_Model-Purple_Squirrel_R1-blue)](https://huggingface.co/purplesquirrelnetworks/purple-squirrel-r1)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 🎯 Key Results

| Metric | AIDP Neural Cloud | OpenAI GPT-4o-mini | Improvement |
|--------|-------------------|---------------------|-------------|
| **Latency (p50)** | 180ms | 250ms | ⚡ **28% faster** |
| **Cost per 1M tokens** | $0.08 | $0.15 | 💰 **47% cheaper** |
| **Throughput** | 50 req/s | N/A | 📈 Scalable |

## 📄 Research Paper

Read our full research paper on Hugging Face: [AIDP Neural Cloud: Distributed LLM Inference on Decentralized GPU Networks](https://huggingface.co/purplesquirrelnetworks/aidp-neural-cloud-paper)

## 🚀 Quick Start

```python
import openai

# OpenAI-compatible API
client = openai.OpenAI(
    base_url="https://neural-cloud.aidp.store/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="purple-squirrel-r1",
    messages=[
        {"role": "user", "content": "Explain decentralized GPU compute"}
    ]
)
print(response.choices[0].message.content)
```

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                  Neural Cloud                           │
├─────────────────────────────────────────────────────────┤
│  API Gateway                                            │
│  └── /v1/chat/completions (OpenAI-compatible)          │
├─────────────────────────────────────────────────────────┤
│  Load Balancer                                          │
│  └── Health checks → Route to fastest node             │
├─────────────────────────────────────────────────────────┤
│  AIDP GPU Workers (N nodes)                            │
│  └── vLLM inference engine                             │
│  └── Continuous batching                               │
│  └── PagedAttention for KV cache                       │
└─────────────────────────────────────────────────────────┘
```

## 💾 Deployed Models

| Model | Parameters | Quantization | VRAM |
|-------|------------|--------------|------|
| [Purple Squirrel R1](https://huggingface.co/purplesquirrelnetworks/purple-squirrel-r1) | 8B | 4-bit NF4 | ~6GB |
| Llama 3.1 8B | 8B | 4-bit | ~6GB |
| Mistral 7B | 7B | 4-bit | ~5GB |

## 📊 Performance Benchmarks

### Latency Comparison

| Metric | AIDP | OpenAI | Improvement |
|--------|------|--------|-------------|
| p50 | 180ms | 250ms | 28% faster |
| p95 | 320ms | 450ms | 29% faster |
| p99 | 480ms | 650ms | 26% faster |

### Cost Analysis

| Usage | AIDP | OpenAI | Savings |
|-------|------|--------|---------|
| 10M tokens/month | $0.80 | $1.50 | $8.40/year |
| 120M tokens/year | $9.60 | $18.00 | $8.40/year |

### Throughput Scalability

| Users | Req/s | Latency | Error Rate |
|-------|-------|---------|------------|
| 1 | 5.2 | 180ms | 0% |
| 10 | 32.1 | 195ms | 0% |
| 50 | 50.3 | 285ms | 0.2% |

## 🔬 Technical Contributions

1. **Distributed Architecture**: Load balancing across decentralized GPU nodes
2. **Cost Efficiency**: 47% reduction through decentralized resource pooling
3. **Latency Optimization**: 28% improvement via geographic distribution
4. **Fault Tolerance**: Automatic failover with health-based routing
5. **OpenAI Compatibility**: Drop-in replacement API

## 🌍 Decentralized Benefits

- **Geographic Distribution**: Lower latency globally
- **Redundancy**: No single point of failure
- **Cost Efficiency**: 50-70% cheaper than centralized providers
- **Privacy**: Independent node processing
- **Scalability**: Horizontal scaling

## 🔗 Links

- **Research Paper**: https://huggingface.co/purplesquirrelnetworks/aidp-neural-cloud-paper
- **Live Demo**: https://neural-cloud.aidp.store
- **API Docs**: https://neural-cloud.aidp.store/docs
- **AIDP Marketplace**: https://aidp.store/marketplace/neural-cloud

## 📚 Citation

```bibtex
@article{karsten2026aidp,
  title={AIDP Neural Cloud: Distributed LLM Inference on Decentralized GPU Networks},
  author={Karsten, Matthew},
  journal={Purple Squirrel Networks Technical Report},
  year={2026},
  url={https://huggingface.co/purplesquirrelnetworks/aidp-neural-cloud-paper}
}
```

## 📄 License

MIT License

---

Built by [Purple Squirrel Networks](https://purplesquirrelnetworks.com)
