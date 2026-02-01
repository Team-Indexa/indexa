![Indexa](../Assets/indexa.png)

# Features

## Core Search Engine

### Hybrid Multi-Signal Ranking

Indexa combines multiple retrieval and ranking approaches to deliver high-quality search results:

**Parallel Retrieval System**
- Simultaneous execution of full-text search and semantic vector search
- Full-text search contributes 60% to final ranking using BM25 algorithm
- Semantic search contributes 20% using vector embeddings for conceptual matching
- PageRank authority signals contribute 10% based on link analysis
- Domain authority contributes 10% based on site credibility scoring

**Query Intelligence**
- Automatic query expansion for concise searches (three words or fewer)
- Expands queries with relevant synonyms and acronyms to improve result coverage
- Spell correction system suggests alternatives for misspelled queries
- Levenshtein distance algorithm powers "Did you mean?" functionality

**Search Assistance**
- Real-time autocomplete with query suggestions
- Keyboard navigation support for accessibility
- 300ms debounce optimization for smooth user experience

### Advanced Web Crawling

**Intelligent Content Discovery**
- Automatic sitemap.xml detection and processing
- Priority-based crawling respects site-defined importance
- Comprehensive robots.txt compliance with crawl delay respect
- Blocked path detection and adherence to site preferences

**Modern Web Support**
- Two-phase rendering strategy for optimal performance
- Static HTML processing for traditional websites
- JavaScript rendering for single-page applications (React, Vue, Angular)
- Browser automation for dynamic content capture

**Content Quality**
- Near-duplicate detection using SimHash fingerprinting
- 64-bit fingerprints for efficient similarity comparison
- Structured data extraction from schema.org markup
- Support for Recipe, Product, Event, and Article types

## Dufus AI Assistant

### Data-Unified Functional Understanding System

An integrated conversational AI system designed to enhance search with natural language interaction:

**Intelligent Query Processing**
- Multi-mode chat interface for versatile interactions
- Intent classification distinguishes factual, conversational, and computational queries
- Context aggregation ranks and synthesizes relevant search results
- Multi-query detection splits complex questions into manageable sub-queries

**Response Generation**
- Real-time token streaming for natural conversation flow
- Source citations with clickable links to original content
- Markdown rendering with code block syntax highlighting
- Conversation history with ability to start fresh chats

**Specialized Modes**
- Chat mode for general questions and discussions
- Image mode for visual search queries
- Code mode (activated with /code) for programming assistance
- Quick reply system for greetings and common interactions

**Knowledge Integration**
- Wikipedia fallback for comprehensive knowledge coverage
- Multiple data source aggregation for thorough answers
- Featured answer extraction for direct responses

### Available Interaction Modes
- Chat: General conversational search assistance
- Image: Visual content discovery and questions
- Video: Coming soon

## Spaces

**Interactive Immersive Search Engine** (Coming Soon)

Next-generation spatial search experience currently in development:
- Immersive three-dimensional navigation of search results
- Interactive knowledge exploration with visual relationships
- Topic relationship mapping for connected learning
- Spatial organization of information for intuitive browsing

Currently displayed with "Coming Soon" status in the interface.

## Shopping Search

### E-commerce Product Discovery

Dedicated shopping search functionality with specialized product indexing:

**Product Database**
- Full-text indexed product catalog
- Multi-site aggregation from major Indian e-commerce platforms
- Supported retailers: Croma, Vijay Sales, Myntra
- Structured product data with complete metadata

**Advanced Filtering**
- Price range selection and sorting
- Rating and review filtering
- Brand-specific searches
- Category browsing
- Stock availability status

**Sorting Options**
- Relevance-based ranking (default)
- Price ascending and descending
- Customer rating sorting
- Featured product highlighting

**Product Display**
- Rich product cards with images and details
- Price, rating, and availability at a glance
- Direct links to purchase pages
- Featured products for best matches

**Search Features**
- Product-specific autocomplete suggestions
- Trending product discovery
- Featured product recommendations
- Fast, dedicated product search API

## Image Search

Visual content discovery across indexed web pages:

**Search Capabilities**
- Full-text search across indexed images
- Alt text and caption matching
- Surrounding page content analysis for context
- BM25 relevance ranking for results

**Result Information**
- Image URL and dimensions
- Source page reference
- Image metadata and context
- Direct links to original content

## Rich Results & Knowledge Features

### Structured Data Display

Enhanced result cards for specific content types:

**Recipe Cards**
- Star ratings and review counts
- Cooking time and difficulty
- Calorie information
- Ingredient lists and instructions

**Event Cards**
- Event dates and times
- Venue locations and maps
- Ticket purchase links
- Event descriptions

**Product Cards**
- Current pricing information
- Product availability status
- Customer reviews and ratings
- Product specifications

**Article Cards**
- Author information
- Publication dates
- Estimated reading time
- Article summaries

