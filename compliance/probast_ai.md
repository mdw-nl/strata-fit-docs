### Table 2 – PROBAST+AI Compliance Status

| Domain      | Signaling Topic                                      | STRATA-FIT Implementation                                                                                 | Status               |
|-------------|-------------------------------------------------------|------------------------------------------------------------------------------------------------------------|----------------------|
| Participants| Privacy-preserving reporting of small N              | All statistical outputs mask low-frequency counts; orchestration restricts execution with few sites        | Implemented          |
|             | Local execution, no raw-data leakage                 | All operations occur locally; raw data never leaves institutional infrastructure                          | Implemented          |
|             | Representativeness / EPV justification               | EPV thresholds and representativeness analyses not yet standardized                                        | Not implemented      |
|             | Eligibility/flow description                         | Defined in WP2 deliverables and supported by cohort criteria and PRP input                                | Implemented          |
| Predictors  | Standardised definition and measurement              | Shared schema defines strict types, coding, and units across partners                                     | Implemented          |
|             | Measurement consistency across sites                 | Version-controlled schema files shared across sites                                                       | Implemented          |
|             | Missing data handling                                | Required fields enforced; missing visit detection present; no imputation logic yet                        | Partially implemented |
| Outcome     | Outcome definition and consistency                   | Computed using harmonized logic and aligned with clinical endpoints                                       | Implemented          |
|             | Adjudication / blinded assessment                    | Algorithmic outcome derivation; manual blinding not applicable                                             | Not implemented      |
|             | Censoring and class balance                          | Censoring handled; class imbalance not yet formalized                                                     | Not implemented      |
| Analysis    | Continuous variable processing                       | Descriptive stats and outlier detection pipelines implemented                                              | Implemented          |
|             | Categorical handling & privacy                       | Category-level results masked if below privacy threshold                                                   | Implemented          |
|             | Interval-censored survival modelling                 | Survival analyses based on harmonized intervals and consistent survival time logic                        | Implemented          |
|             | Differential privacy / noise injection               | Optional noise injection supported to reduce re-ID risk                                                   | Implemented          |
|             | Reproducibility: docker, CI, logs                    | All components containerized with fixed deps, automated tests, full logs and CI                           | Implemented          |
|             | Internal validation / testing                        | Mock nodes and synthetic tests verify federated integrity and output                                      | Implemented          |
|             | Fairness or subgroup performance                     | Subgroup fairness metrics not yet calculated across sites                                                  | Not implemented      |
|             | Calibration / discrimination                         | Planned but not yet executed in federated runs                                                             | Not implemented      |
|             | Encryption & key exchange                            | Encryption enforced by default with MFA for researchers/admins                                            | Implemented          |
