# SocialGANetwork

This repo contains a project to generate social media content by leveraging Generalised Adversarial Networks

## Social Media Pages:
**Instagram:** [https://www.instagram.com/socialganetwork/](https://www.instagram.com/socialganetwork/)

## Approach

### Original Plan
Initially the plan was to have a full end to end process automated through use of instagrams API.
Naively I did not expect their API to be so locked down and have had to abandon many elements of my originalplans, at least in the short term.

I had originally envisaged the finished project having a process such as below:

1. Programatically choose a hashtag
    - take biggest trending hashtag
    - allow community engagement - voting on hashtag by commenting on images on the account - take most requested
2. Scrape the top ~10k from that hashtag
3. Train Model
4. Generate new images from G - 9 to create an instagram "grid" for each run
5. Automatically upload with hashtag, details of the methodology and some metrics of the image and run

### Current state

A number of the above elements have had to be de-scoped or de-priortised - at present:
- A hashtag is determined by the user (me)

- The batch of images is downloaded using a 3rd party app [4K Stogram](https://www.4kdownload.com/products/product-stogram)

- Upload is performed manually using a mobile browser emulator (uploading from desktop is prohibited)

- Each run so far is a copy of the same notebook with input parameters modified

### Issues

- **Garbage In/Garbage Out**

  - I believe a major blocker for generating better images is the heterogeneity of instagram content with a particular hashtag. Hashtags are often "spammed" and attached to images which they are not directly relevant to.
  - Examples:
    - The top images for the hashtag [sunset](https://www.instagram.com/explore/tags/sunset/) contains many images that we would not recognise as "sunsets". 
    - Discovering the site [ingramer](https://ingramer.com/tools/instagram-top-hashtags/) highlighted how banal instagram's user's use of hashtags often is.
  -  Ways around this would be
    - Attempt to find choose suitable, homogenous hashtags, manually chosen to be quite niche
    - alternative sources of images (such as google images)
    - use some other technique to determine which images are unlikely to belond in your set of training images before training the GAN.
  - I guess part of the objective of "predicting" instagram content should naturally include the influence of a hashtag's "abuse" and this will lead to more *abstract impressions* of images from a topic/hashtag



## Future Developments:
- [Incorporate laplacian pyramid approach](https://arxiv.org/pdf/1506.05751.pdf)
- Filter images before training
- Train/output higher resolution images
- AI Upscaling of images
- Twitter / NLP Equivalent

## References:
A large proportion of the current code is taken from the following site:
[DCGAN Tutorial — PyTorch Tutorials 1.6.0 documentation](https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html)
