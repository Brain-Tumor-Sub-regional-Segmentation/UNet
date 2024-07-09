### U-Net

The U-Net architecture, originally designed for biomedical image segmentation, is widely recognized for its effective feature extraction and precise localization capabilities. Here's a concise overview of the U-Net architecture:

1. **Contracting Path (Encoder)**:
   - 📉 Captures contextual information and reduces spatial resolution.
   - Comprises convolutional and pooling operations, increasing the depth (number of channels) while decreasing spatial dimensions.
   - Functions similarly to an autoencoder, extracting hierarchical features.

2. **Bottleneck**:
   - Performs a final convolutional operation to produce a feature map that captures high-level semantic information.
   - 🔗 Serves as a transition point between the contracting and expansive paths.

3. **Expansive Path (Decoder)**:
   - Decodes the encoded data and uses skip connections from the contracting path to generate a segmentation map with the same spatial resolution as the input.
   - Consists of upsampling and convolutional operations, increasing spatial dimensions while decreasing depth.
   - 🔄 **Skip connections**: Concatenate feature maps from the contracting path to corresponding layers in the expansive path, helping to recover spatial details lost during encoding.

4. **Output Layer**:
   - 🎯 Generates the final segmentation map, often representing binary segmentation (foreground vs. background).
   - The output size may be slightly smaller, but spatial information is preserved and refined through skip connections.

5. **Training and Loss**:
   - 🏋️‍♂️ We run the model on BraTS-20 and BraTS-21 datasets using Kaggle's free GPU (GPU T4 x2).
   - Learns to assign labels to pixels based on features extracted and localized through the contracting and expansive paths.

U-Net is particularly effective in medical image segmentation and other computer vision applications, especially where limited annotated data is available. Its success is largely due to its ability to capture detailed spatial information through skip connections. 

📄 Read our paper [here](https://arxiv.org/abs/1505.04597) on ArXiv for a formal introduction.
