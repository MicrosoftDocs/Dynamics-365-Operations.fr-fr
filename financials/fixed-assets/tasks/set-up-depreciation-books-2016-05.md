--- 
title: "Paramétrer les registres d'amortissement "
description: "Ce guide de tâche va créer un registre des amortissements et l'associera à un groupe d'immobilisations."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f8ca9cc59df4eab5a476524e92200687e5979bc9
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-depreciation-books"></a>Paramétrer les registres d'amortissement  

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche va créer un registre des amortissements et l'associera à un groupe d'immobilisations.  Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.


## <a name="create-a-depreciation-book"></a>Créer un registre des amortissements
1. Accédez à Immobilisations > Paramétrage > Registres des amortissements.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Registre des amortissements.
4. Dans le champ Description, entrez une valeur.
5. Cochez ou décochez la case Calculer l'amortissement.
6. Dans le champ Profil d'amortissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez le profil d'amortissement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Autre profil d'amortissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Dans la liste, sélectionnez le profil d'amortissement souhaité.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Le profil d'amortissement exceptionnel est utilisé pour l'amortissement supplémentaire d'un actif dans des circonstances peu courantes. Par exemple, vous pouvez utiliser cette opération pour enregistrer l'amortissement résultant d'une catastrophe naturelle.  
12. Cochez ou décochez la case Créer des ajustements d'amortissement avec des amortissements de base
13. Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Associer le registre des amortissements à un groupe d'immobilisations
1. Cliquez sur Groupes d'immobilisations.
2. Dans le champ Groupe d'immobilisations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Sélectionnez une option dans le champ Convention d'amortissement.
6. Entrez un nombre dans le champ Durée de vie.
    * Notez que la valeur du champ Périodes d'amortissement est calculée après la définition de la durée de vie.  

