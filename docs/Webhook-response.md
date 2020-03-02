## Webhook Request

This article shows the request, that is POSTed to the user's webhook after a document has been submitted to the `/document` endpoint.


### Body
```json json_schema
{
  "type": "object",
  "required": [
    "company_name"
  ],
  "properties": {
    "company_name": {
      "type": "string"
    },
    "contact": {
      "type": "array",
      "items": { "$ref": "#/definitions/contact" }
    },
    "founders_team": {
      "type": "array",
      "items": { "$ref": "#/definitions/founder" }
    },
    "pitch_long": {
      "type": "string"
    },
    "categories": {
      "type": "object"
    },
    "keywords": {
      "type": "array"
    },
    "trace_id": {
      "type": "object",
      "description": "Trace Id, which was passed with the original request."
    }
  },
  "definitions": {
    "founder": {
      "type": "object",
      "required": [ "name", "role" ],
      "properties": {
        "name": {
          "type": "string"
        },
        "role": {
          "type": "string"
        },
        "linkedIn": {
          "type": "string"
        },
        "areas": {
          "type": "array",
          "items": "string"
        },
        "email": {
          "type": "string"
        },
        "email_valid": {
          "type": ["boolean", "string"]
        }
      }
    },
    "contact": {
      "type": "object",
      "properties": {
        "email": {
          "type": ["string", "array"]
        },
        "phone": {
          "type": ["string", "array"]
        },
        "website": {
          "type": "string"
        },
        "email_valid": {
          "type": ["boolean", "string", "array"]
        }
      }
    }
  }
}
```
