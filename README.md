# crewai-multi-agent-job-application-system

# AI Job Application Crew (CrewAI)

## Overview

This project is a multi-agent AI workflow built using CrewAI to help automate the job application preparation process.

The system uses multiple specialized AI agents that collaborate to:

1. Analyze a job posting.
2. Research and profile a candidate.
3. Tailor a resume to match job requirements.
4. Generate interview preparation materials.

The project was originally built using older versions of CrewAI and related libraries. 
# It is preserved here primarily for reference, learning, and historical purposes.


## Workflow

### 1. Job Research Agent

**Purpose:**

* Reads and analyzes a job posting.
* Extracts key requirements, skills, qualifications, and expectations.

**Tools Used:**

* Website scraping
* Web search

**Output:**

* Structured list of job requirements.

---

### 2. Personal Profiler Agent

**Purpose:**

* Analyzes the candidate's information.
* Uses resume data, GitHub profile, and personal write-up.

**Tools Used:**

* Resume reader
* Semantic search over resume
* Web search
* Website scraping

**Output:**

* Comprehensive candidate profile.

---

### 3. Resume Strategist Agent

**Purpose:**

* Aligns the resume with the target job.
* Highlights relevant skills and experiences.
* Improves positioning without inventing information.

**Input:**

* Candidate profile
* Job requirements

**Output:**

* Tailored resume (`tailored_resume.md`)

---

### 4. Interview Preparation Agent

**Purpose:**

* Creates interview preparation materials.
* Generates likely interview questions.
* Produces talking points based on the tailored resume.

**Input:**

* Job requirements
* Tailored resume

**Output:**

* Interview preparation document (`interview_materials.md`)

---

## Architecture

```text
Job Posting
      |
      v
+------------------+
| Research Agent   |
+------------------+
      |
      v
Job Requirements
      |
      v
+------------------+
| Profiler Agent   |
+------------------+
      |
      v
Candidate Profile
      |
      v
+------------------+
| Resume Strategist|
+------------------+
      |
      v
Tailored Resume
      |
      v
+------------------+
| Interview Agent  |
+------------------+
      |
      v
Interview Materials
```

---

## Main Libraries Used

The notebook was built using older versions of:

* CrewAI
* crewai-tools
* OpenAI API
* Serper Search API
* FileReadTool
* MDXSearchTool
* ScrapeWebsiteTool

---

## Required Inputs

The workflow expects:

### Job Posting URL

A public URL containing the job description.

Example:

```python
job_posting_url = "https://example.com/job-posting"
```

### GitHub Profile

Candidate's GitHub profile URL.

Example:

```python
github_url = "https://github.com/username"
```

### Personal Write-up

Short professional biography or summary.

Example:

```python
personal_writeup = """
Experienced software engineer with expertise in AI and cloud systems...
"""
```

### Resume File

The project expects a markdown resume file:

```text
fake_resume.md
```

---

## Expected Outputs

After successful execution:

```text
tailored_resume.md
interview_materials.md
```

These files contain:

* Customized resume
* Interview questions
* Suggested talking points

---

## Why This Repository Exists

This repository serves as:

* A learning example for multi-agent workflows.
* A historical CrewAI implementation.
* A reference architecture for AI-powered job application assistants.

It may not run successfully on current library versions without modification.

---

## Running the Project Today

This notebook was created using older CrewAI APIs.

Several components have changed significantly since then:

* CrewAI architecture
* Agent definitions
* Task definitions
* Tool APIs
* Embedding and retrieval systems
* OpenAI integrations

As a result, the code may fail if installed with the latest package versions.

---

## What Would Be Needed To Modernize It

To run this project today, you would likely need to:

### Update CrewAI

Rewrite:

* Agent definitions
* Task definitions
* Crew initialization

to match the latest CrewAI APIs.

### Replace Deprecated Tools

Some tools used in the notebook may no longer exist or may have changed:

* MDXSearchTool
* FileReadTool
* ScrapeWebsiteTool

Alternative implementations may be required.

### Update OpenAI Integration

Modern versions often require:

```python
OPENAI_API_KEY
```

and updated model configurations.

### Configure Search Provider

The project uses Serper.

You will need:

```text
SERPER_API_KEY
```

and potentially updated tool initialization code.

### Rebuild Resume Retrieval

Semantic search over resumes may require:

* Vector databases
* Modern embedding models
* Updated retrieval pipelines

---

## Environment Variables

Typical variables required:

```env
OPENAI_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

---

## Disclaimer

This repository is preserved in its original educational form.

The code may require substantial updates before it can be executed successfully with the latest CrewAI ecosystem. Use it primarily as a reference implementation for understanding multi-agent orchestration and AI-assisted job application workflows.
