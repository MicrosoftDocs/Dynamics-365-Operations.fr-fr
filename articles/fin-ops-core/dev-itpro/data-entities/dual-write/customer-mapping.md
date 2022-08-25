---
title: Données principales client intégrées
description: Cet article décrit l’intégration des données client entre les applications de finances et d’opérations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ea142aff7c8f4b442d7224325e44359129efe8a8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289678"
---
# <a name="integrated-customer-master"></a>Données principales client intégrées

[!include [banner](../../includes/banner.md)]



Les données client peuvent être gérées dans plusieurs applications Dynamics 365. Par exemple, une ligne client peut provenir d’une activité de vente dans Dynamics 365 Sales (une application d’engagement client), ou une ligne peut provenir d’une activité de vente au détail dans Dynamics 365 Commerce (une application de Finances et Opérations). Peu importe d’où proviennent les données client, elles sont intégrées en arrière-plan. Le client principal intégré vous permet de gérer les données client dans n’importe quelle application Dynamics 365 et offre une vue complète du client dans la suite de l’application Dynamics 365.

## <a name="customer-data-flow"></a>Flux de données client

*Client* est un concept bien défini dans les applications. Par conséquent, l’intégration des données client implique l’harmonisation du concept de client entre les deux applications. La relation des données est illustrée dans le flux de données client.

![Flux de données client.](media/dual-write-customer-data-flow.png)

Les clients peuvent être classés largement en deux types : les clients commerciaux/organisationnels et les consommateurs/utilisateurs finaux. Ces deux types de clients sont stockés et gérés différemment dans les applications de finances et d’opérations et Dataverse.

Dans les applications de finances et d’opérations, des clients commerciaux/organisationnels et des consommateurs/utilisateurs finaux sont gérés dans une table unique nommée **CustTable** (CustCustomerV3Entity), et ils sont classés selon l’attribut **Type**. (Si **Type** est défini sur **Organisation**, le client est commercial/organisationnel, et si **Type** est défini sur **Personne**, le client est client/utilisateur.) Les informations de principale personne à contacter sont traitées via la table de SMMContactPersonEntity.

Dans Dataverse, les clients commerciaux/organisationnels sont gérés dans la table Compte et identifiés comme clients lorsque l’attribut **RelationshipType** est défini sur **Client**. Les consommateurs/utilisateurs finaux et la personne à contacter sont représentés par la table Contact. Pour fournir une séparation claire entre un consommateur/utilisateur final et une personne à contacter, la table **Contact** a un indicateur booléen nommé **Vendable**. Lorsque **Vendable** est **True**, le contact est un consommateur/utilisateur final, et des devis et des commandes peuvent être créés pour ce contact. Lorsque **Vendable** est **False**, le contact est simplement une principale personne à contacter d’un client.

Lorsqu’un contact non vendable participe à un processus de devis ou de commande, **Vendable** est défini sur **True** pour indiquer que le contact est un contact de vente. Un contact qui devient un contact de vente reste un contact de vente.

## <a name="templates"></a>Modèles

Les données client incluent toutes les informations sur le client, telles que le groupe de clients, les adresses, les informations de contact, le profil de paiement, le profil de facture, et le statut de fidélité. Un ensemble de mappages de tables fonctionne ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

Applications de finances et d’opérations | Applications Customer Engagement         | Description
----------------------------|---------------------------------|------------
[Contacts CDS V2](mapping-reference.md#115) | contacts | Ce modèle synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.
[Groupes de clients](mapping-reference.md#126) | msdyn_customergroups | Ce modèle synchronise les informations du groupe de clients.
[Modes de paiement des clients](mapping-reference.md#127) | msdyn_customerpaymentmethods | Ce modèle synchronise les informations de la méthode de paiement des clients.
[Clients V3](mapping-reference.md#101) | comptes | Ce modèle synchronise les informations principales client pour les clients commerciaux et organisationnels.
[Clients V3](mapping-reference.md#116) | contacts | Ce modèle synchronise les données principales de clients pour les clients et les utilisateurs finaux.
[Affixes de nom](mapping-reference.md#155) | msdyn_nameaffixes | Ce modèle synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.
[Lignes de jour de paiement CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Ce modèle synchronise les données de référence des lignes du jour de paiement, pour les clients et les fournisseurs.
[Jours de paiement CDS](mapping-reference.md#158) | msdyn_paymentdays | Ce modèle synchronise les données de référence des jours de paiement, pour les clients et les fournisseurs.
[Lignes d’échéancier de paiement](mapping-reference.md#159) | msdyn_paymentschedulelines | Synchronise les références de données des lignes du programme de paiement, à la fois pour les clients et les fournisseurs.
[Echéancier de paiement](mapping-reference.md#160) | msdyn_paymentschedules | Ce modèle synchronise les données de référence du programme de paiement, pour les clients et les fournisseurs.
[Conditions de paiement](mapping-reference.md#161) | msdyn_paymentterms | Ce modèle synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

