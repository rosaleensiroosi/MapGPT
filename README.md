# MapGPT

### Language to Maps


V1 (In Progress)

![Design](https://github.com/QueueLab/MapGPT/assets/115367894/40ea0a4f-354b-4486-b873-114bbab411d8)



## Contributing

Welcome! Please see the issues for items that need attention, and below for some tools to aid in development and debugging. We're working to interpolate chat functionality onto the map module.


### Map module 

Visit our roadmap for more information.

(https://draw.roadmap.sh/664d9e21d6b907c7f745be36)

### Running the app on your own machine

1. Install the Python dependencies, and run the tile server proxy.
    ```
    $ cd server
    $ python -m venv env
    $ . env/bin/activate
    $ pip install -r requirements.txt
    $ python tile_server_proxy.py
    ```
2. Run a web server, such as live-server, in the working directory. Make sure you specify a port that doesn't conflict with the tile server proxy.
    ```
    $ npm install live-server
    $ live-server --port=8081 .
    ```

## Third-party libraries used
1. [Turf.js](https://turfjs.org/) (for GeoJSON processingand geospatial calculations)
2. [Leaflet](https://leafletjs.com/) (provides OpenStreetMap widget)≥
3. [unmute](https://github.com/swevans/unmute) (improved web audio behavior on iOS)

### Chat module:

Move the chat folder out of MapGPT as it has not been interpolated yet. This module is standalone at the moment. 

An AI-powered search engine with a generative UI.


## 🧱 Stack

- App framework: [Next.js](https://nextjs.org/)
- Text streaming / Generative UI: [Vercel AI SDK](https://sdk.vercel.ai/docs)
- Generative Model: [OpenAI](https://openai.com/)
- Search API: [Tavily AI](https://tavily.com/) / [Exa AI](https://exa.ai/)
- Serverless Database: [Upstash](https://upstash.com/)
- Component library: [shadcn/ui](https://ui.shadcn.com/)
- Headless component primitives: [Radix UI](https://www.radix-ui.com/)
- Styling: [Tailwind CSS](https://tailwindcss.com/)


### 2. Install dependencies

```
cd chat
bun install
```

### 3. Setting up Upstash Redis

Follow the guide below to set up Upstash Redis. Create a database and obtain `UPSTASH_REDIS_REST_URL` and `UPSTASH_REDIS_REST_TOKEN`. Refer to the [Upstash guide](https://upstash.com/blog/rag-chatbot-upstash#setting-up-upstash-redis) for instructions on how to proceed.

### 4. Fill out secrets

```
cp .env.local.example .env.local
```

Your .env.local file should look like this:

```
# OpenAI API key retrieved here: https://platform.openai.com/api-keys
OPENAI_API_KEY=

# Tavily API Key retrieved here: https://app.tavily.com/home
TAVILY_API_KEY=

# Upstash Redis URL and Token retrieved here: https://console.upstash.com/redis
UPSTASH_REDIS_REST_URL=
UPSTASH_REDIS_REST_TOKEN=
```

_Note: This project focuses on Generative UI and requires complex output from LLMs. Currently, it's assumed that the official OpenAI models will be used. Although it's possible to set up other models, if you use an OpenAI-compatible model, but we don't guarantee that it'll work._

### 5. Run app locally

```
bun dev
```

You can now visit http://localhost:3000.

## ✅ Verified models

List of verified models that can be specified to writers.

- [Groq](https://console.groq.com/docs/models)
  - LLaMA3 8b
  - LLaMA3 70b

≥
