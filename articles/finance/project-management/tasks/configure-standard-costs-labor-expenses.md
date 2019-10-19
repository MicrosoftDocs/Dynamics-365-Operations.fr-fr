---
title: Configurer les coûts standard pour le travail et les dépenses
description: Cette rubrique décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185403"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configurer les coûts standard pour le travail et les dépenses

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet. Cette tâche utilise l'ensemble de données USSI.

1. Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de revient (heure)**.
2. Sélectionnez **Nouveau**.
3. Entrez une date dans le champ **Date d'effet**.
4. Entrez un nombre dans le champ **Prix de revient**. Vous pouvez définir un prix de revient standard pour la catégorie de projet ou un prix de revient par matricule de collaborateur, numéro de projet, catégorie, date ou n'importe quelle combinaison de ces trois éléments. Le prix de revient appliqué est celui dont le niveau de détail est le plus élevé.  
5. Sélectionnez **Enregistrer**.
6. Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de vente (heure)**.
7. Sélectionnez **Nouveau**.
8. Entrez une date dans le champ **Date d'effet**.
9. Dans le champ **Valide pour**, sélectionnez une option.
10. Dans le champ **Tarification**, entrez un nombre. Vous pouvez définir un prix de vente standard pour les transactions horaires ou pour une catégorie de projets. Vous pouvez également paramétrer des prix de vente par matricule de collaborateur, numéro de projet, catégorie, date de transaction ou n'importe quelle combinaison de ces éléments. Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans le journal des heures correspond au prix de vente ayant le plus haut niveau de détail. Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.  
11. Sélectionnez **Enregistrer**.
12. Fermez la page.
13. Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de revient (dépense)**.
14. Sélectionnez **Nouveau**.
15. Entrez une date dans le champ **Date d'effet**.
16. Entrez un nombre dans le champ **Prix de revient**. Plusieurs champs peuvent être renseignés, mais ces éléments constituent le minimum requis pour sauvegarder l'enregistrement.  
17. Sélectionnez **Enregistrer**.
18. Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de vente (dépense)**.
19. Sélectionnez **Nouveau**.
20. Entrez une date dans le champ **Date d'effet**.
21. Dans le champ **Valide pour**, sélectionnez une option.
22. Dans le champ **Tarification**, entrez un nombre. Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans un journal de dépenses est le prix de vente ayant le plus haut niveau de détail. Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.  
23. Sélectionnez **Enregistrer**.

