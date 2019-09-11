---
title: Ordres de travail créés manuellement
description: Cette rubrique explique comment créer des ordres de travail manuellement dans le module Gestion des actifs.
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
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875650"
---
# <a name="manually-created-work-orders"></a>Ordres de travail créés manuellement

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Vous pouvez créer des ordres de travail manuellement de deux façons :

- dans **Tous les ordres de travail** ou **Ordres de travail actifs**  
- dans **Toutes les demandes de maintenance** ou **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**.  

## <a name="create-work-order"></a>Créer un ordre de travail

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Cliquez sur le bouton **Nouveau**.

3. Dans le menu déroulant **Créer le bon de travail**, sélectionnez un type d'ordre de travail.

4. Le cas échéant, sélectionnez une description.

5. Sélectionnez l'actif pour l'ordre de travail ainsi que le type de tâche de maintenance.

>[!NOTE]
>Lorsque vous sélectionnez un actif, trois onglets peuvent être disponibles : L'onglet **Mes actifs** contient des actifs associés à des postes techniques dans lesquels vous (l'agent de maintenance connecté au système) pouvez être affecté(e) (configuré dans [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md)). Si aucun poste technique n'est paramétré sur un agent de maintenance dans l'écran [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md), l'onglet **Mes actifs** ne sera pas visible. L'onglet **Actifs actifs** contient la liste de tous les actifs avec l'état de cycle de vie de l'actif « Actif ». L'onglet **Vue des actifs** affiche une arborescence des postes techniques et des actifs installés sur ces emplacements.

6. Si nécessaire, sélectionnez **Variante de type de tâche de maintenance** et **Transaction**.

7. Si nécessaire, vous pouvez modifier le niveau de service des ordres de travail dans le champ **Niveau de service**.

8. Sélectionnez les dates de début et de fin prévues dans les champs associés.

9. Cliquez sur **OK** pour créer un ordre de travail.

10. Modifiez l'ordre de travail dans **Tous les ordres de travail**, si nécessaire.

- Dans **Tous les ordres de travail**, vous pouvez ajouter plusieurs actifs à un ordre de travail dans la vue détaillée en ajoutant des lignes sur l'organisateur **Tâches de maintenance des ordres de travail**. Sur un actif, vous ne pouvez sélectionner que les types de tâche de maintenance définis sur le type d'actif sélectionné pour l'actif.  
- Si vous avez modifié un niveau de service d'actif ou un élément critique d'actif après les avoir utilisés sur un ordre de travail (consultez [Niveaux de service d'actif](../setup-for-objects/object-priorities.md) associez et [Criticalities d'immobilisation](../setup-for-objects/object-criticalities.md)), le niveau de service ou l'élément critique sur l'ordre de travail qui n'est pas mis à jour en conséquence.
- L'élément critique sur un ordre de travail est recalculé chaque fois qu'une ligne d'ordre de travail est ajoutée ou supprimée de l'ordre de travail.
- Dans la vue détaillée **Tous les ordres de travail** Vue détaillée > vue **En-tête** > organisateur **Programme**, vous pouvez sélectionner un groupe d'agents de maintenance responsable ou un agent de maintenance responsable dans les champs **Groupe responsable** ou **Responsable**. Ces paramètres peuvent être modifiés dans la mesure où l'ordre de travail est actif, par exemple, lorsque l'état du cycle de vie de l'ordre de travail change. La sélection automatique effectuée lors de la création des ordres de travail est basée sur le paramétrage dans **Agents de maintenance responsables**. Si vous ajoutez ou supprimez des tâches d'ordres de travail après avoir créé un ordre de travail, et si le champ **Groupe responsable** et le champ **Responsable** sont vides lorsque vous mettez à jour l'ordre de travail, le module Gestion des actifs recherche une correspondance possible dans le formulaire de paramétrage pour un groupe d'agents de maintenance responsable ou un agent de maintenance responsable. Si le champ **Groupe responsable** ou le champ **Responsable** est déjà rempli lorsque vous mettez un ordre de travail à jour, aucune modification n'est effectuée. 

- Dans **Statut de maintenance**, vous pouvez effectuer un calcul pour obtenir une vue d'ensemble de la charge de travail concernant les ordres de travail entrants et terminés.  

- Dans l'organisateur **Détails de ligne**, utilisez les champs **Latitude** et **Longitude** pour ajouter des coordonnées géographiques pour l'actif sélectionné sur la tâche de l'ordre de travail.  

## <a name="create-related-work-order"></a>Créer un ordre de travail associé

Vous pouvez créer un ordre de travail associé à un ordre de travail existant, par exemple, si vous souhaitez travailler avec les ordres de travail principaux et secondaires. Un nouvel ordre de travail est basé sur une tâche d'ordre de travail depuis un ordre de travail existant.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail pour lequel vous souhaitez effectuer un ordre de travail associé.

3. Cliquez sur **Ordre de travail associé**.

