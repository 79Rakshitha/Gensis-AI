Genesis AI - The World's First Graph-Based AI Pre-Production Studio
Genesis AI is a revolutionary, AI-powered pre-production platform that transforms the creative workflow for filmmakers, documentary creators, and content producers. Built with cutting-edge technology, Genesis enables you to go from initial concept to a complete, investor-ready pitch deck in hours, not weeks—representing a 10x improvement over traditional pre-production methods.

This comprehensive web-based application integrates research, scriptwriting, storyboarding, audio generation, and presentation creation into a single, intelligent ecosystem powered by state-of-the-art AI models.

Revolutionary Features
World-First Graph-Based Interface
Interactive Project Visualization: Navigate your entire project as an interconnected network of scenes, scripts, characters, and assets
Visual Workflow Management: Drag-and-drop nodes to restructure your narrative in real-time

Context-Aware AI: AI suggestions powered by your project's structure and relationships
Scene Dependencies: Visualize how scenes, characters, and plot points connect across your story

AI Script Co-Pilot (Groq LLaMA 3.3 70B)
Real-time dialogue enhancement and structure optimization

Context-aware suggestions based on your entire screenplay

Character consistency checking across all scenes

Screenplay formatting with industry-standard templates

Auto-save with version history

Speed: 800+ tokens/second for instant feedback

Cinematic Storyboard Generation (Flux.1)
Generate production-quality storyboard images from scene descriptions

Consistent character appearances across all frames

Cinematic composition and professional lighting

Batch generation for entire scripts

Export in multiple formats

Multi-Voice Audio Drama Creation (ElevenLabs)
Automatic character voice assignment

Multi-voice dialogue synthesis with distinct voices for each character

Professional narrator voice for scene descriptions

Export complete audio dramas in MP3 format

Voices: Adam (Narrator), Josh (Male Lead), Rachel (Female Lead)

Automated Presentation Builder
One-click PowerPoint generation from your entire project

Includes: Script excerpts, storyboard images, audio samples, and project overview

Professional templates optimized for investor pitches

Edit slides with built-in AI enhancement

Export as .pptx with all media embedded

Centralized Research Hub
Organize notes, transcripts, and reference materials

Tag and categorize content for easy retrieval

Link research directly to script scenes

Rich text editor with markdown support

Cloud sync across all devices

Intelligent Transcription System
Upload audio/video interviews for automatic transcription

AI-powered speaker detection

Timestamped transcript generation

Convert transcripts directly to screenplay format

Export to multiple formats

Real-Time Collaboration
Multi-user project access

Live editing with presence indicators

Comment and annotation system

Activity feed and notifications

Team permissions management

Tech Stack
Frontend
Framework: Next.js 14 (App Router)

Language: TypeScript

Styling: Tailwind CSS

UI Components: shadcn/ui

Animations: Framer Motion

Graph Visualization: ReactFlow

Icons: Lucide React

Backend & Database
Database: Supabase (PostgreSQL)

Storage: Supabase Storage

Authentication: Clerk

API Routes: Next.js Serverless Functions

AI Services
Script Enhancement: Groq (LLaMA 3.3 70B) - Ultra-fast inference

Image Generation: Replicate Flux.1 - Cinema-grade visuals

Voice Synthesis: ElevenLabs - Multi-voice audio

Transcription: OpenAI Whisper (via API)

Development Tools
Package Manager: npm/yarn

Deployment: Vercel

Version Control: Git/GitHub

Getting Started
Prerequisites
Node.js v18 or later

npm or yarn

Supabase account (for database and storage)

Clerk account (for authentication)

API Keys for AI services (Groq, Replicate, ElevenLabs)

Installation
Clone the repository:

bash
git clone https://github.com/Eleyaraja/TECHNOVA.git
cd TECHNOVA
Install dependencies:

bash
npm install
# or
yarn install
Set up environment variables:
Create a .env.local file in the root directory with the following keys:

text
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key

# AI Services
GROQ_API_KEY=your_groq_api_key
REPLICATE_API_TOKEN=your_replicate_token
ELEVENLABS_API_KEY=your_elevenlabs_key
OPENAI_API_KEY=your_openai_key
Set up Supabase tables:
Run the following SQL in your Supabase SQL Editor:

sql
-- Projects table
create table projects (
  id uuid primary key default uuid_generate_v4(),
  user_id text not null,
  title text not null,
  description text,
  script_content text,
  created_at timestamp with time zone default now()
);

-- Scenes table
create table scenes (
  id uuid primary key default uuid_generate_v4(),
  project_id uuid references projects(id) on delete cascade,
  title text not null,
  description text,
  image_url text,
  audio_url text,
  order_index integer,
  created_at timestamp with time zone default now()
);

-- Research notes table
create table research_notes (
  id uuid primary key default uuid_generate_v4(),
  project_id uuid references projects(id) on delete cascade,
  title text not null,
  content text,
  tags text[],
  created_at timestamp with time zone default now()
);
Run the development server:

bash
npm run dev
# or
yarn dev
Open http://localhost:3000 in your browser.

How to Use
Sign Up/Sign In: Create an account using email or social login (Google/GitHub)

Create a Project: Start a new film project from the dashboard

Write Your Script: Use the AI-powered script editor with real-time suggestions

Generate Storyboards: Click "Generate Storyboards" to create visuals for your scenes

Create Audio: Generate multi-voice audio dramas from your script

Build Presentation: Auto-generate a professional PowerPoint with one click

Collaborate: Share your project with team members for real-time collaboration

Export: Download your complete pre-production package

Use Cases
Independent Filmmakers: Complete pre-production for short films and features

Documentary Creators: Organize research, transcripts, and storyboards

YouTube Creators: Plan and visualize content before production

Film Students: Learn industry-standard pre-production workflows

Production Companies: Streamline client presentations and pitches

Innovation Highlights
Graph-Based Workflow: First platform to visualize pre-production as an interactive graph

Multi-Modal AI: Combines text, image, and voice generation in one unified workflow

Speed: 10x faster than traditional pre-production methods

All-in-One: Eliminates the need for 5-7 separate tools

Production-Ready Output: Professional-quality assets suitable for investor presentations

Team
Built by:

Eleyaraja R - Full Stack Developer & AI Integration Specialist

Vinutha J - UI/UX Designer & Frontend Developer

Nayanashree P - Backend Developer & Database Architect

Contributing
We welcome contributions! Please follow these steps:

Fork the repository

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

License
This project is licensed under the MIT License - see the LICENSE.md file for details.