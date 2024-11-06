# Improving support for Functional Data in ClinVar
Here we present our prototypes to improve submission and reporting of functional data for genetic variants. We welcome feedback from both submitters and users of this data; your input will help us to develop solutions best suited for the clinical genetics community.  
- [Submission templates](submission/SubmissionTemplate_functional_data_empty.xlsx)
- [Example submissions](submission)
- [XSDs](xsd)
- [Sample XMLs](reporting)

IMPORTANT: The prototypes are based on studies that have been submitted to ClinVar. However, NCBI staff have filled in the prototypes using data available within the ClinVar submission or in a publication, without consulting the submitters of the data. The prototypes are for testing and providing feedback only! Do NOT incorporate this data into your production system.

## Background
Almost 50% of variants in ClinVar are variants of uncertain significance (VUS). Experimental studies that demonstrate the effect of a variant on the gene or gene product provide a critical type of evidence for classification of variants. Because of the importance of these data, many assays are being developed, often at scale. While these data are often published, it can be time-consuming to search the literature for relevant assays for a variant of interest. Additionally, functional data is sometimes generated as part of clinical testing and never published. ClinVar is improving the way functional data are submitted and reported in ClinVar so that these data are easier to find and fewer variants are classified as uncertain.
The improvements in ClinVar will support assays that measure the effect of a variant on the transcript or protein function, as well as animal models. These improvements will accommodate datasets of any size, from an experiment on a single variant to a MAVE (multiplexed assay of variant effects) with data for thousands of variants. Functional data may be submitted to ClinVar on its own, without a classification of the variant for disease. Alternatively, if the submitter generated functional data to inform their variant classification, the functional data may be submitted as part of the evidence for the submitter’s classification. 
Here we present our prototypes to improve submission and reporting of functional data for genetic variants. We welcome feedback from both submitters and users of this data; your input will help us to develop solutions best suited for the clinical genetics community.

## Submission
Initially we will update the Excel spreadsheet templates for submissions of functional data. Support for the API and online submissions forms will be added later. Several examples are provided to illustrate different types of functional data that may be submitted. We welcome interested submitters to test the templates by filling in their own data.  

### Submission of functional data only, no classification
Functional data may be submitted on its own, without a classification. This type of submission is appropriate for any experiment, including MAVEs, where only the functional result is reported and there is not a comprehensive review of evidence to provide a variant classification for disease. We propose [a new template](submission/SubmissionTemplate_functional_data_empty.xlsx)
 for this scenario.  

