# Flower Image Generation Experiment  
DCGAN with Latent Dimension 100 and Batch Size Comparison

This project conducts an experimental study on image generation using DCGAN across multiple flower categories. The main objective is to evaluate the effect of different batch sizes while keeping the latent dimension fixed at 100.

The experiment focuses on understanding how batch size influences training stability and image quality.

## Dataset

The dataset consists of several flower categories organized in separate folders:

- astibe  
- bellflower  
- common_daisy  
- corn  
- dandelion  
- rose  
- tulip  
- water_lily  

Each folder contains real images used to train the generative model.

## Experiment Setup

- Model: Deep Convolutional GAN (DCGAN)  
- Latent Dimension (z): 100  
- Batch Sizes Tested: 32, 64, 128  
- Image Type: RGB flower images  
- Training Type: Separate experiments for each batch size  

All experiments use the same architecture and hyperparameters, except for the batch size.

## Methodology

### 1. Data Preparation

- Images are resized and normalized.  
- Each class is trained separately.  
- Data is loaded using standard PyTorch or TensorFlow data loaders.

### 2. Training Process

For each flower category:

1. Train DCGAN with batch size 32  
2. Train DCGAN with batch size 64  
3. Train DCGAN with batch size 128  

The generator and discriminator are trained using adversarial loss.

### 3. Evaluation

Evaluation is performed using:

- Visual inspection of generated images  
- Training stability (loss curves)  
- Mode collapse observation  
- Consistency across epochs  

No pre-trained model is used; all models are trained from scratch.

## How to Run

### Install Dependencies

```
pip install numpy torch torchvision matplotlib
```

### Run Notebook

```
jupyter notebook tulip_zdim100_bs32.ipynb
```

(Repeat for other batch size notebooks.)

## Project Structure

```
.
├── astibe/
├── bellflower/
├── common_daisy/
├── corn/
├── dandelion/
├── rose/
├── tulip/
├── water_lily/
└── notebooks/
    ├── *_zdim100_bs32.ipynb
    ├── *_zdim100_bs64.ipynb
    └── *_zdim100_bs128.ipynb
```

## Results (Summary)

General observations:

- Batch size 32: More stable training, better diversity  
- Batch size 64: Balanced performance  
- Batch size 128: Faster training but higher risk of mode collapse  

Final quality is assessed visually and may vary per flower category.

## Possible Improvements

- Try different latent dimensions (50, 128, 256)  
- Add FID and IS metrics  
- Use WGAN-GP or StyleGAN  
- Train with higher image resolution  
- Perform data augmentation  

## Use Case

This project is suitable for:

- GAN research experiments  
- Studying hyperparameter effects  
- Academic thesis projects  
- Generative model benchmarking  

## License

This project is intended for educational and research purposes.
