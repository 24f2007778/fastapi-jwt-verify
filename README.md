# FastAPI RS256 JWT Verification API

## Endpoint
`POST /verify` with JSON `{"token":"<JWT string>"}`.

Valid tokens return HTTP 200 and `valid`, `email`, `sub`, and `aud`.
Invalid tokens return HTTP 401.

## Deploy without Blueprint
1. Create a GitHub repository and upload `main.py` and `requirements.txt`.
2. In Render, choose **New → Web Service**, connect the repository, and select a Free instance if available.
3. Build command: `pip install -r requirements.txt`
4. Start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`
5. Deploy, then use `https://YOUR-SERVICE.onrender.com/verify`.

## Smoke test
`curl -i -X POST 'https://YOUR-SERVICE/verify' -H 'Content-Type: application/json' -d '{"token":"not-a-jwt"}'`
