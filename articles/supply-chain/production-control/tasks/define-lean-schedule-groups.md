--- 
title: "Définir les groupes de calendriers de production au plus juste"
description: "Les groupes de calendriers de production au plus juste sont définis pour regrouper et distinguer les produits dans le calendrier kanban."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e07fa270b47be3527c572dc53ca30a7bcde5ba6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="define-lean-schedule-groups"></a>Définir les groupes de calendriers de production au plus juste

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les groupes de calendriers de production au plus juste sont définis pour regrouper et distinguer les produits dans le calendrier kanban. Le regroupement peut être effectuée comme l'association générique par société ou être spécifique à une cellule de travail. Chaque groupe est doté d'un code couleur pour l'indication visuelle dans la page de liste de calendrier kanban. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="define-lean-scheduling-group"></a>Définir un groupe de calendriers de production au plus juste
1. Accédez à Gestion des informations sur les produits > Lean Manufacturing > Groupes de calendriers de production au plus juste.
2. Cliquez sur Nouveau.
3. Dans le champ Groupe de programmes, tapez une valeur.
    * Un groupe de calendriers de production peut être défini comme un groupe global ou spécifique à une cellule de travail. Dans cet exemple simple, nous définissons un groupe global, et la cellule de travail demeure vide. Les paramètres de ce groupe s'appliquent à toutes les cellules de travail qui n'ont pas de groupes de calendriers de production spécifiques.  
4. Sélectionnez une couleur de la sélection des couleurs.
    * Les couleurs permettent de mettre en surbrillance les tâches de la page de liste du programme kanban ou du tableau de traitement kanban.  
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="associate-product"></a>Associer un produit
1. Associer un produit spécifique
    * Il existe deux manières d'associer des produits aux groupes de calendriers de production au plus juste, comme produit spécifique (Type de relation d'article = Article) ou dans le cadre d'une clé de répartition par article (Type de relation d'article = groupe).    
2. Dans le champ Type de relation d'article, sélectionnez Article
3. Tapez une valeur dans le champ Numéro d'article.
4. Dans le champ Taux de débit, entrez un nombre.
    * Le taux par défaut de débit est 1, ce qui signifie que les produits associés consomment précisément la capacité spécifiée dans les activités de processus des flux de production. Taux de débit > 1 définit une consommation de ressource plus élevée, Taux de débit < 1 définit une consommation de ressource plus faible. Le taux est utilisé dans le calcul des coûts et dans le calcul de la consommation de la tâche de kanban.  

## <a name="associate-item-allocation-key"></a>Associer une clé de répartition par article
1. Associer une clé de répartition par article
    * Ajoutez une association à une clé de répartition par article à l'aide du groupe Type de relation d'article.   Notez que pour ce processus, vous devez la clé de répartition par article prévue doit être définie dans vos données.  
2. Dans le champ Type de relation d'article, sélectionnez Groupe
3. Dans le champ Clé de répartition par article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.


