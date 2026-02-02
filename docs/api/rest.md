# REST API

API reference for the Vindicta Platform.

---

## Base URL

```
https://api.vindicta.dev/v1  (hosted)
http://localhost:8000/v1     (local)
```

## Authentication

Currently open. Authentication coming in v1.1.

## Endpoints

### Health

```http
GET /health
```

Returns platform health status.

---

### Dice

#### Roll Dice

```http
POST /dice/roll
```

```json
{
  "notation": "2d6+3",
  "count": 1
}
```

Response:

```json
{
  "results": [11],
  "notation": "2d6+3",
  "proof": "a1b2c3..."
}
```

---

### Economy

#### Get Balance

```http
GET /economy/balance
```

#### Record Usage

```http
POST /economy/usage
```

---

### Oracle

#### Get Prediction

```http
POST /oracle/predict
```

```json
{
  "my_list": {...},
  "opponent_list": {...},
  "mission": "Purge the Enemy"
}
```

---

## Error Responses

```json
{
  "error": "insufficient_credits",
  "message": "Not enough credits for this operation",
  "required": 10,
  "available": 5
}
```

## OpenAPI Spec

Full spec available at `/docs` when running locally.
