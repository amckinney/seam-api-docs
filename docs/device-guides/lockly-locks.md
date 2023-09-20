---
description: Guide for using Lockly locks with Seam
---

# Lockly Locks

## Overview

Seam integrates with Lockly smart locks. With a focus on security, Lockly smart locks work with a vast array of door types, such as traditional deadbolts, latch bolts, and patio doors. In addition, Lockly smart locks support offline access codes that you can issue when you are not connected to your Lockly lock. Further, you can issue these offline access codes with a validity period.

***

## Supported Devices

This integration supports [all Lockly smart locks](https://lockly.com/collections/door-lock).

{% @seam-gitbook-plugin-v2/seam-component content="<seam-supported-device-table
  endpoint="https://connect.getseam.com"
  client-session-token="seam_cst126DAjfor_2kxn8QAAEUkj3Zu4Nr1Aoauy"
  brands='["lockly"]'
/>" %}

We support the following features:

* [Triggering web lock and unlock actions](../products/smart-locks/lock-and-unlock.md)
* [Programming access codes](../products/smart-locks/access-codes/) on locks that have a keypad

***

## Set Up Instructions

1. Download and create an account for the [Lockly mobile app](https://lockly.com/pages/download-lockly-app) if you have not done so already.
2. In the Lockly mobile app, set up each of your Lockly locks as follows:
   1. Click the card for the lock.
   2. In the lower, right corner, click **Settings**.
   3. Click **Sync with LocklyOS**, and then enable **Sync with LocklyOS**.
3. In a web browser, navigate to the [Lockly Access Portal](https://lap.lockly.com/lap/index.html#/login) (LAP) and log in with your Lockly mobile app credentials.
4. Purchase a plan that suits your needs.
5. Email [support@lockly.com](mailto:support@lockly.com) to enable API access for your LAP account.
6. In the left-hand navigation pane of the Lockly Access Portal, click **Account** > **User Management**.
7. Click **Add Account**.
8.  Specify the following values to configure the new user account:

    1. In the **Credential Type** field, select **Access Key - Programmatic access**.
    2. In the **User Name** field, type a descriptive name, such as **Seam Integration**.
    3. In the **Property** field, select all the properties to which you want the Seam application to have access.
    4. In the **Role** field, select **Property And Room (Read & Write)**, **Doorlock (Read & Write)**, and **API EBadge Admin**.
    5. In the **Validity Period** field, select **Permanent**.

    <figure><img src="../.gitbook/assets/lockly-access-portal-add-account.png" alt="Create a user account in the Lockly Access portal." width="563"><figcaption></figcaption></figure>
9.  Click **Confirm**.\
    The Lockly Access Portal creates the new account and displays the following information:

    <figure><img src="../.gitbook/assets/lockly-access-portal-account-created-successfully.png" alt="Note the information for the newly-created user account." width="563"><figcaption></figcaption></figure>
10. Make note of the client ID, access key ID, access key secret, token ID, and token secret.
11. Log in to the [Seam Connect Webview](../core-concepts/connect-webviews.md) and specify these noted values to connect your Lockly devices to Seam.

    <figure><img src="../.gitbook/assets/seam-connect-webview-lockly.png" alt="Specify the noted credentials to connect your Lockly devices to Seam." width="375"><figcaption></figcaption></figure>

***

## Where to Order

Order Lockly locks directly from the Lockly website.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td><strong>Lockly</strong></td><td></td><td><a href="https://lockly.com/collections/door-lock">https://lockly.com/collections/door-lock</a></td><td><a href="../.gitbook/assets/lockly-logo.png">lockly-logo.png</a></td></tr></tbody></table>

***
