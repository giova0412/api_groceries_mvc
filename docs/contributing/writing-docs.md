# Writing Documentation

Follow these conventions to document public APIs, functions, and components.

## JavaScript/TypeScript (TSDoc/JSDoc)
```ts
/**
 * Calculates the total price of a cart.
 *
 * @param items - Array of cart items
 * @param items[].price - Unit price
 * @param items[].quantity - Quantity
 * @returns Total price including tax
 * @example
 * const total = calculateTotal([{ price: 2.5, quantity: 2 }]);
 */
export function calculateTotal(items: { price: number; quantity: number }[]): number { /* ... */ }
```

Generate docs:
```bash
npm i -D typedoc typedoc-plugin-markdown
npx typedoc --out docs/api --plugin typedoc-plugin-markdown src/index.ts
```

## Python (docstrings)
```python
def calculate_total(items: list[dict]) -> float:
    """Calculate the total price of a cart.

    Args:
        items: List of items with ``price`` and ``quantity``.

    Returns:
        Total price including tax.

    Examples:
        >>> calculate_total([{"price": 2.5, "quantity": 2}])
        5.0
    """
    pass
```

Generate with `pdoc`:
```bash
pip install pdoc
pdoc -o docs/api your_package
```

## React Components
```tsx
/** Button that triggers checkout.
 *
 * @prop label - Visible text
 * @prop onClick - Click handler
 * @example
 * <CheckoutButton label="Buy" onClick={() => {}} />
 */
export function CheckoutButton({ label, onClick }: { label: string; onClick: () => void }) { /* ... */ }
```

## HTTP API Endpoints (Markdown template)
```md
### GET /api/v1/items
- Description: List items
- Auth: Bearer <token>
- Query: `page` (int), `limit` (int)
- Response: 200 OK
```