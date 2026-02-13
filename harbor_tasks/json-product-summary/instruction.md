# JSON Product Summary

## Objective

Read the product catalog from `/app/input.json`, process the data, and write the result to `/app/output.json`.

## Input

The file `/app/input.json` contains a JSON array of product objects. Each product has the following fields:

- `name` (string): Product name
- `category` (string): Product category
- `price` (number): Product price
- `in_stock` (boolean): Whether the product is in stock
- `quantity` (integer): Number of items available

## Processing Steps

1. **Filter**: Keep only products where `in_stock` is `true`.
2. **Sort**: Sort the filtered products by `price` in **descending** order (highest price first).
3. **Transform**: For each product in the sorted list, create an object with only these fields:
   - `name`: The product name
   - `category`: The product category
   - `price`: The product price
4. **Wrap**: Place the resulting array under a key called `"products"` and include:
   - `"count"`: The number of filtered products
   - `"total_value"`: The sum of all filtered product prices, rounded to 2 decimal places
   - `"categories"`: An object mapping each category name to the number of products in that category

## Output

Write the result as a JSON file to `/app/output.json`. The JSON must be formatted with 2-space indentation and a trailing newline.

### Expected Output Structure

```json
{
  "count": <number_of_in_stock_products>,
  "total_value": <sum_of_prices_rounded_to_2_decimals>,
  "categories": {
    "CategoryA": <count>,
    "CategoryB": <count>
  },
  "products": [
    {
      "name": "...",
      "category": "...",
      "price": ...
    }
  ]
}
```
