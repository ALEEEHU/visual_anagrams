<p align=center> 𝐌𝐨𝐝𝐞𝐥𝐢𝐧𝐠 𝐏𝐞𝐫𝐜𝐞𝐩𝐭𝐮𝐚𝐥 𝐀𝐦𝐛𝐢𝐠𝐮𝐢𝐭𝐲 𝐢𝐧 𝐀𝐈-𝐆𝐞𝐧𝐞𝐫𝐚𝐭𝐞𝐝 𝐈𝐦𝐚𝐠𝐞𝐬 </p>

# Test Examples (Click the website [here](https://yuqihuisgreat.github.io/))

1. Test codes: Visual anagrams and IllusionDiffusion

2. 90-degree rotation illusion (counter-clockwise)

## Hyperparameters Code 
Seeds, Inference_steps and guidance_scale have tested.

IllusionDiffusion code in `IllusionDiffusion_hyperparameters.ipynb`


## Diffusion Model Parameters

This section explains three key parameters you will often see when running diffusion models.

### 🎲 Seed
- Controls the random number generator used at the start of sampling.  
- Using the same seed with the same settings → reproducible results.  
- Changing the seed → new random noise → different image variations.  

### ⏱ Inference Steps
- The number of denoising steps the model runs to transform noise into an image.  
- **Low steps** → faster, but results may look rough or less detailed.  
- **High steps** → slower, but usually higher quality and more stable.  

### 🎯 Guidance Scale
- Also called *classifier-free guidance scale*.  
- Controls how strongly the model follows the text prompt.  
- **Low values (3–5)** → looser, more creative, less tied to the prompt.  
- **High values (7–12)** → closely follows the prompt, but may reduce diversity or naturalness.  


In our experiments, we use the following parameter ranges:

- **Seed list**: `[0, 1, 2, 42, 100]`  
- **Inference steps list**: `[50, 100, 200, 500, 1000]`  
- **Guidance scale list**: `[2, 5, 7.5, 10, 15]`

<details span>
<summary><b>Why These Settings?</b></summary>

##### 🎲 Seed
- Multiple seeds ensure that results are **not biased by a single random initialization**.  
- Using both small values (0, 1, 2) and common defaults (42, 100) provides diversity and reproducibility.  
- This setup allows us to evaluate the **stability and consistency** of the model across different noise conditions.  

##### ⏱ Inference Steps
- Covers a **broad spectrum** from fast generation (`50` steps) to high-quality sampling (`1000` steps).  
- Intermediate values (`100`, `200`, `500`) allow us to study the **trade-off between efficiency and image quality**.  
- Such scaling is important for understanding how much the model improves with more iterations, and where diminishing returns occur.  

##### 🎯 Guidance Scale
- The chosen values range from **weak guidance (2)** to **strong prompt adherence (15)**.  
- Including moderate values (`5`, `7.5`, `10`) lets us study the **balance between creativity and prompt faithfulness**.  
- This range is widely used in practice, making results **scientifically comparable** to prior works.  
  
</details>



# Methods Comparison

| Method               | rotation illusion                                    | flip illusion | zoom in and out illusion (Hybrid Images) |
| -------------------- | ---------------------------------------------------- | ------------- | ---------------------------------------- |
| Visual_anagrams      | 90-degree (clockwise, counter-clockwise, 180-degree) | √            | ×                                       |
| IllusionDiffusion    | 90-degree(counter-clockwise,180-degree)              | ×            | ×                                       |
| Factorized Diffusion | ×                                                   | ×            | √                                       |

# References

1. Visual Anagrams: Generating Multi-View Optical Illusions with Diffusion Models (CVPR 24 Oral) [Website](https://dangeng.github.io/visual_anagrams/)，[Paper](https://arxiv.org/abs/2311.17919)
2. IllusionDiffusion, [Code](https://github.com/tancik/Illusion-Diffusion)
3. Factorized Diffusion (ECCV 24)，[Website](https://dangeng.github.io/factorized_diffusion/), [Paper](https://arxiv.org/abs/2404.11615)
