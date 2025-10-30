## CycleGAN For Style Transfer - Translating Impressionist Paintings into Photographs
  For this project, I implemented a CycleGAN as described in the original paper 'Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks' (Zhun et al. 2017). The implementation is from scratch in PyTorch using the original architecture and hyperparameters with one tweak: in the original paper, the weight for the identity loss is given by $0.5 \times \lambda_{cycle} = 5$. The purpose of the identity loss is to ensure that the generators preserve color and content of the input image. However, I found that the identity loss was weighed too highly, and the generators were learning to simply translate paintings into paintings with a more realistic color palette (e.g. from Monet's trademark pastel colors into the same painting with more realistic greens and browns).
  
  To address the issue, the weight for the idenity loss was reduced to $0.1 \times \lambda_{cycle} = 1$. Current results are displayed after running training for 130 epochs. The quality in translation has not bottomed out yet, so more training is yet to be conducted.
  
![monet_original](/example_images/monet_original.jpg)

![monet_translation](/example_images/monet_translation_to_photo.jpg)
