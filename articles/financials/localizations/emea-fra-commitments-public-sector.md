---
title: Engagements dans le secteur public en France
description: "Les engagements sont des documents source de contrôle budgétaire utilisés par les entités du secteur public en France. Ils permettent de réserver des montants budgétés afin qu'une organisation puisse explicitement suivre des réservations budgétaires à des fins de gestion et de déclaration tout au long du cycle des dépenses."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration, PurchAgreement, PurchCommitment_PSN, PurchTable
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 19531
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1224e7983341fdb8be6a1e731e394106d27b2960
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="commitments-in-the-public-sector-in-france"></a>Engagements dans le secteur public en France

[!INCLUDE [banner](../includes/banner.md)]

Les engagements sont des documents source de contrôle budgétaire utilisés par les entités du secteur public en France. Ils permettent de réserver des montants budgétés afin qu'une organisation puisse explicitement suivre des réservations budgétaires à des fins de gestion et de déclaration tout au long du cycle des dépenses. 

Lorsque des engagements sont utilisés dans le cadre du processus de budgétisation, chaque contrat d'achat, commande fournisseur et facture fournisseur est associé à au moins un engagement. L'engagement est exonéré lorsque les fonds sont débloqués à partir du contrat d'achat et que la commande fournisseur est confirmée. Lorsqu'une facture ne référence pas une commande fournisseur ou un contrat d'achat, l'engagement associé à la facture est exonéré lorsque cette dernière est validée. En outre, un engagement peut spécifier un fournisseur. Dans ce cas, tout contrat d'achat, commande fournisseur ou facture fournisseur référençant l'engagement doit avoir le même fournisseur. Les engagements sont valides de leur date de création jusqu'à la fin de l'exercice ou jusqu'à leur clôture. Les engagements ne peuvent pas être reportés d'un exercice à l'autre.  
>[!NOTE]
>Le champ **Type d'engagement** de la page **Contrat d'achat** n'est pas associé au document d'engagement. Ce champ spécifie uniquement si le contrat d'achat est basé sur une valeur ou une quantité.

## <a name="set-up-budget-control-and-related-prerequisites"></a>Paramétrage du contrôle budgétaire et des conditions préalables requises
Avant de pouvoir utiliser des engagements, il est nécessaire de définir des souches de numéros pour les engagements et de paramétrer le contrôle budgétaire. Il faut en outre que des montants budgétaires soient disponibles. Le workflow d'engagement est facultatif, mais recommandé.

-   Sur la page **Paramètres de budgétisation**, définissez des souches de numéros pour les engagements.
-   Définissez un workflow pour gérer le processus de révision des engagements.
-   Sur la page **Configuration du contrôle budgétaire**, paramétrer le contrôle budgétaire. Les options répertoriées ci-dessous doivent obligatoirement être activées pour les engagements. Les paramètres non mentionnés peuvent être sélectionnés en fonction des besoins et des pratiques de l'organisation.
    -   Dans la section **Fonds budgétaires disponibles**, sélectionnez les options suivantes :
        -   Budget d'origine
        -   Dépenses réelles
        -   Réservations budgétaires pour les engagements
        -   Réservations budgétaires pour les engagements préalables
        -   Réservations budgétaires pour les engagements préalables non confirmés
    -   Dans la section **Documents et journaux** :
        -   Vérifiez que les options d'en-tête et de ligne sont sélectionnées pour les engagements, les commandes fournisseur, et les factures fournisseur.
        -   Vérifiez que les options d'en-tête et de ligne sont désactivées pour les demandes d'achat.
    -   Dans la section **Activer le contrôle budgétaire**, activez la configuration du contrôle budgétaire, puis activez le contrôle budgétaire.
-   Sur la page **Paramètres de comptabilité**, vérifiez que les options du groupe **Comptabilité d'engagements** de la section **Comptabilité** sont désactivées. Lorsque les engagements sont activés, il devient impossible de valider des transactions budgétaires dans la comptabilité.

## <a name="consume-a-commitment"></a>Consommation d'un engagement
Il existe trois manières de consommer un engagement.

-   **Assigner un contrat d'achat à une ligne d'engagement.** L'engagement est consommé lorsque les fonds sont débloqués à partir du contrat d'achat. Pour effectuer cette opération, spécifiez le contrat d'achat sur la ligne d'engagement lors de la création de l'engagement.
-   **Référencer l'engagement directement sur une ligne de commande fournisseur.** L'engagement est consommé lorsque la commande fournisseur est confirmée. Aucun contrat d'achat n'est impliqué. Pour exécuter cette opération, créez une commande fournisseur selon votre processus habituel. Lorsque vous ajoutez une ligne à la commande fournisseur, sélectionnez l'engagement à utiliser pour cette dernière.
-   **Référencer l'engagement directement sur une facture fournisseur.** Un contrat d'achat peut être spécifié sur l'en-tête de la facture, mais aucune commande fournisseur n'est impliquée. L'engagement est consommé lorsque la facture est validée. Pour exécuter cette opération, créez une facture fournisseur selon votre processus habituel. Lorsque vous ajoutez une ligne à la facture, sélectionnez l'engagement à utiliser pour cette dernière.

Un engagement peut être limité à un fournisseur particulier ou il peut être affecté à n'importe quel fournisseur. Si l'engagement est limité à un fournisseur spécifique, l'engagement n'est accessible à la sélection que lorsque la facture fournisseur ou la commande fournisseur concerne ce fournisseur particulier.

## <a name="increase-or-decrease-a-commitment"></a>Augmentation ou réduction d'un engagement
Il est parfois nécessaire de modifier un engagement déjà confirmé. Par exemple, si les conditions météorologiques exigent de passer plus de temps pour déblayer la neige et effectuer les services connexes, il vous sera nécessaire d'augmenter l'engagement. Si une ligne d'engagement a déjà été référencée par une commande fournisseur ou une facture fournisseur, votre capacité à la supprimer ou à la modifier peut-être limitée.

## <a name="close-commitments"></a>Clôturer les engagements
Les engagements doivent être clôturés manuellement.

-   Vous pouvez clôturer une seule ligne d'engagement ou un engagement entier par l'intermédiaire du bouton **Clôturer** du volet Actions de l'engagement.
-   Le processus de fin d'exercice de commande fournisseur contrepasse automatiquement les entrées de clôture et crée ou met à jour le budget dans les documents d'engagement du nouvel exercice. Cette opération est exécutée par le processus. Aucune intervention manuelle n'est requise. Toutefois, une fois que vous avez traité les commandes fournisseur et les engagements, vous devez accéder à la page **Clôture de l'engagement**pour clôturer les engagements de l'exercice de clôture.

**Important** : lorsque vous sélectionnez les engagements que vous souhaitez clôturer, vérifiez de ne pas sélectionner les engagements que vous avez déjà créés pour le nouvel exercice. La clôture d'une ligne d'engagement ne peut pas être contrepassée. Si vous clôturez accidentellement une ligne d'engagement, vous devez créer un autre engagement pour restaurer la réservation budgétaire. Pour en savoir plus sur le processus de fin d'exercice, voir [Traitement de fin d'exercice dans le secteur public](../public-sector/year-end-processing-public-sector.md).

<a name="see-also"></a>Voir également :
--------

[Comptabilité du secteur public en France](emea-fra-public-sector-accounting.md)




