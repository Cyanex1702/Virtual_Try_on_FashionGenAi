# Virtual Try-On FashionGenAI

**Virtual Try-On FashionGenAI** is an AI-powered tool that allows users to visualize themselves in different clothes based on their own images and text prompts. The project utilizes **Stable Diffusion Inpainting** and the **U2Net segmentation model** to isolate clothing parts (upper or lower body) and generate a customized outfit based on the user's choice.

## Features
- Use pre-trained **Stable Diffusion** for realistic clothing inpainting.
- Automatic **clothing segmentation** with U2Net.
- Customizable prompts for clothing style and color.
- Optional background removal using **rembg**.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Cyanex1702/Virtual_Try_on_FashionGenAi.git
   cd Virtual_Try_on_FashionGenAi
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the pre-trained U2Net model:
   ```bash
   # Assumes the checkpoint path is already configured
   # Alternatively, manually place the checkpoint in the `trained_checkpoint` folder
   ```

## Usage
To run the virtual try-on pipeline, use the following command:

```bash
python main.py --image <path_to_image> --prompt "A pink cloth" --part upper --resolution 512 --output output.jpg
```

### Arguments
- `--image`: Path to the input image.
- `--prompt`: Text prompt describing the desired clothing style.
- `--part`: Which body part to focus on (`upper` or `lower`).
- `--resolution`: Resolution for the generated output.
- `--num_steps`: Number of diffusion steps (default 5).
- `--guidance_scale`: Strength of prompt adherence (default 7.5).
- `--rembg`: Enable background removal.
- `--output`: Path to save the final output image.

## Model Details
- **Stable Diffusion Inpainting**: Utilizes a model trained by RunwayML to fill in the clothing region.
- **U2Net Segmentation**: Used for precise segmentation of clothing regions (upper or lower body) from images.
- **rembg**: Background removal for a cleaner result.

## Examples
Example command:
```bash
python main.py --image ./example.jpg --prompt "A blue dress" --part upper --output result.jpg
```
Output:
![Example Output](./assets/output_example.jpg)

## Future Work
- Support for additional clothing items.
- Enhanced fine-tuning for more diverse prompts.

## Credits
This project leverages the open-source [Stable Diffusion](https://huggingface.co/runwayml/stable-diffusion-inpainting) and [U2Net](https://github.com/NathanUA/U-2-Net).

## License
[MIT License](LICENSE)
