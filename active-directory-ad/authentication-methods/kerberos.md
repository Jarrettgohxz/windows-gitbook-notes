---
description: >-
  Kerberos is the default authentication protocol for any recent version of
  Windows.
---

# Kerberos

{% embed url="https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-kile/b4af186e-b2ff-43f9-b18e-eedb366abf13" %}

The general idea is that whenever a user wants to log into a service, they will be assigned a ticket. This ticket acts as a proof of previous authentication, which allows them to utilize a service by presenting it.

### Kerberos authentication

#### Kerberos authentication involves 2 entities:

1. The user to authenticate
2. **Key Distribution Cente**r (**KDC**), a service usually installed on the Domain Controller
   * In charge of creating Kerberos tickets

#### Overview of important terms

1. **Ticket Granting Ticket** (**TGT**)

* a certain ticket that allows a user to request additional tickets (**TGS**) to access specific services without passing their credentials to the services themselves

2. **Ticket Granting Service** (**TGS**)

* tickets that only allow connection to specific service for which they are created

3. **Service Principal Name** (**SPN**)

* indicates the service and server name to access

4. **Session Key**

* returned by the **KDC** from the first **TGT** request
* required for the subsequent **TGS** request

5. **Service Owner**

* user or machine account under which a particular service runs

6. **Service Session Key**

* a copy of this key will be contained within the encrypted **TGS**
* it will be validated by the **Service Owner** (configured account running the service) when accessing that particular service

7. **Service Owner Hash**

* used to encrypt the **TGS**

8. **krbtgt** account

{% embed url="https://learn.microsoft.com/en-us/defender-for-identity/change-password-krbtgt-account" %}

> The **krbtgt** account in Active Directory is a built-in account used by the Kerberos authentication service. It encrypts and signs all Kerberos tickets, enabling secure authentication within the domain.

#### The process is as follows:

1. The user sends their username and a timestamp (encrypted using a key derived from their password) to the **Key Distribution Center** (**KDC**)&#x20;
2. The **KDC** will create a **Ticket Granting Ticket** (**TGT**), and send this along with a **Session Key** back to the user
   * The **TGT** allows the user to request for service tickets (needed to access a particular service) without passing their credentials then next time they want to access a service
   * The **Session Key** is required for access to a service too (discussed in detail below)

> The **TGT** is encrypted using the **krbtgt** account's password hash, and it contains a copy of the **Session Key** as part of its contents.

3. When the user wants to connect to a service on the network (eg. database, share), they will make a request to the **KDC** with their username, timestamp encrypted with the **Session Key,** **TGT** and a **Service Principal Name** (**SPN**).

* The **Session Key** and **TGT** are retrieved from the previous requests
* The **SPN** indicates the server and server name to access

4. The **KDC** will create a **Ticket Granting Service** (**TGS**), and send this along with a **Service Session Key** back to the user

* The **TGS** is encrypted using a key derived from the **Service Owner Hash**
* The **Service Owner** is the user or machine account that the service runs with

> Note that the **TGS** contains a copy of the **Service Session Key** in its encrypted content

5. Finally, the user can use the **TGS** to make a request to the desired service on the network

* The service will use its configured account's password hash to decrypt the **TGS** and validate the **Service Session key**

#### General overview

{% stepper %}
{% step %}
### Request for Ticket Granting Ticker (TGT)

<mark style="color:blue;">**REQUEST**</mark>

**\[User** 🧑‍�&#xDCBB;**]** : username, timestamp (encrypted w key derived from password)&#x20;

\--> | **KDC** �&#xDDA5;**|**

<mark style="color:green;">**RESPONSE**</mark>

\| **KDC** �&#xDDA5;**|**: **TGT**, **Session Key** --> **\[User** 🧑‍�&#xDCBB;**]**&#x20;
{% endstep %}

{% step %}
### Request for Ticket Granting Service (TGS)

<mark style="color:blue;">**REQUEST**</mark>

**\[User** 🧑‍�&#xDCBB;**]** : username, timestamp (encrypted w **Session Key**), **TGT**, **SPN** --> | **KDC** �&#xDDA5;**|**

<mark style="color:green;">**RESPONSE**</mark>

\| **KDC** �&#xDDA5;**|** : **TGS**, service **Session Key** ---> **\[User** 🧑‍�&#xDCBB;**]**&#x20;
{% endstep %}

{% step %}
### User make a request to the desired service (eg. database)

<mark style="color:blue;">**REQUEST**</mark>

**\[User** 🧑‍�&#xDCBB;**]** : **TGS** --> | DB🛢️|: validate the **Service Session Key** encrypted within the **TGS**


{% endstep %}
{% endstepper %}



{% embed url="https://tryhackme.com/room/winadbasics" %}
