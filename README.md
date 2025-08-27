# AI GraphQL Pentester - Burp Suite Extension

A comprehensive Burp Suite extension that leverages Burp's native **Montoya AI** to generate sophisticated malicious GraphQL test queries for authorized security testing. Features dynamic AI status monitoring, schema introspection, RAG integration, and intelligent query formatting.

## 🚀 Features

### Core AI-Powered Functionality
- **Montoya AI Integration**: Uses Burp Suite's built-in AI capabilities (Professional edition required)
- **Dynamic AI Status**: Real-time AI status monitoring with automatic updates
- **Schema Extraction**: Two methods supported
  - Automatic introspection of GraphQL endpoints
  - Manual schema input and parsing
- **AI-Powered Query Generation**: Two modes available:
  - **Bulk Generation**: Generates multiple malicious queries targeting common vulnerabilities
  - **Single Query Testing**: Generate malicious variants of a specific target query/mutation
- **Custom AI Messages**: Direct interaction with Montoya AI for specialized security guidance

### Advanced Security Testing
Tests for comprehensive GraphQL vulnerabilities:
- SQL injection attempts
- Authorization bypass vulnerabilities
- DoS via deep nesting and resource exhaustion
- Information disclosure through introspection
- Input validation bypass
- NoSQL injection attacks
- Time-based attack vectors
- Field access bypasses
- Rate limiting vulnerabilities
- Authentication bypass in nested queries

### Advanced Features
- **Single-Line Query Format**: Automatically converts multi-line GraphQL queries to single-line format for easy testing
- **Dynamic Status Updates**: AI status automatically refreshes when toggling the "Use AI" checkbox
- **External RAG Integration**: Optional integration with RAG services for enhanced security knowledge
- **Smart Query Processing**: Intelligent parsing of AI responses with context preservation
- **Unicode Handling**: Robust Unicode character processing for international content
- **Caching System**: Prevents duplicate expensive operations and RAG queries
- **Background Processing**: Non-blocking AI operations to keep Burp responsive

## 📋 Requirements

- **Burp Suite Professional** with AI features enabled
- **Montoya API 2025.8** or later
- **Java 17+** runtime environment
- **AI Credits**: Burp Suite AI credits for query generation

## 🛠 Installation

### Method 1: Pre-built JAR (Recommended)
1. Download the pre-built JAR: `AIGraphqlPentester-1.0.jar`
2. Open Burp Suite Professional
3. Go to **Extensions** → **Installed** → **Add**
4. Select **Java** as extension type
5. Choose the JAR file and click **Next**
6. **Enable AI**: Check the **"Use AI"** checkbox for the extension in the Extensions tab

### Method 2: Build from Source
```bash
git clone <repository-url>
cd AIGraphqlPentester
./gradlew clean build
# Use build/libs/AIGraphqlPentester-1.0.jar
```

## 🎯 Usage

### Initial Setup

1. **Enable AI Features**:
   - Go to **Extensions** → **Installed**
   - Find **"AI GraphQL Pentester"**
   - Check the **"Use AI"** checkbox
   - AI Status tab will show "ENABLED" when active

2. **Optional - RAG Integration**: 
   - Configure external RAG endpoint (e.g., `http://localhost:50001`)
   - Set Lambda multiplier (0.0=diversity, 1.0=relevance, default=0.7)
   - Set Documents count (1-20, default=5)

### Schema Extraction

**Method 1: Automatic Introspection**
1. Enter your GraphQL endpoint URL
2. Click **"Introspect Schema"**
3. Schema will be automatically extracted and parsed

**Method 2: Manual Input**
1. Paste your GraphQL schema JSON in the text area
2. Click **"Parse Schema"**

### AI-Powered Query Generation

**Targeted Testing (Recommended):**
1. Paste a specific GraphQL query/mutation in the "Target Query/Mutation" field
2. Specify attack types: `SQL Injection, Authorization Bypass, DoS, Information Disclosure`
3. Click **"Generate Malicious Queries"**
4. Montoya AI will create malicious variants with detailed explanations

**Comprehensive Testing:**
1. Leave target query field empty for bulk generation
2. Specify desired attack types
3. Click **"Generate Malicious Queries"**
4. Review generated test queries with attack descriptions

### Custom AI Interaction

**Direct AI Communication:**
1. Switch to **"Custom Messages"** tab
2. Enter specific security testing requirements:
   - `"Focus on NoSQL injection in GraphQL mutations"`
   - `"Generate authentication bypass variants"`
   - `"Create resource exhaustion test queries"`
3. Click **"Send Custom Message"**
4. Receive tailored security advice and specialized queries

### Dynamic AI Status Monitoring

