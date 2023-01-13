# Troubleshoot/Utility

## VSCode configuration

### Link steps in the feature with their definition

Check *cucumberautocomplete* extension settings, the parameter *cucumberautocomplete.steps* will look like:

```json
"cucumberautocomplete.steps": [
        "e2e-test/step-definitions/*.steps.ts",
        "node_modules/@rgi/playwright-cucumber-runner-lib/dist/step-definitions/*.js",
        "node_modules/@rgi/playwright-globalshare-lib/dist/step-definitions/*.js"
    ]
```