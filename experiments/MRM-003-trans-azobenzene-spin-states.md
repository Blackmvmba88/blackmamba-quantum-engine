# MRM-003 — trans-Azobenzene Spin-State Map

Date: 2026-09-30  
Platform: Rowan Scientific  
Repository: Blackmvmba88/blackmamba-quantum-engine

## Objective

Establish the spin-state baseline for trans-azobenzene before coupling spin to vibrational, rotational, frequency, phase, polarization, or driven-dynamics hypotheses.

## Input geometry

The starting geometry was reused from the completed Rowan electronic-properties baseline:

- Workflow: `43e1423f-9316-4cb0-bc9d-0938f9d27151`
- Name: `BM Switch Bank — trans-Azobenzene electronic baseline`
- Status: `completed_ok`
- Charge: 0
- Initial multiplicity: 1
- SMILES: `c1ccc(/N=N/c2ccccc2)cc1`

## Electronic baseline

- HOMO: **-0.200491 Ha**
- LUMO: **-0.106539 Ha**
- HOMO-LUMO gap: **0.093952 Ha** (~**2.557 eV**)
- Dipole vector: **[0.000030, -0.004263, 0.002620]**

These values are the static electronic reference for the spin-state campaign.

## Rowan spin-state workflow

- Workflow UUID: `890974cf-a1dd-457f-ba89-f5067f923333`
- Name: `MRM-003 — trans-Azobenzene spin-state map`
- Workflow type: `spin_states`
- Method stack: **r2SCAN-3c//GFN2-xTB**
- Requested multiplicities: **1, 3, 5**
- Frequencies: false
- Transition-state mode: false
- Credit cap: **2**

## Completed states

| Multiplicity | State | Electronic energy (Ha) | Relative to singlet |
|---:|---|---:|---:|
| 1 | singlet | -572.605269 | 0.000 kcal/mol |
| 3 | triplet | -572.565212 | ~25.136 kcal/mol |

At this level of theory, the **singlet is lower than the triplet by ~25.14 kcal/mol**.

## Quintet status

The quintet geometry optimization completed at the GFN2-xTB optimization stage, but its final r2SCAN-3c single-point energy was not completed before the workflow stopped.

Therefore:

- **Do not report a final quintet energy.**
- **Do not treat the 1/3/5 map as complete.**
- The validated comparison from this run is **singlet vs triplet only**.

## Workflow termination

Rowan status: `stopped`

The run reached **2.03 credits charged** against a requested `max_credits=2` cap and stopped during the quintet single-point stage.

This is recorded as a **partial-but-scientifically-usable run**, not a completed three-state scan.

## Interpretation

The result is consistent with treating ground-state trans-azobenzene as a closed-shell singlet for the current Molecular Resonance Map baseline.

This does **not** establish excited-state dynamics, intersystem crossing rates, spin-orbit coupling, or a frequency-driven spin transition. Those require separate calculations and should not be inferred from this energy ordering alone.

## Next experiment

### MRM-004 — certified singlet/triplet closure

Run only multiplicities `[1, 3]` if an independently complete Rowan result object is needed.

Then continue toward:

1. vibrational frequencies on the relevant state,
2. normal-mode / torsional-coordinate mapping,
3. rotational and moment-of-inertia analysis,
4. electronic/vibrational transition matching,
5. eventual frequency + polarization + phase control hypotheses.

## Scientific rule

Spin is not treated as an arbitrary control knob.

For BlackMamba Molecular Lab, it enters the model only through physically defined quantities such as:

- spin multiplicity,
- energetic separation between spin surfaces,
- spin-orbit coupling,
- intersystem crossing,
- selection rules,
- and experimentally testable observables.

---

**BlackMamba Molecular Lab**  
Structure → Electronics → Spin → Dynamics → Tuning → Function
