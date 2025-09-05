# Unit & Integration Test Case Documentation (Python: pytest/unittest)

For all unit and integration tests, use detailed docstrings in your Python test code. Do not include Test Case IDs in the code. Instead, your docstring should capture:

- Title
- Description (purpose)
- Mocking Strategy
- Assertion Strategy
- Any relevant notes

## Example: pytest

```python
from unittest.mock import patch

def get_user_details(user_id):
    # Simulated function to fetch user details
    pass

@patch("module_containing_function.user_db_service")
def test_get_user_details(mock_user_db_service):
    """
    Title: Service returns user details
    Description: Verifies get_user_details returns correct user info in the right format.
    Mocking Strategy: Mock user_db_service to return generic data, no real DB call.
    Assertion Strategy: Assert that the returned value equals {"id": 123, "name": "John Doe"} and type is dict.
    """
    mock_user_db_service.get_by_id.return_value = {"id": 123, "name": "John Doe"}
    result = get_user_details(123)
    assert result == {"id": 123, "name": "John Doe"}
    assert isinstance(result, dict)
```

## Example: unittest

```python
import unittest
from unittest.mock import patch

class TestUserService(unittest.TestCase):
    @patch("module_containing_function.user_db_service")
    def test_get_user_details(self, mock_user_db_service):
        """
        Title: Service returns user details
        Description: Verifies get_user_details returns correct user info in the right format.
        Mocking Strategy: Mock user_db_service to return generic data, no real DB call.
        Assertion Strategy: Assert that the returned value equals {"id": 123, "name": "John Doe"} and type is dict.
        """
        mock_user_db_service.get_by_id.return_value = {"id": 123, "name": "John Doe"}
        result = get_user_details(123)
        self.assertEqual(result, {"id": 123, "name": "John Doe"})
        self.assertIsInstance(result, dict)
```

**Best Practices:**
- No Test Case IDs in code.
- Docstrings must include: Title, Description, Mocking Strategy, Assertion Strategy.
- Mock all external dependencies, use only generic (non-sensitive) data.
- Assert on exact returned data and type.
