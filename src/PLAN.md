# GraphRAG C# Migration Plan (.NET 10)

This document serves as the roadmap for porting the Python-based GraphRAG system to C# targeting .NET 10.

## Overview
The goal is to achieve full feature parity with the Python implementation while adopting idiomatic .NET patterns.

## Architecture
- Framework: .NET 10
- LLM Engine: Microsoft Semantic Kernel
- Vector Storage: Qdrant (replacing CosmosDB)
- Primary Storage: Local File System (Parquet/JSON/Text)
- Dependency Injection: Microsoft.Extensions.DependencyInjection
- Pipeline: Hosted Services for batch processing

## Phases

### Phase 1: Core Foundation & Domain Models
- Project structure (GraphRag.Core, GraphRag.Cli)
- POCO Models for Knowledge Model (Document, TextUnit, Entity, etc.)
- Configuration system (settings.yaml/json)
- Core abstractions (IStorage, ILanguageModel, IVectorStore)

### Phase 2: Infrastructure & Storage
- File system storage implementation
- Semantic Kernel integration
- Qdrant connector implementation

### Phase 3: Indexing Pipeline
- Document chunking
- LLM Graph extraction
- Community detection
- Summarization and embeddings

### Phase 4: Query & Search
- Local search
- Global search
- Drift search

### Phase 5: CLI Tooling
- graphrag CLI parity
- System.CommandLine implementation

## Parity & Validation
- Output comparison between C# and Python for identical inputs
- Porting of existing unit tests from Python to xUnit/NUnit
