---
title: Définir le processus de comptage de cycle partiel d’emplacement
description: Lorsque vous utilisez des plans d’inventaire tournant pour créer le travail d’inventaire, vous pouvez guider les opérations d’inventaire réelles en demandant que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de l’ensemble du stock disponible dans l’emplacement.
author: Mirzaab
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c179b7f6e0b8546e20204a971cb2951c7b62d7b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579974"
---
# <a name="define-partial-location-cycle-counting-process"></a>Définir le processus de comptage de cycle partiel d’emplacement 

[!include [banner](../../includes/banner.md)]

Lorsque vous utilisez des plans d’inventaire tournant pour créer le travail d’inventaire, vous pouvez guider les opérations d’inventaire réelles en demandant que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de l’ensemble du stock disponible dans l’emplacement. Lorsque vous appliquez un filtre sur des produits spécifiques, le gestionnaire d’entrepôt peut réduire les frais généraux de révision, éviter toute erreur de consolidation et gagner du temps. Généralement, un gestionnaire d’entrepôt effectue les tâches de paramétrage. Vous pouvez exécuter cette procédure avec la société fictive de démonstration USMF ou avec vos propres données.


## <a name="create-a-cycle-counting-work-template"></a>Créer un modèle de travail d’inventaire tournant
1. Accédez à Gestion des entrepôts > Configuration > Travail > Modèles de travail.
2. Dans le champ Type d’ordre d’exécution, sélectionnez « Cycle tournant ».
3. Cliquez sur Nouveau.
4. Entrez un nombre dans le champ Numéro de souche.
    * L’ordre de tri est du plus petit nombre au plus grand nombre. La valeur doit être supérieure à 0 (zéro).  
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ Modèle de travail, tapez une valeur.
7. Dans le champ Description du modèle de travail, tapez une valeur.
8. Dans le champ ID pool de travail, saisissez ou sélectionnez une valeur.
9. Dans le champ Priorité du travail, entrez une valeur.
10. Cliquez sur Enregistrer.
11. Cliquez sur Nouveau.
12. Dans la liste, marquez la ligne sélectionnée.
13. Dans le champ Type de travail, sélectionnez « Comptage ».
14. Saisissez ou sélectionnez une valeur dans le champ ID classe de travail.
15. Cliquez sur Enregistrer.
16. Cliquez sur Pauses de ligne de travail.
17. Cliquez sur Nouveau.
18. Entrez un nombre dans le champ Numéro de souche.
    * L’ordre de tri est du plus petit nombre au plus grand nombre. La valeur doit être supérieure à 0 (zéro).  
19. Cliquez sur Enregistrer.
20. Fermez la page.
21. Fermez la page.

## <a name="create-a-cycle-counting-plan"></a>Créer un plan d’inventaire tournant
1. Accédez à Gestion de l’entrepôt > Paramétrage > Inventaire tournant > Plans d’inventaire tournant.
2. Cliquez sur Nouveau.
3. Dans le champ ID plan d’inventaire tournant, entrez une valeur.
4. Tapez une valeur dans le champ Description.
5. Dans le champ Nombre maximal d’inventaires tournants, entrez un nombre.
6. Saisissez ou sélectionnez une valeur dans le champ Modèle de travail.
7. Cliquez sur Nouveau.
8. Entrez un nombre dans le champ Numéro de souche.
    * L’ordre de tri est du plus petit nombre au plus grand nombre. La valeur doit être supérieure à 0 (zéro).  
9. Dans le champ Description, entrez une valeur.
10. Cliquez sur Enregistrer.
11. Cliquez sur Définir une requête de produit.
12. Dans la liste, marquez la ligne sélectionnée.
13. Dans le champ Critères, saisissez ou sélectionnez une valeur.
14. Cliquez sur OK.
15. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]