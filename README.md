*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [Generative AI Development](https://www.intuz.com/generative-ai-development/) · [Custom AI Development Solution](https://www.intuz.com/ai/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Automate AI video ad generation with Google Veo 3, Gemini, and Airtable

This n8n template from Intuz provides a complete and automated solution for transforming a static product image and a creative idea into a dynamic, AI-generated video ad.

Using Google’s state-of-the-art Veo 3 model, this workflow manages the entire creative process from concept to a final, downloadable video file.

## Who’s this workflow for?

- E-commerce Brands & Marketers
- Advertising Agencies
- Social Media Content Creators
- Product Managers

## How it works

1. **Submit a Creative Brief:** The workflow starts when a user submits a creative idea via a simple web form (e.g., “A Pepsi can exploding into a vibrant disco party”).

2. **Upload a Product Image:** The user is then prompted to upload a corresponding image (e.g., a high-quality photo of the Pepsi can).

3. **Log the Project in Airtable:** The idea and the uploaded image are saved to an Airtable base, which acts as the central tracking system for all video generation projects.

4. **AI Creative Analysis:** Google Gemini analyzes both the user’s text prompt and the uploaded image. It acts as an “AI Creative Director,” generating a detailed video brief that reinterprets the static image according to the user’s creative vision.

5. **Generate Video with Veo 3:** The detailed creative brief is sent to Google’s Veo 3 AI video generation model. The workflow initiates a long-running task to create the video.

6. **Retrieve the Final Video:** After a brief waiting period, the workflow polls the Veo 3 API to retrieve the finished video, converts it into a binary file, and makes it available for download directly from the n8n execution log.

## Key Requirements to Use This Template

### n8n Instance & Required Nodes

- An active n8n account (Cloud or self-hosted).
- This workflow uses the official n8n LangChain integration (`@n8n/n8n-nodes-langchain`).
- If you are using a self-hosted version of n8n, please ensure this package is installed.

### Google Cloud Account

- A Google Cloud Project with the Vertex AI API enabled.
- You must have access to both the Gemini and Veo 3 models within your project.
- You will need a Gemini API Key and a Google OAuth2 Credential configured for the Vertex AI scope.

### Airtable Account

- An Airtable base with a table set up to track the video projects. It should have columns for Image Prompt, Image (Attachment), Video (Attachment/URL), and Status.

## Setup Instructions

### 1. Airtable Configuration (Crucial)

- In the **Create a record**, **Get a record**, and **Update record** nodes, connect your Airtable credentials and update the Base ID and Table ID to match your setup.
- In the **Uploading Image in Airtable** (HTTP Request) node, you must edit the URL and the Authorization header to include your Base ID, Table ID, and Personal Access Token.

### 2. Google AI Configuration (Gemini & Veo)

- In the **Analyze image** (Google Gemini) node, select your Gemini API credentials.
- In both the **Generate Video Veo 3** and **Get the Video** (HTTP Request) nodes:
  - Replace `[Project ID]` and `[Location]` in the URLs with your own Google Cloud Project ID and region (e.g., `us-central1`).
  - Select your Google OAuth2 credentials for authentication.

### 3. Customize Video Parameters (Optional)

- In the **Parse Request** (Code) node, you can modify the JavaScript code to change video generation settings like `aspectRatio`, `durationSeconds`, and `resolution`.

### 4. Execute the Workflow

- Activate the workflow. Open the Form URL from the **Prompt your Idea** node to start the process.

## Sample Videos

Add sample video files or links here after you upload them to the repo.

## FAQ

**Is this template free to use?**
Yes. It's an open-source n8n workflow published by Intuz — copy the workflow JSON from this repo and import it into your own n8n instance at no cost.

**Do I need a paid n8n plan to run this?**
No. It runs on n8n's free self-hosted Community Edition or on n8n Cloud. You'll need your own Google Cloud (Gemini + Veo 3) and Airtable credentials, not a specific n8n pricing tier.

**Does it publish the ad automatically?**
No. It generates the video with Veo 3 and makes the file available from the n8n execution log (and tracks the project in Airtable). Publishing to social channels is a separate step.

## Related n8n templates from Intuz

- [Automate AI video creation & multi-platform publishing with Gemini & Creatomate](https://github.com/Intuz-production/AI-video-generator-for-social-media)
- [Automate LinkedIn post creation with image using Google Gemini & DALL-E](https://github.com/Intuz-production/AI-Powered-LinkedIn-Post-Image-Generator)
- [Automate Twitter posting with GPT-4 content generation & Google Sheets tracking](https://github.com/Intuz-production/Twitter-Post-Automation)

[See all of Intuz's free n8n templates](https://www.intuz.com/n8n-workflow-automation-templates/)

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate.

* **Website:** [https://www.intuz.com](https://www.intuz.com)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
