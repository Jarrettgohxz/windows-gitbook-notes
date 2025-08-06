---
description: >-
  Kerberos is the default authentication protocol for any recent version of
  Windows.
---

# Kerberos

The general idea is that whenever a user wants to log into a service, they will be assigned a ticket. This ticket acts as a proof of previous authentication, which allows them to utilize a service by presenting it.

### Kerberos authentication

#### Kerberos authentication involves 2 entities:

1. The user to authenticate
2. Key Distribution Center (_**KDC**_), a service usually installed on the Domain Controller
   * In charge of creating Kerberos tickets

#### The process is as follows:

1. The user sends their username and a timestamp (encrypted using a key derived from their password) to the Key Distribution Center (_**KDC**_) described above
2. The _**KDC**_ will create a Ticket Granting Ticket (_TGT_), and send this along with a _session key_ back to the user
   * The _TGT_ allows the user to request for service tickets (needed to access a particular service) without passing their credentials then next time they want to access a service
   * The _session key_ is required for access to a service too (discussed in detail below)
3. When the user wants to connect to a service on the network (eg. database, share), they will make a request to the _**KDC**_ with their username, timestamp encrypted with the _session key_, _TGT_ and a Service Principal Name (_SPN_).
   * The _session key_ and TGT are retrieved from the previous requests
   * The _SPN_ indicates the server and server name to access
4.  The _**KDC**_ will create a Ticket Granting Service (_TGS_), and send this along with a _service session key_ back to the user

    * The TGS is encrypted using a key derived from the _service owner hash_
    * The _service owner hash_ is the user or machine account that the service runs with

    > Note that the _TGS_ contains a copy of the _service session key_ in its encrypted content
5. Finally, the user can use the _TGS_ to make a request to the desired service on the network
   * The service will use its configured account's password hash to decrypt the _TGS_ and validate the _service session key_ contained in the _TGS_

#### General overview

{% stepper %}
{% step %}
### Request for Ticket Granting Ticker (TGT)

<mark style="color:blue;">**REQUEST**</mark>

**\[User** 🧑‍�&#xDCBB;**]** : username, timestamp (encrypted w key derived from password)&#x20;

\--> | **KDC** �&#xDDA5;**|**

<mark style="color:green;">**RESPONSE**</mark>

\| **KDC** �&#xDDA5;**|**: TGT, session key --> **\[User** 🧑‍�&#xDCBB;**]**&#x20;
{% endstep %}

{% step %}
### Request for Ticket Granting Service (TGS)

<mark style="color:blue;">**REQUEST**</mark>

**\[User** 🧑‍�&#xDCBB;**]** : username, timestamp (encrypted w session key), TGT, SPN --> | **KDC** �&#xDDA5;**|**

<mark style="color:green;">**RESPONSE**</mark>

\| **KDC** �&#xDDA5;**|** : TGS, service session key ---> **\[User** 🧑‍�&#xDCBB;**]**&#x20;
{% endstep %}

{% step %}
### User make a request to the desired service (eg. database)

<mark style="color:blue;">**REQUEST**</mark>

**\[User** 🧑‍�&#xDCBB;**]** : TGS --> | DB🛢️|: validate service session key encrypted within the TGS


{% endstep %}
{% endstepper %}



{% embed url="https://tryhackme.com/room/winadbasics" %}
