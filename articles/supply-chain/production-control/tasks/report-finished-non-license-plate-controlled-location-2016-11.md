---
title: Déclarer comme terminé à un emplacement ne faisant pas l'objet d'un contrôle de contenant (application, mai 2016)
description: Ce guide de tâche présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 180035668d9c8a03b83f669af7459725eecc8def
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981179"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>Déclarer comme terminé à un emplacement ne faisant pas l'objet d'un contrôle de contenant (application, mai 2016)

[!include [banner](../../includes/banner.md)]

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

