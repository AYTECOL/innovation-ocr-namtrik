# OCR Development for Namtrik using EasyOCR
Using:
* Main EasyOCR cutom model docs: https://github.com/JaidedAI/EasyOCR/blob/master/custom_model.md
* TextRecognitionDataGenerator: https://github.com/Belval/TextRecognitionDataGenerator
* Custom Datasets and pretrained models: https://jaided.ai/easyocr/modelhub/
* Benchmarking and training example: https://github.com/clovaai/deep-text-recognition-benchmark

## Run

* Run "Easy OCR Custom Model" to test a Custom Model. Each custom model has 3 files: _.pth_ containing the model weights, _.py_ containing the model architecture, and _.yaml_ containing the model configuration. The downloaded Custom Model is provided by the same documentation and contains a Fully-Connected CNN, as of the paper from EasyOCR. It is trained for english using "en_sample.zip" dataset. 
* A dataset can be generated in "Generate OCR Image Dataset" notebook. Basically it does a small demonstration and therefore takes all single words (unique words) and sentences from our Namtrik Datasets (spa-gum family) and creates images with different distortions. All images are save into /output (numerically) and in labels.csv dataset (containing filename and words). Same format as en_sample.zip dataset. 
* Training can be achieve configuring en_filtered_conf.yaml and runing trainer/trainer.ipynb notebook. It will produce two .pth files in /saved_models. Those are the models to copy into /.EasyOCR (see "Easy OCR Custom Model".ipynb in "Running EasyOCR"). _.pth_ files are moved to /.EasyOCR/model, and _.yaml_ and _.py_ are (already) moved into user_network. 
* TODO: the dataset should be splitted into _train and _val datasets and provided into the en_filtered_conf.yaml (/trainer/configfiles) train dataset is selected in selected data
  
# Data Generator for Namtrik
Using """pip install trdg"""

Documentation in: https://textrecognitiondatagenerator.readthedocs.io/en/latest/index.html

For new Language, read page 3: https://textrecognitiondatagenerator.readthedocs.io/_/downloads/en/latest/pdf/

## Acknowledgment

This is under development for Ayté only, it would be wise to split the OCR part on another repo with cleaner procedures once it is stable and replicable.