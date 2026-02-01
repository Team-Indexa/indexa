![Indexa](../Assets/indexa.png)

# Technical Overview

## Architecture Philosophy

Indexa is built on a foundation of performance, privacy, and simplicity. The technical stack prioritizes embedded solutions, local processing, and minimal external dependencies to deliver a fast, secure search experience.

## Backend Infrastructure

### Runtime Environment

**Node.js Platform** (18.0.0 or higher)
- Asynchronous I/O for high concurrency
- Event-driven architecture for scalable operations
- Cross-platform compatibility

**Fastify Framework** (4.26)
- High-performance HTTP server
- Low overhead request handling
- Plugin-based architecture for modularity
- Manual cookie parsing for precise control

**TypeScript Implementation** (5.3.3)
- Full type safety across codebase
- ES2022 target for modern JavaScript features
- CommonJS module system
- Strict mode compilation for error prevention
- Source maps for debugging support

### Data Storage

**SQLite Primary Database**

Embedded relational database with zero configuration:
- Synchronous bindings for predictable performance
- Asynchronous operations for non-blocking tasks
- Write-Ahead Logging (WAL) mode for improved concurrency
- FTS5 extension with BM25 ranking algorithm
- Built-in full-text search capabilities
- No separate database server required

**Redis In-Memory Store**

Advanced caching and distributed system coordination:
- Multi-tier caching architecture
- Distributed job queue management
- FIFO list operations for crawl coordination
- Set and hash data structures for efficient lookups
- High-performance read operations

## Artificial Intelligence & Machine Learning

### Local Embedding Generation

**Transformer Models**

On-device neural network inference:
- ONNX runtime for cross-platform compatibility
- BGE-base-en-v1.5 model for English text embeddings
- Int8 quantization for 75% memory reduction
- No external API dependencies
- Fully offline operation for privacy
- Zero per-query costs

**Vector Search Implementation**

Custom approximate nearest neighbor search:
- Hierarchical Navigable Small World (HNSW) graph structure
- Optimized for high-dimensional vector spaces
- O(log N) search complexity
- Custom implementation for full control
- Graph persistence separate from main database

### Language Model Integration

**Dufus AI Assistant**

Local large language model support:
- Native LLaMA model integration
- Streaming response generation
- Server-Sent Events (SSE) for real-time output
- Context aggregation from search results
- Intent classification for query understanding
- Multi-query decomposition for complex questions

## Web Crawling & Content Processing

### HTTP Operations

**Request Handling**

Robust HTTP client with retry logic:
- Automatic retry on transient failures
- Custom timeouts and connection pooling
- HTTP/2 support for performance
- Compression handling (gzip, brotli)

**Content Parsing**

Multi-stage content extraction:
- jQuery-like HTML parsing for structure extraction
- DOM implementation for JavaScript execution
- Mozilla Readability algorithm for article extraction
- Robots.txt compliance checking and enforcement

### JavaScript Rendering

**Browser Automation**

Headless browser for modern web applications:
- Chromium-based rendering engine
- Custom browser pool with resource controls
- Two-tier render cache (memory and persistent storage)
- Anti-detection measures for reliability
- Selective rendering based on content analysis

**Rendering Strategy**

Two-phase intelligent rendering:
1. Static HTML processing for traditional websites
2. Browser rendering for single-page applications
3. Detection logic determines appropriate method
4. Performance optimization through caching

### Content Quality

**Duplicate Detection**

SimHash fingerprinting for near-duplicate identification:
- 64-bit fingerprints for similarity comparison
- Custom implementation for web-scale deduplication
- Efficient comparison operations
- Configurable similarity thresholds

**Structured Data**

Schema.org extraction for rich results:
- Recipe, Product, Event, and Article types
- JSON-LD and Microdata format support
- Automatic structured data discovery
- Enhanced result presentation

## Authentication & Security

### OwlGuard System

Secure user authentication infrastructure:

**Password Security**
- Industry-standard password hashing algorithm
- Salt generation for each password
- Configurable work factor for computational cost
- Secure password comparison

**Session Management**
- Token-based authentication
- Secure cookie handling
- Manual parsing for control and security
- Separate authentication database
- Session expiration and renewal

**Security Practices**
- No plaintext password storage
- Secure token generation
- HTTPS-ready configuration
- Protection against common vulnerabilities

## Frontend Architecture

### Design Philosophy

Minimal framework overhead for maximum performance:

