---
title: Données principales fournisseur intégrées
description: Cette rubrique décrit l’intégration des données fournisseur entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f57a20ed56a761894b2cedf8835310dac098b098
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750616"
---
# <a name="integrated-vendor-master"></a>Données principales fournisseur intégrées

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Le terme *Fournisseur* désigne une organisation de fournisseurs ou un propriétaire unique qui fournit des biens ou des services à une entreprise. Bien que le *fournisseur* soit un concept établi dans les applications Microsoft Dynamics 365 Supply Chain Management, il n’existe aucun concept de fournisseur dans les applications pilotées par un modèle dans Dynamics 365. Cependant, vous pouvez surcharger la table **Compte/Contact** pour stocker les informations fournisseur. Le fournisseur principal intégré introduit un concept de fournisseur explicite dans les applications pilotées par un modèle dans Dynamics 365. Vous pouvez utiliser le nouveau concept de fournisseur ou stocker les données fournisseur dans la table **Compte/Contact**. La double écriture prend en charge les deux approches.

Dans les deux approches, les données du fournisseur sont intégrées entre Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service et les portails Power Apps. Dans Supply Chain Management, les données sont disponibles pour les workflows tels que les demandes d’achat et les commandes d’achat.

## <a name="vendor-data-flow"></a>Flux de données fournisseur

Si vous ne souhaitez pas stocker les données fournisseur dans la table **Compte/Contact** dans Dataverse, vous pouvez utiliser le nouveau concept de fournisseur.

![Flux de données fournisseur](media/dual-write-vendor-data-flow.png)

Si vous ne souhaitez pas continuer à stocker les données fournisseur dans la table **Compte/Contact**, vous pouvez utiliser le concept étendu de fournisseur. Pour utiliser le concept étendu de fournisseur, vous devez configurer les flux de travail du fournisseur dans le package de solution de double écriture. Pour plus d’informations, voir [Permuter entre les configurations de fournisseur](vendor-switch.md).

![Flux de données fournisseur étendues](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Si vous utilisez les portails Power Apps pour les fournisseurs en libre-service, les informations sur les fournisseurs peuvent passer directement vers les applications Finance and Operations.

## <a name="templates"></a>Modèles

Les données fournisseur incluent toutes les informations sur le fournisseur, telles que le groupe de fournisseurs, les adresses, les informations de contact, le profil de paiement et le profil de facture. Un ensemble de mappages de tables fonctionne ensemble pendant l’interaction des données fournisseur, comme indiqué dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365     | Description
----------------------------|-----------------------------|------------
Vendor V2                   | Compte                     | Les sociétés qui utilisent la table Compte pour stocker les informations fournisseur peuvent continuer de l’utiliser de la même manière. Elles peuvent également tirer parti de la fonctionnalité de fournisseur explicite qui apparaît du fait de l’intégration des applications Finance and Operations.
Vendor V2                   | Msdyn\_vendors              | Les sociétés qui utilisent une solution personnalisée pour les fournisseurs peuvent profiter du concept de fournisseur prêt à l’emploi introduit dans Dataverse du fait de l’intégration des applications Finance and Operations. 
Groupes de fournisseurs               | msdyn\_vendorgroups         | Ce modèle synchronise les informations du groupe de fournisseurs.
Mode de paiement fournisseur       | msdyn\_vendorpaymentmethods | Ce modèle synchronise les informations de la méthode de paiement des fournisseurs.
Contacts CDS V2             | contacts                    | Le modèle [Contacts](customer-mapping.md#cds-contacts-v2-to-contacts) synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.
Lignes d’échéancier de paiement      | msdyn\_paymentschedulelines | Le modèle [Lignes du programme de paiement](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synchronise les données de référence pour les clients et les fournisseurs.
Échéancier de paiement            | msdyn\_paymentschedules     | Le modèle [Lignes du programme de paiement](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) synchronise les données de référence du programme de paiement pour les clients et les fournisseurs.
Lignes de jour de paiement CDS V2    | msdyn\_paymentdaylines      | Le modèle [Lignes de jour de paiement](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synchronise les données de référence des lignes de jour de paiement pour les clients et les fournisseurs.
Jours de paiement CDS            | msdyn\_paymentdays          | Le modèle [Jours de paiement](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) synchronise les données de référence des jours de paiement pour les clients et les fournisseurs.
Conditions de paiement            | msdyn\_paymentterms         | Le modèle [Conditions de paiement](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.
Affixes de nom                | msdyn\_nameaffixes          | Le modèle [Affixes de nom](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]