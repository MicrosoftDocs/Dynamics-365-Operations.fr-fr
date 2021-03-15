---
title: Ajouter une stratégie de calcul de quantité kanban à une règle de kanban
description: Cette procédure est orientée sur la création d'une stratégie de calcul de quantité de kanban et le fait de l'ajouter à une règle de kanban optimise la taille et les quantités de kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab17ba5a6ee950c2d3977990123a8f9277f858ea
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998810"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Ajouter une stratégie de calcul de quantité kanban à une règle de kanban

[!include [banner](../../includes/banner.md)]

Cette procédure est orientée sur la création d'une stratégie de calcul de quantité de kanban et le fait de l'ajouter à une règle de kanban optimise la taille et les quantités de kanban. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au responsable de la chaîne de valeur. Cette procédure doit impérativement être effectuée avant de créer la procédure Calculer des suggestions de quantité de kanban. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Créer une stratégie de calcul de quantité de kanban
1. Accédez à Contrôle de la production > Tâches périodiques > Calcul de quantité de kanban > Stratégies de calcul de quantité de kanban.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
    * Par exemple, tapez Speaker2016.  
4. Dans le champ Plan général, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez StaticPlan pour calculer la demande.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur Enregistrer.
8. Entrez 1 dans le champ Quantité de kanban minimale.
    * Il s'agit du nombre de kanbans supplémentaires inclus au calcul de la quantité de kanban.  
9. Définissez le facteur de sécurité sur 1.
    * Il s'agit du facteur utilisé pour calculer la quantité de stock de sécurité supplémentaire.  
10. Entrez 30 dans le champ Jours restants.
    * Il s'agit du nombre de jours précédant la date de calcul de la quantité de kanban à laquelle la demande est incluse dans le calcul.  
11. Entrez 30 dans le champ Jours passés.
    * Il s'agit du nombre de jours restants à partir de la date de calcul de la quantité de kanban à laquelle la demande sera incluse dans le calcul  La formule utilisée pour le calcul est désignée par les valeurs actuelles. Par exemple, quantité de kanban = ((Demande quotidienne moyenne x délai x 2,00) / Quantité de produits par unité de manutention) + 1  
12. Fermez la page.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Ajouter une stratégie de calcul de quantité de kanban à la règle de kanban
1. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la règle de kanban 000020 pour cette procédure.  
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Activez ou désactivez l'extension de la section Stratégies de calcul de quantité de kanban.
5. Cliquez sur Ajouter.
    * Ajoutez la stratégie de calcul de quantité de kanban que vous venez de créer dans la sous-tâche précédente.  
6. Dans la liste, marquez la ligne sélectionnée.
7. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la stratégie Speaker2016 que vous venez de créer dans la sous-tâche précédente.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]