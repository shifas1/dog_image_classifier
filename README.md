# Dog Breed Classification using CNNs

This project uses Convolutional Neural Networks (CNNs) to classify dog images and identify their breeds. The model also distinguishes between dog images and "not-a-dog" images, providing insights into the correctness of classifications.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Project Features](#project-features)
- [Requirements](#requirements)
- [How to Run the Project](#how-to-run-the-project)
- [Output Example](#output-example)
- [Project Structure](#project-structure)
- [Key Logic](#key-logic)
- [Contribution](#contribution)
- [License](#license)
- [Contact](#contact)

## Project Overview
The goal of this project is to classify images into:

1. **Dog images**: Correctly identifying the breed.
2. **"Not-a-dog" images**: Correctly determining that the image is not a dog.

The project outputs performance metrics, identifies misclassified dog breeds, and prints "not-a-dog" classification statistics.

### Model Architecture
The project uses CNN-based models like AlexNet, VGG, ResNet, or other pre-trained architectures for feature extraction and classification.

## Dataset Description
The project takes in a directory of images that belong to two main categories:

1. **Dog Images**: Images of dogs, including various breeds.
2. **"Not-a-dog" Images**: Images that do not contain any dogs.

Each image is compared against classifier predictions to determine:
- Whether the classifier correctly identified the image as a dog.
- Whether the dog breed was correctly classified.

## Project Features
### Performance Metrics
- Number of total images, dog images, and "not-a-dog" images.
- Percentage of correctly classified dogs, breeds, and "not-a-dog" images.
- Overall match percentage between predicted and actual labels.

### Misclassification Detection
- Identifies images where dogs are misclassified as "not-a-dog" and vice versa.
- Identifies images where the breed of the dog is misclassified.

### Customizable CNN Architecture
- Users can test the project with different CNN models such as AlexNet, VGG, ResNet, etc.

## Requirements
To run this project, you need the following dependencies:

- Python (>=3.8)
- NumPy
- Pandas
- PyTorch or TensorFlow/Keras (for CNN models)
- OpenCV or PIL (for image processing)

Install all dependencies using the following command:

```bash
pip install numpy pandas torch torchvision opencv-python
```

## How to Run the Project
### Clone the repository:
```bash
git clone https://github.com/your-username/dog-breed-classification.git
cd dog-breed-classification
```

### Prepare the Dataset:
Place all image files in an appropriate directory:
```bash
./images/
```

### Run the Project:
Execute the Python script:
```bash
python classify_dogs.py --model alexnet --data_dir ./images
```
Replace `--model` with your desired CNN architecture (alexnet, vgg, resnet, etc.).

## Output Example
Sample output for AlexNet architecture:

```text
Using the alexnet CNN model architecture
Number of Images: 40
Number of Dog Images: 30
Number of 'Not-a' Dog Images: 10
100.0% Correctly Classified Dogs
80.0% Correctly Classified Breeds
100.0% Correctly Classified 'Not-a' Dog Images
75.0% Match Between Labels

Misclassified Breeds of Dogs:
Image: Boston_terrier_02285.jpg, Classifier Label: basenji
Image: Great_pyrenees_05367.jpg, Classifier Label: kuvasz
Image: Golden_retriever_05182.jpg, Classifier Label: tibetan mastiff
Image: Golden_retriever_05257.jpg, Classifier Label: afghan hound, afghan
Image: Beagle_01170.jpg, Classifier Label: walker hound, walker foxhound
Image: Beagle_01141.jpg, Classifier Label: english foxhound
```


## Key Logic
### Classification Metrics
Calculate statistics such as correct classifications for dogs, breeds, and "not-a-dog" images.

### Misclassified Dogs
Condition to detect misclassified dogs:
```python
sum([int(values[3]), int(values[4])]) == 1
```

### Misclassified Breeds
Additional condition:
```python
n_correct_dogs != n_correct_breed
```

## Contribution
Contributions are welcome! If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

## License
This project is licensed under the MIT License.

## Contact
For any questions or clarifications, reach out to:

**Name:** Shifa S  
**Email:** shifasyed9990@gmail.com  
**LinkedIn:** [LinkedIn Profile](#https://www.linkedin.com/in/shifa-s/)
