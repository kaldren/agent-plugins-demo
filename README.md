# dotnet

A single [Agent Plugins 1.0](https://agent-plugins.org/) plugin, version **1.1.0**, with two skills for .NET unit testing:

- `create-unit-tests`: create or extend tests using existing project conventions.
- `run-unit-tests`: execute existing tests, summarize results, and diagnose failures.

The skill follows existing project conventions for xUnit, NUnit, or MSTest, covers relevant behaviors and boundaries, and runs the tests when the .NET SDK is available.

## Install in VS Code

1. Enable agent plugins in VS Code (`chat.plugins.enabled`).
2. Open the Command Palette and run **Chat: Install Plugin From Source**.
3. Enter this repository URL:

   ```text
   https://github.com/kaldren/agent-plugins-demo
   ```

See the [official VS Code plugin installation instructions](https://code.visualstudio.com/docs/agent-customization/agent-plugins#install-a-plugin-from-source).

## Update an installed copy

Publishing a new version makes it available upstream. Your installed copy receives it when VS Code performs a plugin update.

For a plugin installed through **Chat: Install Plugin From Source**, run **Extensions: Check for Extension Updates** from the Command Palette and apply the update if prompted. VS Code also checks every 24 hours when `extensions.autoUpdate` is enabled.

If you installed through `/plugin install` in an Agent Host Copilot session, use `/plugin list` to find its installed identity, then `/plugin update <plugin>` in that same interface. The slash commands and Agent Customizations editor currently manage separate plugin inventories.

After updating, confirm version **1.1.0** and look for `run-unit-tests` in the skill list. See the [official update documentation](https://code.visualstudio.com/docs/agent-customization/agent-plugins#update-plugins).

## Use

Open your .NET project and ask the agent:

> Create unit tests for OrderService using the create-unit-tests skill. Follow the existing test framework and cover successful orders and invalid inputs.

To try the skill added in 1.1.0:

> Use the run-unit-tests skill to run the unit tests and summarize any failures.

Running generated tests requires a compatible .NET SDK and any package restore access needed by your project.

## Layout

The repository root is the plugin root, so installation requires no marketplace or subdirectory configuration.

```text
plugin.json
skills/
  create-unit-tests/
    SKILL.md
  run-unit-tests/
    SKILL.md
```

The manifest follows the [official Agent Plugins manifest format](https://agent-plugins.org/plugin-authors/manifest); the skill follows the [Agent Skills specification](https://agentskills.io/specification).

## License

MIT. See [LICENSE](LICENSE).
