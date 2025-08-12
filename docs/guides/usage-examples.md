# Usage Examples

Replace placeholders to match your actual API.

## REST API (cURL)
```bash
# List items
curl -sS -X GET "http://localhost:3000/api/v1/items" | jq

# Get item by id
curl -sS -X GET "http://localhost:3000/api/v1/items/<id>" | jq

# Create item
curl -sS -X POST "http://localhost:3000/api/v1/items" \
  -H 'Content-Type: application/json' \
  -d '{"name":"Milk","price":2.49}' | jq
```

## JavaScript/TypeScript SDK (example)
```ts
import { Client } from '<your-sdk>';

const client = new Client({ baseUrl: 'http://localhost:3000', apiKey: process.env.API_KEY });
const items = await client.items.list();
```

## Python SDK (example)
```python
from your_sdk import Client

client = Client(base_url='http://localhost:3000', api_key=os.environ.get('API_KEY'))
items = client.items.list()
```

## CLI (example)
```bash
yourcli items list --base-url http://localhost:3000 --json
```