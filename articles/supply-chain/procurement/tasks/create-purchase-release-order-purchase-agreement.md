---
title: Appliquer un contrat d’achat lors de la création d’une commande fournisseur
description: Cette procédure indique comment utiliser un contrat d’achat lorsque vous créez une commande fournisseur.
author: GalynaFedorova
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a21821d75be2d5340cd418c12be39431870d2779
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678741"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Appliquer un contrat d’achat lors de la création d’une commande fournisseur

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment utiliser un contrat d’achat lorsque vous créez une commande fournisseur. Le contrat d’achat doit être appliqué lorsque vous créez la commande fournisseur car il existe des conditions générales qui doivent être copiées dans l’en-tête de la commande fournisseur. Cette tâche est généralement effectuée par un agent des achats. Comme préalable à ce guide, vous devez posséder un contrat d’achat effectif avec un engagement de quantité de produits pour un fournisseur et des articles. La même procédure peut être utilisée si vous avez un contrat d’achat avec d’autres types d’engagements.

## <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Production et approvisionnement \> Espaces de travail \> Préparation de la commande fournisseur**.
1. Sélectionnez **Nouvelle commande fournisseur** dans le volet Actions.
1. La boîte de dialogue **Créer une commande fournisseur** s'ouvre. Sélectionnez un **Compte fournisseur**. Inspectez et ajustez les autres champs d'adresse si nécessaire.
1. Développez l’organisateur **Général**.
1. Dans le champ **Contrat d’achat**, recherchez et sélectionnez le contrat en vigueur que vous souhaitez utiliser. Tous les accords disponibles pour le fournisseur sont répertoriés ici.  
1. Cliquez sur **Oui**.
1. Cliquez sur **OK**.

## <a name="add-a-line"></a>Ajouter une ligne

1. Dans le champ **Numéro d’article**, tapez une valeur. S’il existe des dimensions spécifiques de stock ou d’emplacement de l’engagement, vous devez entrer les mêmes valeurs dans la ligne de commande fournisseur pour utiliser l’accord.
1. Dans le champ **Site**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche. Le site peut être déjà rempli avec la valeur par défaut de la commande ou du fournisseur. Si c’est le cas, ignorez cette étape.  
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Entrez un nombre dans le champ **Quantité**. Validez que le prix est copié à partir de l’engagement.  

## <a name="look-up-the-commitment"></a>Rechercher l’engagement

1. Sélectionnez **Mettre à jour la ligne**.
1. Sélectionnez **Joint**. Ici, vous pouvez obtenir des détails sur le contrat d’achat. Par exemple, vous pouvez afficher le prix et savoir si le prix et la remise sont fixes, ce qui signifie que si vous modifiez le prix ou la remise sur la commande fournisseur sur une valeur différente de celle de l’engagement, le système supprimera le lien de sorte que la ligne de commande fournisseur n’honore pas l’engagement. Vous pouvez également voir si l’option Le max. est appliqué est sélectionnée, ce qui signifie que la quantité présente sur l’engagement ne peut pas être dépassée en additionnant tous les achats qui honorent l’engagement.  
1. Fermez la page.

## <a name="look-up-the-purchase-agreement"></a>Rechercher le contrat d’achat

1. Dans le **volet Actions**, sélectionnez **Général**.
1. Sélectionnez **Contrat d'achat**.
1. Fermez la page.
1. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]