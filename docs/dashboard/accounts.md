---
id: accounts
title: Account Management
sidebar_label: Accounts
---

In an Elastic Path Commerce Cloud store, sellers can create accounts using Commerce Manager and view the purchase history and the addresses associated with an account.

## Creating Accounts

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.
1. Click **New Account**.
1. In the **Name** field, enter a name for the account.
1. In the **Legal name** field, enter a legal name of the account.
1. (Optional) In the **Registration ID** field, enter a unique registration ID for the account.
1. (Optional) In the **Parent ID** field, enter the registration ID of the parent account.
1. Click **Save**.

## Viewing Account Details

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.
    All accounts in the store are displayed.
1. To view details of an account, click the account name in the list.

    Account overview, account members associated with the account, purchase history of the account, and the addresses associated with the account are displayed in corresponding tabs.

### Viewing account members associated with an account

1. In Commerce Manager, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Account Members** tab.

    The name and email address of the account members are displayed.

### Adding account members to an account

1. In Commerce Manager, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Account Members** tab.
1. (Optional) To add a new account member to the system, click **Create Account Member**
1. Enter the following information:

    - **Name**: The name of the account member.
    - **Email**: The email of the account member.

1. Click **Save**.
1. In the account members page, search for the name of the account member in the search bar.
1. To add the account member to this account, click the **+** icon.

### Viewing purchase history of an account

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Purchase History** tab.

    The **Purchase History** tab displays the following information about each purchase:

    - **Date** : Specifies the date of the purchase.
    - **Customer** : Specifies the email address of the customer who made the purchase on behalf of the account.
    - **Items** : Specifies the number of items purchased.
    - **Total** : Specifies the total amount of the purchase.
    - **Payment** : Specifies the status of the payment for the purchase, such as **unpaid**, **authorized**, **paid**, or **refunded**.
    - **Shipping** : Specifies the status of the shipment of the purchase, such as **fulfilled** or **unfulfilled**.
    - **Status** : Specifies the status of the order, such as **incomplete** or **complete**.

    When you click on a listing in the purchase history, the [**View order**](orders.md) page is displayed. You can manage the orders by updating details, such as, shipping address, shipping status, and payment status.

### Viewing addresses associated with an account

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Address Book** tab.

    A list of names in each address are displayed.

### Adding addresses to an account

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Address Book** tab.
1. To add a new address, click a **Add a new address**.

    The **Add New Address** window is displayed.
1. Enter the following information:

    - (Optional) **Name**: The name with which the address is saved.
    - **First name**: The first name of the recipient on this address.
    - **Last name**: The last name of the recipient on this address.
    - (Optional) **Phone number**: A phone number for the address.
    - (Optional) **Company name**: The company name for the address, if any.
    - **Line 1**: The first line of the address, such as the street address.
    - (Optional) **Line 2**: The second line of the address, such as an apartment or unit number.
    - **Postcode**: The ZIP Code, postcode, or other postal reference numbers for the address.
    - (Optional) **City**: The city for the address.
    - **County**: The province for the address.
    - **Country**: The country for the address.
    - (Optional) **Instructions**: Any delivery instructions for the address.

1. Click **Save**.

### Editing addresses associated with an account

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Address Book** tab.

    A list of names in each address are displayed.
1. To edit the details of an address, do one of the following:

      - Click a name.
      - In the address list, click the **...** icon next to the address name and click **Edit**.

      The **Edit Address** window is displayed.

1. Update the details as required.
1. Click **Save**.

### Deleting addresses associated with an account

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the account name in the list.
1. In the account details page, click the **Address Book** tab.

    A list of names in each address are displayed.
1. To delete an address, click the **...** icon next to the address name and click **Delete**.

## Deleting Accounts

1. In the **Commerce Manager Home** page, go to **Store > Accounts**.

    All accounts in the store are displayed.
1. Click the **...** icon next to the account name in the list and click **Delete**.

## Related Topics

### Concepts

- [Account Management](../concepts/account_management.md)

### APIs

- [Accounts](../api/customers-and-accounts/account-management/accounts/index.md)
- [Account Members](../api/customers-and-accounts/account-management/account-members/index.md)
- [Account Memberships](../api/customers-and-accounts/account-management/account-memberships/index.md)
