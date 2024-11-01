# 🌐 AD4GD Data Trustworthiness Framework

This Data Trustworthiness Framework outlines a set of guidlelines for determining and translating data trustworthiness measures into metata. Designed to ensure that all datasets consumed and produced within the project adhere to the highest standards of trustworthiness and quality, it establishes a consistent methodology for assessing and documenting data quality.

## 📜 Overview

The Data Trustworthiness Framework is built to help users evaluate datasets against critical trustworthiness factors, allowing for robust decision-making and enhanced data interoperability. This framework adopts concepts from [QualityML](https://www.qualityml.org/):

| Element               | Description                                                                                      |
|-----------------------|--------------------------------------------------------------------------------------------------|
| **Completeness**      | Presence and absence of features, attributes, and their relationships.                          |
| **Logical Consistency** | Adherence to logical rules of structure, attribution, and relationships.                      |
| **Positional Accuracy** | Accuracy of feature positions within a spatial reference system.                               |
| **Temporal Quality**  | Accuracy of temporal attributes and relationships.                                               |
| **Thematic Accuracy** | Correctness of quantitative and non-quantitative attributes and classifications.                 |
| **Usability**         | Adherence to a dataset’s specific set of user requirements.                                      |
| **Metaquality**       | Quality statements about the evaluation itself and its results.                                  |
| **Certainty**         | Degree of confidence or likelihood in findings, predictions, or indicators.                      |

For each of these dimensions, we offer structured methods for documenting, validating, and maintaining dataset quality within AD4GD.

## 🛠️ Methodologies for Assessing Trustworthiness

The framework utilizes several methodologies for evaluating trustworthiness:

1.	Ground Truthing: Comparing datasets to known standards or trusted datasets.
2.	Data Lineage: Documenting the sources and process steps used to create the dataset.
3.	External Uncertainty Quantification: Addressing uncertainty from sources like sensor calibration.
4.	Published Research: Leveraging peer-reviewed studies to validate data or methodologies.
5.	User Feedback: Collecting insights from data users to continually refine and improve dataset quality.

Each of these methodologies is applied according to the specific needs and contexts of AD4GD datasets, allowing for a flexible yet comprehensive approach.

## 📚 Notebooks
1. [Creating Basic Dataset Metadata on Geonetwork using ISO19115](dataset_metadata_on_geonetwork/README.md)
