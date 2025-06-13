# Custom Microsoft Graph Connector Setup Guide

## 📘 Introduction

This guide provides best practices and step-by-step instructions for building custom Microsoft Graph connectors. It focuses on .NET as the primary language but includes notes for other Microsoft Graph SDK-supported languages: JavaScript, TypeScript, Python, Java, and Go.

---

## ✅ Prerequisites

- Azure subscription
- Access to Microsoft Entra ID (formerly Azure AD)
- .NET SDK installed (6.0+ recommended)
- Azure CLI or PowerShell
- Docker (for containerized deployments)
- Familiarity with Microsoft Graph API

---

## 🔐 App Registration in Microsoft Entra ID

1. **Register a new application**
   - Go to https://entra.microsoft.com/
   - Navigate to **App registrations** > **New registration**
   - Set a name and redirect URI (if applicable)

2. **Configure authentication**
   - Add a client secret or upload a certificate
   - Store credentials securely (e.g., Azure Key Vault)

3. **API Permissions**
   - Add Microsoft Graph permissions:
     - `Sites.Read.All`
     - `User.Read`
     - `Directory.Read.All`
   - Grant admin consent

4. **Best Practices**
   - Use certificate-based auth in production
   - Separate apps for dev/test/prod environments

---

## 🧱 Connector Architecture

### Components
- **Authentication**: Secure access to Graph API
- **Data Source**: External system or API
- **Schema Definition**: Define searchable fields
- **Indexer**: Push content to Microsoft Search

### Diagram (Textual)
