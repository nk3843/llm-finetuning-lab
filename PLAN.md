# llm-finetuning-lab — Plan

**Golden rule:** every phase ends with a result in the results table.
Never two half-finished experiments at once. Predict before every run.

## Phase 0: Concepts (1h)
**Goal:** explain LoRA and QLoRA without notes.
**Steps:** HF course ch.11 → LoRA paper (method only) → QLoRA paper (method only) → LoRA Without Regret post.
**Done when:** you can write W + (alpha/r)·BA from memory and say what each term does.
**Trap:** passive reading. After each section, explain it aloud first.

## Phase 1: Baseline eval (1h)
**Goal:** a number for the untuned model.
**Steps:** pick a narrow task with an automatic metric → split train/test → eval script → score the base model on 100-200 held-out examples.
**Done when:** the baseline is in results.md.
**Trap:** test examples leaking into training; unfair prompt format for the base model.

## Phase 2: Data + chat template (45m)
**Goal:** correct training inputs.
**Done when:** you can print one example showing the templated text and which tokens contribute to loss.
**Trap:** wrong template, missing EOS, training on prompt tokens.

## Phase 3: First LoRA run (1h)
**Goal:** SFTTrainer + LoRA on a free GPU, beat the baseline.
**Done when:** loss curve saved, adapter saved, eval score recorded.
**Trap:** reusing a full fine-tuning learning rate (loss barely moves); overfitting.

## Phase 4: Ablations (1h)
**Goal:** know which knobs matter.
**Steps:** vary rank, then LR, one at a time, with a written prediction first.
**Done when:** 4+ runs in the table, one-sentence takeaway each.
**Trap:** changing two things at once.

## Phase 5: Merge + inference (30m); optional QLoRA
**Done when:** merged model generates correctly; QLoRA memory difference noted.

## Phase 6: Break it on purpose (30m)
**Steps:** wrong template, train on full sequence, absurd LR.
**Done when:** one line per failure on how it showed up.

## Phase 7: Notes, repo, oral check (1.5h)
**Done when:** one-page cheat sheet, README with results table, 5 oral questions answered.

## Progress
- [ ] Phase 0 - [ ] Phase 1 - [ ] Phase 2 - [ ] Phase 3
- [ ] Phase 4 - [ ] Phase 5 - [ ] Phase 6 - [ ] Phase 7
- [ ] Recall check in 2-3 days
