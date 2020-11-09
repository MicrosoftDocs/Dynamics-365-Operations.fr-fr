---
title: Données principales fournisseur intégrées
description: Cette rubrique décrit l'intégration des données fournisseur entre les applications Finance and Operations et Common Data Service.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5c4cc92fd7809f4016d8421c98f41a85fcfedc7b
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997645"
---
# <a name="integrated-vendor-master"></a>Données principales fournisseur intégrées

[!include [banner](../../includes/banner.md)]



Le terme *Fournisseur* désigne une organisation de fournisseurs ou un propriétaire unique qui fournit des biens ou des services à une entreprise. Bien que le *fournisseur* soit un concept établi dans les applications Microsoft Dynamics 365 Supply Chain Management, il n'existe aucun concept de fournisseur dans les applications pilotées par un modèle dans Dynamics 365. Cependant, vous pouvez surcharger l'entité **Compte/Contact** pour stocker les informations du fournisseur. Le fournisseur principal intégré introduit un concept de fournisseur explicite dans les applications pilotées par un modèle dans Dynamics 365. Vous pouvez utiliser la nouvelle conception du fournisseur ou stocker les données du fournisseur dans l'entité **Compte/Contact**. La double écriture prend en charge les deux approches.

Dans les deux approches, les données du fournisseur sont intégrées entre Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service et les portails Power Apps. Dans Supply Chain Management, les données sont disponibles pour les workflows tels que les demandes d'achat et les commandes d'achat.

## <a name="vendor-data-flow"></a>Flux de données fournisseur

Si vous ne souhaitez pas stocker les données fournisseur dans l'entité **Compte/Contact** dans Common Data Service, vous pouvez utiliser le nouveau concept de fournisseur.

![Flux de données fournisseur](media/dual-write-vendor-data-flow.png)

Si vous ne souhaitez pas continuer à stocker les données fournisseur dans l'entité **Compte/Contact** , vous pouvez utiliser le concept étendu de fournisseur. Pour utiliser le concept étendu de fournisseur, vous devez configurer les flux de travail du fournisseur dans le package de solution de double écriture. Pour plus d'informations, voir [Permuter entre les configurations de fournisseur](vendor-switch.md).

![Flux de données fournisseur étendues](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Si vous utilisez les portails Power Apps pour les fournisseurs en libre-service, les informations sur les fournisseurs peuvent passer directement vers les applications Finance and Operations.

## <a name="templates"></a>Modèles

Les données fournisseur incluent toutes les informations sur le fournisseur, telles que le groupe de fournisseurs, les adresses, les informations de contact, le profil de paiement et le profil de facture. Un ensemble de mappages d'entités fonctionne ensemble pendant l'interaction des données fournisseur, comme indiqué dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365     | Description
----------------------------|-----------------------------|------------
Vendor V2                   | Compte                     | Les sociétés qui utilisent l'entité Compte pour stocker les informations fournisseur peuvent continuer de l'utiliser de la même manière. Elles peuvent également tirer parti de la fonctionnalité de fournisseur explicite qui apparaît du fait de l'intégration des applications Finance and Operations.
Vendor V2                   | Msdyn\_vendors              | Les sociétés qui utilisent une solution personnalisée pour les fournisseurs peuvent profiter du concept de fournisseur prêt à l'emploi introduit dans Common Data Service du fait de l'intégration des applications Finance and Operations. 
Groupes de fournisseurs               | msdyn\_vendorgroups         | Ce modèle synchronise les informations du groupe de fournisseurs.
Mode de paiement fournisseur       | msdyn\_vendorpaymentmethods | Ce modèle synchronise les informations de la méthode de paiement des fournisseurs.
Contacts CDS V2             | contacts                    | Le modèle [Contacts](customer-mapping.md#cds-contacts-v2-to-contacts) synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.
Lignes d'échéancier de paiement      | msdyn\_paymentschedulelines | Le modèle [Lignes du programme de paiement](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synchronise les données de référence pour les clients et les fournisseurs.
Échéancier de paiement            | msdyn\_paymentschedules     | Le modèle [Lignes du programme de paiement](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) synchronise les données de référence du programme de paiement pour les clients et les fournisseurs.
Lignes de jour de paiement CDS V2    | msdyn\_paymentdaylines      | Le modèle [Lignes de jour de paiement](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synchronise les données de référence des lignes de jour de paiement pour les clients et les fournisseurs.
Jours de paiement CDS            | msdyn\_paymentdays          | Le modèle [Jours de paiement](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) synchronise les données de référence des jours de paiement pour les clients et les fournisseurs.
Conditions de paiement            | msdyn\_paymentterms         | Le modèle [Conditions de paiement](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.
Affixes de nom                | msdyn\_nameaffixes          | Le modèle [Affixes de nom](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
