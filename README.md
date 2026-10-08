# Agent Plugins demo

Two independently versioned [Agent Plugins](https://agent-plugins.org/) packages in one repository.

| Plugin | Version | Skills |
| --- | --- | --- |
| [dotnet](dotnet/) | 1.2.0 | `create-unit-tests`, `run-unit-tests` |
| [python](python/) | 1.0.0 | `test-fastapi` |

## Install in VS Code

Enable `chat.plugins.enabled`, then add this repository to your user settings as a plugin marketplace:

```json
{
  "chat.plugins.marketplaces": [
    "kaldren/agent-plugins-demo"
  ]
}
```

If you already have marketplaces configured, append this entry to the existing list.

Open the Extensions view, search for `@agentPlugins`, and install **dotnet**, **python**, or both from **agent-plugins-demo**. Each plugin is installed independently. See the [official VS Code marketplace instructions](https://code.visualstudio.com/docs/agent-customization/agent-plugins#configure-plugin-marketplaces).

For an Agent Host Copilot session, you can instead use:

```text
/plugin marketplace add https://github.com/kaldren/agent-plugins-demo
/plugin install dotnet@agent-plugins-demo
/plugin install python@agent-plugins-demo
```

The slash commands and Agent Customizations editor currently manage separate plugin inventories; manage each installation through the interface you used to install it.

### Migrating the previous installation

The repository root is now a marketplace; the .NET plugin moved into `dotnet/`. If you previously installed the repository URL directly with **Chat: Install Plugin From Source**, uninstall that old installation through the interface where you installed it, then install **dotnet** from the marketplace above. This avoids keeping duplicate installations. The two existing .NET skills are preserved.

## Use

In a .NET project:

> Use create-unit-tests to test OrderService using the existing test framework.

> Use run-unit-tests to run the unit tests and summarize failures.

In a Python FastAPI project:

> Use test-fastapi to test the items endpoint, including successful requests and invalid payloads.

Executing tests requires the project's .NET SDK or Python environment and its test dependencies.

## Independent versions and updates

Each plugin owns its version in its own `plugin.json`. For a release, bump only the changed plugin's version and the matching entry in `.claude-plugin/marketplace.json`. The other plugin's version stays unchanged. The manifest `$schema` selects Agent Plugins specification version 1.0.0 and is separate from each plugin's release version.

After publishing, run **Extensions: Check for Extension Updates** in VS Code and apply any update if prompted. In the slash-command interface, use `/plugin marketplace update agent-plugins-demo`, then `/plugin update dotnet@agent-plugins-demo` or `/plugin update python@agent-plugins-demo`. See the [official update documentation](https://code.visualstudio.com/docs/agent-customization/agent-plugins#update-plugins).

## Layout

```text
.claude-plugin/
  marketplace.json
dotnet/
  plugin.json
  LICENSE
  skills/
    create-unit-tests/SKILL.md
    run-unit-tests/SKILL.md
python/
  plugin.json
  LICENSE
  skills/
    test-fastapi/SKILL.md
```

The marketplace index points to each plugin directory. Each directory is a self-contained portable package with its own manifest, skills, and license.

## License

MIT. See [LICENSE](LICENSE).
