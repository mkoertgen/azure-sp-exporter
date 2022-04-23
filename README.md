# azure-sp-exporter

Exposing Prometheus Metrics for Azure Service Principals

## Requirements

- [Python >=3.10](https://www.python.org/)

## Development

```shell
# Install dependencies
pip install --user -r requirements.txt -r requirements-dev.txt

# Update dependencies
$ python -m pur -r requirements.txt -r requirements-dev.txt
All requirements up-to-date.

# Run tests
$ python -m pytest --cov
tests\api\test_sp.py .                                           [100%]

============================= 1 passed in 0.05s =============================

# Run - development mode
$ python -m uvicorn main:app --reload
INFO:     Will watch for changes in these directories: ['...azure-sp-exporter/src']
INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
INFO:     Started reloader process [3272] using statreload
WARNING:  The --reload flag should not be used in production.
INFO:     Started server process [20152]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

Next hit

- API: [/api/openapi.json](http://localhost:8000/api/openapi.json) & Swagger-UI at [/docs]](http://localhost:8000/docs)
- Metrics: [/health](http://localhost:8000/health) & [/metrics](http://localhost:8000/metrics)

## References

- [az ad sp credential list](https://docs.microsoft.com/de-de/cli/azure/ad/sp/credential?view=azure-cli-latest#az-ad-sp-credential-list)
- [List servicePrincipals](https://docs.microsoft.com/en-us/graph/api/serviceprincipal-list?view=graph-rest-1.0&tabs=http)
