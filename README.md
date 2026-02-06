# Lux Charts

Helm charts for Lux blockchain infrastructure.

## Charts

| Chart | Description |
|-------|-------------|
| node | Lux blockchain node |
| validator | Lux validator node |
| subnet | Lux subnet deployment |
| explorer | Block explorer |

## Usage

```bash
helm repo add luxfi https://luxfi.github.io/charts/
helm repo update
helm install my-node luxfi/node
```

## Development

```bash
# Lint charts
ct lint --all

# Test charts
ct install --all
```
