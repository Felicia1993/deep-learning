# Transfer learning
## Dataset
mini-ImageNet(https://drive.google.com/drive/folders/17a09kkqVivZQFggCw9I_YboJ23tcexNM)        
EuroSAT dataset (https://github.com/phelber/EuroSAT)

## Evorinment 
python=3.9.18, torch=2.1.1, torchvision=0.16.1

## steps
i. Download and read the miniImageNet (Because the dataset miniImageNet usually is used in the few-shot learning task. Hence, the train, val, and test data are from different categories. For easier, you can only focus on the train.tar, and split the data in train.tar as train, val, and test dataset, which means you can ignore both val.tar and test.tar.) & EuroSAT(RGB) datasets.     

ii. Pretrain ResNet18 model  on the training set of miniImageNet, evaluate & test it on the validation & test set.     

iii. Save the pretrained model.     

iv. Choose 100 images from EuroSAT dataset, which are from 5 different categories and each category includes 20 samples. You should randomly choose 25 images from these 100 samples as training set (The 25 images should be from the 5 different categories. Each category includes 5 images).      

v. Fine-tune the pre-trained model with these 25 training images and test it on the rest 75 samples, show the results. Better to fine-tuning several times on different 100 EuroSAT images and get their average result.         

