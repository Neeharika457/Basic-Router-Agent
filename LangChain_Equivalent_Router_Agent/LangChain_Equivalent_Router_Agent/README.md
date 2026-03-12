# Setup Instructions

## API Configuration

This notebook uses Large Language Models (LLMs) through API integrations. While the code uses the OpenAI API by default, it can be configured to work with other providers (for example, **GROQ**) based on user preference and API availability.

---

## Getting API Keys

- **OpenAI**: https://platform.openai.com/api-keys
- **GROQ**: https://console.groq.com  

---

## Environment Setup

1. Create a `.env` file in the project root directory.
2. Add your API key for the provider you wish to use:

**For OpenAI:**
```bash
OPENAI_API_KEY=your_api_key_here
```

**For GROQ:**
```bash
GROQ_API_KEY=your_api_key_here
```

---

## Provider Configuration

The LLM provider can be changed in the code configuration.  
OpenAI is used as the default provider, and other supported providers such as GROQ can be plugged in with minimal code changes.

---

## Notes

- Never commit your `.env` file to version control.
- Ensure `.env` is included in your `.gitignore`.
- An active internet connection is required to use any LLM provider.