- **Real-time Updates**: AI status automatically refreshes when switching tabs
- **Button State Management**: AI buttons enable/disable based on current AI status
- **Visual Feedback**: Color-coded status indicators (Green=Enabled, Red=Disabled)
- **Instructions**: Dynamic help text based on current AI availability

## 🔧 Configuration

### AI Configuration
- **Status Check**: Automatic AI availability detection
- **Credit Usage**: Monitor AI credits in Burp Suite settings
- **Response Processing**: Intelligent parsing of Montoya AI responses
- **Error Handling**: Comprehensive error handling with user feedback

### RAG Integration (Optional)
```json
{
  "endpoint": "http://localhost:50001",
  "search_params": {
    "k": 5,
    "search_type": "mmr",
    "fetch_k": 15,
    "lambda_mult": 0.7
  }
}
```

#### RAG Parameters
- **search_type**: "mmr" for Maximum Marginal Relevance
- **k**: Documents to retrieve (1-20)
- **fetch_k**: Candidates for MMR selection (auto: k×3)
- **lambda_mult**: Relevance vs diversity (0.0-1.0)

## 📱 User Interface

### Tabs Overview
1. **Schema & Testing**: Main testing interface with schema extraction and query generation
2. **AI Status**: Real-time AI status monitoring with dynamic updates
3. **RAG Configuration**: Optional external knowledge integration settings
4. **Custom Messages**: Direct Montoya AI communication interface

### Dynamic Features
- **Tab Change Detection**: Status updates automatically when switching to AI Status tab
- **Button State Sync**: AI buttons reflect current availability status
- **Status Indicators**: Visual feedback with color-coded status labels
- **Contextual Help**: Dynamic instructions based on AI availability

## 🔍 Security Testing Workflow

1. **Schema Discovery**: Extract GraphQL schema via introspection or manual input
2. **AI Status Check**: Verify AI is enabled and ready for query generation
3. **Attack Vector Selection**: Choose specific vulnerabilities to test
4. **Query Generation**: Use Montoya AI to create malicious test queries
5. **Manual Testing**: Apply generated single-line queries to target endpoints
6. **Custom Analysis**: Use AI messaging for specialized security insights

## ⚡ Performance & Reliability

- **Background Processing**: AI operations run asynchronously to prevent UI blocking
- **Smart Caching**: RAG responses cached to prevent duplicate expensive operations
- **Resource Management**: Proper cleanup and memory management
- **Error Recovery**: Comprehensive error handling with user-friendly messages
- **Status Monitoring**: Real-time AI availability checking

## 🛡 Security Notice

**This tool is designed for authorized defensive security testing only.**

- ✅ Use only on systems you own or have explicit permission to test
- ✅ Follow responsible disclosure practices
- ✅ Designed for defensive security improvements
- ❌ Not intended for malicious activities

## 🐛 Troubleshooting

### AI Not Available
1. Ensure Burp Suite Professional is running
2. Verify AI features are enabled in your license
3. Check the "Use AI" checkbox in Extensions tab
4. Switch to AI Status tab to see current status
5. Restart Burp Suite if needed

### RAG Connection Issues
- Verify RAG service is running on specified port
- Check network connectivity and firewall settings
- Review Burp Suite proxy configuration
- RAG integration is optional - extension works without it

### Performance Issues
- AI operations run in background threads
- Large schemas may require additional processing time
- RAG responses are cached to improve performance
- Monitor AI credit usage in Burp Suite settings

## 🔄 Version History

### v1.0 - Current Release
- **Montoya AI Integration**: Full integration with Burp Suite's native AI
- **Dynamic Status Monitoring**: Real-time AI status updates and button management
- **Enhanced Capability Declaration**: Proper `EnhancedCapability.AI_FEATURES` implementation
- **Smart UI Updates**: Tab change detection with automatic status refresh
- **Single-line Query Formatting**: Optimized for security testing workflows
- **RAG Integration**: Optional external knowledge enhancement
- **Custom AI Messaging**: Direct communication with Montoya AI
- **Comprehensive Error Handling**: User-friendly error management
- **Background Processing**: Non-blocking AI operations
- **BApp Store Compliance**: Meets all PortSwigger BApp Store requirements

## 🤝 Contributing

Contributions focused on defensive security testing are welcome:

- **Security Testing**: Enhanced vulnerability detection capabilities
- **AI Integration**: Improved Montoya AI utilization
- **Performance**: Optimization and reliability improvements
- **Documentation**: Usage examples and security guidance

## Contributors
Thanks to all the people who already contributed!
Nayan Goel
Nandan Gupta

## 📜 License

This extension is designed for authorized security testing and educational purposes. Use responsibly and in accordance with applicable laws and regulations.

---

**🤖 Built with Montoya AI Integration for Burp Suite Professional**

*Leveraging Burp Suite's native AI capabilities for advanced GraphQL security testing*
