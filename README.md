
# Universal AI Image Generator

Generate images using multiple AI providers from a single script. Supports OpenAI DALL-E, Grok, Stability AI, Replicate, Together AI, and more.

## 🎨 Supported Providers

| Provider | Models | Key Features |
|----------|--------|--------------|
| **OpenAI** | DALL-E 2, DALL-E 3 | High quality, multiple styles |
| **Grok (X.AI)** | Grok-2-Vision | Fast, customizable quality |
| **Stability AI** | Stable Diffusion XL | Open source, highly customizable |
| **Replicate** | SDXL, FLUX, and more | Access to various models |
| **Together AI** | FLUX.1 Schnell | Fast generation, competitive pricing |

## ✨ Features

- ✅ **Multi-provider support** - Switch between AI providers seamlessly
- ✅ **Automatic downloads** - All images saved to organized folders
- ✅ **Customizable settings** - Control size, quality, steps, and more
- ✅ **Smart file naming** - Timestamps and provider names in filenames
- ✅ **Interactive CLI** - Easy-to-use command-line interface
- ✅ **Error handling** - Robust error messages and retry capability

## 📦 Installation

### Requirements
- Python 3.7 or higher

### Install Dependencies

```bash
pip install requests
```

Or use the requirements file:
```bash
pip install -r requirements.txt
```

## 🚀 Quick Start

1. Run the script:
```bash
python universal_ai_image_generator.py
```

2. Enter download folder name (or press Enter for default)