Example 1: [RNASeq to evaluate the effect of an intronic FAS variant on splicing](submission/SubmissionTemplate_functional_data_with_RNASeq.xlsx)  
This example represents the result of a single assay performed on a single variant. In this example, the submission is only functional data; it is based data on a public record ([SCV000863424.2](https://www.ncbi.nlm.nih.gov/clinvar/variation/598753/?oq=SCV000863424)) that includes functional data and a classification.

Example 2: [an in vitro assay to measure the effect of a BRCA1 coding variant on cell survival](submission/SubmissionTemplate_functional_data_with_BRCA1.xlsx)  
This example represents results of a single assay performed on several variants. It is based on data in [a much larger dataset in ClinVar from a MAVE](https://www.ncbi.nlm.nih.gov/clinvar/submitters/506636/).

Example 3: [An animal model (zebrafish) to determine the effect of a PIP5K1C coding variant on development](submission/SubmissionTemplate_functional_data_with_animal_model.xlsx)  
This example represents the result of two experiments (an in vitro assay and an animal model) performed on a single variant. In this example, the submission is only functional data; it is based data on a public record ([SCV001736859.2](https://www.ncbi.nlm.nih.gov/clinvar/variation/1172539/?oq=SCV001736859.2)) that includes functional data and a classification.

### Submission of functional data to support a classification
In some cases, functional data are generated to help a laboratory classify a specific variant. For this case, functional data may be submitted as part of the evidence for a classification that is submitted to ClinVar. We propose to update the full template for germline variants for this scenario.  
At this time, we are not updating the full template for somatic variants to accept functional data. This enhancement may be added in the future. If needed, a workaround is to submit somatic classifications using the somatic template and use the functional data template to submit the functional data separately.  

Example 4: [RNASeq to evaluate splicing, as part of the evidence for an intronic VPS51 variant](submission/SubmissionTemplate_classification_with_functional_data.xlsx)

## Aggregation and Reporting
We are updating the ClinVar XML files, for both VCV and RCV records, to better represent functional data. Several examples are provided to illustrate different scenarios for aggregate records.  

Notes for RCV records:  
Submissions with only functional data may indicate the disease context for the data. In the XML, this disease will be stored in the same element that is used for the condition for the classification, the TraitSet for the ClinVarAssertion. This will allow submissions for the same disease to be aggregated together, whether there is a classification or only functional data. Submitters of functional data may indicate different disease contexts, which would be aggregated into different RCV records. For this reason, the VCV record will be used to find all functional data for a variant, regardless of the disease context, as it is used to find all classifications for a variant regardless of the disease for the classification.  
The field for disease context for functional data is required in submission; if the submitter does not wish to provide this information, they must enter “not provided” as the disease context. These submissions will aggregate with other submissions for the variant which may have a classification but where the disease was “not provided”.

VCV (variant) XSD: ClinVarVCV  
- [Proposed XSD](xsd/ClinVarVCV_functional_data.xsd)
- [Diff of changes](xsd/ClinVarVCV_diff.html)  

RCV (variant-disease) XSD: ClinVarRCV  
- [Proposed XSD](xsd/ClinVarRCV_functional_data.xsd)
- [Diff of changes](xsd/ClinVarRCV_diff.html)

| Example | Description | VCV XML | RCV XML* |
|---------|-------------|---------|---------|
|Example 5: A variant with a germline classification from one submitter, and a submission of only functional data from a second submitter|In Example 5, the variant has two submissions, one with a germline classification and one with only functional data, no classification. The aggregate classification is based only on the submission with a germline classification. Submissions with only functional data do not contribute to the aggregate classification.<br>This example also includes an assertion for the strength of the evidence for the functional data in a new, proposed element StrengthMappingList. Read more about this feature [below](#strength-of-the-evidence).|[Example 5 VCV XML](reporting/VariationID_868615_VCV_one_germline_one_functional_data.xml)|[Example 5 RCV XML](reporting/VariationID_868615_RCV_functional_data_only.xml)|
|Example 6: A variant submitted with only functional data, no classification|In Example 6, the variant has a single submission that includes only functional data so there is no classification of the variant. We propose a new element, NoClassification, at the same level as GermlineClassification, for aggregate records that have evidence like functional data but no classification.|[Example 6 VCV XML](reporting/VariationID_2687784_VCV_with_only_functional_data.xml)|[Example 6 RCV XML](reporting/VariationID_2687784_RCV_with_only_functional_data.xml)|
|Example 7: A variant with a submission that includes a germline classification, and has both clinical data and functional data as the evidence|In Example 7, the variant has a single submission that includes a germline classification. Two observations are provided as the evidence, one with clinical data and the second with functional data (RNAseq). We propose adding an attribute of Type=”Functional” to the ObservedIn element to indicate an observation of functional data.|[Example 7 VCV XML](reporting/VariationID_2691776_VCV_one_submission_with_both_germline_and_functional.xml)|[Example 7 RCV XML](reporting/VariationID_2691776_RCV_one_submission_with_both_germline_and_functional.xml)|
|Example 8: A variant with two submissions, where both submissions include a germline classification and both submissions have clinical data and functional data as the evidence|In Example 8, the variant has two submissions; both submissions have a germline classification with clinical and functional data provided as the evidence. We propose that we will not provide any aggregate value for functional data when there are multiple results reported to ClinVar. In other words, we will not calculate an overall functional status like “functional” or “non-functional” or “conflicting reports of function” for the variant. There will be no aggregate value for functional data in the XML; the summary section on VCV web pages (mock-up to be posted) will simply indicate that there is functional data available for the variant.|[Example 8 VCV XML](reporting/VariationID_2691774_VCV_two_submissions_with_both_germline_and_functional.xml)|[Example 8 RCV XML](reporting/VariationID_2691774_RCV_two_submissions_with_both_germline_and_functional.xml)|
|Example 9: A variant with one submission with a germline classification, one submission with an oncogenicity classification, and one submission with only functional data|In Example 9, the variant has three submissions. One submission has a germline classification; the second has an oncogenicity classification; and the third has no classification, only functional data which is relevant for this variant in the somatic context for cancer. This example illustrates that functional data will not be submitted with a somatic classification. Submitters who have functional data relevant for somatic variants and cancer should submit their somatic classifications and functional data in separate submissions. We may add support for submitting functional data as part of the evidence for a somatic variant classification in the future|[Example 9 VCV XML](reporting/VariationID_635390_VCV_oncogenicity_germline_functional_data.xml)|[Example 9 RCV XMLs](reporting/VariationID_635390_RCV_oncogenicity_germline_functional_data.xml)|  

\* A VCV can be mapped to multiple RCVs. Only RCVs with functional data are shown here. RCVs without functional data will have no changes, thus are omitted for clarity.

### Variant, or VCV, pages
We will also update the VCV web pages; mock-ups that correspond to the examples for submission and XML will be posted soon.

## Strength of the evidence

Some groups, including expert panels and some of the data generators for functional data, may want to provide assertions for the strength of the evidence for functional assays. For example, an expert panel may indicate that the result of an assay can be considered strong evidence (PS3) when classifying the variant for a certain disease using the expert panel's criteria for variant classification.

We propose to accept these assertions in a new process, so that they are considered annotations on submissions rather than full submissions themselves. Initially we will work with the expert panels to pilot this process.  
The Example 5 VCV XML above demonstrates how this data will be modeled in the VCV XML files. Mock-ups (to be posted soon) will include an example for how this data will be shown on variant pages.
