{
  "name": "Announcement",
  "type": "object",
  "properties": {
    "title": {
      "type": "string"
    },
    "content": {
      "type": "string"
    },
    "media_type": {
      "type": "string",
      "enum": [
        "none",
        "image",
        "video"
      ],
      "default": "none"
    },
    "media_url": {
      "type": "string"
    },
    "is_active": {
      "type": "boolean",
      "default": true
    },
    "order": {
      "type": "number",
      "default": 0
    }
  },
  "required": [
    "title"
  ],
  "rls": {
    "create": {
      "user_condition": {
        "role": "admin"
      }
    },
    "read": {
      "$or": [
        {
          "user_condition": {
            "role": "user"
          }
        },
        {
          "user_condition": {
            "role": "admin"
          }
        }
      ]
    },
    "update": {
      "user_condition": {
        "role": "admin"
      }
    },
    "delete": {
      "user_condition": {
        "role": "admin"
      }
    }
  }
}
