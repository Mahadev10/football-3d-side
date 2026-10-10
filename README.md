# Messi 3D Farewell — Python Web App

A small Flask web app featuring a stylized 3D football tribute using Three.js.

## Requirements
- Python 3.10+
- Internet connection in the browser for the Three.js CDN

## Run locally
```bash
python3 -m venv .venv
source .venv/bin/activate      # macOS/Linux
# .venv\\Scripts\\activate       # Windows PowerShell
pip install -r requirements.txt
python app.py
```
Open http://127.0.0.1:5000

## Run on Ubuntu
```bash
sudo apt update
sudo apt install python3 python3-venv -y
python3 -m venv .venv
. .venv/bin/activate
pip install -r requirements.txt
python app.py
```
For production, use Gunicorn behind Nginx rather than Flask's development server.

The footballer is an abstract 3D tribute, not a photorealistic likeness. Three.js is loaded from a CDN, so the browser needs internet access.
