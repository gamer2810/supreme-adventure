---
media_subpath: assets/img/uploads/
title: Run Deepseek R-1 on your NVIDIA-powered Windows laptop
date: February 2, 2025 7:10 PM
categories:
  - AI
tags:
  - deepseek
  - tutorial
  - wsl
  - windows
  - nvidia
  - r-1
description: A very short walkthrough with ready-to-run commands to install
  Deepseek R-1 on your NVIDIA-powered Windows laptop.
toc: true
comments: true
---
## Prerequisite: Install WSL 2

Reference: https://learn.microsoft.com/en-us/windows/wsl/install

## Step 1: Install WSL

Open your Command Prompt and run this command to have wsl installed 

```bash
wsl --install
```

## Step 2: Install Ollama on WSL

Wait for the WSL installation to complete.

Run the following command on your WSL console:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

## Step 3: Install Deepseek R-1 model

Now you can install your favorite Deepseek R-1 model. 

They are listed here: [Ollama's Deepseek R-1](https://ollama.com/library/deepseek-r1:7b)

I used the 8B params version on my 3070ti and it works nice.

You should test out different versions to see which works for you.

Run the following command on your WSL console:

```bash
ollama run deepseek-r1:7b
```

## Step 4: Install uv

You may have to install `curl` using `sudo apt install curl`

Then run this command to install uv

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## Step 5: Install Open Web UI

Make sure there is no process listening on port 8080 on the *windows* interface.

Run the following command on WSL:

```bash
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

## Step 6: Start chatting!

Go to http://localhost:8080/ on your windows browser, setup a locally-saved account and start chatting with the model.

![demo-chat-ui](/assets/img/uploads/chatui.png "The result!")

Have fun!
