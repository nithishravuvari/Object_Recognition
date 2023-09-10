# Object Recognition Using MATLAB 

This MATLAB code is designed for object recognition using a pretrained neural network model, specifically GoogleNet, which is further fine-tuned using transfer learning. The code utilizes a webcam to capture a live image, preprocesses it to match the network's input size, and then classifies the image to recognize the object within it.

## Dependencies

- MATLAB with the Deep Learning Toolbox
- A webcam connected to your computer

## Instructions for Use

Follow these steps to use the code:

1. **Clear Workspace Environment**: Clear the workspace environment to ensure a clean start.

    ```matlab
    clc
    clear
    close all
    ```

2. **Setting Up the Camera**: Set up the webcam for capturing images.

    ```matlab
    camera = webcam;
    ```

3. **Capturing a Snapshot**: Capture a single image from the webcam.

    ```matlab
    picture = camera.snapshot;
    ```

4. **Clearing the Camera**: After capturing the image, clear the camera.

    ```matlab
    clear camera;
    ```

5. **Initializing the Pretrained Network**: Initialize a pretrained GoogleNet model.

    ```matlab
    net = googlenet;
    ```

6. **Checking the Input Size**: Retrieve and display the input size required by the network.

    ```matlab
    inlayer = net.Layers(1);
    expectedSize = inlayer.InputSize;
    ```

7. **Preprocessing the Image**: Resize the captured image to match the network's input size (224x224 pixels).

    ```matlab
    picture = imresize(picture, [224, 224]);
    ```

8. **Classifying the Image**: Classify the resized image using the pretrained network.

    ```matlab
    label = classify(net, picture);
    ```

9. **Displaying the Result**: Display the classified object label as the title of the image.

    ```matlab
    title(upper(char(label)));
    ```

## Additional Notes

- Ensure that your webcam is properly connected and functioning before running the code.
- Make sure you have the required MATLAB toolbox (Deep Learning Toolbox) installed and configured.

