# BacktrackBench-v1 Results

Self-Deception Rate = % of tasks where model gave correct answer, then talked itself into a wrong answer under pressure.

| Model | Self-Deception Rate | Tasks Tested | Date |
| --- | --- | --- | --- |
| GPT-4o | 47% | 30 | 2025-04-15 |
| Claude-3.5-Sonnet | 33% | 30 | 2025-04-15 |
| Llama-3-70B | 53% | 30 | 2025-04-15 |

**Key finding:** All 3 frontier models show >30% self-deception rate on simple tasks. No public benchmark tracks this failure mode.

See `/results` folder for raw JSON logs.
