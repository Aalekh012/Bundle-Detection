# bod

# Bundle Detection Using Object Detection Models

This project involves detecting and localizing bundles of items within images using Faster R-CNN and Mask R-CNN models from PyTorch. The primary goal is to identify and visualize bundles of utensils, but the code can be adapted for other object categories as well.

## Installation and Setup

Create an environment to ensure proper working.

```bash
git clone https://github.com/yourusername/your-repo.git
cd your-repo
```

## 

```python
conda create -n venv__ python=3.11.1 -c conda-forge -y
pip install -r requirements.txt

```

## Usage 

Prepare your images:

Place your images in a folder, and set the folder_path variable in the script to point to this folder.
```python
folder_path = "/path/to/your/images"
evaluate_folder(folder_path, faster_rcnn_model, threshold=0.5, objects=UTENSILS_CLASSES, save_visualizations=True, output_folder="output")
```

## Functions
#### get_predictions(pred, threshold=0.8, objects=None): Filters predictions based on a confidence threshold and object classes.
#### identify_bundles(boxes, proximity_threshold=50): Identifies bundles of objects based on proximity.
#### draw_bundles(img, bundles, rect_th=2, text_size=0.5, text_th=2, download_image=False, img_name="img"): Draws bounding boxes and labels on the image to visualize bundles.
#### evaluate_folder(folder_path, model, threshold=0.5, objects=None, save_visualizations=False, output_folder="output"): Evaluates images in a folder and visualizes detected bundles.

## Assumptions
#### The images in the folder should be in PNG, JPG, or JPEG formats.
#### The code assumes that pre-trained models are used and may require adjustments if fine-tuning is performed.
#### The proximity threshold for identifying bundles is set to 50 pixels by default but can be adjusted.

## Details
This project utilizes pre-trained models for object detection. Bundle detection is a broad topic that encompasses various applications. In this project, the focus is on detecting bundles of utensils. Specifically, the project aims to identify bundles consisting of spoons, forks, or knives in images.

For evaluation, qualitative metrics were used. The observations indicated that Mask R-CNN performed better in terms of identifying bundles. However, it occasionally produced false positives. False positives occur when the model incorrectly identifies objects that do not exist in the image.

To address this issue, further hyperparameter tuning is necessary. This tuning should be performed on an image dataset containing labeled bounding boxes of utensil bundles. As of now, publicly available datasets for bundle detection are limited. Therefore, to enhance model performance and achieve better results, a custom dataset must be created.

In this project, COCO (Common Objects in Context) instance category names were utilized for object classification. The models employed include Faster R-CNN and Mask R-CNN, which are both robust architectures for object detection. These models use region-based approaches and deep convolutional neural networks (CNNs) to detect and localize objects within images. By integrating advanced techniques such as Non-Maximum Suppression (NMS) and refining model parameters, the goal is to improve detection accuracy and reduce false positives.

## License

[MIT](https://choosealicense.com/licenses/mit/)
