# Image Segmentation with SAM and CLIPSeg

This repository contains scripts and Jupyter notebooks for segmenting grayscale images using two models: the Segment Anything Model (SAM) and CLIPSeg. Both workflows generate segmentation masks, store the outputs in structured folders, and record timing statistics for each image.

## Folder Structure

    ├── Sample Images/
    │   ├── CLIPSeg_Masks/          # Segmentation masks and timing CSVs from CLIPSeg
    │   ├── SAM_Masks/              # Segmentation masks and timing CSVs from SAM
    │   └── ...                     # Input grayscale images
    ├── CLIPSeg.ipynb               # Notebook using CLIPSeg
    ├── SAM.ipynb                   # Notebook using SAM
    ├── requirements.txt            # Dependency list
    └── README.md

## Model Weights (Required)

### SAM Weights  
The SAM notebook requires the ViT-B weights file:

    sam_vit_b_01ec64.pth

Download it from Meta AI's official release:

https://github.com/facebookresearch/segment-anything 

Direct download link: https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth 

Place the downloaded file in the root directory of this repository next to `SAM.ipynb`.

### CLIPSeg  
CLIPSeg weights are downloaded automatically from the Hugging Face model hub when the notebook runs for the first time.

## Installation

Install dependencies:

    pip install -r requirements.txt

Both notebooks check for GPU availability automatically.

## Usage

1. Add your grayscale images to the **Sample Images** folder.
2. Download the SAM weights (see above) and place the file in the repository root.
3. Launch Jupyter:

       jupyter notebook

4. Run either:
   - `SAM.ipynb` for SAM-based segmentation  
   - `CLIPSeg.ipynb` for CLIPSeg-based segmentation  
5. Outputs will be saved automatically in:
   - `Sample Images/SAM_Masks/`
   - `Sample Images/CLIPSeg_Masks/`

## Notebooks Overview

### SAM.ipynb
- Loads input images from `Sample Images/`
- Uses the ViT-B version of the Segment Anything Model
- Saves segmentation masks and timing CSVs
- Visualizes segmentation results

### CLIPSeg.ipynb
- Loads input images from `Sample Images/`
- Applies CLIPSeg using a user-defined text prompt
- Saves segmentation masks and timing CSVs
- Displays segmented outputs for inspection

## References

- Kirillov et al., “Segment Anything,” Meta AI, 2023.  
- Lüddecke and Ecker, “CLIPSeg: Image Segmentation Using Text and Image Prompts,” CVPR, 2022.

## License

This repository does not include any model weights. Refer to the original model repositories for their respective licenses.
