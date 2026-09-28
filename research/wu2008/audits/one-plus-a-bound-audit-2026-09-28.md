# One-plus-a bound audit (2026-09-28)

Branch: `research/one-plus-a-bound-audit`.

This checkpoint audits the existing Li–Liu / Wu-style machinery for pushing below `1+1.9`. It is numerical reconnaissance, not a proof.

The repository already proves in `WSourceRevisedClosureBudget.lean` that the weaker 1.8938-oriented scalar closure follows from

`g234 + g5 + g6 >= 343/2500 = 0.1372`.

Using the certified nine-node vector `WSrcNineCertificate.z` and the exact repository definitions, high-accuracy numerical evaluation gives approximately:

- low H/h part of g234: 0.0200996802685
- seven-window `psiSevenPaid`: 0.0310294590365
- mapped full g234: 0.0511291393050
- fifth analytic-mass gain: 0.00110189034637
- conservative sixth gain: 0.0436587739340
- mapped total: 0.0958898035854
- deficit to 0.1372: 0.0413101964146

Counterfactual check: replacing `z` by the stronger historical `originalH` target (without claiming it is proved admissible) gives approximately:

- mapped g234: 0.0549625526574
- fifth analytic-mass gain: 0.00131692531048
- conservative sixth gain: 0.0519665198546
- mapped total: 0.108245997822
- deficit to 0.1372: 0.0289540021775

Strategic consequence: closing the current nine-row `originalH` matrix target is not sufficient by itself under the mapped producer set. The next phase should map missing/over-conservative gain sectors and quantify headroom before spending effort only on R2Matrix.

All numbers above must be replaced by rigorous interval/rational certificates before they can support a Lean theorem. No new Goldbach result is claimed here.
