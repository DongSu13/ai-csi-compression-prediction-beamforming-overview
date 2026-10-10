# CSI Compression, Prediction and Future Beam Selection

[中文](README.md) | [English](README.en.md)

This project explores joint channel state information (CSI) compression, future channel prediction and codebook beam selection under limited digital feedback and candidate scanning budgets.

This repository currently provides a project overview as an entry point for future public material. Source code, datasets, model weights and detailed experiment archives have not been released.

The source code is still being updated and will be made public at a later stage.

## Research Question

User equipment measures CSI and feeds it back to a base station. Feedback bandwidth is limited, and the channel changes with motion. The project studies how compressed historical information can support CSI reconstruction and prediction while selecting a small set of candidate beams for a future time.

The research considers feedback size, CSI reconstruction and prediction quality, candidate scanning cost and computation latency together.

## Method Overview

```text
UE: historical CSI → encoding and quantization → digital feedback packets
BS: parse feedback → causal history modeling
                     ├─ current CSI reconstruction
                     ├─ future CSI prediction
                     └─ future candidate beam selection
```

The project has evolved from independent baselines for the three tasks toward shared representations and multitask models. Research topics include multiscale quantized encoding, combining physical prediction with learned models, and joint training for beam utility.

Beam selection uses a fixed codebook, aiming to retain high received power with a limited number of candidate scans.

## Current Research Status

Simulation evaluations indicate that a shared model can improve future beam power retention over an adapted independent cascade with the same feedback and candidate scanning budgets, while introducing tradeoffs in future CSI prediction metrics.

The results apply to the evaluated simulation scenarios. Continuous execution still faces latency and queueing constraints. Real RF and real-time deployment validation have not been completed, and the results do not establish superiority across all three tasks.

## Related Public Resources

These resources provide relevant methods or simulation background. Listing them does not mean that this project distributes their code, data or models, or has reproduced all results from their papers.

- [CsiNet](https://github.com/sydney222/Python_CsiNet): learned CSI feedback.
- [CRNet](https://github.com/Kylin9511/CRNet): multiscale CSI compression networks.
- [OFSQ CSI Feedback](https://github.com/Smasko7/OFSQ_CSI_Feedback): ordered quantization and multiple feedback budgets.
- [WiFo](https://github.com/PKU-PCNI/WiFo): wireless channel prediction models.
- [QuaDRiGa](https://github.com/fraunhoferhhi/QuaDRiGa): wireless channel simulation tools.

## License

The original project overview currently included in this repository is licensed under the [MIT License](LICENSE). Papers, external code, datasets and models retain their respective licenses. This license does not cover unreleased project source code or external resources.
