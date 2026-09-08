# Aircraft — Electric VTOL Research

> **Status: Concept and engineering research · No verified flight-test results**

This project investigates an electric vertical-takeoff-and-landing aircraft with a nose-mounted tilting electric ducted fan (EDF), a circular front intake, and rear vectored propulsion. The initial approximately **2 kg all-up-mass demonstrator** is a research target intended to produce data for future design decisions.

The longer-term ambition is to investigate larger aircraft. Scale-up depends on measured propulsion, structural, control, and energy performance; the small demonstrator is the first research step.

## Contents

- [The research problem](#the-research-problem)
- [Core aircraft concept](#core-aircraft-concept)
- [Proposed operating modes](#proposed-operating-modes)
- [Engineering architecture](#engineering-architecture)
- [Research questions](#research-questions)
- [Current development status](#current-development-status)
- [Validation plan](#validation-plan)
- [Development roadmap](#development-roadmap)
- [Repository purpose](#repository-purpose)

## The research problem

VTOL propulsion must provide lift during hover while allowing efficient forward flight. A tilting propulsion system also introduces mechanical loads, changing airflow, center-of-gravity constraints, and transition-control challenges.

The central question is whether a compact nose-mounted tilting EDF and rear vectored EDF can provide useful hover capability and a controllable transition to wing-borne flight within a realistic mass and power budget.

## Core aircraft concept

| Element | Current concept |
|---|---|
| Front intake | Circular nose intake adapted for subsonic EDF operation |
| Front propulsion | Electric EDF on a supported tilt mechanism |
| Rear propulsion | Main electric EDF with a changeable thrust direction |
| Airframe | Geometry developed around propulsion, mass distribution, and control needs |
| Flight control | Matek H743-WING V3 hardware reported available; ArduPilot Plane/VTOL is an intended direction |
| First demonstrator | Approximately 2 kg all-up-mass target, subject to a feasible mass budget |

Existing aircraft influenced the architectural thinking. Their propulsion systems, supersonic intake geometry, dimensions, and performance are not assumed to transfer to this electric prototype.

## Proposed operating modes

| Mode | Intended behavior | Main question |
|---|---|---|
| Hover | Front and rear systems direct thrust for vertical lift | Is there sufficient measured thrust and control authority? |
| Transition | Thrust directions change while aerodynamic lift develops | Can attitude and altitude remain controllable throughout the change? |
| Cruise | Wings carry more of the weight and propulsion provides forward thrust | What is the useful performance per unit of electrical energy? |

These are intended modes, not demonstrated flight capabilities.

## Engineering architecture

### Propulsion and intake

The front intake concept includes a rounded centerbody and a short, smooth duct. Earlier fan sizes, intake dimensions, and thrust estimates are preliminary. They require checks against actual fan operating points, losses, available inlet area, installation mass, and the complete aircraft budget.

### Tilt mechanism

The front EDF concept uses a cradle, two-sided bearing support, a shaft, an actuator/linkage, mechanical stops, and position feedback. Actuator selection depends on actual geometry and loads. A servo's advertised torque alone does not validate the mechanism.

### Power and control

The proposed electrical system includes battery power distribution, separate propulsion ESCs, a flight controller, tilt and door actuation, and suitable sensing. Cirkit Designer is being used to document the wiring direction. Detailed output mapping and flight-controller configuration remain to be established from the final hardware architecture.

### Instrumentation

Useful research data includes thrust, electrical power, current, voltage, RPM, temperature, tilt position, and—where practical—duct pressure or airflow. Optional future telemetry and additional sensing should follow a functioning core demonstrator.

## Research questions

1. How much thrust and electrical power does each installed EDF produce across its useful range?
2. What losses are introduced by the front intake and tilt positions?
3. How do mass distribution and thrust-line movement affect controllability?
4. Can the mechanism position the propulsion system accurately under realistic loads?
5. Does feeding front-EDF airflow toward the rear system improve total performance, or add losses?
6. Is the full mass and energy budget compatible with the intended flight sequence?

The front-to-rear airflow idea is an unproven hypothesis. Fans arranged in series must not be assumed to provide a free thrust increase.

## Current development status

- [x] Aircraft concept and research questions documented.
- [x] Initial propulsion, intake, tilt, and wiring directions recorded.
- [x] Matek H743-WING V3 and A2212 2450 KV motor reported available.
- [ ] Complete mass, power, and center-of-gravity budgets verified.
- [ ] Final EDF and actuator selections justified with data.
- [ ] CAD and structural calculations supplied to this repository.
- [ ] Instrumented propulsion and mechanism tests recorded.
- [ ] Integrated prototype and transition behavior demonstrated.
- [ ] Flight-test results available.

Available components do not establish a flight-ready aircraft. The A2212 motor is part of the experimentation context and is not declared the final EDF propulsion choice.

## Validation plan

Start with component and installation measurements before committing to an integrated flight configuration. Compare the rear EDF alone, front EDF alone, both operating independently, and any coupled-duct arrangement using the same measurement method. Record both total thrust and total electrical power, along with test conditions.

For the mechanism, document position accuracy, range, loading, temperature, vibration, and repeatability. Progress to an integrated demonstrator only after the mass budget, mechanical behavior, propulsion performance, and control approach are supported by evidence.

No numerical thrust, speed, endurance, or efficiency result is presented as measured in this repository.

## Development roadmap

| Phase | Focus | Completion evidence |
|---|---|---|
| 1 — Baseline | Requirements, budgets, and coordinate definitions | Consistent design brief and calculations |
| 2 — Bench research | Propulsion, intake, and tilt tests | Instrumented logs and comparisons |
| 3 — Integration | CAD, wiring, structure, and control interfaces | Reviewed demonstrator design |
| 4 — Demonstration | Progressive integrated validation | Repeatable operation and recorded results |
| 5 — Refinement | Use data to revise the design | Traceable comparison with the baseline |
| 6 — Scale research | Assess larger configurations | A justified scaling model and remaining limits |

## Repository purpose

This repository currently contains the research brief and editable `project.json`. CAD, fabrication files, flight-controller parameters, firmware, and measured test data have not been supplied here. As those materials become available, add their assumptions, versions, and validation evidence alongside them.

## Author

**Rohan Sashank Reddy**  
[GitHub](https://github.com/Rohansashankreddy07) · [LinkedIn](https://www.linkedin.com/in/rohan-sashank-reddy-chilukuri-aa169336a/) · [Instagram](https://www.instagram.com/rohansashankreddy/)

## Maintaining this repository

Keep this README and `project.json` aligned as the project develops. Record evidence when a planned feature becomes implemented or a target becomes a measured result. Preserve the project ID so future portfolio updates can link to the same project.
