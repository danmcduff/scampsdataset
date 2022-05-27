# The SCAMPS Dataset

SCAMPS is a dataset of synthetics containing 2,800 videos (1.68M frames) with aligned cardiac and respiratory signals and facial action intensities. The RGB frames are provided alongside segmentation maps. 

It was introduced in our paper [**SCAMPS: Synthetics for Camera Measurement of Physiological Signals**](...).

Synthetics have proven valuable in several areas of computer vision, particularly face and body analyses.
However, creating high fidelity 3D assets for simulating many different facial appearances (e.g., bone structures, facial attributes, skin tones etc.) is time consuming and expensive. Therefore, in this paper we present a new dataset (\projectname) of high fidelity synthetic human simulations that will be made publicly available. These data are designed for the purposes of training and testing camera physiological measurement methods.

![An image showing frames of a video with line graphs below it showing synchronized physiological signals](images/waveforms.png)

## What the Dataset Contains

Our dataset contains:
- 2,800 synthetic videos (1.68M frames)
- Aligned cardiac and respiratory waveforms for all frames
- Action unit labels for all frames
- Groundtruth heart rate, breathing rate, interbeat intervals and heat rate variability


Each RGB frame is accompanied by segmentation masks beard, eyelashes, eyebrows, glasses, hair, skin and clothing.

![An image showing a single frame of video and a set of segmentation frames with different regions (e.g., hair, clothing, etc.) segmented](images/segmentation.png)

## How the Dataset was Created

![An image of a system diagram which shows how the synthetic avatars were created. The base skin albedo is altered using the blood volume pulse signal and then clothing, hair and background are added](images/architecture.jpg)


## How to Download the Dataset

Small example of 10 video and labels (.mat format - 3GB) can be downloaded [here](...)

The full set of videos and labels (.mat format - 1TB) can be downloaded [here](...)

The full set of labels only (.mat format - ...) can be downloaded [here](...)

The full set of labels only (.csv format - ...) can be downloaded [here](...)



## The Dataset Structure

```
scamps_videos.tar.gz
  PXXXXXX.mat
  ├── RawFrames        # Rendered images of the avatar at 320 x 240 resolution - [ channel , width , height , time ]
  ├── Xsub              # Center cropped images containing the face at 240 x 240 pixels - [ time , width , height , channel ]
  ├── ...               # ...
```

RawFrames', 'Xsub', 'au12', 'au15', 'au17', 'au18', 'au2', 'au26', 'au27', 'au4', 'au45', 'au7', 'combined_mask', 'd_br', 'd_ekg', 'd_pitch', 'd_ppg', 'd_roll', 'd_yaw', 'numerical_mask', 'skin_mask

Reading the data example:

```
import h5py
f = h5py.File('P000001.mat', 'r')
print(f.keys())
...
```

## Transparency and Broader Impacts

This dataset was created for research and experimentation on camera measurement of physiological signals. While the dataset is useful for testing models, is not designed as a test set for evaluating the clinical efficacy of a model, just because a model performs well on synthetic data does not mean it will generalize to videos of real people.

The SCAMPS dataset was not designed for computer vision tasks such as face recognition, gender recognition, facial attribute recognition, or emotion recognition. We do not believe this dataset would be suitable for these applications without further validation.

Advantages of camera physiological measurement are that contact with the body is not required and that cameras are ubiquitous sensors. However, these advantages can cause problems. Unobtrusive measurement from small, ubiquitous sensors makes measurement without a subject's knowledge simpler. 

## Disclaimer

Some of our rendered faces may be close in appearance to the faces of real people.  Any such similarity is naturally unintentional, as it would be in a dataset of real images, where people may appear similar to others unknown to them.


## Generalization to real data

...


## Citation

If you use the SCAMPS Dataset your research, please cite the following [paper](LINK):


```
@misc{
}
