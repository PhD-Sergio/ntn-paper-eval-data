# NTN LEO Satellite Routing Evaluation Data

This repository contains the raw evaluation data supporting the research paper on topological routing for LEO satellite networks.

## Overview

This dataset contains performance metrics for multiple routing algorithms evaluated across different LEO satellite constellation configurations. The evaluation was conducted using the [LEOPath](https://github.com/Fundacio-i2CAT/LEOPath) simulation framework.

## Constellations

- **Starlink**: 22 planes × 72 satellites = 1,584 satellites
- **OneWeb**: 18 planes × 36 satellites = 648 satellites  
- **Telesat**: 27 planes × 13 satellites = 351 satellites
- **Kuiper**: Various configurations
- **Dense Synthetic**: 72 planes × 72 satellites = 5,184 satellites

## Routing Algorithms

1. **Topological Routing** (proposed): Stateless, greedy forwarding based on topological addresses
2. **Link-State Shortest Path**: Traditional OSPF-like routing
3. **Predictive Link-State**: Link-state with prediction horizons (0m, 5m, 10m)
4. **Segment Routing**: Constrained segment lists (k=2, k=3)
5. **Traditional Segment Routing**: Segment routing variant

## ISL Scenarios

- **Ring**: 2 ISLs per satellite (intra-plane only)
- **+Grid**: 4 ISLs per satellite (intra-plane + inter-plane)

## Metrics

Each evaluation run produces:
- `timestep_metrics.csv`: Per-timestep metrics (forwarding state size, churn, stretch, compute time)
- `delta_metrics.csv`: Changes between consecutive timesteps
- `metadata.json`: Configuration and run parameters

### Key Metrics

| Metric | Description |
|--------|-------------|
| Forwarding State | Number of routing entries per satellite |
| Churn | Rate of next-hop changes between timesteps |
| Stretch | Ratio of actual path length to optimal path length |
| Compute Time | Wall-clock time to process each snapshot |

## Citation

If you use this data in your research, please cite:

```
@software{leopath_eval_data,
  author = {Sergio Giménez-Antón and Eduard Grasa and Jordi Perelló},
  title = {NTN LEO Satellite Routing Evaluation Data},
  year = {2026},
  url = {https://github.com/PhD-Sergio/ntn-paper-eval-data}
}
```

## Related Repositories

- [LEOPath](https://github.com/Fundacio-i2CAT/LEOPath) - LEO satellite routing simulation framework

## License

CC BY 4.0 - Creative Commons Attribution 4.0 International
