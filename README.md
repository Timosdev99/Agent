# AGENT

this is an AI agent used for HR management it uses LangGraph and MongoDB for generating and managing AI agents and conversational application using agentic Approach 

## Features

- Utilizes LangGraph for managing agentic conversational flows in TypeScript
- Integrates with MongoDB Atlas for storing and retrieving conversation data
- Implements a RESTful API using Express.js for chat interactions
- Uses OpenAI's GPT model and Anthropic's API for generating responses
- Includes a tool for employee lookup using MongoDB Atlas vector search

## Prerequisites

- [Node.js and npm](https://nodejs.org/)
- [MongoDB Atlas account](https://www.mongodb.com/cloud/atlas)
- [OpenAI API key](https://platform.openai.com/account/api-keys)
- [Anthropic API key](https://www.anthropic.com/claude)

## Installation

1. Clone this repository:

```bash
git clone https://github.com/Timosdev99/Agent.git 
cd Agent
```

2. Install the required dependencies:

```bash
npm install
```

3. Set up your environment variables:
- Create a `.env` file in the root directory
- Add your API keys and MongoDB URI:
  
  ```
  OpenAI_API_KEY=your_openai_api_key_here
  ANTHROPIC_API_KEY=your_anthropic_api_key_here
  MONGO_DB_URL=your_mongodb_atlas_uri_here
  ```

## Seed the Database

1. Run the seed script to generate and seed the database:

```bash
npm run seed
```

## Usage

1. Start the server:

```bash
npm run dev
```

2. Use the following API endpoints:

- Start a new conversation:
  ```
  curl -X POST -H "Content-Type: application/json" -d '{"message": "Your message here"}' http://localhost:3003/chat
  ```
- Continue an existing conversation:
  ```
  curl -X POST -H "Content-Type: application/json" -d '{"message": "Your follow-up message"}' http://localhost:3003/chat/{threadId}
  ```

## Project Structure

- `index.ts`: Entry point of the application, sets up the Express server and API routes
- `agent.ts`: Defines the LangGraph agent, tools, and conversation flow
- `seed-db.ts`: Script for generating and seeding synthetic employee data into MongoDB

## How it works

1. The seed script in `seed-db.ts` generates synthetic employee data and populates the MongoDB database.
2. The LangGraph agent is defined in `agent.ts`, including the conversation graph structure and tools.
3. MongoDB operations are integrated directly into the agent for storing and retrieving conversation data.
4. The Express server in `index.ts` provides API endpoints for starting and continuing conversations.
5. User inputs are processed through the LangGraph agent, generating appropriate responses and updating the conversation state.
6. Conversation data is persisted in MongoDB Atlas, allowing for continuity across sessions.


