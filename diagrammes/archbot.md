@startuml
title 🤖 Bot Architecte – Diagramme de séquence RAG

actor Utilisateur
participant "Gradio / FastAPI\n(UI)" as UI
participant "RAG Bot\n(Python App)" as Bot
participant "ChromaDB\n(Vector Store)" as DB
participant "sentence-transformers\n(Embedding)" as Emb
participant "LLM via Ollama\n(Mistral / DeepSeek)" as LLM

Utilisateur -> UI : Pose une question
UI -> Bot : Envoie la question

Bot -> DB : Recherche sémantique (embedding + similarité)

DB --> Bot : Top-K chunks similaires

Bot -> LLM : Prompt = [Context + Question]
LLM --> Bot : Réponse générée

Bot -> UI : Affiche la réponse
UI --> Utilisateur : Réponse affichée

@enduml