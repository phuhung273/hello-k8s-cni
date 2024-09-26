## Reference
https://github.com/f1ko/demystifying-cni

## Create cluster
```bash
kind create cluster --config kind.yaml --name default
```

## Code break down
### CNI Config
![First step](cni-step-1.png)
```json
// Config manifest under /etc/cni/net.d/
{
  "cniVersion": "1.0.0",
  "name": "hello",
  "type": "demystifying" // executable under /opt/cni/bin/
}
```

### CRI pass data (JSON + environment) to executable
![Second step](cni-step-2.png)