--- 
title: "Déclarer comme terminé à un emplacement de contrôle de contenant"
description: "Ce guide de tâche présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 34fac03a0ff3d71a2349b66f8f85e4e124dcd708
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a>Déclarer comme terminé à un emplacement de contrôle de contenant 

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant. Une stratégie de travail applicable correspond est une condition préalable pour cette tâche. Un guide de tâche précédent a indiqué le paramétrage de la stratégie de travail. L'application Dynamics AX 7.0.1 ou ultérieure est requise pour ce guide de tâche.




## <a name="set-up-an-output-location"></a>Définir un emplacement de sortie
1. Accédez à Administration d'organisation > Ressources > Groupes de ressources.
2. Sélectionnez le groupe de ressources 5102 dans la liste.
3. Cliquez sur Modifier.
4. Entrez 51 dans le champ Entrepôt de sortie.
5. Entrez 001 dans le champ Emplacement de sortie.
    * L'emplacement 001 n'est un emplacement qui fait l'objet d'un contrôle de contenant. Vous pouvez uniquement paramétrer un emplacement de sortie faisant l'objet d'un contrôle de contenant si une stratégie de travail applicable existe pour l'emplacement.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Créer un ordre de fabrication et le déclarer comme terminé
1. Fermez la page.
2. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
3. Cliquez sur Nouvel ordre de fabrication.
4. Entrez L0101 dans le champ Numéro d'article.
5. Cliquez sur Créer.
6. Cliquez sur Ordre de fabrication dans le volet Actions.
7. Cliquez sur Estimer.
8. Cliquez sur OK.
9. Cliquez sur Démarrer.
10. Cliquez sur l'onglet Général.
11. Dans le champ Consommation de nomenclature automatique, sélectionnez Jamais.
12. Cliquez sur OK.
13. Cliquez sur Déclaration de fin.
14. Cliquez sur l'onglet Général.
15. Dans le champ Accepter les erreurs, sélectionnez Oui.
16. Cliquez sur OK.
17. Cliquez sur Entrepôt dans le volet Actions.
18. Cliquez sur Détails du travail.
    * Lorsque l'ordre de fabrication a été déclaré comme terminé, aucune tâche de rangement n'a été générée. Cela se produit car une stratégie de travail est définie et empêche la tâche d'être générée lorsque le produit L0101 est déclaré comme terminé à l'emplacement 001.  


