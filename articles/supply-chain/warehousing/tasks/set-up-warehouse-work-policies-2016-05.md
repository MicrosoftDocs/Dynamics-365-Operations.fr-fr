---
title: Paramétrer des stratégies de travail d'entrepôt (Application, mai 2016)
description: Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62fbf2f44216c300af5e092f5dbd05ef2239321b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216779"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a>Paramétrer des stratégies de travail d'entrepôt (Application, mai 2016)

[!include [banner](../../includes/banner.md)]

Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt. En définissant une stratégie de travail, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques. Les données fictives de la société USMF ont été utilisées pour créer cet enregistrement. L'application Dynamics AX 7.0.1 ou ultérieure est requise pour ce guide de tâche.

1. Accédez à Gestion des entrepôts > Paramétrage > Travail > Stratégies de travail.
2. Cliquez sur Nouveau.
3. Entrez Aucun travail de rangement dans le champ Nom de la stratégie de travail.
4. Cliquez sur Enregistrer.
5. Cliquez sur Ajouter.
6. Dans la liste, marquez la ligne sélectionnée.
7. Sélectionnez Rangement des produits finis dans le champ Type d'ordre d'exécution.
8. Cliquez sur Ajouter.
9. Dans la liste, marquer la ligne sélectionnée.
10. Sélectionnez Rangement des coproduits et des sous-produits dans le champ Type d'ordre d'exécution.
11. Développez la section Emplacement de stockage.
12. Cliquez sur Ajouter.
13. Dans la liste, marquez la ligne sélectionnée.
14. Entrez 51 dans la liste Entrepôt.
15. Saisissez ou sélectionnez 001 dans le champ Emplacement.
16. Développez la section Produits.
17. Sélectionnez Sélectionné dans le champ Sélection de produits.
18. Cliquez sur Ajouter.
19. Dans la liste, marquer la ligne sélectionnée.
20. Entrez ou sélectionnez L0101 dans le champ Numéro d'article.
21. Cliquez sur Enregistrer.

