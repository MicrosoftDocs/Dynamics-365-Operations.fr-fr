---
title: "Configurer les dénominations des disponibilités pour le PDV"
description: "Les dénominations des disponibilités pour les billets et les pièces peuvent être définies dans l'arrière-guichet qui sera utilisé par les caissiers, les associés de vente et les directeurs du magasin à partir du PDV."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45e70765c43b93e9d8abab5fbb9de1d67a739a74
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="configure-cash-denominations-for-pos"></a>Configurer les dénominations des disponibilités pour le PDV

[!include[banner](includes/banner.md)]

Les dénominations des disponibilités pour les billets et les pièces peuvent être définies dans l'arrière-guichet qui sera utilisé par les caissiers, les associés de vente et les directeurs du magasin à partir du PDV. Ces dénominations peuvent être utilisées pour faciliter le comptage de caisse en fin de journée ou pour enregistrer rapidement une vente.

## <a name="define-denominations"></a>Définir des dénominations
Les dénominations sont paramétrées par magasin dans la page **Paramétrage** > **Option de déclaration des montants en caisse à partir de la propriété du magasin**. 

![dénominations des disponibilités](./media/image1-denomination.png)

Pour définir une dénomination :
1. Cliquez sur **Nouveau**.
1. Spécifiez le type (pièce ou billet).
1. Spécifiez le montant (valeur).

![dénominations des disponibilités](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Configurer le profil de la fonctionnalité
Lors du règlement en espèces dans le PVD, l'utilisateur peut utiliser les dénominations de billet pour entrer rapidement le montant payé par le client. Dans le profil de la fonctionnalité, vous pouvez configurer les deux options pour afficher la dénomination dans le PDV.

**Supérieur ou égal au montant dû** : par défaut, le PDV n'affiche que les dénominations de billet qui sont supérieures au montant dû, ce qui permet d'effectuer la transaction en une seule étape. Par exemple, si le montant dû est $7,50, le PDV affiche les dénominations suivantes : $10, $20, $50 et $100 Si vous touchez l'un de ces montants, la vente est automatiquement enregistrée pour ce montant. Les billets de $1 et $5 ne sont pas affichés, car ces montants sont inférieurs au montant dû.

**Toutes les dénominations** : sélectionnez cette option pour afficher systématiquement toutes les dénominations de billet dans le PDV, quel que soit le montant dû. Cela signifie que l'utilisateur peut utiliser une combinaison de billets pour atteindre le montant dû. Par exemple, si le montant dû est $25,00, l'utilisateur peut choisir $20 et $5 pour terminer la vente.

