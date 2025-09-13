openapi: 3.1.0
info:
  title: Sophia Interview Session Control
  version: 1.0.0
servers:
- url: https://localhost:8787
paths:
  /set_mode:
    post:
      operationId: set_mode
      summary: Configure session format/persona/stations
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                format:
                  type: string
                  enum:
                  - MMI
                  - Traditional
                  - Panel
                stations:
                  type: integer
                  minimum: 1
                  maximum: 12
                persona:
                  type: string
                focus_competencies:
                  type: array
                  items:
                    type: string
                duration_minutes:
                  type: integer
                  minimum: 5
                  maximum: 120
              required:
              - format
      responses:
        '200':
          description: OK
  /start_timer:
    post:
      operationId: start_timer
      summary: Start a countdown timer
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                seconds:
                  type: integer
                  minimum: 10
                  maximum: 900
              required:
              - seconds
      responses:
        '200':
          description: OK
  /stop_timer:
    post:
      operationId: stop_timer
      responses:
        '200':
          description: OK
components:
  securitySchemes:
    api_key:
      type: apiKey
      in: header
      name: x-api-key
security:
- api_key: []
