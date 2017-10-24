--- 
title: "Créer une commande fournisseur pour un fournisseur occasionnel"
description: "Cette procédure vous indique comment créer une commande fournisseur pour un fournisseur occasionnel."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2d4dabaf6e1d79cbd626294ee4e327f2725a5e43
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Créer une commande fournisseur pour un fournisseur occasionnel

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous indique comment créer une commande fournisseur pour un fournisseur occasionnel. Le fournisseur est créé automatiquement avec la commande fournisseur, plutôt que d'avoir à créer le compte fournisseur manuellement. Les commandes fournisseur sont généralement créées par un agent des achats. L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. Il est impératif qu'un compte fournisseur occasionnel soit défini dans la page Paramètres des achats.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Créer une commande fournisseur pour un fournisseur occasionnel
1. Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Fournisseur occasionnel, sélectionnez Oui.
    * Un compte fournisseur est automatiquement créé et affecté à la commande fournisseur. Le compte fournisseur est créé en fonction du modèle qui est spécifié sur l'onglet Général de la page Paramètres de la comptabilité fournisseur.  
4. Dans le champ Nom, tapez un nom pour le fournisseur.
5. Cliquez sur OK.
    * La commande fournisseur peut maintenant être traitée comme n'importe quelle autre commande. Il n'y a aucune caractéristique spéciale liée à la façon dont ceci est fait. La facture va prendre en compte une transaction due sur le compte fournisseur qui a été créé avec la commande et le paiement sera alors traité. Quand ceci est accompli, le compte fournisseur peut être supprimé. Ceci est fait généralement par le département Comptabilité fournisseur.  


