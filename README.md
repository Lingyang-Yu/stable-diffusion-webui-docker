# Stable Diffusion Webui Docker

This repository provides the [WebUI](https://github.com/hlky/stable-diffusion-webui) as docker for easy setup and deployment.

Special thanks to everyone behind these awesome projects, without them, none of this would have been possible:

- https://github.com/hlky/stable-diffusion-webui
- https://github.com/AUTOMATIC1111/stable-diffusion-webui
- https://github.com/CompVis/stable-diffusion

## Setup

make sure you have docker installed and up to date. Download this repo and run:

```
docker compose build
```

you can let it build in the background while you go to the next step:

### Download the different models

[More info here](https://rentry.org/GUItard)

- Stable Diffusion version 1.4 can be downloaded [here](https://drive.yerf.org/wl/?id=EBfTrmcCCUAGaQBXVIj5lJmEhjoP1tgl), rename to `model.ckpt`
- GFPGAN to improve generated faces. Download [GFPGANv1.3.pth](https://github.com/TencentARC/GFPGAN/releases/download/v1.3.0/GFPGANv1.3.pth).
- RealESRGAN for super-sampling, download [RealESRGAN_x4plus.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.1.0/RealESRGAN_x4plus.pth) and [RealESRGAN_x4plus_anime_6B.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.2.4/RealESRGAN_x4plus_anime_6B.pth).

Put all of the downloaded models in the `models` folder, if everything is setup correctly, the folder structure should look something like this:

```
├── README.md
├── docker-compose.yml
├── build
│   └── Dockerfile
├── cache
├── models
│   ├── GFPGANv1.3.pth
│   ├── RealESRGAN_x4plus.pth
│   ├── RealESRGAN_x4plus_anime_6B.pth
│   └── model.ckpt
├── output
```

### Run

After the build is done, you can run the app with:

```
docker compose up --build
```

Will start the app on http://localhost:7860/

Note: the first start will take sometime as some other models will be downloaded, these will be cached in the `cache` folder, so next runs are faster.

## Config

in the `docker-compose.yml` you can change the cli parameters of the webui, the ports, and gpu setup. You can find all cli configs [here](https://github.com/hlky/stable-diffusion-webui/blob/b2dc4539d4171ab4fc78471a5bb9425d6a5d5445/webui.py)

# Disclaimer

The authors of this project are not responsible for any content generated using this interface.

This license of this software forbids you from sharing any content that violates any laws, produce any harm to a person, disseminate any personal information that would be meant for harm, spread misinformation and target vulnerable groups. For the full list of restrictions please read [the license](./LICENSE).

By using this software you agree to the aforementioned license and [this one](./Licen.TXT)
