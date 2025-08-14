---
post_title: "Credit Card Fraud Detection with Azure ML and .NET"
author1: "AI Copilot"
post_slug: "ghcp-dotnet"
microsoft_alias: "aicopilot"
featured_image: ""
categories: ["machine-learning", "dotnet", "azure"]
tags: ["fraud-detection", "credit-card", "azureml", "dotnet", "ai"]
ai_note: true
summary: "A .NET 9.0 console app that demonstrates credit card fraud detection using both local rule-based logic and Azure Machine Learning integration."
post_date: 2025-07-23
---

## Overview

> [!TIP]
> This project is a reference implementation for credit card fraud detection using .NET and Azure Machine Learning. It combines local rule-based detection with cloud-based AI for robust, real-world scenarios.

## Features

- Detects fraudulent credit card transactions using:
  - Local rule-based logic
  - Azure Machine Learning endpoint (customizable)
- Markdown-formatted reasoning for each detection method
- Easy to extend with new rules or ML models
- .NET 9.0, C# top-level statements

## Getting Started

### Prerequisites

- [.NET 9.0 SDK](https://dotnet.microsoft.com/download)
- An [Azure Machine Learning endpoint](https://learn.microsoft.com/azure/machine-learning/) (optional, for cloud-based detection)

### Setup

1. Clone the repository:
   ```sh
   git clone https://github.com/your-org/ghcp-dotnet.git
   cd ghcp-dotnet
   ```
2. Build the project:
   ```sh
   dotnet build
   ```
3. (Optional) Configure your Azure ML endpoint and API key in `Program.cs`:
   ```csharp
   string azureEndpoint = "https://<your-ml-endpoint>.azurewebsites.net/score";
   string apiKey = "<your-api-key>";
   ```
4. Run the app:
   ```sh
   dotnet run
   ```

## How It Works

- **Local Rule-Based Detection:**
  - Flags transactions over $10,000, unknown locations, or those between 2am-4am as potentially fraudulent.
- **Azure ML Detection:**
  - Sends transaction data to an Azure ML endpoint for AI-based fraud prediction.
- Both methods output markdown-formatted reasoning to the console for transparency.

## Example Output

```text
Local Rule-Based Fraud Detection Reasoning:
- **Transaction Features:**
    - Amount: $15,000.00
    - Location: New York
    - Timestamp: 2025-07-23 14:30
    - Card Number: ************3456
- **Detection Logic:**
    - Rule-based: Flags transactions over $10,000, unknown locations, or those between 2am-4am as potentially fraudulent.
- **Reasoning:**
    - Amount exceeds $10,000: Yes
    - Location is 'Unknown': No
    - Time between 2am-4am: No
- **Conclusion:**
    - This transaction is fraudulent.
```

## Customization

- Add or modify rules in `FraudDetector.IsFraudulent` for local detection.
- Update the Azure ML endpoint and payload as needed for your ML model.

## Resources

- [Azure Machine Learning Documentation](https://learn.microsoft.com/azure/machine-learning/)
- [.NET Documentation](https://learn.microsoft.com/dotnet/)

> [!NOTE]
> This project is for educational and demonstration purposes. For production use, ensure compliance with security and privacy best practices.
