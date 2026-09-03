# Lux Charts

Helm charts for Lux network infrastructure.

## Charts

| Chart | Description |
|-------|-------------|
| node  | A validator — luxd, its chains and its peer identity |

## The node chart

One chart serves every network that runs `luxfi/node`. Per-network values
select the network id and nothing else:

```bash
helm install lux   oci://ghcr.io/luxfi/charts/node -f charts/node/values-lux.yaml    # id 1
helm install hanzo oci://ghcr.io/luxfi/charts/node -f charts/node/values-hanzo.yaml  # id 36963
helm install zoo   oci://ghcr.io/luxfi/charts/node -f charts/node/values-zoo.yaml    # id 200200
```

Lux's primary network is 1 (mainnet), 2 (testnet), 3 (local). A sovereign L1
uses its EVM id as its network id, so one number names one network wherever
it appears.

The image is pinned by digest in each values file and falls back to the
chart's `appVersion`. Set `image.digest` to pin exactly; a floating tag is not
a deployable pin. Environment-specific values live in `lux/universe`.

## Usage

```bash
helm repo add luxfi https://luxfi.github.io/charts/
helm repo update
```

## Development

```bash
helm lint charts/node
helm template n charts/node -f charts/node/values-lux.yaml
```
