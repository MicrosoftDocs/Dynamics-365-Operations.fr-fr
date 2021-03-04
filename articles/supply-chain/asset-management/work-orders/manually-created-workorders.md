---
title: Ordres de travail créés manuellement
description: Cette rubrique explique comment créer des ordres de travail manuellement dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a4b148d9ac5d032d2caa5fcea0398a5a3726f0e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427705"
---
# <a name="manually-created-work-orders"></a>Ordres de travail créés manuellement

[!include [banner](../../includes/banner.md)]


Vous pouvez créer des ordres de travail manuellement de deux façons :

- Sur la page **Tous les ordres de travail** ou **Ordres de travail actifs** 
- Sur la page **Toutes les demandes de maintenance** ou **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**. 

## <a name="create-work-order"></a>Créer un ordre de travail

1. Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez **Nouveau**.

3. Dans la boîte de dialogue **Créer un ordre de travail**, sélectionnez un ordre de travail dans le champ **Type d'ordre de travail**.

4. Le cas échéant, sélectionnez une **Description**.

5. Dans le champ **Actif**, sélectionnez l'actif.

>[!NOTE]
>Lorsque vous sélectionnez un actif, trois onglets peuvent être disponibles dans le menu déroulant **Actif** : 

- **Actifs actifs** - Cet onglet contient la liste de tous les actifs avec un état de cycle de vie de l'actif « Actif ». 
- **Vue des actifs** - Cet onglet affiche une arborescence des postes techniques et les actifs qui y sont installés.
- **Mes actifs** - Cet onglet contient les actifs associées aux postes techniques auxquels vous (le collaborateur connecté au système) pouvez être affecté. (Pour plus d'informations sur le paramétrage, voir [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md).) Si aucun poste technique n'est paramétré sur un collaborateur dans [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md), l'onglet **Mes actifs** n'est pas disponible. 

6. Dans le champ **Type de tâche de maintenance**, sélectionnez le type de tâche de maintenance pour l'ordre de travail.

7. Si nécessaire, sélectionnez **Variante de type de tâche de maintenance** et **Transaction**.

8. Si nécessaire, vous pouvez modifier le niveau de service des ordres de travail dans le champ **Niveau de service**.

9. Sélectionnez les dates de **début prévue** et de **fin prévue** dans les champs associés.

10. Cliquez sur **OK** pour créer l'ordre de travail.

11. Dans la page de liste **Tous les ordres de travail**, vous pouvez modifier l'ordre de travail comme vous le souhaitez.

Notez les points suivants :

- Dans la vue des détails de la page de liste **Tous les ordres de travail**, vous pouvez ajouter plusieurs actifs à un ordre de travail en ajoutant des lignes sur l'organisateur **Tâches de maintenance des ordres de travail**. Sur un actif, vous ne pouvez sélectionner que les types de tâche de maintenance définis sur le type d'actif qui est sélectionné pour l'actif.  

- Si vous modifiez un niveau de service d'actif ou un élément critique d'actif après l'avoir utilisé sur un ordre de travail, le niveau de service ou l'élément critique sur l'ordre de travail n'est pas mis à jour en conséquence. Pour plus d'informations sur les niveaux de service et les éléments critiques, voir [Niveaux de service de l'actif](../setup-for-objects/object-priorities.md) et [Types critiques de l'actif](../setup-for-objects/object-criticalities.md).

- L'élément critique sur un ordre de travail est recalculé chaque fois qu'une tâche d'ordre de travail est ajoutée ou supprimée de l'ordre de travail.

- Dans la vue détaillée **Tous les ordres de travail** > onglet **En-tête** > organisateur **Programme**, dans le champ **Groupe responsable** ou **Responsable**, vous pouvez sélectionner un groupe d'agents de maintenance responsable ou un agent de maintenance responsable. Ces paramètres ne peuvent pas être modifiés lorsque l'ordre de travail est actif. Par exemple, ils peuvent être modifiés lorsque l'état du cycle de vie de l'ordre de travail change. La sélection automatique effectuée lors de la création des ordres de travail est basée sur le paramétrage sur la page **Agents de maintenance responsables**. Si vous ajoutez ou supprimez des tâches d'ordres de travail après avoir créé un ordre de travail, et si le champ **Groupe responsable** et le champ **Responsable** sont vides lorsque vous mettez à jour l'ordre de travail, le module Gestion des actifs essaie de rechercher un groupe d'agents de maintenance responsable ou un agent de maintenance responsable pour une correspondance possible sur la page de paramétrage. Si le champ **Groupe responsable** ou **Responsable** est déjà renseigné lorsque vous mettez un ordre de travail à jour, aucune modification n'est effectuée. Pour plus d'informations sur les agents de maintenance responsables et les groupes collaborateurs, voir [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md).

- Sur la page [Statut de maintenance](../controlling-and-reporting/maintenance-status.md), vous pouvez effectuer un calcul pour obtenir une vue d'ensemble de la charge de travail concernant les ordres de travail entrants et terminés.  

- Dans la vue détaillée de la page **Tous les ordres de travail**, sous l'organisateur **Détails de la ligne**, vous pouvez utiliser les champs **Latitude** et **Longitude** pour ajouter des coordonnées géographiques pour l'actif sélectionné sur la tâche d'ordre de travail.  


## <a name="create-related-work-order"></a>Créer un ordre de travail associé

Vous pouvez créer un ordre de travail associé à un ordre de travail existant. Cette capacité est utile si, par exemple, vous souhaitez utiliser des ordres de travail principaux et secondaires. Un nouvel ordre de travail est basé sur une tâche d'ordre de travail depuis un ordre de travail existant.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail pour lequel créer un ordre de travail associé.

3. Dans le volet Actions, sous l'onglet **Ordre de travail**, dans le groupe **Nouveau**, sélectionnez **Ordre de travail associé**.

4. Dans la boîte de dialogue **Créer un ordre de travail associé**, dans le champ **Tâche d'ordre de travail**, sélectionnez l'ordre de travail pour lequel créer un ordre de travail associé.

5. Sélectionnez un type de tâche de maintenance dans le champ **Type de tâche de maintenance**.

6. Sélectionnez une variante et une transaction associées au type de tâche de maintenance dans les champs **Variante du type de tâche de maintenance** et **Transaction**; au besoin.

7. Si cet ordre de travail est le premier ordre de travail associé créé pour l'ordre de travail sélectionné, procédez comme suit :
    1. Sélectionnez l'option **Nouvel ordre de travail**.
    2. Dans le champ **Type d'ordre de travail**, sélectionnez un type d'ordre de travail.
    3. Entrez une description dans le champ **Description**.
    4. Dans le champ **Niveau de service**, modifiez le niveau de service des ordres de travail au besoin.
    5. Dans les champs **Début prévu** et **Fin prévue**, sélectionnez les dates de début et de fin prévues.
    6. Cliquez sur **OK**. Le nouvel ordre de travail associé est affiché sur la page de liste **Tous les ordres de travail**.  

8. Si l'ordre de travail pour lequel vous créez cet ordre de travail associé a déjà des ordres de travail associés, procédez comme suit pour ajouter une nouvelle tâche d'ordre de travail à un ordre de travail associé existant :
    1. Sélectionnez l'option **Ajouter à l'ordre de travail associé**.
    2. Dans le champ **Ordre de travail**, sélectionnez l'ordre de travail associé auquel vous souhaitez ajouter une nouvelle tâche d'ordre de travail.
    3. Dans le champ **Niveau de service**, modifiez le niveau de service des ordres de travail au besoin.
    4. Dans les champs **Début prévu** et **Fin prévue**, modifiez les dates de début et de fin prévues au besoin.
    5. Cliquez sur **OK**. La tâche de l'ordre de travail est ajoutée à l'ordre de travail associé existant.

L'illustration suivante présente un exemple de la boîte de dialogue **Créer un ordre de travail associé**.

![Figure 1](media/03-work-orders.png)

>[!NOTE]
>Si vous avez configuré un masque d'ordre de travail associé dans **Paramètres de gestion des actifs** > **onglet Ordres de travail** > **Masque de l'ordre de travail associé**, les ID des ordres de travail sont créés selon la configuration du masque. Si aucun masque de l'ordre de travail associé n'est configuré, l'ID de l'ordre de travail suivant disponible est utilisé pour les ordres de travail associés.

## <a name="copy-a-work-order"></a>Copier un ordre de travail

Vous pouvez créer rapidement un ordre de travail depuis un ordre de travail existant. Cette manière d'utiliser les ordres de travail diffère de la création des ordres de travail selon les [plans de maintenance](../preventive-and-reactive-maintenance/maintenance-plans.md). Cela est utile si, par exemple, un ordre de travail contient de nombreuses tâches d'ordre de travail et que les différentes tâches doivent être effectuées sur différents actifs à intervalles réguliers.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail à partir duquel copier le contenu.

3. Dans le volet Actions > onglet **Ordre de travail** > groupe **Nouveau**, sélectionnez **Copier l'ordre de travail**.

4. Le paramétrage des ordres de travail depuis l'ordre de travail sélectionné s'affiche. Vous pouvez modifier certains champs, au besoin.

5. Sélectionnez **OK** pour créer l'ordre de travail.

6. Dans la page de liste **Tous les ordres de travail**, vous pouvez modifier l'ordre de travail comme vous le souhaitez.

>[!NOTE]
>Lorsque l'ordre des travail est créé, certaines informations sont copiées directement depuis l'ordre de travail existant. Les informations sur les prévisions, les outils, les listes de contrôle de maintenance, le poste technique, les adresses et la planification ne sont pas copiées. Au lieu de cela, elles ont initialisées par le paramétrage actuel du module Gestion d'actifs. Par conséquent, si ces informations ont été modifiées entre le moment où le premier ordre de travail a été créé et le moment où vous avez créé une copie de l'ordre de travail, les modifications sont incluses dans le nouvel ordre de travail. Des exemples incluent des prévisions ou des mises à jour des listes de contrôle de maintenance.

L'illustration suivante présente un exemple de la boîte de dialogue **Copier un ordre de travail**.

![Figure 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Créer un ordre de travail à partir d'une demande de maintenance

1. Sélectionnez **Gestion des actifs** > **Commun** > **Demandes de maintenance** > **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.

2. Sélectionnez la demande de maintenance pour laquelle créer un ordre de travail et cliquez sur **Modifier**.

3. Dans le volet Actions > onglet **Demande de maintenance** > groupe **Nouveau**, sélectionnez **Ordre de travail**.

4. Dans la boîte de dialogue **Ordre de travail**, définissez les champs. Si un type de tâche de maintenance a été sélectionné dans la demande de maintenance, vous pouvez sélectionner un autre type de tâche de maintenance, lorsque vous créez l'ordre de travail, au besoin.

5. Cliquez sur **OK**. Un message vous informe qu'un ordre de travail a été créé.

6. Pour afficher les ordres de travail associés à une demande de maintenance, dans les listes **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**, sélectionnez la demande de maintenance. Ensuite, dans le volet Actions, sous l'onglet **Demande de maintenance**, dans le groupe **Nouveau**, sélectionnez **Ordres de travail**.


L'illustration suivante présente un exemple de la boîte de dialogue **Créer un ordre de travail**.

![Figure 3](media/05-work-orders.png)


>[!NOTE]
>Si vous souhaitez que les ordres de travail soient créés automatiquement, vous pouvez planifier des tâches de plan de maintenance, ou paramétrer la « Création automatique » des [plans de maintenance](../preventive-and-reactive-maintenance/maintenance-plans.md) ou des [visites de maintenance](../preventive-and-reactive-maintenance/maintenance-rounds.md) sur un actif. Les ordres de travail créés depuis les demandes de maintenance sur la page de liste **Tout le programme de maintenance** sont des types de tâches de maintenance sélectionnés dans les demandes de maintenance.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]