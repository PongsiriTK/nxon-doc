# Billing and Cost Management

## Overview

{{ user_name }}'s Billing and Cost Management is designed to provide users with a transparent, flexible, and cost-effective way to manage their expenses. The platform offers a range of billing options and strategies to help you control costs and maximize resource utilization effectively.

![Billing section ](features/images/{{ resource_dir_name }}/billing/user_billing.png)

### Billing Options

{{ user_name }} offers flexible billing options to help users control costs and improve resource utilization.

- **Pay-as-you-go**: Users pay only for the resources they actually use, without the need for upfront payments, offering flexibility and convenience.

### Billing Logic

- **GPU Pod**: Billed based on usage duration. Parameters include resource rate, discount, and usage duration.
- **BareMetal Cluster**: Billed based on usage duration with rental periods measured in weeks.
- **Serverless API**: Billed based on the number of input/output tokens and the number of API calls, with optional performance quotas.
- **Object Storage and Parallel File System Storage**: Billed based on capacity and duration.

![Billing Overview](features/images/{{ resource_dir_name }}/billing/billing_overview.png)


### Bill Management

{{ user_name }} provides bill management features for easy viewing and management of billing information.

| Feature          | Description                                                  |
|-----------------|-------------------------------------------------------------|
| Bill Generation  | Regularly generates bills listing resource usage and costs.  |
| Bill Inquiry    | Users can download bills for cost analysis and control.    |
| Cost Analysis  | Offers tools to understand cost composition and optimize expenses. |

### Payment Methods

{{ user_name }} supports multiple payment methods to ensure users can conveniently manage their accounts.

| Method          | Description                                                  |
|---------------|-------------------------------------------------------------|
| Credit Card     | Supports binding credit cards for payments.              |
| Bank Transfer  | For large payments, bank transfers are required.                |

### Consumption Reminders

{{ user_name }} provides consumption reminder mechanisms to ensure users are promptly informed about their payment status and account balance.

- **Payment Reminders**: Sent immediately after bill generation or reaching a threshold.

### Risk Control

{{ user_name }} implements risk control measures to protect users' payment security and account health.

- **Payment Risk Control**: Bank transfers required for large payments.
- **Credit Card Risk Monitoring**: Real-time monitoring of credit card status.

### Refund Processing

{{ user_name }} provides a transparent refund policy to ensure users can receive appropriate refunds when needed.

- **Bill Cycle Control**: Reconciliation should be completed within 7 working days after receiving the bill.

### Late Payment Handling

{{ user_name }} takes reasonable measures for overdue accounts, including service suspension and late fees.

### Tips

!!! tip
    Regularly check bills and credit balances to avoid service interruptions.

!!! note
    Ensure that credit card information is accurate to prevent payment failures.

![Billing Details](features/images/{{ resource_dir_name }}/billing/billing_details.png)

### Next Steps

To ensure your account remains in good standing and to comply with all relevant regulations, proceed to the [Security and Compliance](security.md) section for more information on how to secure your account and data.