**FAQ Cards**
- Collapsible question-answer format
- Quick access to common information
- Structured for easy scanning

### Knowledge Panels

Comprehensive entity information display:
- Wikipedia integration for authoritative information
- Brand homepage prioritization for official sources
- Domain authority scoring (0-100 scale)
- Featured answer extraction for direct information access

## Performance & Scalability

### Multi-Tier Caching System

Redis-powered caching for optimal performance:

**Cache Layers**
- Search results cached for 1 hour
- Embeddings cached for 24 hours
- Autocomplete cached for 10 minutes
- Intelligent cache warming for popular queries

**Performance Improvements**
- 15x speedup for cached queries
- Response times: 10-20ms cached vs 150-300ms uncached
- 80-85% cache hit rate after system warm-up
- Scripts available for cache management and warming

### Distributed Crawling

Horizontal scaling for large-scale web indexing:

**Job Queue System**
- Redis-based FIFO queue architecture
- LPUSH/BRPOP for atomic job distribution
- Distributed locking prevents duplicate crawls
- Atomic statistics tracking across workers

**Scaling Capabilities**
- Horizontal worker scaling
- 10 workers capable of 1000+ pages per second
- Independent worker coordination
- Fault-tolerant job distribution

### Index Sharding

Database partitioning for performance at scale:

**Sharding Strategy**
- Consistent hashing by domain
- Independent SQLite databases per shard
- Parallel search execution across shards
- Configurable shard count (4-16 default range)

**Benefits**
- Reduced lock contention
- Improved query parallelization
- Better hardware utilization
- Simplified horizontal scaling

### HNSW Vector Index

Optimized approximate nearest neighbor search:

**Technical Implementation**
- Hierarchical Navigable Small World graph structure
- O(log N) search complexity
- Int8 quantization for 75% memory reduction
- Custom implementation for semantic search needs

**Performance Characteristics**
- Graph persisted separately from main database
- Optimized for high-dimensional vector spaces
- Fast approximate similarity search
- Memory-efficient representation

## OwlGuard Authentication

Secure user authentication and profile management:

**Security Features**
- User registration and login system
- bcrypt password hashing for secure storage
- Session management with secure cookies
- Separate authentication database (owlguard.db)

**User Features**
- Profile dashboard with customization
- Upload support for profile pictures
- Session persistence across visits
- Secure logout functionality

**API Endpoints**
- Registration: /api/auth/signup
- Login: /api/auth/login
- Logout: /api/auth/logout

## PageRank & Domain Authority

### Link Analysis

Advanced authority scoring for result ranking:

**PageRank Algorithm**
- Iterative link analysis computation
- Incremental updates for efficiency
- Authority score from web graph structure
- 0-10 scale for ranking contribution

**Domain Authority**
- Per-domain credibility scoring system
- 0-100 scale similar to industry standards
- Multiple signal aggregation
- Historical performance tracking

**Brand Detection**
- Automatic identification of brand queries
- Official homepage prioritization
- Authority boost for verified sources
- Improved navigational query handling

## User Experience

### Search Quality Improvements

**Zero-Result Prevention**
- Query expansion reduces failed searches by 15-20%
- Automatic spell correction suggestions
- Synonym and acronym expansion
- Graceful handling of edge cases

**Result Diversity**
- Maximum 2 results per domain in standard results
- Domain clustering for variety
- Authority-based domain representation
- Prevention of single-source dominance

**Intent Optimization**
- Query intent classification
- Optimized responses per query type
- Appropriate result format selection
- Context-aware ranking adjustments

### Interface Design

**Modern, Clean Interface**
- Mobile-responsive design
- Lucide icon system for clarity
- Intuitive navigation patterns
- Fast, smooth interactions

**Privacy-First Approach**
- All processing performed locally
- No external API tracking
- No personally identifiable information sharing
- User data remains within system boundaries

## Developer Features

### Technology Stack

**Core Technologies**
- Full TypeScript implementation for type safety
- SQLite with FTS5 for embedded full-text search
- ONNX runtime for local embedding generation
- Fastify server for high-performance HTTP
- Manual cookie parsing for control and security

**AI and Machine Learning**
- Local Xenova/bge-base-en-v1.5 embedding model
- No external API costs or dependencies
- On-device inference for privacy
- Efficient model serving

### Architecture

**Modular Design**
- Clean separation of concerns
- Independent crawler module
- Dedicated indexer component
- Isolated search logic
- Clear module boundaries

**Extensibility**
- Browser extension for new tab integration
- Well-documented APIs
- Script-based management tools
- Configuration flexibility

### Management Scripts

Available npm scripts for system administration:
- Cache warming and clearing
- Crawl coordination and worker management
- Index shard migration
- PageRank computation
- Domain authority calculation

---

*Feature set subject to ongoing development and improvement.*
