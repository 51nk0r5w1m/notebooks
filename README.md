# Notebooks Repository

This repository contains Jupyter notebooks for PowerShell automation and incident response using .NET Interactive.

## Notebooks

### 1. dotnet-powershell-sample.ipynb

A comprehensive sample notebook demonstrating basic PowerShell usage with the .NET Interactive kernel.

**Topics covered:**
- Basic PowerShell commands
- Variables and objects
- PowerShell pipeline operations
- .NET integration
- Functions and error handling
- Arrays and hash tables

**Prerequisites:**
- .NET Interactive installed
- PowerShell kernel available

**Usage:**
```bash
# Open with Jupyter
jupyter notebook dotnet-powershell-sample.ipynb

# Or with VS Code
code dotnet-powershell-sample.ipynb
```

### 2. m365-email-compromised.ipynb

An incident response playbook for investigating and remediating compromised Microsoft 365 mailboxes. This notebook uses app-only authentication for automated/unattended execution.

**Topics covered:**
- App-only authentication to Microsoft Graph
- User and sign-in activity analysis
- Mailbox audit log review
- Inbox rule examination
- OAuth application consent review
- Remediation actions (session revocation, password reset, etc.)
- MFA verification
- Incident report generation

**Prerequisites:**
- Microsoft Graph PowerShell SDK: `Install-Module Microsoft.Graph -Scope CurrentUser`
- Azure AD App Registration with appropriate permissions:
  - `User.Read.All`
  - `AuditLog.Read.All`
  - `Directory.Read.All`
  - `Mail.Read`
- Exchange Online PowerShell (for mailbox-specific operations)
- Client ID, Tenant ID, and Client Secret (or Certificate)

**Security Notes:**
- ⚠️ **NEVER commit secrets to source control**
- Store credentials in Azure Key Vault, environment variables, or secure files
- Restrict access to the notebook and execution environment
- Use certificate-based authentication in production
- Review and test all remediation commands before executing

**Usage:**
1. Configure authentication parameters in the first code cell
2. Update the compromised user email address
3. Execute cells sequentially to investigate
4. Review findings carefully before executing remediation actions
5. Uncomment and execute containment actions as needed

## Setup

### Installing .NET Interactive

```bash
# Install .NET SDK (6.0 or later)
# Download from: https://dotnet.microsoft.com/download

# Install .NET Interactive
dotnet tool install -g Microsoft.dotnet-interactive

# Install Jupyter kernel
dotnet interactive jupyter install
```

### Verify Installation

```bash
# List available kernels
jupyter kernelspec list

# Should show .net-powershell among other kernels
```

## Running Notebooks

### Option 1: Jupyter Notebook

```bash
jupyter notebook
```

### Option 2: JupyterLab

```bash
jupyter lab
```

### Option 3: VS Code

1. Install the Jupyter extension
2. Open the `.ipynb` file
3. Select the PowerShell kernel
4. Run cells interactively

## Repository Structure

```
.
├── README.md                           # This file
├── dotnet-powershell-sample.ipynb      # PowerShell basics and examples
└── m365-email-compromised.ipynb        # M365 incident response playbook
```

## Contributing

Contributions are welcome! Please ensure:
- Code follows PowerShell best practices
- Notebooks are well-documented with markdown cells
- Sensitive information is never committed
- Changes are tested before submission

## License

This repository is provided as-is for educational and incident response purposes.

## Resources

- [.NET Interactive Documentation](https://github.com/dotnet/interactive)
- [Microsoft Graph PowerShell SDK](https://learn.microsoft.com/en-us/powershell/microsoftgraph/)
- [M365 Security Best Practices](https://learn.microsoft.com/en-us/microsoft-365/security/)
- [PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/)

## Support

For issues or questions, please open an issue in the repository.
