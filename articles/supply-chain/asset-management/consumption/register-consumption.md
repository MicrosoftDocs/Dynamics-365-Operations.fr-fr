---
title: Enregistrer la consommation
description: Cette rubrique explique comment enregistrer la consommation dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2c9bbd51da23ea412bc124f932f73876a9506d47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428002"
---
# <a name="register-consumption"></a>Enregistrer la consommation

[!include [banner](../../includes/banner.md)]

 

Lorsqu'une tâche de maintenance a été effectuée sur un ordre de travail, l'étape suivante consiste à effectuer les enregistrements de la consommation et à valider les journaux. Vous pouvez effectuer les enregistrements sur les types de consommation suivants : heures, articles et dépenses. Les différents types de consommation sont enregistrés et validés sur la page **Journaux des ordres de travail**. Le paramétrage du journal dans **Gestion des actifs** permet de créer et de valider les journaux distincts pour les heures, les articles et les dépenses dans le module **Gestion de projets et comptabilité**.

Dans certains cas, vous pouvez être en mesure d'ajouter ou de supprimer des lignes de prévisions sur un ordre de travail. La configuration d'un état du cycle de vie de l'ordre de travail, le type de projet associé et les règles de stade liées au type de projet déterminent si vous êtes en mesure d'ajouter ou de modifier les lignes de journal. Pour plus d'informations sur les états du cycle de vie de l'ordre de travail et les étapes du projet associé, consultez [Prévisions, ordres de travail et projets](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

>[!NOTE]
>Il est possible de paramétrer la validation automatique des journaux dans un état du cycle de vie de l'ordre de travail. Consultez [États du cycle de vie de l'ordre de travail](../setup-for-work-orders/work-order-lifecycle-states.md) pour en savoir plus.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail, et cliquez sur **Journaux**.

3. Cliquez sur **Copier à partir des prévisions** pour transférer les lignes de prévision qui peuvent être liées à l'ordre de travail. Vous pouvez sélectionner les types de consommation que vous souhaitez transférer.

4. Si nécessaire, vous pouvez ajouter des lignes de consommation sur l'organisateur pertinent en cliquant sur **Ajouter une ligne** et en remplissant les données sur la ligne.

5. Cliquez sur **Valider les journaux** pour valider les lignes de journal avant la validation.

6. Cliquez sur **Valider les journaux** pour valider les lignes de journal.

7. Après avoir validé les journaux de consommation, vous pouvez mettre à jour l'état du cycle de vie de l'ordre de travail. Par exemple, pour indiquer que l'ordre de travail a été terminé, vous pouvez mettre à jour l'état du cycle de vie sur « Terminé ».

    - Dans le champ **Afficher** en haut de la page **Journaux des ordres de travail**, sélectionnez les lignes de journal à afficher : **Toutes**, **Non validées** ou **Validées**. Les journaux validés ont une coche dans la case **Validé**.  
    - Lorsque des lignes d'article sont créées dans le journal des ordres de travail, les dimensions de produit et de suivi associées à l'article sont automatiquement transférées vers la ligne de journal.  

Le capture d'écran suivante présente un exemple des enregistrements d'heure et d'article sur un bon de travail dans **Journaux des ordres de travail**.

![Figure 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>Répartir les heures sur les ordres de travail avec plusieurs tâches de l'ordre de travail

Si un ordre de travail contient plusieurs tâches de l'ordre de travail, vous pouvez enregistrer les heures de travail à l'aide de la fonctionnalité **Répartir les heures**, ce qui signifie qu'une ligne d'enregistrement horaire peut être distribuée de manière uniforme sur chaque tâche de l'ordre de travail.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail et cliquez sur **Journaux**.

3. Sélectionnez la ligne d'enregistrement horaire à fractionner, puis cliquez sur **Fractionner les heures**.

4. Dans la boîte de dialogue **Fractionner les heures sur les tâches de maintenance de l'ordre de travail**, le nom de l'agent qui est connecté est automatiquement affiché dans le champ **Agent**. Si nécessaire, vous pouvez sélectionner un autre agent.

5. Sélectionnez une catégorie pour l'enregistrement des heures dans le champ **Catégorie**.

6. Insérez le nombre d'heures de travail à répartir dans le champ **Heures**.

    ![Figure 2](media/02-consumption.png)

7. Cliquez sur **OK**.

*Exemple :* dans la capture d'écran ci-dessous, les lignes de journal pour un ordre de travail contenant trois tâches d'ordre de travail sont affichées. La première ligne, contenant trois heures de travail, a été fractionnée, et une heure de travail est enregistrée sur chaque tâche de l'ordre de travail. Une fois que trois lignes d'enregistrement horaire ont été créées, vous décidez ce qu'il convient de faire avec la ligne d'enregistrement horaire d'origine (la première ligne dans l'exemple). Vous pouvez la garder telle quelle ou la supprimer. 

![Figure 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Dimensions financières sur les enregistrements de consommation

Lorsque vous effectuez des enregistrements de consommation, les dimensions financières associées aux différents types d'enregistrement sont ajoutées aux enregistrements dans une séquence spécifique. 

- *Enregistrements d'heures et de dépenses :* tout d'abord, les dimensions financières de l'en-tête de journal sont ajoutées, le cas échéant. Ensuite, les dimensions financières du projet de l'ordre de travail associé sont ajoutées. Enfin, les dimensions financières de la ressources (agent) sont ajoutées.

- *Enregistrements de l'article :* tout d'abord, les dimensions financières de l'en-tête de journal sont ajoutées, le cas échéant. Puis, les dimensions financières du projet de l'ordre de travail associé sont ajoutées. Ensuite, les dimensions financières du site sont ajoutées. Enfin, les dimensions financières de l'article sont ajoutées.

>[!NOTE]
>Pour tous les types d'enregistrement, la combinaison de dimensions financières est ajoutée et les combinaisons non valides sont grisées. Ceci est une configuration standard avec d'autres applications Finance and Operations.

