# ADF-Azure
 Azure Data Factory (ADF) YAML-Based Deployment

This repository contains Azure Data Factory assets defined in YAML format, enabling version control, automation, and CI/CD deployment across environments.

# Project Structure

ADF-Azure/ ├── adf/ │ ├── pipelines/ │ │ └── Adfprac_pipeline.yaml │ ├── datasets/ │ │ └── source_dataset.yaml │ ├── linkedServices/ │ │ └── azure_blob_ls.yaml │ └── triggers/ │ └── daily_trigger.yaml ├── scripts/ │ └── deploy.sh ├── parameters/ │ └── dev.parameters.json └── README.md


---

## Sample YAML Files

### ✅ Pipeline: `Adfprac_pipeline.yaml`

```yaml
name: Adfprac_pipeline.yaml
properties:
  activities:
    - name: CopyFromBlob
      type: Copy
      dependsOn: []
      inputs:
        - referenceName: SourceDataset
          type: DatasetReference
      outputs: []
      typeProperties:
        source:
          type: BlobSource
        sink:
          type: AzureSqlSink
  annotations: []
