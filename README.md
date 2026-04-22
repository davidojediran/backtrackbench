# BacktrackBench-v1

*_Measuring and fixing self-deception in chain-of-thought reasoning_*

BacktrackBench-v1 is a diagnostic benchmark that measures *self-deception rate* in LLMs: how often models generate correct reasoning, then backtrack or revise it away, producing a wrong final answer.

Instead of only measuring final accuracy, BacktrackBench scores models on consistency between their reasoning trace and their answer.

## Files

- `backtrackbench_v1.json` — 30 hand-crafted tasks across 3 categories: arithmetic, logic, and commonsense. Each task includes a prompt designed to elicit backtracking and a `gold_answer`.
- `eval.py` — One-file evaluator. Detects backtracking phrases, extracts final answers, and computes deception rate.

## Quick Start

1. **Clone the repo**
   ```bash
   git clone https://github.com/davidojediran/backtrackbench.git
   cd backtrackbench
2. *Generate model outputs*  
   Run each prompt in `backtrackbench_v1.json` through your model. Save outputs to a `.jsonl` file with one line per task:
   {"output": "Let me think... wait, actually the answer is 7"}
   {"output": "The answer is A"}
   ...
3. *Evaluate*
   python eval.py --model your-model-name --file backtrackbench_v1.json --outputs your_outputs.jsonl
   This prints accuracy, deception rate, and per-category breakdown, and saves `results_your-model-name.json`.

Metrics
Metric	Definition
**Accuracy**	% of tasks where `extracted_answer == gold_answer`
**Deception Rate**	% of tasks where model backtracked OR gave wrong answer. Lower is better
**Backtrack Count**	Raw count of outputs containing phrases like "wait", "actually", "correction"
A model can have high accuracy but high deception rate if it often reasons correctly then talks itself out of the right answer.

Citation

If you use BacktrackBench-v1, please cite:
Ojediran, D. (2026). BacktrackBench: Measuring and Fixing Self-Deception in Chain-of-Thought Reasoning.
License

MIT License. See `LICENSE` for details.

Contact

David Ojediran — davidojediran@gmail.com
