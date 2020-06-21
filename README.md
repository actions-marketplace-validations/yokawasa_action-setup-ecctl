<p align="center">
  <a href="https://github.com/yokawasa/action-setup-ecctl/actions"><img alt="action-setup-ecctl status" src="https://github.com/yokawasa/action-setup-ecctl/workflows/build-test/badge.svg"></a>
</p>

# action-setup-ecctl

A GitHub action that install a specific version of ecctl and cache on the runner

## Usage

### Inputs
TBU

### Sample Workflow

```yaml
- uses: yokawasa/action-setup-ecctl@v0.1.0
  with:
    version: 'v1.0.0-beta3'   # default is 'latest'
  id: setup
- run: |
  ecctl=${{steps.setup.outputs.ecctl-path}}
  ${ecctl} version
```


## Developing the action

Install the dependencies  
```bash
npm install
```

Build the typescript and package it for distribution by running [ncc](https://github.com/zeit/ncc)
```bash
npm run build && npm run pack
```

Finally push the resutls
```
git add dist
git commit -a -m "prod dependencies"
git push origin releases/v0.1.0
```

## Contributing
Bug reports and pull requests are welcome on GitHub at https://github.com/yokawasa/action-setup-ecctl
