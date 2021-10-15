---
title: Vérifier la disponibilité du stock
description: Cette procédure vous indique comment contrôler le stock physique disponible pour un article spécifique.
author: yufeihuang
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand, InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c1533dc677c53e90d73077e06a67c71cebc1b7e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574615"
---
# <a name="check-the-availability-of-stock"></a>Vérifier la disponibilité du stock

[!include [banner](../../includes/banner.md)]

Cette procédure vous indique comment contrôler le stock physique disponible pour un article spécifique. Elle vous indique également comment obtenir des informations d’approvisionnement associées à un article. Le stock physique disponible représente le stock disponible (c’est-à-dire tout ce qui est acheté, reçu et enregistré). Le stock disponible inclut le stock disponible, mais également le stock commandé et prévu, mais pas encore reçu ou enregistré. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées. Ces tâches sont généralement effectuées par un magasinier.


## <a name="check-on-hand-inventory-for-an-item"></a>Vérifier un article dans le stock disponible
1. Accédez à **Volet de navigation > Modules > Gestion des stocks > Recherches et états > Stock disponible**.
2. Sélectionnez la ligne **Numéro d’article**. Pour rechercher le stock disponible par numéro d’article, sélectionnez la ligne où Tableau est défini sur **Stock disponible** et Champ est défini sur Numéro d’**article**.
3. Dans le champ **Critères**, sélectionnez l’article à rechercher. Si vous utilisez la société fictive USMF, vous pouvez sélectionner M9201.  
4. Cliquez sur **OK**.
5. Cliquez sur **Dimensions** dans le volet **Actions**. L’onglet **Dimensions** vous permet de sélectionner la quantité de détails à afficher à propos du stock disponible. Si vous avez besoin de données liées à la réservation, vous devez afficher toutes les dimensions de stock pour les articles qui utilisent des processus avancés de l’entrepôt.
6. Cliquez sur **OK**.
7. Dans le volet **Actions**, cliquez sur **Informations associées**. Si vous ne voyez pas cette option, vous devez cliquer sur le bouton représentant des points de suspension (…) pour afficher les options du volet Actions supplémentaires.
8. Cliquez sur **Vue d’ensemble de l’approvisionnement**. L’onglet **Vue d’ensemble de l’approvisionnement** fournit des informations d’approvisionnement pour un article spécifique, telles que la quantité disponible, le délai, et les informations fournisseur.  
9. Développez la section **Disponible**.
10. Développez la section **Fournisseurs**.
11. Fermez la page.
12. Fermez la page.

## <a name="check-physical-on-hand-inventory"></a>Vérifier le stock physique disponible
1. Accédez à **Volet de navigation > Modules > Gestion de l’entrepôt > Recherches et états > Stock physique**.
2. Dans le champ **Numéro d’article**, tapez une valeur. Vous pouvez utiliser les champs Site et Entrepôt pour filtrer la liste des articles. 
3. Actualisez la page.
4. Cliquez sur **Affichage des dimensions** dans le volet **Actions**. L’onglet Affichage des dimensions vous permet de sélectionner la quantité de détails à afficher à propos du stock disponible.
5. Cliquez sur **OK**.
6. Fermez la page.

## <a name="check-on-hand-inventory-by-location"></a>Vérifier le stock disponible par emplacement
1. Accédez à **Volet de navigation > Modules > Gestion de l’entrepôt > Recherches et états > Disponible par emplacement**.
2. Dans le champ **Entrepôts**, saisissez une valeur. Si vous utilisez la société fictive USMF, vous pouvez utiliser 51.  
3. Actualisez la page.
4. Cliquez sur **Affichage des dimensions**.
5. Cliquez sur **OK**.
6. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]