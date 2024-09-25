# Node and NPM
This document will focus (mostly) on Node and NPM as they function as build tools. I have **nothing** against Deno, pnpm, Bun, or Yarn. I just don't use them all that much but will add tricks and tips if that changes.

## NPM

### Manual dependency overrides
Sometimes we can't eliminate dependency vulnerabilities with `npm fix [--force]` alone. This is where the NPM [manual override feature]((https://docs.npmjs.com/cli/v9/configuring-npm/package-json#overrides) really shines:

> NPM 8 introduced "overrides" to help workaround these type of issues. You can now override specific transitive dependencies of your direct dependency to the version you need. In your case, you would declare something like below to fix the vulnerable dependency.
> 
> https://stackoverflow.com/a/70490778


```json
{
  "overrides": {
    "your-direct-dependency": {
      "vulnerable-package": "fixed_version"
    }
  }
}
```
