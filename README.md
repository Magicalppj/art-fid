# ArtFID: Quantitative Evaluation of Neural Style Transfer (GCPR Oral 2022)

[**ArtFID: Quantitative Evaluation of Neural Style Transfer**](https://arxiv.org/abs/2207.12280)
[Matthias Wright](http://www.matthias-wright.com/) and [Björn Ommer](https://hci.iwr.uni-heidelberg.de/people/bommer).<br>


## Installation
```sh
> pip install art-fid
```

## Usage
```sh
CUDA_VISIBLE_DEVICES=0 python -m art_fid --style_images path/to/style-images --content_images path/to/content-images --stylized_images path/to/stylized-images
```
The content images and the corresponding stylized images are compared in pairs. In order to ensure that a content image is matched up with the correct stylized image, both the content images and the stylized images are processed in lexicographical order. A simple way of pairing the content images and the stylized images is to use the name of content image for the corresponding stylized image.

### Arguments
`--batch_size` - Batch size for computing activations.
`--num_workers` - Number of threads used for data loading.
`--mode` - Evaluate ArtFID or ArtFID_infinity, choices = ['art_fid', 'art_fid_inf'].
`--content_metric` - Content metric, choices = ['lpips', 'vgg', 'alexnet'].
`--device` - Device to use, choices = ['cuda', 'cpu'].
`--style_images` - Path to style images.
`--content_images` - Path to content images.
`--stylized_images` - Path to stylized images.

## Data
The dataset is contained in [artfid_dataset.csv](https://raw.githubusercontent.com/matthias-wright/art-fid/main/artfid_dataset.csv). It consists of 250k labeled artworks.

## Acknowledgments
* The implementation of the FID is based on [mseitzer/pytorch-fid](https://github.com/mseitzer/pytorch-fid).
* The implementation of the FID_infinity is taken from [mchong6/FID_IS_infinity](https://github.com/mchong6/FID_IS_infinity).
* The implementation of the Inception network is taken from [pytorch/vision](https://github.com/pytorch/vision/blob/main/torchvision/models/inception.py).
* The checkpoint is hosted on the [Huggingface Model Hub](https://huggingface.co/docs/hub/models-the-hub).

## Citation
```
@article{wright_gcpr_2022,
    title={ArtFID: Quantitative Evaluation of Neural Style Transfer},
    author={Matthias Wright and Bj{\"o}rn Ommer},
    journal={GCPR},
    year={2022}
}
```
