---
title: Agents et groupes d'agents de maintenance
description: Cette rubrique décrit les agents et les groupes d'agents de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b81de02f144712786704a46d2096dfb510d5ce68
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017390"
---
# <a name="maintenance-workers-and-worker-groups"></a>Agents et groupes d'agents de maintenance

[!include [banner](../../includes/banner.md)]

 

Cette rubrique décrit les agents et les groupes d'agents de maintenance dans le module Gestion des actifs. Dans le module Gestion des immobilisations, vous pouvez relier des agents de maintenance aux postes techniques. (Pour plus d'informations sur les postes techniques, voir [Créer des postes techniques](../functional-locations/create-functional-locations.md).) Cette fonctionnalité peut être utile si, par exemple, vous planifiez une tâche de maintenance sur une machine située dans le poste technique 01, et vous voulez que cette tâche soit effectuée par des agents de maintenance du même emplacement.

Vous pouvez également créer des groupes d'agents de maintenance et leur associer des agents de maintenance. Cette fonctionnalité est utile lorsque vous effectuez une planification simple des ordres de travail, et vous souhaitez planifier un groupe d'agents de maintenance sur un ordre de travail. Vous pouvez utiliser des agents de maintenance et des groupes d'agents de maintenance pour paramétrer les agents de maintenance préférés et les agents de maintenance responsables. 


## <a name="create-workers"></a>Créer des collaborateurs

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Collaborateurs** \> **Collaborateurs**.
2. Sélectionnez **Nouveau** pour ajouter un collaborateur à la liste.
3. Sélectionnez le collaborateur dans le champ **Collaborateur**.
4. Définissez l'option **Actif** sur **Oui** pour planifier le collaborateur sur les ordres de travail.

    Dans le raccourci **Général**, les champs **Ressource** et **Description** sont automatiquement renseignés si une ressource a été sélectionnée pour le collaborateur. Le champ **Calendrier** est automatiquement renseigné, à condition que vous ayez paramétré le collaborateur comme ressource et affecté un calendrier à cette ressource dans la page **Ressources** (**Administration d'organisation** \> **Ressources** \> **Ressources**).

5. Dans le raccourci **Groupes**, sélectionnez **Ajouter**, puis sélectionnez un groupe d'agents de maintenance pour le collaborateur. Un collaborateur peut être affilié à plusieurs groupes.
6. Dans le paramétrage standard, l'affiliation d'un collaborateur à un groupe est effective à compter de la date d'ajout du groupe, et elle n'expire jamais. Cette date est affichée dans le champ **Date d'effet**. Pour afficher le champ **Date d'effet**, sélectionnez **Afficher** \> **Tous**. Si l'affiliation du collaborateur à un groupe doit être limitée à une période spécifique, utilisez les champs **Date d'effet** et **Date d'expiration** pour définir la période.
7. Dans le raccourci **Postes techniques**, sélectionnez **Ajouter**, puis sélectionnez un poste technique pour l'agent de maintenance. Spécifiez également quel emplacement est le poste technique principal pour le collaborateur.

    > [!NOTE]
    > Lorsque vous ajoutez des postes techniques à un collaborateur, tous les actifs actifs associés à ces postes techniques apparaissent sur les différentes options de menu, telles que **Mes actifs actifs** et **Mes postes techniques actifs**. Ils apparaissent également dans les recherches d'actif qui s'affichent lorsque vous créez un actif, une demande de maintenance ou un ordre de travail.

    Les champs du raccourci **Détails** affichent le nombre de groupes d'agents de maintenance et de postes techniques auxquels est associé l'agent de maintenance sélectionné.

## <a name="create-worker-groups"></a>Créer des groupes d'agents

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Collaborateurs** \> **Groupes d'agents de maintenance**.
2. Sélectionnez **Nouveau** pour ajouter un groupe d'agents à la liste.
3. Dans le champ **Groupe d'agents de maintenance**, entrez un ID groupe.
4. Dans le champ **Nom**, entrez un nom.
5. Dans le raccourci **Collaborateurs**, sélectionnez **Ajouter**, puis sélectionnez un agent de maintenance pour le groupe d'agents. Pour plus d'informations sur les champs **Date d'effet** et **Date d'expiration**, voir l'étape 6 de la procédure précédente.
6. Si un groupe de ressources est associé au groupe d'agents de maintenance sélectionné, sélectionnez **Copier à partir du groupe de ressources**. Dans le champ **Groupe**, sélectionnez le groupe de ressources à partir duquel copier les paramètres de calendrier. Puis, dans le champ **Groupe d'agents**, sélectionnez le groupe d'agents vers lequel copier les paramètres de calendrier du groupe de ressources. Cette étape est utile que si vous souhaitez que les agents de maintenance utilisent le calendrier associé à une ressource (poste de charge) lors de la planification des ordres de travail.

    Le champ du raccourci **Détails** affiche le nombre d'agents de maintenance qui ont été paramétrés sur le groupe d'agents de maintenance sélectionné.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]