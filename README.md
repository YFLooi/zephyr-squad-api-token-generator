# Zephyr Squad API Token generator
Made by translating the methods in the `com.thed.zephyr.cloud.rest.ZFJCloudRestClient` Java package into Python

Contributions are welcome! [Repository](https://github.com/YFLooi/zephyr-squad-api-token-generator)

# Installation
`pip install zephyr-squad-api-token-generator`

# Usage

```python
from zephyr_squad_api_token_generator import generate_zephyr_jwt

jwt_token = generate_zephyr_jwt(
    endpoint_url="https://prod-api.zephyr4jiracloud.com/connect/public/rest/api/1.0/zql/search",
    http_method="GET",
    access_key="your-zephyr-access-key",
    secret_key="your-zephyr-secret-key",
    zephyr_username="your-atlassian-username",
)

# Use the token in your API request headers. For example:
headers = {"Content-Type": "application/json", "Authorization": f"JWT {jwt_token}", "zapiAccessKey": "your-zephyr-access-key"}
```

# Development
Since this is a Poetry package, changes require rebuilding the dist/ folder. Run this from the repo root (where `pyproject.toml` lives). Dependencies listed in pyproject.toml would be installed:
`poetry build`

If you want a clean rebuild, you can delete the dist/ folder first.