--- 
title: "Créer un plan pour un site"
description: "Le gestionnaire de production calcule les besoins en matériaux et en capacité pour la production d'un article spécifique."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d89d34d4d429faf87c70943961f7141a6258d482
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-plan-for-a-site"></a>Créer un plan pour un site

[!include[task guide banner](../../includes/task-guide-banner.md)]

Le gestionnaire de production calcule les besoins en matériaux et en capacité pour la production d'un article spécifique. Une fois les suggestions d'approvisionnement créées, il recherche les commandes sur le site pour lequel il effectue la planification et confirme les commandes, en commençant par celles qui sont urgentes. Les commandes les plus urgentes sont celles qui doivent être confirmées à la date actuelle. Utilisez les données fictives de société USMF pour effectuer ces tâches.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Créer un plan pour les matériaux et la capacité pour un article
1. Cliquez sur Planification.
    * Vous devez accéder au tableau de bord par défaut.  
2. Cliquez sur Exécuter.
3. Développez les enregistrements pour inclure la section.
4. Cliquez sur Filtre.
5. Dans la liste, marquez la ligne sélectionnée.
6. Tapez une valeur dans le champ Critères.
    * Exemple : D0001  
7. Cliquez sur OK.
8. Cliquez sur OK.
    * Ce processus peut prendre quelques minutes.  
9. Actualisez la page.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Identifier les ordres prévisionnels urgents pour l'article
1. Ouvrez le filtre de la colonne Numéro d'article.
2. Appliquez un filtre sur le champ Numéro d'article, avec la valeur D0001, à l'aide de l'opérateur de filtre commence par.
3. Ouvrez le filtre de la colonne Date de commande.
4. Appliquez un filtre sur le champ « Date de commande » avec une valeur de date du jour, à l'aide de l'opérateur de filtre « est exactement ».

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Confirmer les ordres urgents pour l'article
1. Dans la liste, cochez ou décochez toutes les lignes.
2. Cliquez sur Confirmer.
3. Cliquez sur OK.


