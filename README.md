# SiteScan Python API Examples

Example Python functions demonstrating how to use the SiteScan API to automate drone data processing workflows. This script shows practical implementations for project creation, image upload, processing initiation, and result upload to ArcGIS Portal.

## Overview

This example script demonstrates functions for:
- Creating SiteScan projects and missions
- Uploading drone images for processing
- Starting photogrammetric processing
- Monitoring processing status
- Downloading processed products (Orthomosaic, DTM, DSM)
- Uploading results to ArcGIS Portal

## Prerequisites

- Python environment with `requests` and `arcgis` packages
- Valid SiteScan API access and token
- ArcGIS Portal account and credentials

## Getting Started

Simply update the configuration variables in the script and run it to see the SiteScan API in action.

### API Configuration
```python
# Replace with your SiteScan API token
token = 'YOUR_API_TOKEN'

# SiteScan API endpoint (usually doesn't need to change)
url = 'https://sitescan-api.arcgis.com/api/v2'
```

### Processing Configuration
```python
# Customize these for your project
project_name = "nameForProject"
mission_name = "nameForMission"
imagesPath = r"C:\path\to\your\images"
```

### ArcGIS Portal Configuration
The script uses `GIS('home')` which will use your default ArcGIS Pro or saved credentials. Alternatively, you can specify:
```python
gis = GIS("https://yourportal.domain.com/portal", "username", "password")
```

## Usage

This is example code designed to demonstrate SiteScan API functionality. You can use these functions as building blocks to create your own custom workflows.

### Running the Examples

1. Update the configuration variables with your credentials and paths
2. Run the script to see the complete workflow in action:

```bash
python siteScanPythonAPIv1.0.py
```

### Building Your Own Workflow

Use the provided functions as examples to build your own custom SiteScan workflows:
- Mix and match functions based on your needs
- Modify parameters for different processing options
- Add error handling and logging as required
- Integrate with your existing data processing pipelines

### Expected Output

The script will provide status updates throughout the process:
```
Organization ID: org-12345
Project created successfully
Mission created successfully
C:\images\image001.jpg uploaded successfully!
Processing started successfully
Ortho in progress
DTM in progress
DSM in progress
Ortho Created
DTM Created
DSM Created
Downloaded ortho_12345.tif
Uploading ortho_12345.tif to ArcGIS Portal...
Uploaded Ortho to ArcGIS Portal!
```

## Example Functions

The script demonstrates these key SiteScan API operations:
- **Project Management**: Creates and manages SiteScan projects
- **Mission Handling**: Creates missions within projects for organized processing
- **Batch Upload**: Processes all JPEG images in specified directory
- **Status Monitoring**: Continuously checks processing status until completion
- **Product Download**: Downloads all generated products (Orthomosaic, DTM, DSM)
- **Portal Integration**: Automatically uploads results to ArcGIS Portal

## Function Reference

| Function | Description |
|----------|-------------|
| `getOrgID()` | Retrieves organization ID from SiteScan API |
| `createProject()` | Creates a new project in the organization |
| `createMission()` | Creates a new mission within a project |
| `uploadImages()` | Uploads all images from specified directory |
| `startProcessing()` | Initiates photogrammetric processing |
| `checkProcessingStatus()` | Monitors processing and retrieves product URLs |
| `downloadFiles()` | Downloads processed products to temporary directory |
| `createTempFolder()` | Creates temporary directory for downloads |
| `deleteTempFolder()` | Cleans up temporary files |

---

**Note**: This script is designed for educational and demonstration purposes. Use these examples as building blocks to create your own custom SiteScan API workflows.
