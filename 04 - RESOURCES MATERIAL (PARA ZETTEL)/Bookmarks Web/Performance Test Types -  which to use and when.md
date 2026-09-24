"Let's do a load test" is a common phrase, but there are several types of performance tests, each answering different questions. Using the wrong type can give a false sense of security — or waste time testing what doesn't matter.

This article explores the main types of performance tests and when to use each.

> The right test answers the right question. The wrong test gives false confidence.

## Overview

|Type|Question it answers|
|---|---|
|Load Test|Can the system handle expected load?|
|Stress Test|Where is the limit? What happens beyond it?|
|Soak Test|Is the system stable over long periods?|
|Spike Test|Can the system handle sudden spikes?|
|Scalability Test|Does the system scale linearly?|
|Configuration Test|Which configuration is best?|

## Load Test

### What it is

Simulates expected production load to validate that the system meets performance requirements.

### When to use

- Before important releases
- After significant changes
- To validate SLOs
- To establish baseline

### Typical profile

```
Users
    │
100 │          ┌──────────────────────┐
    │         ╱                        ╲
    │        ╱                          ╲
  0 │───────╱                            ╲───────
    └─────────────────────────────────────────────
         Ramp   │    Steady State    │   Ramp
         Up     │     (15-60 min)    │   Down
```

### Important metrics

- Latency (p50, p95, p99)
- Throughput
- Error rate
- Resource usage

### Example result

```
Load Test - 1000 users for 30 minutes
✓ Latency p95: 180ms (SLO: < 200ms)
✓ Error rate: 0.05% (SLO: < 0.1%)
✓ Throughput: 5,000 RPS (expected: 4,500 RPS)
```

## Stress Test

### What it is

Progressively increases load beyond expected to find the breaking point.

### When to use

- To discover real limits
- To understand how the system fails
- For capacity planning
- To identify bottlenecks

### Typical profile

```
Users
    │
    │                              ╱
    │                            ╱
500 │                          ╱ ← Breaking point
    │                        ╱
    │                      ╱
    │                    ╱
100 │──────────────────╱
    │                 ╱
  0 │────────────────╱
    └─────────────────────────────────────────────
         Increases progressively until failure
```

### Important metrics

- Saturation point
- Behavior under saturation
- Recovery after overload
- First symptoms of degradation

### Example result

```
Stress Test - Increasing until failure
✓ Performance stable up to 3,000 users
⚠ Degradation starts at 3,500 users (latency 2x)
✗ System fails at 4,200 users
→ Safe capacity: ~3,000 users
```

## Soak Test (Endurance Test)

### What it is

Maintains moderate load for long periods to identify problems that only appear over time.

### When to use

- To detect memory leaks
- To identify gradual degradation
- To validate stability
- Before major prolonged events

### Typical profile

```
Users
    │
100 │    ┌────────────────────────────────────┐
    │   ╱                                      ╲
  0 │──╱                                        ╲──
    └─────────────────────────────────────────────
              4-24 hours (or more)
```

### Important metrics

- Memory usage over time
- Latency over time
- Accumulated connections
- Unreleased resources

### Example result

```
Soak Test - 500 users for 12 hours
✓ Stable latency (variation < 5%)
⚠ Memory grew from 2GB to 3.5GB
✗ Memory leak detected: ~125MB/hour
→ Investigate leak before production
```

## Spike Test

### What it is

Simulates sudden and extreme load increases to validate behavior under spikes.

### When to use

- To simulate viral events
- To validate autoscaling
- To test circuit breakers
- Before marketing campaigns

### Typical profile

```
Users
    │
    │        ┌──┐
    │        │  │        ┌──┐
500 │        │  │        │  │
    │        │  │        │  │
    │   ┌────┘  └────────┘  └────┐
100 │───┘                        └───
    │
  0 │
    └─────────────────────────────────
            Sudden spikes
```

### Important metrics

- Autoscaling reaction time
- Errors during spike
- Recovery time
- Fallback behavior

### Example result

```
Spike Test - 10x traffic instantly
✓ System absorbed spike without failure
⚠ Latency rose to 800ms during spike (normal: 100ms)
✓ Recovery in 45 seconds after spike
⚠ Autoscaling took 90 seconds to react
```

## Scalability Test

### What it is

Tests whether adding resources results in proportional capacity increase.

### When to use

- To validate architecture
- For capacity planning
- To identify scalability bottlenecks
- Before infrastructure investments

### Typical profile

```
Throughput
    │
    │                    ╱ ← Ideal (linear)
    │                  ╱╱
    │                ╱╱
    │              ╱╱   ← Real
    │            ╱╱
    │          ╱╱
    │        ╱╱
    │      ╱╱
    └─────────────────────────
         Resources (instances)
```

### Important metrics

- Throughput per instance
- Scale efficiency
- Coordination overhead
- Diminishing returns point

### Example result

```
Scalability Test
1 instance:  1,000 RPS
2 instances: 1,900 RPS (95% efficiency)
4 instances: 3,600 RPS (90% efficiency)
8 instances: 6,400 RPS (80% efficiency)
→ Contention starts impacting with >4 instances
```

## Configuration Test

### What it is

Compares performance under different configurations to identify the ideal one.

### When to use

- To optimize settings
- To compare technologies
- To validate tuning
- To choose infrastructure

### Typical profile

Multiple identical tests with different configurations.

### Example result

```
Configuration Test - Connection pool

Pool size: 10
  Throughput: 1,000 RPS, Latency p95: 150ms

Pool size: 50
  Throughput: 2,500 RPS, Latency p95: 80ms ← Best

Pool size: 100
  Throughput: 2,400 RPS, Latency p95: 90ms

→ Optimal pool size: ~50 connections
```

## Choosing the Right Test

### Decision tree

```
What question do you want to answer?
│
├─ "Can it handle normal load?" → Load Test
│
├─ "What's the limit?" → Stress Test
│
├─ "Is it stable for hours?" → Soak Test
│
├─ "Can it handle spikes?" → Spike Test
│
├─ "Does it scale linearly?" → Scalability Test
│
└─ "Which config is best?" → Configuration Test
```

### Common combinations

**Before a release:**

1. Load Test (validates expected load)
2. Stress Test (knows limits)

**Before Black Friday:**

1. Load Test (baseline)
2. Spike Test (simulates spikes)
3. Soak Test (stability during event)

**After optimization:**

1. Configuration Test (compares before/after)
2. Load Test (validates improvement)

## Conclusion

Each test type answers specific questions:

|If you want to know...|Use...|
|---|---|
|If it meets requirements|Load Test|
|Where the limit is|Stress Test|
|If it's stable over time|Soak Test|
|If it handles spikes|Spike Test|
|If it scales well|Scalability Test|
|Which config is best|Configuration Test|

There's no "generic performance test". Choose consciously based on what you need to learn.

> A performance test without a clear objective is just tool exercise.