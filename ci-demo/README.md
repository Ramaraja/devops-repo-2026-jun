# Install dependencies
. venv/bin/activate
pip install -r requirements.txt

# Run locally
. venv/bin/activate
python app/main.py

# Test API
curl http://localhost:5000/todos
curl -X POST http://localhost:8000/todos -H "Content-Type: application/json" -d '{"task":"CI Demo 2"}'

# Run tests
. venv/bin/activate
pytest -v --cov=app

# Run lint
. venv/bin/activate
flake8 app tests
