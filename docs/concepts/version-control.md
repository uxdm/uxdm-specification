# Version Control

We use [Semver](https://semver.org/) as the basics of our version control system, which aligns with standard software development and product release progress. The only difference is we use a separated version suffix to help solve the problem of minor design fixes after the "final" design review and before the update release.

## Format

`<semver string>:<fix iterations>`

Example: `1.2.0:4` (The fourth design fix for version 1.2.0)

Notice: If you use one UXDM project to manage a product targeting multiple platforms, you should consider the Semver more of a product version instead of the platform app version.

## Branch

### Hierarchy

- Major version
  - Minor version
    - Patch version
      - Fixes

In this early draft, we plan to set up branches following the version number. Fixes applied to the lower version number will be committed to the higher version number automatically. For example, your team stabilized the `2.4.9:1` version, and you're designing the `2.4.10` version. Suddenly they find out a crucial design flaw in the `2.4.9:1` version. You patch it with the `2.4.9:2` fix. What will happen next is the tool pushes the changes onto your `2.4.10` version. It's crucial to keep the design in sync with the product release.

### Major release

After a major release, your product manager can lock the related major branch. No more edits are allowed.
