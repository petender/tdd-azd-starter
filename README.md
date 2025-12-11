# [YOUR-SCENARIO-NAME]

<!-- CONTRIBUTOR: Replace [YOUR-SCENARIO-NAME] with your project title (e.g., "Azure Functions with Event Hub Integration") -->
<!-- CONTRIBUTOR: Write 1-2 sentences describing what gets deployed and the target audience -->

This is a starter template for creating Azure Developer CLI (azd) compatible templates for the **[Trainer Demo Deploy Catalog](https://aka.ms/trainer-demo-deploy)**. Replace this description with your scenario overview.

💪 This template scenario is part of the larger **[Microsoft Trainer Demo Deploy Catalog](https://aka.ms/trainer-demo-deploy)**. 

## 📋 What You'll Deploy

<!-- CONTRIBUTOR: List all Azure resources with SKU types and estimated costs -->

This starter template includes:
- Resource Group
- [Add your resources here]

**Estimated Cost:** $X-Y per day  
<!-- CONTRIBUTOR: Use Azure Pricing Calculator and provide realistic estimates -->

## 🏗️ Architecture

<!-- CONTRIBUTOR: Add diagram and explain data flow, security boundaries -->

```
[Add architecture diagram here]
```

## ⏰ Deployment Time

Approximately **15-20 minutes**  
<!-- CONTRIBUTOR: Update with realistic time estimate after testing -->

## ⬇️ Prerequisites

Before deploying this template, ensure you have:

- **Azure Subscription** with Owner or Contributor access
- **[Azure Developer CLI (azd)](https://learn.microsoft.com/azure/developer/azure-developer-cli/install-azd)** installed
  - Installing azd will also install: GitHub CLI, Bicep CLI
- Additional prerequisites listed in [prereqs.md](prereqs.md)

## 🚀 Quick Start

Deploy this template using three simple commands:

1. **Initialize the project**
   ```bash
   azd init -t petender/tdd-azd-starter
   ```

2. **Provision and deploy to Azure**
   ```bash
   azd up
   ```

3. **Clean up resources when finished**
   ```bash
   azd down
   ```

## 🎯 What You'll Demonstrate

<!-- CONTRIBUTOR: Add clear step-by-step demo instructions for trainers -->

After deployment, you can demonstrate:
1. [Add demo steps here]
2. [Add more steps]

## ✅ Verification Steps

<!-- CONTRIBUTOR: Add specific steps to verify successful deployment -->

To verify the deployment:
1. Navigate to the Azure Portal
2. Locate the resource group: `rg-<your-environment-name>`
3. Verify all resources are created and running
4. [Add your specific checks here]

## 🔧 Troubleshooting

<!-- CONTRIBUTOR: Add common issues and solutions for your scenario -->

**Issue:** [Describe common problem]  
**Solution:** [Your solution]

## 💰 Cost Management

<!-- CONTRIBUTOR: Add cost optimization tips specific to your resources -->

To minimize costs:
- Use `azd down` to delete resources when not in use
- Consider using lower-tier SKUs for demos
- Monitor costs in Azure Cost Management

## 🧹 Clean Up

To remove all deployed resources:

```bash
azd down
```

This will delete the resource group and all contained resources.

## 🤝 Contributing

Interested in contributing your template to the catalog? See [CONTRIBUTING.md](CONTRIBUTING.md) and the [catalog contribution guide](https://microsoftlearning.github.io/trainer-demo-deploy/docs/contribute).

## 📄 License

<!-- CONTRIBUTOR: Add appropriate license (typically MIT for TDD templates) -->

This project is licensed under the MIT License.


 