3. Configure providers by entering API keys (skip any you don't have)

4. Start generating images!

## 🔑 Getting API Keys

### OpenAI (DALL-E)
- Visit: https://platform.openai.com/api-keys
- Sign up and create an API key
- Models: `dall-e-2`, `dall-e-3`

### Grok (X.AI)
- Visit: https://console.x.ai/
- Create account and get API key
- Models: `grok-2-vision-1212`

### Stability AI
- Visit: https://platform.stability.ai/
- Sign up and get API key
- Models: `stable-diffusion-xl-1024-v1-0`

### Replicate
- Visit: https://replicate.com/
- Create account and get API token
- Access to: SDXL, FLUX, Stable Diffusion, and more

### Together AI
- Visit: https://api.together.xyz/
- Sign up and get API key
- Models: FLUX.1 Schnell and more

## 📖 Usage Examples

### Basic Usage

```bash
$ python universal_ai_image_generator.py

# Select provider
🤖 Select provider (openai/grok/stability): openai

# Enter prompt
💭 Enter image prompt: a serene mountain lake at sunset

# Generated! ✅
```

### Custom Settings

Each provider has specific settings you can customize:

#### OpenAI DALL-E
```
Model: dall-e-2 or dall-e-3
Size: 1024x1024, 1792x1024, 1024x1792
Quality: standard, hd
Style: vivid, natural
```

#### Grok
```
Size: 256x256, 512x512, 1024x1024, 1792x1024, 1024x1792
Quality: low, medium, high
Style: natural, vivid
```

#### Stability AI
```
Width: 512-1536 (multiple of 64)
Height: 512-1536 (multiple of 64)
Steps: 10-50
CFG Scale: 0-35
```

#### Replicate
```
Model: stability-ai/sdxl, black-forest-labs/flux-schnell, etc.
Width/Height: customizable
Inference Steps: 1-100
```

#### Together AI
```
Model: black-forest-labs/FLUX.1-schnell
Width/Height: customizable
Steps: 1-50
```

## 💻 Programmatic Usage

You can also use the generator in your own Python scripts:

```python
from universal_ai_image_generator import UniversalImageGenerator

# Initialize
generator = UniversalImageGenerator(download_folder="my_images")

# Add providers
generator.add_provider('openai', 'your-openai-key')
generator.add_provider('grok', 'your-grok-key')
generator.add_provider('stability', 'your-stability-key')

# Generate with OpenAI
filepath = generator.generate(
    provider='openai',
    prompt='a futuristic city at night',
    model='dall-e-3',
    size='1024x1024',
    quality='hd',
    style='vivid'
)

# Generate with Grok
filepath = generator.generate(
    provider='grok',
    prompt='abstract art with vibrant colors',
    size='1024x1024',
    quality='high'
)

# Generate with Stability AI
filepath = generator.generate(
    provider='stability',
    prompt='photorealistic portrait',
    width=1024,
    height=1024,
    steps=40,
    cfg_scale=7
)

print(f"Image saved to: {filepath}")
```

## 📁 File Organization

Images are saved with the following naming convention:
```
YYYYMMDD_HHMMSS_provider_prompt_text.png
```

Examples:
- `20260203_143052_openai_mountain_lake.png`
- `20260203_143125_grok_abstract_art.png`
- `20260203_143200_stability_portrait.png`

## 🎯 Provider Comparison

| Feature | OpenAI | Grok | Stability | Replicate | Together |
|---------|--------|------|-----------|-----------|----------|
| Speed | Fast | Fast | Medium | Varies | Fast |
| Quality | High | High | High | Varies | High |
| Customization | Medium | Medium | High | High | High |
| Cost | $$$ | $$ | $ | $ | $ |
| Ease of Use | Easy | Easy | Medium | Medium | Easy |

## ⚙️ Advanced Configuration

### Multiple Providers
You can configure multiple providers and switch between them:

```python
# Configure all providers
generator.add_provider('openai', 'sk-...')
generator.add_provider('grok', 'xai-...')
generator.add_provider('stability', 'sk-...')

# Use whichever you want
generator.generate('openai', 'prompt here')
generator.generate('grok', 'another prompt')
```

### Batch Generation
Generate multiple images with different providers:

```python
prompts = [
    "a sunset over mountains",
    "abstract geometric patterns",
    "futuristic cityscape"
]

for prompt in prompts:
    generator.generate('grok', prompt)
    time.sleep(2)  # Rate limiting
```

## 🐛 Troubleshooting

### Authentication Errors
- Double-check your API keys
- Ensure keys have proper permissions
- Check if billing is set up (for paid APIs)

### Rate Limiting
- Add delays between requests
- Check your provider's rate limits
- Consider upgrading your plan

### Download Failures
- Check internet connection
- Verify folder permissions
- Ensure enough disk space

### Provider Not Working
- Verify API endpoint URLs are current
- Check provider's status page
- Review error messages for details

## 🔒 Security Notes

- Never commit API keys to version control
- Use environment variables for production
- Rotate keys regularly
- Monitor API usage and costs

## 📊 Cost Optimization

- **OpenAI DALL-E 3**: ~$0.040-0.080 per image
- **Grok**: Pricing varies, check X.AI
- **Stability AI**: ~$0.004 per image
- **Replicate**: Pay-per-second pricing
- **Together AI**: Competitive per-image pricing

Choose providers based on your quality needs and budget!

## 🆘 Support

For issues or questions:
1. Check this README
2. Review provider documentation
3. Check API status pages
4. Test with simple prompts first

## 📝 License

Free to use and modify for personal and commercial projects.

## 🚧 Future Enhancements

Potential additions:
- Image editing capabilities
- Batch processing from files
- GUI interface
- More providers (Midjourney API when available)
- Image variations and editing
- Prompt templates library
Here are some ready-to-use prompts to animate images (for tools like Runway, Pika, Kaiber, LeiaPix, or AnimateDiff). You can copy and adjust based on your image style.

---

## 🎬 General Image Animation Prompts

### 1️⃣ Cinematic Motion Prompt

```
Add smooth cinematic camera movement, subtle parallax depth, gentle lighting changes, realistic motion, soft wind effect, ultra realistic animation, 4k, cinematic depth of field, natural movement
```

### 2️⃣ Slow Zoom + Parallax

```
Create a slow zoom-in camera movement with parallax depth effect, subtle background motion, smooth transitions, cinematic lighting, high quality realistic animation
```

### 3️⃣ Dramatic Motion Prompt

```
Animate with dramatic lighting, moving clouds, dynamic camera pan, realistic motion blur, cinematic atmosphere, ultra detailed, movie scene style
```

### 4️⃣ Fantasy Style Animation

```
Add magical glowing particles, floating dust, gentle wind movement, soft cinematic motion, fantasy atmosphere, smooth animation, dreamy lighting
```

### 5️⃣ Realistic Character Animation

```
Make the character slightly breathe, natural eye blink, soft hair movement, subtle body motion, realistic facial animation, smooth cinematic motion
```

---

## 🌆 Scene-Based Prompts

### 🌃 City / Background Image

```
Animate neon lights flickering, moving cars, slow camera pan, light reflections, cinematic night atmosphere, ultra realistic motion
```

### 🌿 Nature / Landscape Image

```
Add flowing water motion, moving clouds, wind blowing trees, birds flying, soft camera movement, peaceful cinematic animation
```

### 🧑 Portrait Animation Prompt

```
Subtle breathing motion, natural blinking eyes, slight head movement, soft hair movement, cinematic lighting, realistic animation
```

---

## ⚡ Advanced Professional Prompt

```
Ultra smooth cinematic animation, parallax depth, dynamic lighting changes, realistic motion blur, slow camera dolly movement, high detail, 4k, film look
```

---

## 🎥 Short Loop Animation Prompt

```
Create a seamless loop animation, subtle motion, smooth camera movement, natural environment effects, high quality cinematic loop
```

---


