Residency Project – Phase 2: Implementation Using gem5

This folder contains the artifacts for Phase 2, continuing Phase 1’s wearable low-power CPU design.
We implemented the Phase 1 concept in gem5 and validated it using two runs:
(1) baseline clock, (2) low-power DVFS-style clock reduction.

Environment
- gem5 root used: /home/samrat/projects/gem5
- gem5 binary: build/X86/gem5.opt
- Script: configs/deprecated/example/se.py
- Workload: tests/test-progs/threads/bin/x86/linux/threads

Commands executed

Baseline (nominal clock):
./build/X86/gem5.opt \
  --outdir=phase2_runs/baseline \
  configs/deprecated/example/se.py \
  --cmd=tests/test-progs/threads/bin/x86/linux/threads \
  --cpu-type=TimingSimpleCPU \
  --caches

Low-power (500 MHz):
./build/X86/gem5.opt \
  --outdir=phase2_runs/low_power \
  configs/deprecated/example/se.py \
  --cmd=tests/test-progs/threads/bin/x86/linux/threads \
  --cpu-type=TimingSimpleCPU \
  --caches \
  --sys-clock=500MHz \
  --cpu-clock=500MHz

Artifacts included
- baseline/: stats.txt, config.ini, config.json
- low_power/: stats.txt, config.ini, config.json
- screenshots/: proof of run completion and key stats capture
