---
title: Installer des actifs à des postes techniques
description: Cette rubrique explique comment installer des actifs à des postes techniques dans Gestion des actifs.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 818c7eb86851047fa333fd4df11c8c7534c2a06b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839701"
---
# <a name="install-assets-on-functional-locations"></a>Installer des actifs à des postes techniques

[!include [banner](../../includes/banner.md)]

 

Après avoir créé des structures de postes techniques, l’étape suivante consiste à installer des actifs aux postes techniques appropriés. Cette rubrique explique comment installer des actifs à ces postes techniques dans Gestion des actifs. Pour plus d’informations sur la création d’actifs, voir [Introduction aux actifs](../objects/introduction-to-objects.md).

Si vous avez créé une structure d’actif, l’ensemble de celle-ci doit être installée à un poste technique. Par conséquent, seuls des actifs parents (actifs supérieurs sans actif parent) peuvent être sélectionnés à un poste technique. Tous les actifs enfants associés (sous-actifs) sont également installés au poste technique. Lorsque vous installez des actifs à un poste technique, les dimensions financières de celui-ci peuvent être automatiquement transférées aux actifs, selon le paramétrage du type de poste technique sélectionné pour celui-ci. Pour plus d’informations sur la configuration des types de postes techniques, voir [Types de poste techniques](../setup-for-functional-locations/functional-location-types.md).

> [!NOTE]
> Vous pouvez paramétrer des types d’actifs sur le type de poste technique utilisé pour un poste technique. Dans ce cas, lorsque vous installez des actifs au poste technique, seuls les actifs parents avec le même type d’actif sont affichés dans la liste d’actifs qui peuvent être installés au poste technique.

Après avoir installé les actifs à un poste technique, vous pouvez remplacer un actif parent ou une structure d’actif comme vous le souhaitez. Comme lorsque vous installez des actifs, vous sélectionnez un actif parent à remplacer. Tous les actifs enfants associés sont également être remplacés. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Installation d’une structure d’actif à un poste technique

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Postes techniques** \> **Tous les postes techniques** ou **Postes techniques actifs**.
2. Sélectionnez le poste technique auquel installer l’actif.
3. Sélectionnez **Installer l’actif**.

    La section **Attributs** affiche une liste des exigences d’attribut de l’actif paramétrées sur le type de poste technique sélectionné pour le poste technique. Les attributs sont fournis uniquement à titre indicatif. Le système ne valide pas les attributs par rapport aux attributs de l’actif qui sont paramétrés dans l’actif que vous installez. Vous devez effectuer cette validation après avoir sélectionné un actif dans le champ **Actif**.

4. Dans le champ **Actif**, sélectionnez l’actif parent à installer. Tous les actifs enfants associés sont inclus automatiquement dans l’installation.

    La section **Attributs de l’actif** à droite de la liste des actifs affiche les attributs d’actif associés à l’actif sélectionné.

5. Dans le champ **Date d’effet**, sélectionnez la date et l’heure à partir desquelles l’installation de l’actif est valide. Après la date et l’heure, les coûts de l’actif et les sous-actifs associés sont liés au poste technique.

    > [!NOTE]
    > Les attributs de l’actif qui sont paramétrés sur l’actif sont ajoutés à la section **Attributs**. Par exemple, l’exigence d’attribut **Poids** a été ajoutée comme besoin pour l’actif et le poste technique. Si l’actif présente des exigences d’attribut du même type que le poste technique, les valeurs des exigences d’attribut de l’actif sont entrées dans les champs **Valeur**. Par conséquent, vous pouvez valider les valeurs d’actif par rapport aux exigences d’attributs qui sont paramétrées au poste technique. Les exigences d’attributs paramétrées au poste technique sont marquées d’une coche.

6. Cliquez sur **OK**.

    > [!NOTE]
    > Pour modifier l’installation d’un actif en l’installant à un nouveau poste technique, suivez les étapes 1 à 6 de cette procédure. Lorsque vous installez un actif à un nouveau poste technique, l’actif est automatiquement désinstallé du précédent poste technique. Tous les demandes de maintenance ou ordres de travail actifs créés sur l’actif avant que vous l’ayez installé à un nouveau poste technique ne sont **pas** automatiquement transférées vers le nouveau poste technique. Si ces demandes de maintenance et ordres de travail sont toujours requis pour l’actif, vous devez les recréer manuellement une fois l’actif installé au nouveau poste.

7. Pour afficher une liste de tous les actifs, notamment les sous-actifs, qui sont installés au poste technique, sélectionnez le poste technique à la page **Tous les postes techniques**, puis sélectionnez **Actifs**.
8. Pour afficher une liste des demandes de maintenance actives, des ordres de travail actifs ou des enregistrements de pannes associés aux actifs installés à un poste technique, sélectionnez le poste technique sur la page **Tous les postes techniques**, puis sélectionnez **Demandes**, **Ordres de travail** ou **Défaillances**.

> [!NOTE]
> Lorsque des données liées aux actifs sont modifiées, elles sont automatiquement mises à jour au poste technique où l’actif est installé. Cette mise à jour automatique concerne les modifications apportées aux demandes de maintenance, aux ordres de travail, aux enregistrements de défaillance d’actifs, aux enregistrements de temps d’arrêt pour maintenance et aux enregistrements de mesures d’actif.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Créer automatiquement un actif à un poste technique

Vous pouvez paramétrer des phases de poste technique et des types de postes techniques pour gérer la création automatique d’*un* actif à un poste technique. L’actif obtient les mêmes ID et nom que ceux du poste technique. Cette fonctionnalité peut s’avérer utile lorsque vous gérez la maintenance d’un actif statique et volumineux, comme un bâtiment.

Avant de pouvoir créer automatiquement un actif à un poste technique, les données de paramétrage suivantes doivent être disponibles :

- Créez un type de poste technique pour gérer la création automatique d’un actif. Dans le champ **Type d’actif**, sélectionnez un type d’actif. Pour plus d’informations, voir [Types de postes techniques](../setup-for-functional-locations/functional-location-types.md).
- Créez un état du cycle de vie du poste technique pour gérer la création automatique d’un actif. Définissez l’option **Créer un actif** sur **Oui**. Pour plus d’informations, voir [États du cycle de vie du poste technique](../setup-for-functional-locations/functional-location-stages.md).

Une fois les données de paramétrage disponibles, vous êtes prêt à créer un actif.

1. Sur la page **Tous les postes techniques**, assurez-vous que le poste technique auquel vous souhaitez que l’actif soit créé automatiquement utilise le type de poste technique créé à cet effet.
2. Sélectionnez le poste technique dans la liste.
3. Sélectionnez **Mettre à jour l’état du poste technique**, puis sélectionnez l’état du cycle de vie créé à cet effet. Un actif est désormais automatiquement installé au poste technique. Cet actif porte le même nom que celui du poste technique.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]