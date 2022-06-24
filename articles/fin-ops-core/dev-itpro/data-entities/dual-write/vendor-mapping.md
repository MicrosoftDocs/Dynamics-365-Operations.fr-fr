---
title: Données principales fournisseur intégrées
description: Cet article décrit l’intégration des données fournisseur entre les applications Finances et Opérations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 394bb19000076eace6377e07bb3a939c8345da8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905313"
---
# <a name="integrated-vendor-master"></a>Données principales fournisseur intégrées

[!include [banner](../../includes/banner.md)]



Le terme *Fournisseur* désigne une organisation de fournisseurs ou un propriétaire unique qui fournit des biens ou des services à une entreprise. Bien que le *fournisseur* soit un concept établi dans les applications Microsoft Dynamics 365 Supply Chain Management, il n’existe aucun concept de fournisseur dans les applications d’engagement client. Cependant, vous pouvez surcharger la table **Compte/Contact** pour stocker les informations fournisseur. Le fournisseur principal intégré introduit un concept de fournisseur explicite dans les applications d’engagement client. Vous pouvez utiliser le nouveau concept de fournisseur ou stocker les données fournisseur dans la table **Compte/Contact**. La double écriture prend en charge les deux approches.

Dans les deux approches, les données du fournisseur sont intégrées entre Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service et les portails Power Apps. Dans Supply Chain Management, les données sont disponibles pour les workflows tels que les demandes d’achat et les commandes d’achat.

## <a name="vendor-data-flow"></a>Flux de données fournisseur

Si vous ne souhaitez pas stocker les données fournisseur dans la table **Compte/Contact** dans Dataverse, vous pouvez utiliser le nouveau concept de fournisseur.

![Flux de données fournisseur.](media/dual-write-vendor-data-flow.png)

Si vous ne souhaitez pas continuer à stocker les données fournisseur dans la table **Compte/Contact**, vous pouvez utiliser le concept étendu de fournisseur. Pour utiliser le concept étendu de fournisseur, vous devez configurer les flux de travail du fournisseur dans le package de solution de double écriture. Pour plus d’informations, voir [Permuter entre les configurations de fournisseur](vendor-switch.md).

![Flux de données fournisseur étendues.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Si vous utilisez les portails Power Apps pour les fournisseurs en libre service, les informations sur les fournisseurs peuvent passer directement vers les applications Finances et Opérations.

## <a name="templates"></a>Modèles

Les données fournisseur incluent toutes les informations sur le fournisseur, telles que le groupe de fournisseurs, les adresses, les informations de contact, le profil de paiement et le profil de facture. Un ensemble de mappages de tables fonctionne ensemble pendant l’interaction des données fournisseur, comme indiqué dans le tableau suivant.

Applications de Finances et Opérations | Applications Customer Engagement     | Description
----------------------------|-----------------------------|------------
[Contacts CDS V2](mapping-reference.md#115) | contacts | Ce modèle synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.
[Affixes de nom](mapping-reference.md#155) | msdyn_nameaffixes | Ce modèle synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.
[Lignes de jour de paiement CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Ce modèle synchronise les données de référence des lignes du jour de paiement, pour les clients et les fournisseurs.
[Jours de paiement CDS](mapping-reference.md#158) | msdyn_paymentdays | Ce modèle synchronise les données de référence des jours de paiement, pour les clients et les fournisseurs.
[Lignes d’échéancier de paiement](mapping-reference.md#159) | msdyn_paymentschedulelines | Synchronise les références de données des lignes du programme de paiement, à la fois pour les clients et les fournisseurs.
[Echéancier de paiement](mapping-reference.md#160) | msdyn_paymentschedules | Ce modèle synchronise les données de référence du programme de paiement, pour les clients et les fournisseurs.
[Conditions de paiement](mapping-reference.md#161) | msdyn_paymentterms | Ce modèle synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.
[Fournisseurs V2](mapping-reference.md#202) | msdyn_vendors | Les sociétés qui utilisent une solution personnalisée pour les fournisseurs peuvent profiter du concept de fournisseur prédéfini introduit dans Dataverse en raison de l’intégration des applications Finances et Opérations.
[Groupes de fournisseurs](mapping-reference.md#200) | msdyn_vendorgroups | Ce modèle synchronise les informations du groupe de fournisseurs.
[Mode de paiement fournisseur](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Ce modèle synchronise les informations de la méthode de paiement des fournisseurs.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
