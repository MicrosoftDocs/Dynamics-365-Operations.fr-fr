---
title: Calculer des suggestions de quantité de kanban
description: Cette procédure est orientée sur l'optimisation de la taille et des quantités de kanban pour une règle de kanban spécifique à l'aide du calcul de quantité de kanban.
author: ChristianRytt
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa6a01d8f918c45aaa454e5234f80c312d7a5061
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212386"
---
# <a name="calculate-kanban-quantity-suggestions"></a>Calculer des suggestions de quantité de kanban

[!include [banner](../../includes/banner.md)]

Cette procédure est orientée sur l'optimisation de la taille et des quantités de kanban pour une règle de kanban spécifique à l'aide du calcul de quantité de kanban. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au responsable de la chaîne de valeur. Vous devez absolument avoir effectué la procédure Ajouter une stratégie de calcul de quantité kanban à une règle de kanban.


## <a name="create-a-kanban-quantity-calculation"></a>Créer un calcul de quantité de kanban
1. Accédez à Contrôle de la production > Tâches périodiques > Calcul de quantité de kanban > Calculer la quantité de kanban.
2. Cliquez sur Nouveau.
3. Saisissez « Speaker2016 » dans le champ Nom.
4. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez la stratégie que vous avez créée dans la procédure Ajouter une stratégie de calcul de quantité kanban à une règle de kanban. Par exemple, Speaker2016.  
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Date d'activation de la règle, définissez la date et l'heure comme suit : « 17-12-2012T08:00:00 ».
    * Cette date sert de base à la détermination des règles de kanban fixes à inclure dans le calcul de la quantité de kanban.  
7. Dans le champ Date de début de la période pour les demandes satisfaites, définissez la date et l'heure comme suit « 17-11-2012T09:00:00 ».
    * La date à partir de laquelle les transactions des demandes passées sont incluses dans le calcul de la quantité de kanban.  
8. Dans le champ Date de fin de la période pour les demandes satisfaites, définissez la date et l'heure comme suit « 17-12-2012T07:59:59 ».
    * La date jusqu'à laquelle les transactions des demandes passées sont incluses dans le calcul de la quantité de kanban.  
9. Dans le champ Date de début de la période de demande, définissez la date et l'heure comme suit « 17-12-2012T08:00:00 ».
    * La date à partir de laquelle les transactions des demandes actuelles sont incluses dans le calcul de la quantité de kanban.  
10. Dans le champ Date de fin de la période de demande, définissez la date et l'heure comme suit « 16-01-2013T07:59:59 ».
    * La date jusqu'à laquelle les transactions des demandes actuelles sont incluses dans le calcul de la quantité de kanban.  

## <a name="generate-kanban-quantity-proposal"></a>Générer une proposition de quantité de kanban
1. Cliquez sur Enregistrer.
2. Cliquez sur Générer.
    * Cela génère une ligne de proposition de quantité de kanban pour la règle de kanban 000020.  

## <a name="run-kanban-quantity-calculation"></a>Exécuter un calcul de quantité de kanban
1. Cliquez sur Calculer.
    * Cette opération permet de calculer la proposition de quantité de kanban.  
2. Cliquez sur OK.
3. Dans la liste, marquez la ligne sélectionnée.
    * Notez que la quantité de kanban suggérée est de 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Modifier la quantité de produits et calculer à nouveau
1. Définissez la quantité de produit sur 5.
2. Cliquez sur Calculer.
3. Cliquez sur OK.
    * Notez qu'avec une quantité de kanban de 5, la suggestion est alors une quantité de kanban de 4.  
    * Cela est dû au fait qu'avec une quantité de produits moindre, il faut plus de kanbans pour répondre à la demande.  

## <a name="update-kanban-rule"></a>Mettre à jour la règle de kanban
1. Entrez une date et une heure dans le champ Date d'effet de la règle.
    * Définissez « Date d'activation de la règle » sur une date dans le futur. Par exemple, la date du jour + un an.  
2. Cliquez sur Mise à jour.
3. Cliquez sur OK.
4. Fermez la page.

## <a name="validate-change-on-kanban-rule"></a>Valider la modification de la règle de kanban
1. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la règle de kanban créée dans la tâche précédente. Il doit s'agir de la première règle de kanban de la liste triée par numéro.  
3. Activez ou désactivez l'extension de la section Détails.
    * Notez la date d'effet, qui indique que cette règle n'est pas activée jusqu'à cette date.  
4. Activez ou désactivez l'extension de la section Quantités.
    * Notez qu'il s'agit de la quantité par défaut entrée dans le calcul de quantité de kanban.  
    * Notez qu'il s'agit de la quantité de 4 kanban fixe provenant du calcul de quantité de kanban.  
5. Cliquez sur l'onglet ListPanel.

