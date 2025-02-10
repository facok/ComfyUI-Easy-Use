![comfyui-easy-use](https://github.com/user-attachments/assets/9b7a5e44-f5e2-4c27-aed2-d0e6b50c46bb)

<div align="center">
<a href="https://space.bilibili.com/1840885116">Video Tutorial</a> |
<a href="https://docs.easyuse.yolain.com">Docs</a> | 
<a href="https://github.com/yolain/ComfyUI-Yolain-Workflows">Workflow Collection</a> |
<a href="#%EF%B8%8F-donation">Donation</a> 
<br><br>
<a href="./README.md"><img src="https://img.shields.io/badge/🇬🇧English-0b8cf5"></a>
<a href="./README.ZH_CN.md"><img src="https://img.shields.io/badge/🇨🇳中文简体-e9e9e9"></a>
</div>

**ComfyUI-Easy-Use** is an efficiency custom nodes integration package, which is extended on the basis of [TinyTerraNodes](https://github.com/TinyTerra/ComfyUI_tinyterraNodes). It has been integrated and optimized for many popular awesome custom nodes to achieve the purpose of faster and more convenient use of ComfyUI. While ensuring the degree of freedom, it restores the ultimate smooth image production experience that belongs to Stable Diffusion.

## 👨🏻‍🎨 Introduce

- Inspire by [tinyterraNodes](https://github.com/TinyTerra/ComfyUI_tinyterraNodes), which greatly reduces the time cost of tossing workflows。
- UI interface beautification, the first time you install the user, if you need to use the UI theme, please switch the theme in Settings -> Color Palette and refresh page.
- Added a node for pre-sampling parameter configuration, which can be separated from the sampling node for easier previewing
- Wildcards and lora's are supported, for Lora Block Weight usage, ensure that the custom node package has the [ComfyUI-Inspire-Pack](https://github.com/ltdrdata/ComfyUI-Inspire-Pack)
- Multi-selectable styled cue word selector, default is Fooocus style json, custom json can be placed under styles, samples folder can be placed in the preview image (name and name consistent, image file name such as spaces need to be converted to underscores '_')
- The loader enables the A1111 prompt mode, which reproduces nearly identical images to those generated by webui, and needs to be installed [ComfyUI_smZNodes](https://github.com/shiimizu/ComfyUI_smZNodes) first. 
- Noise injection into the latent space can be achieved using the `easy latentNoisy` or `easy preSamplingNoiseIn` node
- Simplified processes for SD1.x, SD2.x, SDXL, SVD, Zero123, etc. [Example](https://github.com/yolain/ComfyUI-Easy-Use?tab=readme-ov-file#StableDiffusion)
- Simplified Stable Cascade [Example](https://github.com/yolain/ComfyUI-Easy-Use?tab=readme-ov-file#StableCascade)
- Simplified Layer Diffuse [Example](https://github.com/yolain/ComfyUI-Easy-Use?tab=readme-ov-file#LayerDiffusion)，The first time you use it you may need to run `pip install -r requirements.txt` to install the required dependencies.
- Simplified InstantID [Example](https://github.com/yolain/ComfyUI-Easy-Use?tab=readme-ov-file#InstantID), You need to make sure that the custom node package has the [ComfyUI_InstantID](https://github.com/cubiq/ComfyUI_InstantID)
- Extending the usability of XYplot
- Fooocus Inpaint integration
- Integration of common logical calculations, conversion of types, display of all types, etc.
- Background removal nodes for the RMBG-1.4 model supporting BriaAI, [BriaAI Guide](https://huggingface.co/briaai/RMBG-1.4)
- Forcibly cleared the memory usage of the comfy UI model are supported
- Stable Diffusion 3 multi-account API nodes are supported
- Support SD3's model
- Support Kolors‘s model
- Support Flux's model
- Support lazy if else and for loops

## 👨🏻‍🔧 Installation
Clone the repo into the **custom_nodes** directory and install the requirements:
```shell
#1. Clone the repo
git clone https://github.com/yolain/ComfyUI-Easy-Use
#2. Install the requirements
Double-click install.bat to install the required dependencies
```

## 📜 Changelog

**v1.2.7**

- Optimize display of the node maps
- Add `ben2` on `easy imageRemBg`
- Using a new way to display the models thumbnails in the loaders (supported diffusion_models、lors、checkpoints)

**v1.2.6**

- Fix missing the "Red Rect" styles when you are missing custom nodes.
- Adjust the default value of `clip_skip` from `-1` to `-2` in some easy loaders.
- Fix the issue due to set nodes missing custom nodes which their connected, causing canvas to be messed up.
- Fix the `easy imageChooser` can not using in a loop.

**v1.2.5**

- Added `enable (GPU=A1111)` noise mode on `easy preSamplingCustom` and `easy preSamplingAdvanced` 
- Added `easy makeImageForICLora`
- Added `REGULAR - FLUX and SD3.5 only (high strength)` preset for InstantX Flux ipadapter on `easy ipadapterApply`
- Fix brushnet can not be used with startup arg `--fast` mode
- Support briaai RMBG-2.0
- Support mochi 
- Implement reuse of end nodes output in the loop body (e.g: previewImage and showAnything and sth.) 

**v1.2.4**

- Added `easy imageSplitTiles` and `easy imageTilesFromBatch`
- Support `model_override`,`vae_override`,`clip_override` can be input separately to `easy fullLoader`
- Added `easy saveImageLazy`
- Added `easy loadImageForLoop`
- Added `easy isFileExist`
- Added `easy saveText`

**v1.2.3**

- `easy showAnything` and `easy cleanGPUUsed` added slot of output
- Added human parts segmentation to `easy humanSegmentation` - Code based on [ComfyUI_Human_Parts](https://github.com/metal3d/ComfyUI_Human_Parts)
- Using FluxGuidance when you are using a flux model and choose basicGuider and set the cfg>0 on `easy preSamplingCustom`
- Added `easy loraStackApply` and `easy controlnetStackApply` - Apply loraStack and controlnetStack

**v1.2.2**

- Added `easy batchAny`
- Added `easy anythingIndexSwitch`
- Added `easy forLoopStart` and `easy forLoopEnd`  
- Added `easy ifElse`  
- Added v2 web frond-end code
- Added `easy fluxLoader`
- Added support for `controlnetApply` Related nodes with SD3 and hunyuanDiT
- Fixed after using `easy applyFooocusInpaint`, all lora models become unusable

**v1.2.1**

- Added `easy ipadapterApplyFaceIDKolors`
- Added **inspyrenet** to `easy imageRemBg` 
- Added `easy controlnetLoader++`
- Added **PLUS (kolors genernal)** and **FACEID PLUS KOLORS** preset to `easy ipadapterApply` and `easy ipadapterApplyADV` (Supported kolors ipadapter）
- Added `easy kolorsLoader` - Code based on [MinusZoneAI](https://github.com/MinusZoneAI/ComfyUI-Kolors-MZ)'s and [kijai](https://github.com/kijai/ComfyUI-KwaiKolorsWrapper)'s repo, thanks for their contribution.

**v1.2.0**

- Added `easy pulIDApply` and `easy pulIDApplyADV`
- Added `easy huanyuanDiTLoader` and `easy pixArtLoader`
- Added **easy sliderControl** - Slider control node, which can currently be used to control the parameters of ipadapterMS (double-click the slider to reset to default)
- Added **layer_weights** in `easy ipadapterApplyADV`

**v1.1.9**

- Added **gitsScheduler**
- Added `easy imageBatchToImageList` and `easy imageListToImageBatch` 
- Recursive subcategories nested for models
- Support for Stable Diffusion 3 model
- Added `easy applyInpaint` - All inpainting mode in this node

**v1.1.8**

- Added `easy controlnetStack`
- Added `easy applyBrushNet` - [Workflow Example](https://github.com/yolain/ComfyUI-Yolain-Workflows/blob/main/workflows/2_advanced/2-4inpainting/2-4brushnet_1.1.8.json)
- Added `easy applyPowerPaint` - [Workflow Example](https://github.com/yolain/ComfyUI-Yolain-Workflows/blob/main/workflows/2_advanced/2-4inpainting/2-4powerpaint_outpaint_1.1.8.json)

**v1.1.7**

- Added `easy prompt` - Subject and light presets, maybe adjusted later
- Added `easy icLightApply` - Light and shadow migration, Code based on [ComfyUI-IC-Light](https://github.com/huchenlei/ComfyUI-IC-Light)
- Added `easy imageSplitGrid`
- `easy kSamplerInpainting` added options such as different diffusion and brushnet in **additional** widget
- Support for brushnet model loading - [ComfyUI-BrushNet](https://github.com/nullquant/ComfyUI-BrushNet)
- Added `easy applyFooocusInpaint` - Replace FooocusInpaintLoader
- Removed `easy fooocusInpaintLoader`

**v1.1.6**

- Added **alignYourSteps** to **schedulder** widget in all `easy preSampling` and `easy fullkSampler`
- Added **Preview&Choose** to **image_output** widget in `easy kSampler` & `easy fullkSampler`
- Added `easy styleAlignedBatchAlign` - Credit of [style_aligned_comfy](https://github.com/brianfitzgerald/style_aligned_comfy)
- Added `easy ckptNames`
- Added `easy controlnetNames`
- Added `easy imagesSplitimage` - Batch images split into single images
- Added `easy imageCount` - Get Image Count
- Added `easy textSwitch` - Text Switch

<details>
<summary><b>v1.1.5</b></summary>

- Rewrite `easy cleanGPUUsed` - the memory usage of the comfyUI can to be cleared
- Added `easy humanSegmentation` - Human Part Segmentation
- Added `easy imageColorMatch`
- Added `easy ipadapterApplyRegional`
- Added `easy ipadapterApplyFromParams`
- Added `easy imageInterrogator` - Image To Prompt
- Added `easy stableDiffusion3API` - Easy Stable Diffusion 3 Multiple accounts API Node
</details>

<details>
<summary><b>v1.1.4</b></summary>

- Added `easy preSamplingCustom` - Custom-PreSampling, can be supported cosXL-edit
- Added `easy ipadapterStyleComposition`
- Added the right-click menu to view checkpoints and lora information in all Loaders
- Fixed `easy preSamplingNoiseIn`、`easy latentNoisy`、`east Unsampler` compatible with ComfyUI Revision>=2098 [0542088e] or later
</details>

<details>
<summary><b>v1.1.3</b></summary>

- `easy ipadapterApply` Added **COMPOSITION** preset
- Supported [ResAdapter](https://huggingface.co/jiaxiangc/res-adapter) when load ResAdapter lora
- Added `easy promptLine`
- Added `easy promptReplace`
- Added `easy promptConcat`
- `easy wildcards` Added **multiline_mode**  
</details>

<details>
<summary><b>v1.1.2</b></summary>

- Optimized some of the recommended nodes for slots related to EasyUse
- Added **Enable ContextMenu Auto Nest Subdirectories** The setting item is enabled by default, and it can be classified into subdirectories, checkpoints and loras previews
- Added `easy sv3dLoader` 
- Added `easy dynamiCrafterLoader` 
- Added `easy ipadapterApply`
- Added `easy ipadapterApplyADV`
- Added `easy ipadapterApplyEncoder`
- Added `easy ipadapterApplyEmbeds`
- Added `easy preMaskDetailerFix`
- Fixed `easy stylesSelector` is change the prompt when not select the style
- Fixed `easy pipeEdit` error when add lora to prompt
- Fixed layerDiffuse xyplot bug
- `easy kSamplerInpainting` add *additional* widget，you can choose 'Differential Diffusion' or 'Only InpaintModelConditioning'
</details>

<details>
<summary><b>v1.1.1</b></summary>

- The issue that the seed is 0 when a node with a seed control is added and **control before generate** is fixed for the first time run queue prompt.
- `easy preSamplingAdvanced` Added **return_with_leftover_noise**
- Fixed `easy stylesSelector` error when choose the custom file
- `easy preSamplingLayerDiffusion` Added optional input parameter for mask
- Renamed all nodes widget name named seed_num to seed
- Remove forced **control_before_generate** settings。 If you want to use control_before_generate, change widget_value_control_mode to before in system settings
- Added `easy imageRemBg` - The default is BriaAI's RMBG-1.4 model, which removes the background effect more and faster
</details>

<details>
<summary><b>v1.1.0</b></summary>

- Added `easy imageSplitList` - to split every N images
- Added `easy preSamplingDiffusionADDTL` - It can modify foreground、background or blended additional prompt
- Added `easy preSamplingNoiseIn` It can replace the `easy latentNoisy` node that needs to be fronted to achieve better noise injection
- `easy pipeEdit` Added conditioning splicing mode selection, you can choose to replace, concat, combine, average, and set timestep range
- Added `easy pipeEdit` - nodes that can edit pipes (including re-enterable prompts)
- Added `easy preSamplingLayerDiffusion` and `easy kSamplerLayerDiffusion`
- Added a convenient menu to right-click on nodes such as Loader, Presampler, Sampler, Controlnet, etc. to quickly replace nodes of the same type
- Added `easy instantIDApplyADV` can link positive and negative
- Fixed layerDiffusion error when batch size greater than 1
- Fixed `easy wildcards` When LoRa is not filled in completely, LoRa is not automatically retrieved, resulting in failure to load LoRa
- Fixed the issue that 'BREAK' non-initiation when didn't use a1111 prompt style
- Fixed `easy instantIDApply` mask not input right
</details>

<details>
<summary><b>v1.0.9</b></summary>

- Fixed the error when ComfyUI-Impack-Pack and ComfyUI_InstantID were not installed
- Fixed `easy pipeIn`
- Added `easy instantIDApply` - you need installed [ComfyUI_InstantID](https://github.com/cubiq/ComfyUI_InstantID) fisrt, Workflow[Example](https://github.com/yolain/ComfyUI-Easy-Use/blob/main/README.en.md#InstantID)
- Fixed `easy detailerFix` not added to the list of nodes available for saving images formatting extensions
- Fixed `easy XYInputs: PromptSR` errors are reported when replacing negative prompts
</details>

<details>
<summary><b>v1.0.8</b></summary>

- `easy cascadeLoader` stage_c and stage_b support the checkpoint model (Download [checkpoints](https://huggingface.co/stabilityai/stable-cascade/tree/main/comfyui_checkpoints) models) 
- `easy styleSelector` The search box is modified to be case-insensitive
- `easy fullLoader` **positive**、**negative**、**latent** added to the output items
- Fixed the issue that 'easy preSampling' and other similar node, latent could not be generated based on the batch index after passing in
- Fixed `easy svdLoader` error when the positive or negative is empty
- Fixed the error of SDXLClipModel in ComfyUI revision 2016[c2cb8e88] and above (the revision number was judged to be compatible with the old revision)
- Fixed `easy detailerFix` generation error when batch size is greater than 1
- Optimize the code, reduce a lot of redundant code and improve the running speed
</details>

<details>
<summary><b>v1.0.7</b></summary>

- Added `easy cascadeLoader` - stable cascade Loader
- Added `easy preSamplingCascade` - stable cascade preSampling Settings
- Added `easy fullCascadeKSampler` - stable cascade stage-c ksampler full
- Added `easy cascadeKSampler` - stable cascade stage-c ksampler simple
- 
- Optimize the image to image[Example](https://github.com/yolain/ComfyUI-Easy-Use/blob/main/README.en.md#image-to-image)
</details>

<details>
<summary><b>v1.0.6</b></summary>

- Added `easy XYInputs: Checkpoint`
- Added `easy XYInputs: Lora`
- `easy seed` can manually switch the random seed when increasing the fixed seed value
- Fixed `easy fullLoader` and all loaders to automatically adjust the node size when switching LoRa
- Removed the original ttn image saving logic and adapted to the default image saving format extension of ComfyUI
</details>

<details>
<summary><b>v1.0.5</b></summary>

- Added `easy isSDXL` 
- Added prompt word control on `easy svdLoader`, which can be used with open_clip model
- Added **populated_text** on `easy wildcards`, wildcard populated text can be output
</details>

<details>
<summary><b>v1.0.4</b></summary>

- `easy showAnything` added support for converting other types (e.g., tensor conditions, images, etc.)
- Added `easy showLoaderSettingsNames` can display the model and VAE name in the output loader assembly
- Added `easy promptList`
- Added `easy fooocusInpaintLoader` （only the process of SDXLModel is supported）
- Added **Logic** nodes
- Added `easy imageSave` - Image saving node with date conversion and aspect and height formatting
- Added `easy joinImageBatch`
- `easy kSamplerInpainting` Added the **patch** input value to be used with the FooocusInpaintLoader node

- Fixed xyplot error when with Pillow>9.5
- Fixed `easy wildcards` An error is reported when running with the PS extension
- Fixed `easy XYInputs: ControlNet` Error
- Fixed `easy loraStack` error when **toggle** is disabled


- Changing the first-time install node package no longer automatically replaces the theme, you need to manually adjust and refresh the page
- `easy imageSave` added **only_preivew**
- Adjust the `easy latentCompositeMaskedWithCond` node
</details>

<details>
<summary><b>v1.0.3</b></summary>

- Added `easy stylesSelector`
- Added **scale_soft_weights** in `easy controlnetLoader` and `easy controlnetLoaderADV` 
- Added the queue progress bar setting item, which is not enabled by default


- Fixed `easy XYInputs: Sampler/Scheduler` Error
- Fixed the right menu has a problem when clicking the button
- Fixed `easy comfyLoader` error
- Fixed xyPlot error when connecting to zero123
- Fixed the error message in the loader when the prompt word was component
- Fixed `easy getNode` and `easy setNode` the title does not change when loading
- Fixed all samplers using subdirectories to store images


- Adjust the UI theme, divided into two sets of styles: the official default background and the dark black background, which can be switched in the color palette in the settings
- Modify the styles path to be compatible with other environments
</details>

<details>
<summary><b>v1.0.2</b></summary>

- Added `easy XYPlotAdvanced` and some nodes about `easy XYInputs`
- Added **Alt+1-Alt+9** Shortcut keys to quickly paste node presets for Node templates (corresponding to 1~9 sequences)
- Added a `📜Groups Map(EasyUse)` to the context menu.
- An `autocomplete` folder has been added, If you have [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) installed, the txt files in that folder will be merged and overwritten to the autocomplete .txt file of the pyssss package at startup.


- Fixed XYPlot is not working when `a1111_prompt_style` is True
- Fixed UI loading failure in the new version of ComfyUI
- `easy XYInputs ModelMergeBlocks` Values can be imported from CSV files
- Fixed `easy pipeToBasicPipe` Bug

- Removed `easy imageRemBg`
- Remove the introductory diagram and workflow files from the package to reduce the package size
- Replaced the font file used in the generation of XY diagrams
</details>

<details>
<summary><b>v1.0.1</b></summary>

- Fixed `easy comfyLoader` error
- Fixed All nodes that contain the value of the image size
- Added `easy kSamplerInpainting`
- Added `easy pipeToBasicPipe`
- Fixed `width` and `height` can not customize in `easy svdLoader`
- Fixed all preview image path (Previously, it was not possible to preview the image on the Mac system)
- Fixed `vae_name` is not working in `easy fullLoader` and `easy a1111Loader` and `easy comfyLoader`
- Fixed `easy fullkSampler` outputs error
- Fixed `model_override` is not working in `easy fullLoader`
- Fixed `easy hiresFix` error
- Fixed `easy xyplot` font file path error
- Fixed seed that cannot be fixed when you convert `seed_num` to `easy seed` 
- Fixed `easy pipeIn` inputs bug
- `easy preDetailerFix` have added a new parameter `optional_image`
- Fixed `easy zero123Loader` and `easy svdLoader` model into cache.
- Added `easy seed`
- Fixed `image_output` default value is "Preview"
- `easy fullLoader` and `easy a1111Loader` have added a new parameter `a1111_prompt_style`,that can reproduce the same image generated from stable-diffusion-webui on comfyui, but you need to install [ComfyUI_smZNodes](https://github.com/shiimizu/ComfyUI_smZNodes) to use this feature in the current version
</details>

<details>
<summary><b>v1.0.0</b></summary>

- Added `easy positive` - simple positive prompt text
- Added `easy negative` - simple negative prompt text
- Added `easy wildcards` - support for wildcards and hint text selected by Lora
- Added `easy portraitMaster` - PortraitMaster v2.2
- Added `easy loraStack` - Lora stack
- Added `easy fullLoader` - full version of the loader
- Added `easy zero123Loader` - simple zero123 loader
- Added `easy svdLoader` - easy svd loader
- Added `easy fullkSampler` - full version of the sampler (no separation)
- Added `easy hiresFix` - support for HD repair of Pipe
- Added `easy predetailerFix` and `easy DetailerFix` - support for Pipe detail fixing
- Added `easy ultralyticsDetectorPipe` and `easy samLoaderPipe` - Detect loader (detail fixed input)
- Added `easy pipein` `easy pipeout` - Pipe input and output
- Added `easy xyPlot` - simple xyplot (more controllable parameters will be updated in the future)
- Added `easy imageRemoveBG` - image to remove background
- Added `easy imagePixelPerfect` - image pixel perfect
- Added `easy poseEditor` - Pose editor
- New UI Theme (Obsidian) - Auto-load UI by default, which can also be changed in the settings 

- Fixed `easy globalSeed` is not working
- Fixed an issue where all `seed_num` values were out of order due to [cg-use-everywhere](https://github.com/chrisgoringe/cg-use-everywhere) updating the chart in real time
- Fixed `easy imageSize`, `easy imageSizeBySide`, `easy imageSizeByLongerSide` as end nodes
- Fixed the bug that `seed_num` (random seed value) could not be read consistently in history
</details>

<details>
<summary><b>Updated at 12/14/2023</b></summary>

- `easy a1111Loader` and `easy comfyLoader` added `batch_size` of required input parameters 
- Added the `easy controlnetLoaderADV` node
- `easy controlnetLoaderADV` and `easy controlnetLoader` added `control_net ` of optional input parameters
- `easy preSampling` and `easy preSamplingAdvanced` added `image_to_latent` optional input parameters
- Added the `easy imageSizeBySide` node, which can be output as a long side or a short side
</details>

<details>
<summary><b>Updated at 12/13/2023</b></summary>

-  Added the `easy LLLiteLoader` node, if you have pre-installed the kohya-ss/ControlNet-LLLite-ComfyUI package, please move the model files in the models to `ComfyUI\models\controlnet\` (i.e. in the default controlnet path of comfy, please do not change the file name of the model, otherwise it will not be read).
-  Modify `easy controlnetLoader` to the bottom of the loader category.
-  Added size display for `easy imageSize` and `easy imageSizeByLongerSize` outputs.
</details>

<details>
<summary><b>Updated at 12/11/2023</b></summary>
-  Added the `showSpentTime` node to display the time spent on image diffusion and the time spent on VAE decoding images
</details>

## The relevant node package involved

Disclaimer: Opened source was not easy. I have a lot of respect for the contributions of these original authors. I just did some integration and optimization.

| Nodes Name(Search Name)        | Related libraries                                                                        | Library-related node     |
|:-------------------------------|:----------------------------------------------------------------------------|:-------------------------|
| easy setNode                   | [ComfyUI-extensions](https://github.com/diffus3/ComfyUI-extensions) | diffus3.SetNode          |
| easy getNode                   | [ComfyUI-extensions](https://github.com/diffus3/ComfyUI-extensions) | diffus3.GetNode          |
| easy bookmark                  | [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) | Bookmark 🔖              |
| easy portraitMarker            | [comfyui-portrait-master](https://github.com/florestefano1975/comfyui-portrait-master) | Portrait Master          |
| easy LLLiteLoader              | [ControlNet-LLLite-ComfyUI](https://github.com/kohya-ss/ControlNet-LLLite-ComfyUI) | LLLiteLoader             |
| easy globalSeed                | [ComfyUI-Inspire-Pack](https://github.com/ltdrdata/ComfyUI-Inspire-Pack) | Global Seed (Inspire)    | 
| easy preSamplingDynamicCFG     | [sd-dynamic-thresholding](https://github.com/mcmonkeyprojects/sd-dynamic-thresholding) | DynamicThresholdingFull  | 
| dynamicThresholdingFull        | [sd-dynamic-thresholding](https://github.com/mcmonkeyprojects/sd-dynamic-thresholding) | DynamicThresholdingFull  | 
| easy imageInsetCrop            | [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) | ImageInsetCrop           | 
| easy poseEditor                | [ComfyUI_Custom_Nodes_AlekPet](https://github.com/AlekPet/ComfyUI_Custom_Nodes_AlekPet) | poseNode                 | 
| easy preSamplingLayerDiffusion | [ComfyUI-layerdiffusion](https://github.com/huchenlei/ComfyUI-layerdiffusion) | LayeredDiffusionApply... | 
| easy dynamiCrafterLoader       | [ComfyUI-layerdiffusion](https://github.com/ExponentialML/ComfyUI_Native_DynamiCrafter) | Apply Dynamicrafter    | 
| easy imageChooser              | [cg-image-picker](https://github.com/chrisgoringe/cg-image-picker) | Preview Chooser         | 
| easy styleAlignedBatchAlign              | [style_aligned_comfy](https://github.com/chrisgoringe/cg-image-picker) | styleAlignedBatchAlign       | 
| easy kolorsLoader              | [ComfyUI-Kolors-MZ](https://github.com/MinusZoneAI/ComfyUI-Kolors-MZ) | kolorsLoader            |


## Credits

[ComfyUI](https://github.com/comfyanonymous/ComfyUI) - Powerful and modular Stable Diffusion GUI

[ComfyUI-ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) - ComfyUI Manager

[tinyterraNodes](https://github.com/TinyTerra/ComfyUI_tinyterraNodes) - Pipe nodes (node bundles) allow users to reduce unnecessary connections

[ComfyUI-extensions](https://github.com/diffus3/ComfyUI-extensions) - Diffus3 gets and sets points that allow the user to detach the composition of the workflow 

[ComfyUI-Impact-Pack](https://github.com/ltdrdata/ComfyUI-Impact-Pack) - General modpack 1

[ComfyUI-Inspire-Pack](https://github.com/ltdrdata/ComfyUI-Inspire-Pack) - General Modpack 2

[ComfyUI-ResAdapter](https://github.com/jiaxiangc/ComfyUI-ResAdapter) - Make model generation independent of training resolution

[ComfyUI_IPAdapter_plus](https://github.com/cubiq/ComfyUI_IPAdapter_plus) - Style migration

[ComfyUI_InstantID](https://github.com/cubiq/ComfyUI_InstantID) - Face migration

[ComfyUI_PuLID](https://github.com/cubiq/PuLID_ComfyUI) - Face migration

[ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) - pyssss🐍

[cg-image-picker](https://github.com/chrisgoringe/cg-image-picker) - Image Preview Chooser

[ComfyUI_ExtraModels](https://github.com/city96/ComfyUI_ExtraModels) - DiT custom nodes

## Disclaimer

This software is provided “as is,” without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.

Users are solely responsible for ensuring that their use of this software complies with all applicable laws and regulations in the jurisdiction where they use the software or publish content generated by it. The authors and copyright holders are not responsible for any violations of laws or regulations by users in their respective locations.

## ☕️ Donation

**Comfyui-Easy-Use** is an GPL-licensed open source project. In order to achieve better and sustainable development of the project, i expect to gain more backers. <br>
If my custom nodes has added value to your day, consider indulging in a coffee to fuel it further! <br>
💖You can support me in any of the following ways:

- [BiliBili](https://space.bilibili.com/1840885116)
- [Afdian](https://afdian.com/a/yolain)
- [Wechat / Alipay](https://github.com/user-attachments/assets/803469bd-ed6a-4fab-932d-50e5088a2d03)

##  🌟Stargazers

My gratitude extends to the generous souls who bestow a star. Your support is much appreciated!

[![Stargazers repo roster for @yolain/ComfyUI-Easy-Use](https://reporoster.com/stars/yolain/ComfyUI-Easy-Use)](https://github.com/yolain/ComfyUI-Easy-Use/stargazers)