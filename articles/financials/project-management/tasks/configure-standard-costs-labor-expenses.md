---
title: Configurer les coûts standard pour le travail et les dépenses
description: Cette procédure décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "339393"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configurer les coûts standard pour le travail et les dépenses

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet. Cette tâche utilise l'ensemble de données USSI.

1. Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de revient (heure).
2. Cliquez sur Nouveau.
3. Entrez une date dans le champ Date d'effet.
4. Dans le champ Prix de revient, entrez un nombre.
    * Vous pouvez définir un prix de revient standard pour la catégorie de projet ou un prix de revient par matricule de collaborateur, numéro de projet, catégorie, date ou n'importe quelle combinaison de ces trois éléments. Le prix de revient appliqué est celui dont le niveau de détail est le plus élevé.  
5. Cliquez sur Enregistrer.
6. Fermez la page.
7. Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de vente (heure).
8. Cliquez sur Nouveau.
9. Entrez une date dans le champ Date d'effet.
10. Dans le champ Valide pour, sélectionnez une option.
11. Dans le champ Tarification, entrez un nombre.
    * Vous pouvez définir un prix de vente standard pour les transactions horaires ou pour une catégorie de projets. Vous pouvez également paramétrer des prix de vente par matricule de collaborateur, numéro de projet, catégorie, date de transaction ou n'importe quelle combinaison de ces éléments. Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans le journal des heures correspond au prix de vente ayant le plus haut niveau de détail. Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.  
12. Cliquez sur Enregistrer.
13. Fermez la page.
14. Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de revient (dépense).
15. Cliquez sur Nouveau.
16. Entrez une date dans le champ Date d'effet.
17. Dans le champ Prix de revient, entrez un nombre.
    * Plusieurs champs peuvent être renseignés, mais ces éléments constituent le minimum requis pour sauvegarder l'enregistrement.  
18. Cliquez sur Enregistrer.
19. Fermez la page.
20. Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de vente (dépense).
21. Cliquez sur Nouveau.
22. Entrez une date dans le champ Date d'effet.
23. Dans le champ Valide pour, sélectionnez une option.
24. Dans le champ Tarification, entrez un nombre.
    * Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans un journal de dépenses est le prix de vente ayant le plus haut niveau de détail. Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.  
25. Cliquez sur Enregistrer.

