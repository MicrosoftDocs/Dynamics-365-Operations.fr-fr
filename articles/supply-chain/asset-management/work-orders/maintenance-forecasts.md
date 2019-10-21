---
title: Prévisions en matière de maintenance
description: Cette rubrique explique les prévisions en matière de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024497"
---
# <a name="maintenance-forecasts"></a>Prévisions en matière de maintenance

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Lorsque vous créez un ordre de travail, vous créez des tâches de l'ordre de travail avec des actifs et des types de tâches de maintenance associés. Lorsque vous sélectionnez un type de tâche de maintenance contenant les prévisions en matière de maintenance, les prévisions sont automatiquement copiées vers l'ordre de travail.

Vous pouvez être en mesure d'ajouter ou de supprimer des lignes de prévisions sur un ordre de travail. La configuration d'un état du cycle de vie de l'ordre de travail, le type de projet associé et les règles de stade liées au type de projet déterminent si vous êtes en mesure d'ajouter ou de modifier les lignes de prévision. 

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail dans la liste et cliquez sur **Prévisions**. Dans **Prévisions en matière de maintenance de l'ordre de travail**, les lignes de prévision du type de tâche de maintenance sélectionné sur la tâche de l'ordre de travail sont affichées.


## <a name="add-hours-forecast-to-a-work-order"></a>Ajouter des prévisions horaires à un ordre de travail

1. Sélectionnez la tâche de l'ordre de travail auquel vous souhaitez ajouter une prévision.

2. Dans l'organisateur **Heures**, cliquez sur **Ajouter** pour créer une ligne.

3. Sélectionnez une catégorie dans le champ **Catégorie**.

4. Insérez le nombre d'heures prévues dans le champ **Heures**.

5. Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.


## <a name="add-items-forecast-to-a-work-order"></a>Ajouter des prévisions d'articles à un ordre de travail

Il existe trois façons d'ajouter des articles à des prévisions en matière de maintenance à un ordre de travail : vous pouvez créer des lignes pour les articles (pièces détachées) qui ne sont pas inclus dans la liste des pièces détachées ou la nomenclature des actifs, vous pouvez sélectionner des pièces détachées depuis la liste des pièces détachées approuvées, et vous pouvez sélectionner les articles depuis la nomenclature des actifs.

1. Sélectionnez la tâche de l'ordre de travail auquel vous souhaitez ajouter une prévision.

2. Sélectionnez l'organisateur **Articles**.

3. Cliquez sur **Ajouter** pour créer une ligne pour une pièce détachée qui n'est pas sur la liste des pièces détachées ou la liste de nomenclature des actifs.

4. Sélectionnez l'élément dans le champ **Numéro d'article**.

5. Insérez la quantité dans le champ **Quantité vendue**, puis sélectionnez une unité de quantité dans le champ **Unité**.

6. Insérez le prix de revient et la devise dans les champs appropriés, puis sélectionnez **Propriété de ligne**.

7. Si vous souhaitez modifier la liste des dimensions affichées dans les lignes d'article, cliquez sur **Stock** > **Dimensions d'affichage**, sélectionnez les dimensions, et sélectionnez « Oui » sur le bouton à bascule **Enregistrer le paramétrage**.

8. Si vous souhaitez ajouter une pièce détachée approuvée aux prévisions en matière de maintenance, cliquez sur **Ajoutez des pièces détachées**, sélectionnez la pièce détachée, modifiez les informations associées au besoin, puis cliquez sur **OK**.

9. Si vous voulez ajouter des articles de nomenclature des actifs aux prévisions, cliquez sur **Ajouter des articles de nomenclature**, sélectionnez l'article, modifiez les informations associées au besoin, puis cliquez sur **OK**.

10. Cliquez sur **Cas d'emploi d'article** si vous souhaitez obtenir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée dans le module Gestion des actifs, en ce qui concerne les actifs, le type de tâche de maintenance par défaut, les pièces détachées et les ordres de travail. 



## <a name="add-expense-forecast-to-a-work-order"></a>Ajouter des prévisions de dépense à un ordre de travail

1. Cette rubrique explique comment ajouter des prévisions de dépense à un ordre de travail. À gauche de l'écran, sélectionnez la tâche de l'ordre de travail à laquelle vous souhaitez ajouter une prévision.

2. Sélectionnez l'organisateur **Dépense**.

3. Cliquez sur **Ajouter** pour créer une ligne.

4. Sélectionnez une catégorie dans le champ **Catégorie**.

5. Insérez la quantité dans le champ **Quantité**.

6. Insérez le prix de revient, la devise de vente et le prix de vente dans les champs appropriés.

7. Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.

>[!NOTE]
>Dans l'organisateur **Totaux de prévisions de maintenance**, vous voyez une vue d'ensemble du nombre de lignes créées sous chaque onglet, pour la tâche de l'ordre de travail sélectionnée et pour l'ordre de travail. En outre, vous pouvez également voir une somme des heures de travail prévues pour la tâche de l'ordre de travail et pour l'ordre de travail.

![Figure 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Mise à jour automatique des prévisions de l'ordre de travail

Dans le module Gestion des actifs, vous pouvez automatiquement mettre à jour les modifications dans les prévisions de l'ordre de travail concernant les coûts horaires, les coûts d'article et les dépenses, qui ont été mises à jour dans d'autres modules. Cela est possible pour veiller à ce que les derniers prix de revient soient toujours utilisés dans vos prévisions d'ordre de travail. Il est également possible d'effectuer des mises à jour similaires pour [prévisions de type de tâche de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Cliquez sur **Gestion des actifs** > **Périodique** > **Prévisions** > **Mettre à jour les prévisions de l'ordre de travail**.

2. Dans la boîte de dialogue de menu déroulant **Mettre à jour les prévisions de l'ordre de travail**, vous pouvez ajouter des sélections concernant les ordres de travail spécifiques ou des tâches d'ordre de travail, si nécessaire. Cliquez sur **Filtre** pour effectuer ces sélections.

3. Le cas échéant, vous pouvez configurer la mise à jour automatique comme traitement par lots sur l'organisateur **Exécuter à l'arrière-plan**.

4. Cliquez sur **OK** pour démarrer la mise à jour des prévisions.


![Figure 2](media/07-work-orders.png)

