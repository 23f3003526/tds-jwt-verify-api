# JWT Verification API

## Run locally
```bash
python -m pip install -r requirements.txt
uvicorn main:app --reload
```

POST `http://127.0.0.1:8000/verify` with JSON:
```json
{"token":"<JWT string>"}
```

## Deploy on Render
1. Push these files to a GitHub repository.
2. In Render, create a new **Web Service** from that repository.
3. Render detects `render.yaml`, or use:
   - Build command: `pip install -r requirements.txt`
   - Start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`
4. After deployment, submit `https://YOUR-SERVICE.onrender.com/verify`.

Invalid tokens return HTTP 401 with `{"detail":{"valid":false}}`.
