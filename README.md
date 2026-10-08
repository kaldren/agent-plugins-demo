# dotnet

A single [Agent Plugins 1.0](https://agent-plugins.org/) plugin with one skill, `create-unit-tests`, for creating .NET unit tests.

The skill follows existing project conventions for xUnit, NUnit, or MSTest, covers relevant behaviors and boundaries, and runs the tests when the .NET SDK is available.

## Install in VS Code

1. Enable agent plugins in VS Code (`chat.plugins.enabled`).
2. Open the Command Palette and run **Chat: Install Plugin From Source**.
3. Enter this repository URL:

   ```text
   https://github.com/kaldren/agent-plugins-demo
   ```

See the [official VS Code plugin installation instructions](https://code.visualstudio.com/docs/agent-customization/agent-plugins#install-a-plugin-from-source).

## Use

Open your .NET project and ask the agent:

> Create unit tests for OrderService using the create-unit-tests skill. Follow the existing test framework and cover successful orders and invalid inputs.

Running generated tests requires a compatible .NET SDK and any package restore access needed by your project.

## Layout

The repository root is the plugin root, so installation requires no marketplace or subdirectory configuration.

```text
plugin.json
skills/
  create-unit-tests/
    SKILL.md
```

The manifest follows the [official Agent Plugins manifest format](https://agent-plugins.org/plugin-authors/manifest); the skill follows the [Agent Skills specification](https://agentskills.io/specification).

## License

MIT. See [LICENSE](LICENSE).
