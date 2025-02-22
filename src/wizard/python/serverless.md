---
name: Serverless (Python)
doc_link: https://docs.sentry.io/platforms/python/guides/serverless/
support_level: production
type: framework
---

It is recommended to use an [integration for your particular serverless environment if available](/platforms/python/#serverless), as those are easier to use and capture more useful information.

If you use a serverless provider not directly supported by the SDK, you can use this generic integration.

Apply the `serverless_function` decorator to each function that might throw errors:

```python
import sentry_sdk
from sentry_sdk.integrations.serverless import serverless_function

sentry_sdk.init(
    dsn="___PUBLIC_DSN___",

    # Set traces_sample_rate to 1.0 to capture 100%
    # of transactions for performance monitoring.
    # We recommend adjusting this value in production,
    traces_sample_rate=1.0,
)

@serverless_function
def my_function(...): ...
```

<!-- TODO-ADD-VERIFICATION-EXAMPLE -->
