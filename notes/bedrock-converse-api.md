# Bedrock Converse API

## What is it?
The **Converse API** is the swiss army knife for message-based interactions with foundation models in Bedrock.

- Provides a **consistent API** across models — makes it easy to swap out foundation models in your app
- At minimum you need: **`modelId`** + **`prompt`** (can reference a stored prompt from Bedrock Prompt Management)

---

## Key Optional Parameters

| Parameter | Purpose |
|-----------|---------|
| `toolConfig` | Pass tool/function definitions for agentic AI workflows |
| `guardrailConfig` | Filter objectionable inputs/outputs via Bedrock Guardrails |
| `inferenceConfig` | Control model behaviour (temperature, maxTokens, topP, stopSequences) |
| `additionalModelRequestFields` | Model-specific settings |
| `promptVariables` | Variable substitution for stored prompts |
| `system` | System prompt configuration |
| `performanceConfig` | Latency settings |
| `serviceTier` | Service tier selection |

---

## API Structure

```json
POST /model/modelId/converse HTTP/1.1
Content-type: application/json

{
  "additionalModelRequestFields": JSON value,
  "additionalModelResponseFieldPaths": [ "string" ],
  "guardrailConfig": { 
    "guardrailIdentifier": "string",
    "guardrailVersion": "string",
    "trace": "string"
  },
  "inferenceConfig": { 
    "maxTokens": number,
    "stopSequences": [ "string" ],
    "temperature": number,
    "topP": number
  },
  "messages": [ 
    { 
      "content": [ { ... } ],
      "role": "string"
    }
  ],
  "outputConfig": { 
    "textFormat": { 
      "structure": { ... },
      "type": "string"
    }
  },
  "performanceConfig": { 
    "latency": "string"
  },
  "promptVariables": { 
    "string" : { ... }
  },
  "requestMetadata": { 
    "string" : "string" 
  },
  "serviceTier": { 
    "type": "string"
  },
  "system": [ { ... } ],
  "toolConfig": { 
    "toolChoice": { ... },
    "tools": [ { ... } ]
  }
}
```

---

## Exam Tips 💡
- You **won't need to write code** in the exam — just understand how it works
- Know that Converse API = consistent interface for **switching models easily**
- Remember the key params: `modelId`, `messages`, `toolConfig`, `guardrailConfig`, `inferenceConfig`
- Stored prompts from **Bedrock Prompt Management** can be referenced here
- **Guardrails** = filtering objectionable inputs/outputs (covered later in course)

---

*Source: Udemy – AWS Certified Generative AI Developer Professional (Frank Kane & Stéphane Maarek)*
