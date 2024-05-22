# GANS-Satellite_to_Maps
--> Generating Maps from Satellite images using the Pix2Pix GAN. <br/>
Developed and Trained a model that can convert aerial satellite imagery ("input") into map routes ("output"). The architecture for the generator is a U-Net and the Discriminator is a PatchGAN. I have saved the model checkpoint while training(pix2pix_15000.pth), that can be used as a pre-trained model. However, it can be trained from scratch.

# Training parameters
adv_criterion = nn.BCEWithLogitsLoss() <br/>
recon_criterion = nn.L1Loss() <br/>
lambda_recon = 200 <br/>
<br/>
n_epochs = 20 <br/>
input_dim = 3 <br/>
real_dim = 3 <br/>
display_step = 200 <br/>
batch_size = 4 <br/>
lr = 0.0002 <br/>
target_shape = 256 <br/>
device = 'cpu' (could be cuda if your device supports!) <br/>

# Dimensions
Shape of the input tensor: torch.Size([1, 3, 256, 256]) <br/>
Shape of the Output tensor: torch.Size([1, 3, 256, 256])

# Dataset
--> Maps.zip <br/>
It contains two folders, one for each training and validation data. <br/>
The image tensor is horizontally concatenated. The condition(satellite image) is left half of the Image and the label(map) is the right half of each image in the dataset.

# Training
<img width="1110" alt="Screenshot 2024-05-22 at 4 59 43 PM" src="https://github.com/jatin67singh/GANS-Satellite_to_Maps/assets/57382628/b8a4885a-39ef-47f5-a991-5c678f035aa7">


