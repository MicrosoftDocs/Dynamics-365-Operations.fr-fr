---
title: Prévisions en matière de maintenance
description: Cet article explique les prévisions en matière de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c2dbd968a22f2bded29cff3517dacbafc79ff8f1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902109"
---
# <a name="maintenance-forecasts"></a>Prévisions en matière de maintenance

[!include [banner](../../includes/banner.md)]



Lorsque vous créez un ordre de travail, vous créez des tâches de l’ordre de travail avec des actifs et des types de tâches de maintenance associés. Lorsque vous sélectionnez un type de tâche de maintenance contenant les prévisions en matière de maintenance, les prévisions sont automatiquement copiées vers l’ordre de travail.

Vous pouvez ajouter des lignes de prévision à un ordre de travail ou les supprimer d’un ordre de travail. La configuration de l’état du cycle de vie de l’ordre de travail, le type de projet associé et les règles de stade liées au type de projet déterminent si vous pouvez ajouter ou modifier les lignes de prévision. Pour plus d’informations sur les états du cycle de vie de l’ordre de travail et les étapes du projet associé, consultez [Prévisions, ordres de travail et projets](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l’ordre de travail dans la liste, puis, dans le volet Actions > onglet **Ordre de travail** > groupe **Projet**, sélectionnez **Prévision**. La page **Prévisions en matière de maintenance de l’ordre de travail** affiche les lignes de prévision du type de tâche de maintenance sélectionné sur la tâche de l’ordre de travail.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Ajouter une prévision horaire à un ordre de travail

1. Dans la page **Prévisions en matière de maintenance de l’ordre de travail**, sélectionnez la tâche d’ordre de travail à laquelle ajouter une prévision.

2. Dans l’organisateur **Heures**, sélectionnez **Ajouter** pour créer une ligne.

3. Dans le champ **Catégorie**, sélectionnez une catégorie.

4. Dans le champ **Heures**, insérez le nombre d’heures prévues.

5. Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.


## <a name="add-an-items-forecast-to-a-work-order"></a>Ajouter une prévision d’articles à un ordre de travail

Il existe trois manières d’ajouter des articles à une prévisions en matière de maintenance d’ordre de travail. Vous pouvez créer des lignes pour les articles (pièces détachées) qui ne sont pas inclus dans la liste des pièces détachées ou la nomenclature des actifs, vous pouvez sélectionner des pièces détachées depuis la liste des pièces détachées approuvées, ou vous pouvez sélectionner les articles depuis la nomenclature des actifs.

- Dans la page **Prévisions en matière de maintenance de l’ordre de travail**, sélectionnez la tâche d’ordre de travail à laquelle ajouter une prévision.

- Dans l’organisateur **Articles**, ajoutez des articles à la prévisions en matière de maintenance à l’aide de la méthode approprié.

Pour créer une ligne pour une pièce détachée qui n’est pas sur la liste des pièces détachées ou la liste de nomenclature des actifs, procédez comme suit :

1. Sélectionnez **Ajouter**.
2. Dans le champ **Numéro d’article**, sélectionnez l’article.
3. Dans le champ **Quantité vendue**, entrez la quantité.
4. Dans le champ **Unité**, sélectionnez l’unité de mesure pour la quantité.
5. Dans les champs **Prix de revient** et **Devise**, entrez les valeurs appropriées.
6. Dans le champ **Propriété de ligne**, sélectionnez une propriété de ligne.
7. Pour modifier la liste des dimensions affichées dans les lignes d’article, sélectionnez **Stock** > **Dimensions d’affichage**, sélectionnez les dimensions, et puis définissez **Enregistrer le paramétrage** sur **Oui**.

Pour ajouter une pièce détachée d’une liste des parties disponibles approuvées, procédez comme suit :

1. Sélectionnez **Ajouter des pièces détachées**.
2. Sélectionnez la pièce détachée, et modifiez les informations associées comme vous le souhaitez.
3. Cliquez sur **OK**.

Pour ajouter un article de la nomenclature d’immobilisation, procédez comme suit :

1. Sélectionnez **Ajouter des articles de nomenclature**.
2. Sélectionnez l’article, et modifiez les informations associées comme vous le souhaitez.
3. Cliquez sur **OK**.

Pour avoir une vue d’ensemble de l’emplacement d’utilisation de l’article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche de maintenance, les pièces détachées et les ordres de travail dans Gestion des actifs, sélectionnez **Cas d’emploi d’article**. Pour plus d’informations sur cette vue d’ensemble, voir [Cas d’emploi d’article](../controlling-and-reporting/item-where-used.md).


## <a name="add-an-expense-forecast-to-a-work-order"></a>Ajouter une prévision de dépense à un ordre de travail

1. Dans la page **Prévisions en matière de maintenance de l’ordre de travail**, sélectionnez la tâche d’ordre de travail à laquelle ajouter une prévision.

2. Dans l’organisateur **Dépense**, sélectionnez **Ajouter** pour créer une ligne.

3. Dans le champ **Catégorie**, sélectionnez une catégorie.

4. Dans le champ **Quantité**, entrez la quantité.

5. Dans les champs **Prix de revient**, **Devise de vente** et **Prix de vente**, entrez les valeurs appropriées.

6. Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.

>[!NOTE]
>L’organisateur **Totaux de prévisions de maintenance** affiche une vue d’ensemble du nombre de lignes créées, pour la tâche de l’ordre de travail sélectionnée et pour l’ordre de travail, sous chaque organisateur. Il affiche également le total des heures de travail prévues pour la tâche de l’ordre de travail et pour l’ordre de travail.

L’illustration suivante présente un exemple de la liste de page **Prévisions en matière de maintenance de l’ordre de travail**.

![Figure 1.](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Mise à jour automatique des prévisions de l’ordre de travail

Si les coûts horaires, les coûts d’article et les dépenses sont mises à jour dans d’autres modules dans Microsoft Dynamics 365 for Finance and Operations, les prévisions de l’ordre de travail dans Gestion des actifs peut automatiquement être mis à jour pour refléter ces modifications. Cette capacité permet de garantir que les derniers prix de revient soient toujours utilisés dans vos prévisions d’ordre de travail. Vous pouvez également effectuer des mises à jour similaires pour [prévisions de type de tâche de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Sélectionnez **Gestion des actifs** > **Périodique** > **Prévisions** > **Mettre à jour les prévisions de l’ordre de travail**.

2. Dans la boîte de dialogue **Mettre à jour les prévisions de l’ordre de travail**, sur l’organisateur **Enregistrements à inclure**, vous pouvez ajouter des sélections concernant les ordres de travail spécifiques ou des tâches d’ordre de travail, si nécessaire. Cliquez sur **Filtrer** pour effectuer les sélections appropriées.

3. Sous le raccourci **Exécuter à l’arrière-plan**, vous pouvez configurer la mise à jour automatique comme traitement par lots comme vous le souhaitez.

4. Cliquez sur **OK** pour démarrer la mise à jour des prévisions.


L’illustration suivante présente un exemple de la boîte de dialogue **Mettre à jour les prévisions de l’ordre de travail**.

![Figure 2.](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]