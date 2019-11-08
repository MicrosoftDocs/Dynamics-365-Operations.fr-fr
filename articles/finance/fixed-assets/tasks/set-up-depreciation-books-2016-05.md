---
title: Paramétrer les registres des amortissements (mai 2016)
description: Ce guide de tâche va créer un registre des amortissements et l'associera à un groupe d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6840e211847494598a81cd3228dbd3796447e18c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186898"
---
# <a name="set-up-depreciation-books-may-2016"></a>Paramétrer les registres des amortissements (mai 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

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
