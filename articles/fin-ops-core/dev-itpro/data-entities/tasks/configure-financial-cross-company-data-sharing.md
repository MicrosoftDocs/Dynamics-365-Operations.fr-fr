---
title: Configurer le partage de données financières entre sociétés
description: Cette procédure indique comment configurer, activer, valider, et résoudre des conflits en partageant des données entre des sociétés.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 98eeae9f50238aae172e4a217d40be39ee46a0b8
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142959"
---
# <a name="configure-financial-cross-company-data-sharing"></a>Configurer le partage de données financières entre sociétés

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment configurer, activer, valider, et résoudre des conflits en partageant des données entre des sociétés. Elle utilise la société USMF et le modèle de partage de données financières.

La plateforme Dynamics AX 7.1 ou ultérieure est requise pour ce guide de tâche.

1. Accédez à **Volet de navigation pane > Modules > Administration système> Espaces de travail > Gestion des données**.
2. Cliquez sur **Importer**.
3. Tapez une valeur dans le champ **Nom**.
4. Dans le champ **Format des données source**, sélectionnez le type de package. Cliquez sur **Charger**. Allez dans l'emplacement du fichier de package du modèle de partage de données financières et sélectionnez ce fichier.
5. Cliquez sur **Enregistrer**.
6. Dans la liste, marquez la ligne sélectionnée. Sélectionnez la stratégie de partage de données qui vient d'être créée.  
7. Cliquez sur **Importer**.
8. Cliquez sur **Fermer**.
9. Actualisez la page.
10. Fermez la page.
11. Fermez la page.
12. Fermez la page.
13. Accédez à **Volet de navigation > Modules > Administration système > Paramétrage > Configurer le partage de données entre sociétés**.
14. Dans la liste, recherchez et sélectionnez **Jours de paiement**.
15. Cliquez sur **Ajouter**.
16. Dans la liste, marquez la ligne sélectionnée.
17. Dans le champ **Société**, saisissez 'USSI'.
18. Cliquez sur **Ajouter**.
19. Dans le champ **Société**, saisissez 'USMF'.
20. Cliquez sur **Enregistrer**.
21. Cliquez sur **Activer**.
22. Cliquez sur **Oui**.
23. Cliquez sur **Rechercher les problèmes de partage**.
24. Cliquez sur **Oui**.
25. Cliquez sur **Mettre à jour la valeur du champ**.
26. Cliquez sur **Utiliser la valeur depuis la Société 1**.
27. Actualisez la page.
28. Fermez la page.

