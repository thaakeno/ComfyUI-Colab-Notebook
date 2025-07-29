# 🚀 ComfyUI on Google Colab: Advanced & Flexible Deployment

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/ecafb60d-630f-42ce-8079-fef958ae4fe8" />

<p>
  <a href="https://visitorbadge.io/status?path=colab-1DkhCfMOAJ51B1rXFtm52lrzBqqPNtbVk">
    <img
      src="https://api.visitorbadge.io/api/visitors?path=colab-1DkhCfMOAJ51B1rXFtm52lrzBqqPNtbVk&label=Visitors&labelColor=%232e3440&countColor=%2337d67a&style=flat&labelStyle=none"
      width="157"
      alt="Visitors"
    />
  </a>
  &nbsp;&nbsp;
  <a href="https://colab.research.google.com/drive/1DkhCfMOAJ51B1rXFtm52lrzBqqPNtbVk?usp=sharing">
    <img
      src="https://colab.research.google.com/assets/colab-badge.svg"
      alt="Open In Colab"
      width="230"
    />
  </a>
</p>

## ✨ Overview

This Google Colab notebook provides a comprehensive and highly configurable environment for deploying and running [ComfyUI](https://comfyui.com/), a powerful node-based interface for Stable Diffusion. Designed for efficiency and scalability, this setup offers robust features for managing models, custom nodes, and remote access, making it suitable for both rapid prototyping and sustained AI art generation.

### Key Features:

*   **💻 Live Command Center:** A rich, real-time dashboard to monitor every aspect of your session, including GPU/CPU/RAM utilization, VRAM usage, server status, and a detailed event log.
*   **💾 Hybrid Storage System:** A sophisticated `SAVE_TO_GDRIVE` toggle allows you to choose your storage strategy. Save everything to Google Drive for persistence, or offload large models to Colab's temporary storage to conserve Drive space.
*   **📥 Universal Asset Downloader:** A powerful, all-in-one downloader that intelligently handles links from **Civitai, Hugging Face, and MEGA**. It automatically detects asset types from Civitai image pages and downloads all required models and LoRAs.
*   **🎥 Specialized WAN/FLUX Model Support:** Dedicated downloader cells for complex video and flow-based models like **WAN 2.2** and **FLUX**, ensuring all components are placed in the correct directories.
*   **🔌 Persistent Custom Nodes:** Install and manage a vast ecosystem of custom nodes with a single click. All nodes are saved to your Google Drive, ensuring they persist across all your sessions.
*   **🌐 Secure Remote Access:** Integrated Ngrok support generates a secure, public URL, allowing you to access and control your ComfyUI instance from any browser, anywhere.
*   **⚙️ Effortless Configuration:** A clean, centralized configuration panel for all your API keys (Civitai, Hugging Face) and settings, including Colab Secrets support for enhanced security.

<img width="1146" height="543" alt="image" src="https://github.com/user-attachments/assets/2987b571-c138-4307-971e-ae09f414039e" />

---

## 💾 Storage Configuration

The notebook’s `SAVE_TO_GDRIVE` setting controls your storage strategy:

*   **`SAVE_TO_GDRIVE = True`**
    All data — including models, nodes, inputs, and outputs — are saved persistently in your Google Drive folder (`GDRIVE_BASE`). This ensures no need to re-download models after reconnecting.

*   **`SAVE_TO_GDRIVE = False`**
    Only essential user data and configurations are saved to Google Drive. Large models are stored temporarily on Colab’s runtime storage. This saves Drive space but requires model re-download each session.
    
    <img width="1816" height="244" alt="image" src="https://github.com/user-attachments/assets/61013201-17d3-4b38-9e69-0b3e707cc8ea" />

---

## ⚙️ Usage Instructions

### 1. Runtime Setup

* Go to `Runtime` > `Change runtime type` in Colab.
* Select GPU accelerator (T4 or A100 recommended).

### 2. Configure Settings

In the "Enhanced ComfyUI User Configuration" cell, set:

* `SAVE_TO_GDRIVE` (True/False)
* `GDRIVE_BASE` (path in your Google Drive)
* API tokens for Hugging Face (`HF_TOKEN`), Civitai (`CIVITAI_API_KEY`), and Ngrok (`NGROK_AUTHTOKEN`)
* Optional: `FORCE_MODEL_REFRESH` to re-download models

### 3. Environment Setup

Run sequentially:

* **Install Dependencies & Setup ComfyUI:** Installs system/Python packages and clones ComfyUI repo.
* **Google Drive Integration & Path Config:** Mounts Drive, creates directories, and configures model paths.

### 4. Manage Models & Nodes

* Use the **Universal Asset Downloader** to fetch assets via URLs (Civitai, Hugging Face, MEGA).
* Download WAN models, Hugging Face models, or Civitai checkpoints/LoRAs from curated lists.
* Install custom nodes, including ComfyUI-Manager and popular extensions, with persistence.

### 5. (Optional) Remote Access Setup

Run the Ngrok setup cell if remote access is required (ensure `NGROK_AUTHTOKEN` is set).

### 6. Launch ComfyUI

Run the launch cell to:

* Start ComfyUI server
* Enable live resource monitoring
* Access via local URL and public Ngrok URL (if configured)

---

## 📥 Importing Custom Workflows

To extend functionality, import JSON workflow files:

1. Download or save a workflow `.json` file.
2. Open your ComfyUI web interface.
3. Use the "Load" button to import the workflow into your node graph.

---

Happy creating with ComfyUI! ✨
