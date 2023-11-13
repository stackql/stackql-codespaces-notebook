[![StackQL](https://stackql.io/img/stackql-logo-bold.png)](https://stackql.io/)  
<br />
[![GitHub Actions](https://github.com/stackql/stackql-codespaces-notebook/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/stackql/stackql-codespaces-notebook/actions/workflows/main.yml)
![License](https://img.shields.io/github/license/stackql/stackql)

# stackql-codespaces-notebook

This repository serves as a template for setting up a development environment for StackQL using GitHub Codespaces. Follow the instructions below to get started.

> **Note**
> 
> **What is StackQL?** [__StackQL__](https://github.com/stackql/stackql) is a SQL based framework to query and manage resources across different cloud and SaaS providers. It allows you to treat your cloud assets and configuration as data, where you can write queries to fetch information, modify resources, and streamline cloud operations.
> 
> **Why use StackQL?** With StackQL, you can simplify the complexity of cloud management by using a familiar SQL-like language, making it easier to perform tasks such as data analysis, resource auditing, and automated deployments across various cloud platforms. This template sets you up with a pre-configured environment to explore and utilize StackQL in GitHub Codespaces.

---

## How to Use This Template

1. Click the "Use this template" button on the GitHub repository page to create a new repository based on this template.
2. Clone your new repository to your local machine or open it directly in GitHub Codespaces.

## Setting Up Codespaces

1. Navigate to the "Secrets" section of your repository settings.
2. Add the necessary provider authentication variables (for detailed instructions, visit the [StackQL Provider Registry docs](https://registry.stackql.io/)).
3. Open the `.devcontainer/devcontainer.json` file and edit the `containerEnv` section to include your secret keys:

```json
{
  "image": "mcr.microsoft.com/devcontainers/universal:2",
  "containerEnv": {
    "STACKQL_GITHUB_PASSWORD": "${{ secrets.STACKQL_GITHUB_PASSWORD }}",
    "STACKQL_GITHUB_USERNAME": "${{ secrets.STACKQL_GITHUB_USERNAME }}"
  },  
  "hostRequirements": {
    "cpus": 2
  },
  "waitFor": "onCreateCommand",
  "updateContentCommand": "python3 -m pip install -r requirements.txt",
  "postCreateCommand": "",
  "customizations": {
    "codespaces": {
      "openFiles": []
    },
    "vscode": {
      "extensions": [
        "ms-toolsai.jupyter",
        "ms-python.python"
      ]
    }
  }
}
```

## Creating and Running Notebooks

1. To add new providers or use cases, create new notebook files in the `notebooks` directory. Use `stackql.ipynb` for instructions and `github.ipynb` as an example.
2. To start the Codespaces environment, click the "Code" button on your repository page and select "Open with Codespaces".
3. To stop your Codespace, you can simply close the browser tab or through the GitHub Codespaces dashboard.

## Contributing

Contributions are what make the open-source community such a fantastic place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

Please see `CONTRIBUTING.md` for details on our code of conduct, and the process for submitting pull requests to us.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

For questions, feedback, or if you need any help, here are two ways you can reach out to the StackQL community and team:

- **GitHub Discussions:** Share your ideas, ask questions, and connect with the community. Visit our [GitHub Discussions](https://github.com/orgs/stackql/discussions) to start a conversation.
- **Discord:** Join our Discord server for real-time chat with the community and team. Click here to [join our Discord](https://discord.com/invite/xVXZ9d5NxN).

We look forward to hearing from you and seeing what you build with StackQL!