4. Dans la boîte de dialogue de menu déroulant **Créer un ordre de travail associé**, sélectionnez la tâche de l'ordre de travail pour laquelle vous souhaitez créer un ordre de travail associé dans le champ **Tâche de l'ordre de travail**.

5. Sélectionnez un type de tâche de maintenance dans le champ **Type de tâche de maintenance** et, le cas échéant, une variante du type de tâche de maintenance associée et la transaction dans les champs **Variante de type de tâche de maintenance** et **Transaction**.

6. Si c'est le premier ordre de travail associé effectué, cliquez sur la case d'option **Nouvel ordre de travail**.

7. Sélectionnez un **Type d'ordre de travail** et une **Description** dans les champs associés.

8. Si nécessaire, modifiez le niveau de service des ordres de travail dans le champ **Niveau de service**.

9. Insérez les dates de début et de fin prévues dans les champs associés.

10. Cliquez sur **OK**. Le nouvel ordre de travail associé est affiché dans la liste **Tous les ordres de travail**.

11. Si vous créez un ordre de travail associé sur un ordre de travail qui a déjà des ordres de travail associés, vous pouvez ajouter la tâche de l'ordre de travail à un ordre de travail déjà associé. Cela est effectué en cliquant sur la case d'option **Ajouter à l'ordre de travail associé** à l'étape 6. Puis vous sélectionnez l'ordre de travail associé auquel vous souhaitez ajouter une nouvelle tâche d'ordre de travail. Modifiez les champs **Niveau de service**, **Début prévu** et **Fin prévue**, le cas échéant, et cliquez sur **OK**. La tâche de l'ordre de travail est ajoutée à l'ordre de travail associé existant.


![Figure 1](media/03-work-orders.png)

**Remarque :** Si vous avez configuré un masque d'ordre de travail associé dans **Paramètres de gestion des actifs** > **Ordres de travail** lien > **Masque de l'ordre de travail associé**, les ID des ordres de travail seront créés selon la configuration du masque. Si aucun masque de l'ordre de travail associé n'est configuré, l'ID de l'ordre de travail suivant disponible sera utilisé pour les ordres de travail associés.

## <a name="copy-work-order"></a>Copier l'ordre de travail

Il est possible de créer rapidement un ordre de travail récents depuis un ordre de travail existant. Cette manière d'utiliser les ordres de travail diffère de la création des ordres de travail selon les plans de maintenance. Cela est utile si, par exemple, vous avez un ordre de travail contenant de nombreuses tâches d'ordre de travail avec différentes tâches sur différents actifs qui doivent être terminées à intervalles réguliers.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail à partir duquel vous souhaitez copier le contenu.

3. Cliquez sur **Copier l'ordre de travail**. Le paramétrage des ordres de travail depuis l'ordre de travail sélectionné s'affiche. Si nécessaire, vous pouvez modifier certains champs.

4. Cliquez sur **OK** pour créer l'ordre de travail.

5. Modifiez l'ordre de travail dans **Tous les ordres de travail**, si nécessaire.

>[!NOTE]
>Lorsque l'ordre des travail est créé, certaines informations sont copiées directement depuis l'ordre de travail existant. Les informations concernant les prévisions, les outils, les listes de contrôle de maintenance, le poste technique, les adresses et la planification ne sont pas copiés, mais initialisés depuis le paramétrage actuel dans le module Gestion des actifs. Cela signifie que si des modifications ont été apportées à ces données à la création du premier ordre de travail jusqu'à ce que vous effectuiez une copie de l'ordre de travail, ces modifications sont incluses dans le nouvel ordre de travail que vous avez créé. Des exemples de modifications sont les prévisions ou les listes de contrôle de maintenance mises à jour.


![Figure 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Créer un ordre de travail à partir d'une demande de maintenance

1. Cliquez sur **Gestion des actifs** > **Commun** > **Demandes de maintenance** > **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.

2. Sélectionnez la demande de maintenance pour laquelle vous souhaitez créer un ordre de travail et cliquez sur **Modifier**.

3. Dans **Tous les demandes**, cliquez sur **Ordre de travail**.

4. Complétez le menu déroulant **Ordre de travail**. Si un type de tâche de maintenance a été sélectionné dans la demande de maintenance, vous pouvez sélectionner un autre type de tâche de maintenance, au besoin, lorsque vous créez l'ordre de travail.

5. Cliquez sur **OK**. Vous allez voir un message vous informant que l'ordre de travail a été créé.

6. Si vous souhaitez afficher les ordres de travail qui sont associés à une demande de maintenance, sélectionnez la demande de maintenance dans les listes **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**, puis cliquez sur le bouton **Ordres de travail**.


![Figure 3](media/05-work-orders.png)


>[!NOTE]
>Les ordres de travail peuvent également être créés automatiquement lors de la planification des tâches de plan de maintenance, ou en paramétrant la « Création automatique » des plans de maintenance ou des visites de maintenance sur un actif. Les ordres de travail créés depuis les demandes de maintenance dans **Programme de maintenance** sont créés avec des types de tâches de maintenance sélectionnés dans les demandes de maintenance.

