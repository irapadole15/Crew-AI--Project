#  CrewAI Blog Post Generator from YouTube Transcript

This project automates the creation of blog posts from YouTube videos using a multi-agent system built with **CrewAI**. It’s designed for content creators, educators, and businesses who want to transform video content into well-structured written articles — with minimal manual effort.

---

##  Why CrewAI?

Unlike other frameworks like LangChain, CrewAI enables seamless **agent-to-agent collaboration**. Each agent is assigned a specific role and can communicate and delegate tasks, allowing complex workflows to be handled in a modular, scalable way.

---

##  Use Case

You're managing a YouTube channel with hundreds (or thousands) of videos — say tutorials on AI, ML, or data science. You want to convert these into blog posts. Doing this manually is tedious and time-consuming.

### Automated Workflow:

1. A topic is entered.
2. A **Researcher Agent** finds the most relevant YouTube video.
3. A transcript is extracted from the video.
4. A **Writer Agent** takes the content and produces a structured, readable blog post.

---

##  System Architecture

###  Agents

- **Blog Researcher Agent**
  - Role: Find relevant video for the given topic
  - Tool: YouTubeChannelSearchTool
  - Output: Extracted transcript and key summaries

- **Blog Writer Agent**
  - Role: Write an engaging blog post using the researcher's output
  - Behavior: Converts summaries into structured articles

### 🛠 Tasks

- **Research Task**: 
  - Extract transcript and generate a three-paragraph summary
  - Use `yt_tool` to search the channel
- **Writing Task**: 
  - Convert summary into a polished blog post
  - Output saved to `new-blog-post.md`
  - Runs only after researcher task completes

###  Tools

- `YoutubeChannelSearchTool` from `crewai_tools`
- Target channel: `@SimplilearnOfficial`

---

##  Project Structure

```

crewai-blog-writer/
│
├── agents.py        # Defines Blog Researcher and Blog Writer agents
├── tools.py         # Sets up YouTube transcript tool (yt\_tool)
├── tasks.py         # Assigns and structures tasks for each agent
├── crew\.py          # Main orchestration file (execution script)
├── .env             # API keys (OpenAI, etc.)
├── requirements.txt
└── README.md

````

---

##  Setup Instructions

### 1. Clone the repo

```bash
git clone https://github.com/your-username/crewai-blog-writer.git
cd crewai-blog-writer
````

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up environment variables

Create a `.env` file:

```env
OPENAI_API_KEY=your_openai_key
```

---

## ▶ Running the Project

```bash
python crew.py --topic "Neural Networks vs Decision Trees"
```

This will:

* Search Simplilearn’s YouTube channel
* Fetch transcript
* Generate a blog post
* Save it as `new-blog-post.md`

---

##  Example Output

**Topic**: Reinforcement Learning
**Generated Blog Title**: "Mastering Reinforcement Learning: A Beginner’s Guide"
**Excerpt**:

> Reinforcement Learning (RL) is a fascinating branch of machine learning that’s inspired by behavioral psychology. This blog explores key concepts from a Simplilearn tutorial including Q-learning, agents, and rewards...

---

##  Future Scope

* Add SEO Optimization Agent
* Integrate grammar & plagiarism checker
* Support multi-language transcription
* Replace OpenAI with open-source LLMs (e.g., Mistral, LLaMA via Ollama or Hugging Face)

---

##  Credits

* Built with [CrewAI](https://github.com/joaomdmoura/crewAI)
* YouTube search via [YoutubeChannelSearchTool](https://pypi.org/project/crewai-tools/)
* Transcripts powered by YouTube
* Inspired by real use case with the Simplilearn channel

---

---

##  Contact

 [irapadole2004@gmail.com](mailto:irapadole2004@gmail.com)
 [LinkedIn](https://www.linkedin.com/in/ira-padole-3487062b4) • [Portfolio](https://irapadole.com)

```
