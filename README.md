# Paul's VS Code Remote Development configs

This is a collection of **VSCode Remote Development - Containers** configurations for projects that I contribute to on GitHub. 

- [hashicorp/consul-k8s](https://github.com/hashicorp/consul-k8s)
- [kubernetes/release](https://github.com/kubernetes/release)

Replace the `{REPLACE_THIS_WITH_WORKSPACE_MOUNT_SRC}` value with the hardcoded value of your source code working folder. This path must be of the form `/path/on/host/`.

You can use the following PowerShell to convert a Windows path to the correct format:

```powershell
$PWD.Path.Replace('\','/').Replace('C:','/c').toLower()
```

# VS Code Remote Development

[Visual Studio Code Remote Development](https://code.visualstudio.com/docs/remote/remote-overview) allows you to use a container, remote machine, or the Windows Subsystem for Linux (WSL) as a full-featured development environment. You can:

- Develop on the **same operating system** you deploy to or use **larger or more specialized** hardware.
- **Sandbox** your development environment to avoid impacting your **local machine configuration**.
- Make it easy for new contributors to **get started** and keep everyone on a **consistent environment**.
- Use tools or runtimes **not available** on your local OS or manage **multiple versions** of them.
- Develop your Linux-deployed applications using the **Windows Subsystem for Linux**.
- Access an **existing** development environment from **multiple machines or locations**.
- Debug an **application running somewhere else** such as a customer site or in the cloud.

**No source code** needs to be on your local machine to get these benefits. Each extension in the [Remote Development extension pack](https://aka.ms/vscode-remote/download/extension) can run commands and other extensions directly inside a container, in WSL, or on a remote machine so that everything feels like it does when you run locally.

![VSCode Remote Development](https://code.visualstudio.com/assets/docs/remote/remote-overview/architecture.png)

# Developing inside a Container

The [Visual Studio Code Remote - Containers](https://code.visualstudio.com/docs/remote/containers) extension lets you use a Docker container as a full-featured development environment. It allows you to open any folder inside (or mounted into) a container and take advantage of VS Code's full feature set. A `devcontainer.json` [file](https://code.visualstudio.com/docs/remote/containers#_creating-a-devcontainerjson-file) in your project tells VS Code how to access (or create) a **development container** with a well-defined tool and runtime stack. This container can be used to run an application or to sandbox tools, libraries, or runtimes needed for working with a codebase.

Workspace files are mounted from the local file system or copied or cloned into the container. Extensions are installed and run inside the container, where they have full access to the tools, platform, and file system. This means that you can seamlessly switch your entire development environment just by connecting to a different container.

![VSCode Remote Development - Containers](https://code.visualstudio.com/assets/docs/remote/containers/architecture-containers.png)

This lets VS Code provide a **local-quality development experience** — including full IntelliSense (completions), code navigation, and debugging — **regardless of where your tools (or code) is located**.