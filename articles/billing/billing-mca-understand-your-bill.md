---
title: Understand the charges on your Microsoft Customer Agreement's invoice - Azure| Microsoft Docs
description: Learn how to read and understand the charges on your invoice
services: ''
documentationcenter: ''
author: jureid
manager: jureid
editor: ''
tags: billing

ms.assetid: 32eea268-161c-4b93-8774-bc435d78a8c9
ms.service: billing
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/19/2019
ms.author: banders

---
# Understand the charges on your Microsoft Customer Agreement's invoice

You can reconcile the charges on your invoice by analyzing the individual transactions on the invoice.

In the billing account for a Microsoft Customer Agreement, an invoice is generated each month for every billing profile. The invoice includes all charges from the previous month. You can view your invoices in the Azure portal. For more information, see [View and download your Microsoft Azure invoice](billing-download-azure-invoice.md).

This article applies to a billing account for a Microsoft Customer Agreement. [Check if you have access to a Microsoft Customer Agreement](#check-access-to-a-microsoft-customer-agreement).

## View transactions for an invoice in the Azure portal

1. Sign in to the [Azure portal](https://www.azure.com).

2. Search on **Cost Management +Billing**.

    ![Screenshot that shows Azure portal search for cost management + billing](./media/billing-understand-your-bill-mca/billing-search-cost-management-billing.png)

3. Select **All transactions** from the left side of the screen. Depending on your access you may have to select a billing account or a billing profile, then select **All transactions**.

4. The All transactions page displays the following information:

    ![Screenshot that shows the billed transactions list](./media/billing-understand-your-bill-mca/mca-billed-transactions-list.png)

    |Column  |Definition  |
    |---------|---------|
    |Date     | The date of transaction  |
    |Invoice ID     | The identifier for the invoice on which the transaction got billed. If you submit a support request, share the ID with Azure support to expedite your support request |
    |Transaction type     |  The type of transaction like purchase, cancel, and usage charges  |
    |Product family     | The category of product like compute for Virtual machines or database for Azure SQL database|
    |Product sku     | A unique code identifying the instance of your product |
    |Amount     |  The amount of transaction      |
    |Invoice section     | The transaction shows up on this section of billing profile's invoice |
    |Billing profile     | The transaction shows up on this billing profile's invoice |

5. Search on invoice ID to filter the transactions for the invoice.

### View transactions by invoice sections

Invoice sections let you organize the costs on a billing profile's invoice. For more information, see [Understand invoice section](billing-mca-overview.md#understand-invoice-sections). When an invoice is generated, charges for all the sections  in the billing profile show up on the invoice.

The following image shows the charges for IT Department invoice section on a sample invoice.

![Example image showing the details by invoice section information](./media/billing-understand-your-bill-mca/invoicesection-details.png)

Once you have identified the charges for an invoice section, you can view the transactions in the Azure portal to reconcile the charges.

1. Go to the All transactions page in the Azure portal to view transactions for an invoice. For more information, see [View transactions for an invoice in the Azure portal](#view-transactions-for-an-invoice-in-the-azure-portal).

2. Filter by invoice section name to view transactions for the invoice section.

## Understand pending charges to estimate your next invoice

In the billing account for a Microsoft Customer Agreement, until the charges are invoiced, they are estimate and considered pending. They are finalized and considered billed when they show on the invoice. You can view pending charges for a billing profile to estimate the charges on your next invoice.

### View charges summary

1. Sign in to the [Azure portal](https://www.azure.com).

2. Search on **Cost Management +Billing**.

   ![Screenshot that shows Azure portal search for cost management + billing](./media/billing-understand-your-bill-mca/billing-search-cost-management-billing.png)

3. Select a billing profile. Depending on your access, you may have to select a billing account. From the billing account, select **Billing profiles** then select a billing profile.

4. Select **Summary** tab from the top of the screen.

5. The charges section display the month-to-date and last month's charges.

   ![Screenshot that shows Azure portal search for cost management + billing](./media/billing-understand-your-bill-mca/mca-billing-profile-summary.png)

The month-to-date charges are the pending charges for the current month and are billed when the invoice is generated for the month. If the invoice for last month is still not generated, then last month's charges are also pending.

### View pending transactions

Once you identify pending charges, you can view individual transactions that contribute to the charges in the All transactions page. At this point, pending usage charges are not displayed on the All transaction page. You can view the pending usage charges on the Azure subscriptions page. For more information, see [View pending usage charges](#view-pending-usage-charges)

1. Sign in to the [Azure portal](https://www.azure.com).

2. Search on **Cost Management +Billing**.

   ![Screenshot that shows Azure portal search for cost management + billing](./media/billing-understand-your-bill-mca/billing-search-cost-management-billing.png)

3. Select a billing profile. Depending on your access, you may have to select a billing account. From the billing account, select **Billing profiles** then select a billing profile.

4. Select **All transactions** from the left side of the screen.

5. Search for **pending**. Use the **Timespan** filter to view pending charges for current or last month.

   ![Screenshot that shows the pending transactions list](./media/billing-understand-your-bill-mca/mca-pending-transactions-list.png)

### View pending usage charges

1. Sign in to the [Azure portal](https://www.azure.com).

2. Search on **Cost Management +Billing**.

   ![Screenshot that shows Azure portal search for cost management + billing](./media/billing-understand-your-bill-mca/billing-search-cost-management-billing.png)

3. Select a billing profile. Depending on your access, you may have to select a billing account. From the billing account, select **Billing profiles** then select a billing profile.

4. Select **All subscriptions** from the left side of the screen.

5. The Azure subscriptions page displays current and last month's charges for each subscription in the billing profile. The month-to-date charges are the pending charges for the current month and are billed when the invoice is generated for the month. If the invoice for last month is still not generated, then last month's charges are also pending.

    ![Screenshot that shows the Azure subscriptions list for billing profile](./media/billing-understand-your-bill-mca/mca-billing-profile-subscriptions-list.png)

You can view the detailed usage charges using the Azure usage and charges file. For more information, see the next section.

## Analyze your Azure usage charges

Use the Azure usage and charges csv file to analyze your usage based charges. You can download the file either for an invoice or for pending charges. For more information, see [Get your Azure billing invoice and daily usage data](billing-download-azure-invoice-daily-usage-date.md).

### View detailed usage by invoice section

You can filter the Azure usage and charges file to reconcile the usage charges for your invoice sections.

The following steps walk you through reconciling compute charges for the Accounting Dept invoice section:

![Example image showing the details by invoice section information](./media/billing-understand-your-bill-mca/invoicesection-details.png)

 | Invoice PDF | Azure usage and charges CSV |
 | --- | --- |
 |IT Department |invoiceSectionName |
 |Usage Charges - Azure Standard |productOrderName |
 |Storage |serviceFamily |

1. Filter the **invoiceSectionName** column in the CSV file to **Accounting Dept**.
2. Filter the **productOrderName** column in the CSV file to **Microsoft Azure Plan**.
3. Filter the **serviceFamily** column in the CSV file to **Microsoft.Compute**.

![Screenshot that shows the usage and charges file filtered by invoice section](./media/billing-understand-your-bill-mca/billing-usage-file-filtered-by-invoice-section.png)

<!--Todo Add screenshot of usage file -->

### View detailed usage by subscription

You can filter the Azure usage and charges csv file to reconcile usage charges for your subscriptions. To view all subscriptions in a billing profile, see [View pending usage charges](#view-pending-usage-charges).

Once you identify charges for a subscription, use the Azure usage and charges csv file to analyze the charges.

The following screenshot displays the list of subscriptions in the Azure portal.

![Screenshot that shows the Azure subscriptions list for billing profile](./media/billing-understand-your-bill-mca/mca-billing-profile-subscriptions-list-highlighted.png)

Filter the **subscriptionName** column in the Azure usage and charges CSV file to **WA_Subscription** to view the detailed usage charges for WA_Subscription.

![Screenshot that shows the usage and charges file filtered by subscription](./media/billing-understand-your-bill-mca/billing-usage-file-filtered-by-subscription.png)

## Pay your bill

Instructions for paying your bill are shown at the bottom of the invoice. [Learn how to pay](billing-mca-understand-your-invoice.md#how-to-pay).

If you've already paid your bill, you can check the status of the payment on the Invoices page in the Azure portal. 

## Check access to a Microsoft Customer Agreement
[!INCLUDE [billing-check-mca](../../includes/billing-check-mca.md)]

## Need help? Contact us

If you have questions or need help, [create a support request](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest).

## Next steps

To learn more about your invoice and detailed usage, see:

- [How to get your Azure billing invoice and daily usage data](billing-download-azure-invoice-daily-usage-date.md)
- [Understand terms on your Microsoft Customer Agreement invoice](billing-mca-understand-your-invoice.md)
- [Understand terms on your Microsoft Customer Agreement usage CSV](billing-mca-understand-your-usage.md)
