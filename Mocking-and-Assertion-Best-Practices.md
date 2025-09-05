# Mocking and Assertion Best Practices (Python)

## Mocking Strategy

- Always mock external dependencies (databases, APIs, external services).
- Use Python’s `unittest.mock` or `pytest-mock`.
- Use only generic, non-sensitive test data (e.g., "John Doe", numbers like `123`).
- Never use real production data or connect to real services in tests.
- Clearly state in the docstring what is mocked and what the mock returns.

## Assertion Strategy

- Assert the exact return values and types (not just that it succeeds).
- For APIs, assert status codes, headers, and response bodies.
- For exceptions, assert correct exception type and message.
- Avoid over-broad assertions; be precise and strict.
- For integration tests, assert the final output as well as any side effects.

## Example

```python
@patch("module.external_api")
def test_fetch_data(mock_external_api):
    """
    Title: Fetch data returns correct structure
    Description: Ensure fetch_data returns a dict with 'results' key.
    Mocking Strategy: Mock external_api to return {"results": [1,2,3]}.
    Assertion Strategy: Assert the returned dict matches the mock exactly.
    """
    mock_external_api.get_data.return_value = {"results": [1,2,3]}
    data = fetch_data()
    assert data == {"results": [1,2,3]}
    assert isinstance(data, dict)
```