**Native JavaScript**
- Modern ES6+ language features
- Fetch API for HTTP requests
- Promise-based asynchronous operations
- Native async/await patterns
- No framework bundle overhead

**UI Components**
- Modern icon library via CDN
- Syntax highlighting for code blocks
- Custom font loading optimization
- Responsive design patterns
- Progressive enhancement approach

### Build Pipeline

**Production Optimization**

Multi-stage minification and optimization:
- JavaScript minification for reduced payload
- CSS minification and compression
- HTML minification with configuration
- Code transformation for production
- Asset optimization

## Data Processing

### Compression & Streaming

**Large File Processing**

Efficient handling of large datasets:
- BZ2 decompression for Wikipedia dumps
- Streaming XML parsing for memory efficiency
- Gzip support for sitemap processing
- Progressive parsing to avoid memory spikes

**Concurrency Control**

Managed parallel operations:
- Configurable concurrency limits
- Rate limiting for external requests
- Resource pooling for efficiency
- Backpressure handling

### Algorithmic Components

**Link Analysis**
- PageRank algorithm for authority scoring
- Iterative computation with convergence detection
- Incremental updates for efficiency

**Domain Scoring**
- Domain authority calculation algorithm
- Multi-signal aggregation
- Historical performance tracking
- 0-100 scale normalization

## Development Infrastructure

### TypeScript Configuration

**Compiler Settings**
- ES2022 compilation target for modern features
- CommonJS module output for Node.js compatibility
- Strict type checking enabled
- Source map generation for debugging
- Incremental compilation support

### Development Workflow

**Hot Reload System**
- Automatic restart on file changes
- Direct TypeScript execution
- Transpile-only mode for speed
- Fast iteration cycles
- Error reporting and logging

## Deployment & Operations

### Process Management

**Production Runtime**

Process management configuration:
- Automatic restart on crashes
- Process clustering for multi-core utilization
- Log aggregation and management
- Environment variable configuration
- Zero-downtime deployment support

### Monitoring & Logging

**Operational Visibility**
- Request logging and metrics
- Error tracking and reporting
- Performance monitoring
- Resource utilization tracking

## Browser Extension

### Extension Architecture

**Manifest V3 Specification**
- Modern Chrome extension API
- New tab page integration
- Minimal permissions model
- Native JavaScript implementation
- No build process required

**Features**
- Sets Indexa as default new tab
- Fast, lightweight operation
- Privacy-respecting integration

## Key Technical Decisions

### Embedded Database Choice

SQLite selected over client-server databases:
- Zero configuration and maintenance
- Single-file portability
- Excellent read performance
- Built-in full-text search
- Perfect fit for search engine workloads
- No network overhead

### Local AI Processing

On-device models over cloud APIs:
- Complete user privacy protection
- Zero per-query operational costs
- Offline functionality
- No rate limiting concerns
- Full data control

### Framework-Free Frontend

Native JavaScript over frameworks:
- Faster page load times
- Smaller bundle sizes
- No framework learning curve
- Direct browser API access
- Reduced complexity

### Type Safety

TypeScript strict mode throughout:
- Compile-time error detection
- Enhanced IDE support
- Better refactoring capabilities
- Self-documenting code
- Reduced runtime errors

### Distributed Architecture

Redis for horizontal scaling:
- Distributed crawling coordination
- Multi-tier caching infrastructure
- Job queue management
- Cross-process communication
- Horizontal scalability

### Selective Rendering

Intelligent JavaScript execution:
- Performance optimization through detection
- Render only when necessary
- Cache rendering results
- Resource usage optimization
- Cost reduction

### Custom Vector Search

In-house HNSW implementation:
- Full control over algorithm
- Optimization for specific use case
- No external dependencies
- Tailored performance characteristics
- Custom persistence strategy

## Performance Characteristics

The technology stack is optimized for:

**Speed**
- Sub-second query response times
- Efficient caching strategies
- Parallel processing where applicable
- Optimized data structures

**Scalability**
- Horizontal worker scaling
- Database sharding support
- Distributed job processing
- Resource pooling

**Privacy**
- Local-first processing
- No external API calls for core functionality
- User data remains on system
- Minimal data collection

**Reliability**
- Automatic error recovery
- Graceful degradation
- Comprehensive error handling
- Process supervision

---

*Technology choices reflect ongoing optimization and may evolve based on performance requirements and best practices.*
