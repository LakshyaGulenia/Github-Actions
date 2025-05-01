# GitHub-Actions-Zero-to-Hero
Repository to kick start your journey with GitHub Actions

## Comparing with Jenkins 

### Advantages of GitHub Actions over Jenkins

- Hosting: Jenkins is self-hosted, meaning it requires its own server to run, while GitHub Actions is hosted by GitHub and runs directly in your GitHub repository.

- User interface: Jenkins has a complex and sophisticated user interface, while GitHub Actions has a more streamlined and user-friendly interface that is better suited for simple to moderate automation tasks.

- Cost: Jenkins can be expensive to run and maintain, especially for organizations with large and complex automation needs. GitHub Actions, on the other hand, is free for open-source projects and has a tiered pricing model for private repositories, making it more accessible to smaller organizations and individual developers.

### Advantages of Jenkins over GitHub Actions

- Integration: Jenkins can integrate with a wide range of tools and services, but GitHub Actions is tightly integrated with the GitHub platform, making it easier to automate tasks related to your GitHub workflow.

In conclusion, Jenkins is better suited for complex and large-scale automation tasks, while GitHub Actions is a more cost-effective and user-friendly solution for simple to moderate automation needs.

# 🏃 GitHub Actions Runners - Explained

## ❓ What is a Runner?

A **runner** is a machine (virtual or physical) that listens for GitHub Actions jobs and executes them. Runners are responsible for running the workflows defined in `.github/workflows` directory of your repository.

There are two types of runners you can use in GitHub Actions:
- ✅ **GitHub-Hosted Runner**
- 🔧 **Self-Hosted Runner**

---

## ⚖️ GitHub-Hosted vs Self-Hosted Runners

| Feature                     | GitHub-Hosted Runner                            | Self-Hosted Runner                              |
|----------------------------|--------------------------------------------------|--------------------------------------------------|
| **Managed By**             | GitHub                                           | You (your organization/server)                  |
| **Setup Required**         | No setup needed                                 | You install and maintain it                     |
| **Billing**                | Free minutes (limits vary by plan)              | No GitHub cost, but infra cost applies          |
| **Performance**            | Shared environment, fresh VM for each job       | Faster if pre-configured with tools/cache       |
| **Customization**          | Limited; install dependencies each run          | Full control over tools and environment         |
| **Security Control**       | GitHub's environment                            | More secure in private networks                 |
| **Scalability**            | Automatically scales                            | Manual setup for scaling                        |

---

## 💡 When to Use What?

### ✅ GitHub-Hosted Runner
- No setup overhead
- For small/medium projects
- When tools change frequently or don't need persistence
- Best for getting started quickly

### 🔧 Self-Hosted Runner
- Need specific software or persistent tools/cache
- Faster builds by avoiding reinstallation
- Lower cost at scale
- Full control and security in enterprise environments

---

## 🛠️ Setting Up a Self-Hosted Runner (Overview)

1. Go to your GitHub repository → **Settings** → **Actions** → **Runners**
2. Click **Add Runner**
3. Choose your OS and architecture
4. Follow the given commands to:
   - Download the runner
   - Configure it with a token
   - Start the runner

You can now reference this runner in your workflow YAML using:

```yaml
runs-on: self-hosted


