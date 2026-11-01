# AgentInferAgent

**An Agent that controls the inference stage of an Agent-native system.**

AgentInferAgent forecasts traffic, routes by latency and cost objectives, selects serving policies, observes live behavior, and contains failures before an SLO breach reaches users.

用 Agent 托管推理：预测流量，按延迟与成本目标路由，选择服务策略，实时观测并在 SLO 违约影响用户前隔离故障。

## Agent loop

| Stage | Responsibility |
|---|---|
| Data | Requests, prompt lengths, modalities, tenants, and traffic events |
| Model | Candidate model versions and quality-cost profiles |
| Training | Offline calibration for routing and fallback policies |
| Inference | Batching, cache, quantization, speculation, and P/D scheduling |
| Harness | vLLM, SGLang, TensorRT-LLM, Kubernetes, and telemetry tools |
| Eval | TTFT, TPOT, throughput, hit rate, errors, and unit cost |

## System contract

- Keep latency, reliability, and cost SLOs explicit.
- Record enough evidence to explain every routing decision.
- Make degradation reversible and visible.

## Engineering principles

- Route by workload characteristics, not a global default.
- Optimize tail behavior as well as average throughput.
- Return runtime failures to harness and evaluation owners.

