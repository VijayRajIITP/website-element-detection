# Website-element-detection
# Object Recognition Model for Webpage Elements

## Objective
Implement a computer vision architecture to perform element detection and identification on webpages. The model should be able to identify various elements such as Breadcrumb, checkbox, container, dropdown Forms, buttons, logo images, Navigation dots, text, links, input fields, radio buttons, and modals. Each identified element should be enclosed within a bounding box and tagged with its corresponding element name.

## Model Architecture and Training

1. **Data Collection:**
   - Gather a diverse dataset of webpage screenshots containing various elements of interest.
   - link- (https://universe.roboflow.com/uied/ui-element-detect/dataset/6)
   - 
| Dataset Name                | Train Images | Test Images | Validation Images |
|-----------------------------|--------------|-------------|-------------------|
| UI element Detect Image Dataset | 6,618        | 829         | 865               |


2. **Preprocessing:**
   - Resize all images to a standard size to ensure consistency.
   - Normalize pixel values to improve model performance.

3. **Model Selection:**
    ### Why Choose YOLOv8x?

 **Enhanced Detection**: YOLOv8x offers deeper and wider network architecture for improved detection capabilities.

 **High Accuracy**: It achieves superior accuracy, especially in detecting small objects and intricate details.

 **Balanced Performance**: YOLOv8x strikes a balance between accuracy and speed, making it ideal for comprehensive object recognition tasks.

4. **Model Training:**
   - Split the annotated dataset into training, validation, and testing sets.
   - Train the selected model architecture using the training set.
   - Fine-tune the model using the validation set to optimize performance.
   - Evaluate the trained model on the testing set to assess its accuracy and generalization capability.

5. **Hyperparameter Tuning:**
   - Experiment with different learning rates, batch sizes, and optimization algorithms to improve model convergence and performance.
   - Utilize techniques like data augmentation to increase dataset diversity and prevent overfitting.

6. **Model Evaluation:**
## Validation Data
| Class              | Images | Instances | Box(P) | R      | mAP50 | mAP50-95 |
|--------------------|--------|-----------|--------|--------|-------|----------|
| all                | 865    | 12255     | 0.893  | 0.798  | 0.871 | 0.762    |
| BackgroundImage    | 865    | 114       | 0.879  | 0.912  | 0.967 | 0.941    |
| Bottom_Navigation  | 865    | 2         | 1      | 0      | 0.663 | 0.663    |
| Button-Outlined    | 865    | 14        | 0.961  | 1      | 0.995 | 0.885    |
| Button-filled      | 865    | 16        | 0.954  | 1      | 0.995 | 0.944    |
| CheckBox           | 865    | 8         | 1      | 0.976  | 0.995 | 0.759    |
| CheckedTextView    | 865    | 155       | 0.883  | 0.723  | 0.859 | 0.731    |
| DropDown           | 865    | 3         | 0.92   | 1      | 0.995 | 0.963    |
| EditText           | 865    | 434       | 0.96   | 0.891  | 0.981 | 0.922    |
| Icon               | 865    | 2194      | 0.952  | 0.945  | 0.953 | 0.833    |
| Image              | 865    | 1593      | 0.95   | 0.887  | 0.958 | 0.93     |
| Modal              | 865    | 54        | 0.923  | 0.944  | 0.985 | 0.959    |
| Multi_Tab          | 865    | 2         | 0      | 0      | 0.063 | 0.063    |
| PageIndicator      | 865    | 291       | 0.981  | 0.962  | 0.987 | 0.82     |
| Profile-image      | 865    | 4         | 0.973  | 1      | 0.995 | 0.681    |
| Spinner            | 865    | 2         | 1      | 0      | 0     | 0        |
| Switch             | 865    | 36        | 0.984  | 0.917  | 0.932 | 0.896    |
| Text Button        | 865    | 5678      | 0.975  | 0.931  | 0.978 | 0.888    |
| Text-Input         | 865    | 7         | 0.954  | 1      | 0.995 | 0.927    |
| TextButton         | 865    | 901       | 0.984  | 0.951  | 0.989 | 0.981    |
| Toggle-Checked     | 865    | 4         | 0.652  | 1      | 0.995 | 0.824    |
| Toggle-Unchecked   | 865    | 6         | 0.9    | 0.667  | 0.913 | 0.722    |
| Toolbar            | 865    | 41        | 0.729  | 0.707  | 0.793 | 0.778    |
| UpperTaskBar       | 865    | 669       | 0.919  | 0.77   | 0.928 | 0.482    |
| link               | 865    | 27        | 0.992  | 0.963  | 0.993 | 0.687    |




## Test Data (Unseen to model)
| Class                           | Images | Instances | Box(P) | R      | mAP50 | mAP50-95 |
|---------------------------------|--------|-----------|--------|--------|-------|----------|
| all                             | 829    | 13278     | 0.578  | 0.509  | 0.499 | 0.429    |
| Action Bar                      | 829    | 2         | 0.206  | 0.5    | 0.255 | 0.155    |
| BackgroundImage                 | 829    | 65        | 0.73   | 0.923  | 0.933 | 0.913    |
| Bottom_Navigation               | 829    | 5         | 0.275  | 0.165  | 0.355 | 0.32     |
| Call to Action                  | 829    | 3         | 0      | 0      | 0.045 | 0.0434   |
| CheckedTextView                 | 829    | 63        | 0.716  | 0.937  | 0.926 | 0.798    |
| Consistency                     | 829    | 5         | 0      | 0      | 0.00406 | 0.00284 |
| EditText                        | 829    | 256       | 0.938  | 0.977  | 0.981 | 0.944    |
| Header with Title               | 829    | 5         | 0.132  | 0.2    | 0.0822 | 0.0641  |
| Horizontal Alignment            | 829    | 17        | 0.558  | 0.353  | 0.335 | 0.277    |
| Icon                            | 829    | 2419      | 0.751  | 0.737  | 0.778 | 0.636    |
| Image                           | 829    | 2193      | 0.684  | 0.606  | 0.619 | 0.543    |
| In Focus Popup                  | 829    | 2         | 0      | 0      | 0.00725 | 0.00725|
| Input                           | 829    | 121       | 0.497  | 0.471  | 0.412 | 0.304    |
| List Item                       | 829    | 5         | 1      | 0      | 0.00104 | 0.00104|
| Meaningful Placeholder Text     | 829    | 3         | 0.0784 | 0.333  | 0.0721 | 0.0649  |
| Modal                           | 829    | 23        | 0.666  | 0.957  | 0.932 | 0.907    |
| Multi_Tab                       | 829    | 4         | 0.444  | 0.5    | 0.389 | 0.383    |
| On-Off Switch                   | 829    | 3         | 0.709  | 0.333  | 0.526 | 0.368    |
| PageIndicator                   | 829    | 138       | 0.978  | 0.971  | 0.994 | 0.832    |
| Slider                          | 829    | 20        | 0.502  | 0.35   | 0.365 | 0.137    |
| Spinner                         | 829    | 1         | 1      | 0      | 0     | 0        |
| Switch                          | 829    | 11        | 0.804  | 0.909  | 0.971 | 0.971    |
| Text Button                     | 829    | 6165      | 0.727  | 0.689  | 0.721 | 0.594    |
| Text                            | 829    | 780       | 0.497  | 0.45   | 0.436 | 0.348    |
| TextButton                      | 829    | 550       | 0.969  | 0.982  | 0.984 | 0.979    |
| Toolbar                         | 829    | 25        | 0.707  | 0.96   | 0.961 | 0.954    |
| UpperTaskBar                    | 829    | 392       | 0.614  | 0.946  | 0.899 | 0.472    |
| Video                           | 829    | 2         | 1      | 0      | 0     | 0        |


# 🚀 Unleashing the Power of YOLOv8 Model

Welcome to the exciting journey of running the YOLOv8 model! This guide will navigate you through the process, ensuring a smooth and successful execution.

## 📚 Prerequisites

Before we dive in, make sure you have the following:

- Python 3.6 or later 🐍
- PyTorch 1.4 or later 🔥
- CUDA 10.0 or later 🎮

## 🚀 Let's Get Started!

Follow these steps to run the YOLOv8 model:

1. **Clone the repository**

    Open your terminal and enter the following commands:

    ```bash
    git clone https://github.com/ultralytics/yolov8.git
    cd yolov8
    ```

2. **Install the requirements**

    Stay in the terminal and execute:

    ```bash
    pip install -r requirements.txt
    ```

3. **Download the weights**

    Now, let's get the weights by running:

    ```bash
    bash weights/download_weights.sh
    ```

4. **Run the model**

    It's showtime! Let's run the model:

    ```bash
    python detect.py --weights yolov8.pt --img 640 --conf 0.25 --source data/images/
    ```

    Don't forget to replace `data/images/` with the path to your images.

## 📝 Creating a YAML File

Before training the model, you need to create a YAML file that specifies the paths to your images and labels. Here's an example of what this file might look like:

```yaml
# my_data.yaml
train: /path/to/train/images/
val: /path/to/validation/images/
nc: 80  # number of classes
names: ['class1', 'class2', ..., 'class80']  # list of class names

In this file:

- `train` and `val` are paths to the directories containing your training and validation images, respectively.
- `nc` is the number of classes.
- `names` is a list of class names.

Make sure your labels are in the YOLO format and are located in the same directory as your images.

## 🚀 Training the Model For Custom Datasets

Once you’ve created your YAML file, you can train the model:

```bash
python train.py --img 640 --batch 16 --epochs 100 --data my_data.yaml --weights yolov8.pt --nosave --cache



## Conclusion

The developed object recognition model provides a powerful tool for automating the detection and identification of relevant elements on webpages. By accurately bounding boxes and tagging elements, it facilitates tasks such as webpage analysis, accessibility testing, and user experience optimization. Continual refinement and updates to the model will ensure its effectiveness in keeping pace with evolving web technologies and design trends.
