---
title: Créer une commande fournisseur pour un fournisseur occasionnel
description: Cette procédure vous indique comment créer une commande fournisseur pour un fournisseur occasionnel.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a55cd8f21b99589a44f7509123d3417fd9dc07f6
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147432"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Créer une commande fournisseur pour un fournisseur occasionnel

[!include [banner](../../includes/banner.md)]

Cette procédure vous indique comment créer une commande fournisseur pour un fournisseur occasionnel. Le fournisseur est créé automatiquement avec la commande fournisseur, plutôt que d'avoir à créer le compte fournisseur manuellement. Les commandes fournisseur sont généralement créées par un agent des achats. L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. Il est impératif qu'un compte fournisseur occasionnel soit défini dans la page Paramètres des achats.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Créer une commande fournisseur pour un fournisseur occasionnel
1. Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Fournisseur occasionnel, sélectionnez Oui.
    * Un compte fournisseur est automatiquement créé et affecté à la commande fournisseur. Le compte fournisseur est créé en fonction du modèle qui est spécifié sur l'onglet Général de la page Paramètres de la comptabilité fournisseur.  
4. Dans le champ Nom, tapez un nom pour le fournisseur.
5. Cliquez sur OK.
    * La commande fournisseur peut maintenant être traitée comme n'importe quelle autre commande. Il n'y a aucune caractéristique spéciale liée à la façon dont ceci est fait. La facture va prendre en compte une transaction due sur le compte fournisseur qui a été créé avec la commande et le paiement sera alors traité.

