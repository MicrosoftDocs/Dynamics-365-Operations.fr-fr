---
title: Données principales client intégrées
description: Cette rubrique décrit l'intégration des données client entre Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 977b74b10b4549d09a8816264f9ff603fa86e91c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172829"
---
# <a name="integrated-customer-master"></a>Données principales client intégrées

[!include [banner](../../includes/banner.md)]


Les données client peuvent être gérées dans plusieurs applications Dynamics 365. Par exemple, un enregistrement client peut provenir d'une activité de vente dans Dynamics 365 Sales (une application basée sur un modèle dans Dynamics 365), ou un enregistrement peut provenir d'une activité de vente au détail dans Dynamics 365 Commerce (une application Finance and Operations). Peu importe d'où proviennent les données client, elles sont intégrées en arrière-plan. Le client principal intégré vous permet de gérer les données client dans n'importe quelle application Dynamics 365 et offre une vue complète du client dans la suite de l'application Dynamics 365.

## <a name="customer-data-flow"></a>Flux de données client

*Client* est un concept bien défini dans les applications. Par conséquent, l'intégration des données client implique l'harmonisation du concept de client entre les deux applications. La relation des données est illustrée dans le flux de données client.

![Flux de données client](media/dual-write-customer-data-flow.png)

Les clients peuvent être classés largement en deux types : les clients commerciaux/organisationnels et les consommateurs/utilisateurs finaux. Ces deux types de clients sont stockés et gérés différemment dans Finance and Operations et dans Common Data Service.

Dans Finance and Operations, des clients commerciaux/organisationnels et des consommateurs/utilisateurs finaux sont gérés dans une table unique nommée **CustTable** (CustomerCustomerV3Entity), et ils sont classés selon l'attribut **Type**. (Si **Type** est défini sur **Organisation**, le client est commercial/organisationnel, et si **Type** est défini sur **Personne**, le client est client/utilisateur.) Les informations de principale personne à contacter sont traitées via l'entité de SMMContactPersonEntity.

Dans Common Data Service, les clients commerciaux/organisationnels sont gérés dans l'entité Compte et identifiés comme clients lorsque l'attribut **RelationshipType** est défini sur **Client**. Les consommateurs/utilisateurs finaux et la personne à contacter sont représentés par l'entité Contact. Pour fournir une séparation claire entre un consommateur/utilisateur final et une personne à contacter, l'entité **Contact** a un indicateur booléen nommé **Vendable**. Lorsque **Vendable** est **True**, le contact est un consommateur/utilisateur final, et des devis et des commandes peuvent être créés pour ce contact. Lorsque **Vendable** est **False**, le contact est simplement une principale personne à contacter d'un client.

Lorsqu'un contact non vendable participe à un processus de devis ou de commande, **Vendable** est défini sur **True** pour indiquer que le contact est un contact de vente. Un contact qui devient un contact de vente reste un contact de vente.

## <a name="templates"></a>Modèles

Les données client incluent toutes les informations sur le client, telles que le groupe de clients, les adresses, les informations de contact, le profil de paiement, le profil de facture, et le statut de fidélité. Un ensemble de mappages d'entités fonctionne ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365         | Description
----------------------------|---------------------------------|------------
Contacts CDS V2             | contacts                        | Ce modèle synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.
Groupes de clients             | msdyn_customergroups            | Ce modèle synchronise les informations du groupe de clients.
Modes de paiement des clients     | msdyn_customerpaymentmethods    | Ce modèle synchronise les informations de la méthode de paiement des clients.
Clients V3                | comptes                        | Ce modèle synchronise les informations principales client pour les clients commerciaux et organisationnels.
Clients V3                | contacts                        | Ce modèle synchronise les données principales de clients pour les clients et les utilisateurs finaux.
Affixes de nom                | msdyn_nameaffixes               | Ce modèle synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.
Lignes de jour de paiement CDS V2    | msdyn_paymentdaylines           | Ce modèle synchronise les données de référence des lignes du jour de paiement, pour les clients et les fournisseurs.
Jours de paiement CDS            | msdyn_paymentdays               | Ce modèle synchronise les données de référence des jours de paiement, pour les clients et les fournisseurs.
Lignes d'échéancier de paiement      | msdyn_paymentschedulelines      | Synchronise les références de données des lignes du programme de paiement, à la fois pour les clients et les fournisseurs.
Echéancier de paiement            | msdyn_paymentschedules          | Ce modèle synchronise les données de référence du programme de paiement, pour les clients et les fournisseurs.
Conditions de paiement            | msdyn_paymentterms              | Ce modèle synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
