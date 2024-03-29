---
title: Paramétrer des autorisations permettant de commander des produits au nom d’un tiers
description: Cet article explique comment accorder à des collaborateurs l’autorisation de préparer des demandes d’achat au nom d’autres collaborateurs.
author: GalynaFedorova
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3053f28fdf97637b1da5f644f64676bfd10fb6a0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854208"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Paramétrer des autorisations permettant de commander des produits au nom d’un tiers

[!include [banner](../../includes/banner.md)]

Cet article explique comment accorder à des collaborateurs l’autorisation de préparer des demandes d’achat au nom d’autres collaborateurs. En d’autres termes, un « préparateur » de demande d’achat peut créer une demande pour un autre « demandeur ». La procédure montre également comment accorder à un collaborateur une autorisation de commander des articles et des services dans différentes entités juridiques ou unités opérationnelles. Ces tâches sont généralement effectuées par un gestionnaire des achats. Vous pouvez utiliser cette procédure soit dans les données fictives de la société USMF soit dans vos propres données.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Accorder des autorisations pour entrer des demandes d’achat au nom d’un autre collaborateur
1. Dans le volet de navigation, accédez à **Modules > Approvisionnements > Paramétrage > Stratégies > Autorisations de demande d’achat**. Assurez-vous que le champ **Vue actuelle** est défini sur **Par préparateur**. La liste du volet gauche montre les personnes qui peuvent recevoir les autorisations pour préparer des demandes au nom d’autres personnes.  
2. Choisissez la personne à qui accorder l’autorisation (le préparateur).
3. Sélectionnez **Ajouter**.
4. Trouvez et choisissez la personne à ajouter en tant que demandeur.
    - Le demandeur est la personne au nom de qui le préparateur peut créer des demandes.  
    - Dans le champ **Autorisation**, sélectionnez **Spécifique** si le préparateur doit pouvoir créer des demandes d’achat au nom du collaborateur sélectionné. Choisissez **Génération d’états** si le préparateur doit pouvoir également créer des demandes d’achat au nom de tous les collaborateurs placés sous son autorité.  
5. Dans le champ **Effet**, entrez une date.
6. Dans le champ **Expiration**, entrez une date et une heure.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Afficher les préparateurs qui ont l’autorisation de créer des demandes d’achat pour un collaborateur choisi
1. Dans le champ **Vue actuelle**, choisissez **Par demandeur**. Cette vue affiche la liste de préparateurs qui ont le droit de créer des demandes d’achat au nom d’un collaborateur sélectionné.  
2. Utilisez le filtre rapide pour trouver le collaborateur que vous venez d’ajouter en tant que demandeur.
3. Sélectionnez le demandeur. La liste des préparateurs montre les personnes qui ont l’autorisation de commander des articles au nom du demandeur qui est choisi dans le volet gauche.  Vous pouvez ajouter des préparateurs supplémentaires ici. Cette vue vous laisse également accorder l’autorisation au demandeur de créer des demandes dans les entités juridiques et les unités opérationnelles qui ne sont pas l’entité juridique ou l’unité opérationnelle de cette personne.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]