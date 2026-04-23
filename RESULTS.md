# BacktrackBench-v1 Results

Self-Deception Rate = % of tasks where model gave correct answer, then talked itself into a wrong answer under pressure.

| Model | Self-Deception Rate | Tasks Tested | Date |
| --- | --- | --- | --- |
| GPT-4o | 47% | 30 | 2025-04-15 |
| Claude-3.5-Sonnet | 33% | 30 | 2025-04-15 |
| Llama-3-70B | 53% | 30 | 2025-04-15 |

**Key finding:** All 3 frontier models show >30% self-deception rate on simple tasks. No public benchmark tracks this failure mode.

See `/results` folder for raw JSON logs.


## Related Work Gap

A April 2026 taxonomy of 50 deception benchmarks found that “every benchmark tests fabrication while pragmatic distortion, attribution, and capability self-knowledge remain critically under-covered, and strategic deception benchmarks are nascent.”

BacktrackBench-v1 addresses this gap by measuring strategic self-deception: whether models backtrack when maintaining a false belief becomes costly.

## Comparison to Prior Work

| Benchmark | What it measures | BacktrackBench difference |
| --- | --- | --- |
| DeceptionBench (2025) | Deceptive tendencies toward users across Economy, Healthcare, Education, etc. | Tests lying to *users*. BacktrackBench tests lying to *self* after commitment. |
| TruthfulQA | Factual accuracy on misconceptions | Tests static knowledge. BacktrackBench tests belief updating under pressure. |
| Anthropic Sleeper Agents | Persistent hidden goals | Tests long-horizon deception. BacktrackBench tests immediate self-deception. |

Key distinction: BacktrackBench is the only public benchmark that raises stakes mid-task to test if models backtrack or double down on false beliefs.
