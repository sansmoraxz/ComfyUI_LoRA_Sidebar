# ComfyUI_LoRA_Sidebar
## What is this?
A custom front-end UX node that creates a visual library of all your LoRAs. It's designed to be fast, slim, and make using LoRAs in Comfy a lot more fun for visual users - especially if you have lots of LoRAs. Should make people used to A1111 and other UI heavy platforms feel more at home. If you've got lots of LoRAs, this sidebar could be your new best friend!

![image](https://github.com/user-attachments/assets/a1140952-2342-4c92-8f50-32067b2e2e0f)


## Features
- Sidebar that automatically generates a visual library of all your LoRA models
- Designed to be super fast for searches
- Easily filter LoRAs by base model (and any search term, obviously)
- View LoRA details via LoRA Info popup, includes important informant and include easy to copy trained words and tags
- Drag and drop LoRAs to create or update LoRA nodes on the canvas
  - Drag and drop images from the LoRA viewer to load entire workflows (if included)
- Categorize and sort your LoRAs in multiple ways such as folder structure and automatic or custom tags
- Works with custom LoRAs - see usage notes below
- Provides NSFW protection for all those LoRAs that you don't remember downloading 😁
- Battle tested with very large (9000+ models) LoRA libraries
- Supports symlinks!
- Supports video preview files, because why not

## Updates
- Initial Release

## Installation
### Registry / Manager
- Coming Soon
### Manual
- `git clone` this repo into your ComfyUI custom nodes folder
  - There are no python dependencies for this node since it's front end only, you can also just download and extract the node there and I won't tell.
- Make sure to enable the new menu in the ComfyUI settings
- After install you probably want to go into Lora Sidebar Settings and configure things to your liking. If you have a very large collection and want to use categories I suggest using the collapsed default setting.
- The sidebar will automatically detect and start to process all your LoRAs when you open it. This can take a while!

*NOTE - This sidebar will process and download images into the loraData directory within the custom node. This is so everything can be fast, but it does take ~1MB of space per 10 LoRAs. A collection of ~9500 LoRAs was ~1GB.*

## Usage
<img align="right" src="https://github.com/user-attachments/assets/32b9a961-e3a1-4d9f-bd87-6970138f1c47" height=550>

- Open the sidebar and start the initial import / process of your LoRAs
  - If you have a lot of LoRAs this can take a while. The reason this is so slow is because I've used **SAFE** rate limits for the CivitAI API. If you know where to look in the code you can change it, but I don't recommend it. The process will run the background and if you close Comfy before it finishes it will resume where it left off.
- Use the search box to quickly search for any LoRAs
  - The sidebar is fastest using no categories and just doing raw searches, I know it's not for everyone but you can give it a try.
- Filter by base model using the dropdown
- Add LoRAs to your favorites by clicking on the ⭐ (remove them by clicking it again)
- View LoRA details by click on the **i** button, this popup contains lots of useful data and lets you copy tags and delete LoRAs
- Copy the lora trained words by using the 📋 button
- Refresh LoRA details with the...refresh button
- Drag and drop the LoRA images to create a LoRA node on your canvas, or drop them on a LoRA node to update it
  - Only supports default (core) ComfyUI nodes for now
- Use the slider at the top to quickly change the size of the LoRA Previews
- Update LoRA previews and/or data by editing the preview image and info files in the LoRA folder in the custom node's loraData folder - this is the best way to get custom LoRAs working fully and all the data is local only 
- Customize the look and feel with the settings

## Settings
This plugin has a host of settings to customize the appearence and sorting. Settings that aren't (hopefully) self explainatory have tooltips to describe how they are used. The one that most people will want to mess with here are the custom tags for sorting, if you don't use your directory structure for that. Because of the performance hit I do recommend giving it a swing with the default None and see if that does the trick, but I get browsing isn't as fun that way. Honestly if you don't have 3k+ LoRAs it really doesn't matter.

![image](https://github.com/user-attachments/assets/9c3fd7bf-5dff-4207-b193-369c9c0a3ac5)

## Limitations
- Drag and drop only supports core Comfy nodes, if you have some custom nodes you use please open an issue and I can add support for whatever
- Sorting does make the sidebar perform worse than with sorting off, it's not really noticable if you have a lot of LoRAs though
- Sometimes with large LoRA libraries the sidebar won't load everything right, closing and reopening it fixes it (or hitting the X button on the search box) - this doesn't affect searching at all
- Sliders don't really look great and they don't use the right node. If you have sliders and use them frequently I strong suggest looking into one of my other sidebars - https://github.com/Kinglord/ComfyUI_Slider_Sidebar
- Again, this isn't a LoRA management tool so it's not made to help you manage your LoRA files
- With large datasets it can cause some timeouts, they are harmless but they do clutter the server logs a bit

## Requirements
- This is a front end plugn so you must use the new menu for to work, you can enable it in the ComfyUI settings here (Top or Bottom doesn't matter)

![image](https://github.com/user-attachments/assets/4dcbb5f2-8a68-4ef8-8759-084a8d5af7ab)

- ComfyUI 0.1.3+
- There's no additional python requirements since it's just a frontend UI.

## Roadmap
- [ ] Adding support for more LoRA nodes outside of ComfyUI Core - just open an issue for me to add them
- [ ] Look into fixing timeouts with large datasets so the server logs don't get spammed
- [ ] Investigate some ways to improve performance when using categories
- [ ] Whatever bugs you find / features you submit
- [X] Fix LoRA processor from grabbing hidden system files

## Why
![image](https://media1.tenor.com/m/wSGnuU9TOFgAAAAC/all-the-things-hyperbole-and-a-half.gif)

There have been other solutions for dealing with LoRAs visually in ComfyUI, but none of them hit the mark for me, and most of them made working with LoRAs slower than normal. I wanted to make smething that made working with LoRAs easier and faster, without any added bloat. I actually had worked on this and stoped when I heard about the new built-in model browser. However, I used it a few days ago and I have too many LoRAs and it crashed the front end. So, I wouldn't recommend trying to use that if you have a bunch like I do. This plugin was designed for true LoRA "power users" and to make their lives easier in ComfyUI.

## Credits
**LoRA Creators for all the great content they produce!**

**Comfy Org (Duh)**  
https://github.com/comfyanonymous/ComfyUI

https://www.comfy.org/discord

### Compatability
Tested on ComfyUI 0.2.0
Should work on any version 0.1.3+
