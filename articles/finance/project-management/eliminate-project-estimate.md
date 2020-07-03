---
title: Éliminer une estimation de projet
description: Cette rubrique fournit des informations sur l'élimination d'une estimation de projet une fois celle-ci terminée.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410218"
---
# <a name="eliminate-a-project-estimate"></a>Éliminer une estimation de projet

[!include [banner](../includes/banner.md)]

Les estimations de projet fournissent la vue financière du travail estimé et planifié pour un projet. Pour utiliser des estimations pour un projet, vous devez associer le projet à un projet d'estimation. Un projet d'estimation est toujours basé sur un projet existant, mais plusieurs projets peuvent faire référence à un seul projet d'estimation. Seuls les projets à prix fixe et les projets d'investissement peuvent être attachés aux projets d'estimation, et ces projets doivent appartenir au même groupe de projets que le projet d'estimation.

Pour éliminer un projet d'estimation, celui-ci doit être terminé. Les étapes suivantes expliquent comment éliminer une estimation.

1. Accédez à **Gestion de projet et comptabilité** > **Tous les projets** et ouvrez le projet. 
2. Dans l'onglet **Gérer**, sélectionnez **Estimations** et dans la page **Estimation**, sélectionnez **Éliminer**.
3. Dans la page **Éliminer l'estimation** de l'onglet **Général**, définissez les options suivantes :

   - **Code période** : sélectionnez le code période pour choisir les projets d'estimation appropriés. 
   - **Date de l'estimation** : sélectionnez la date d'estimation appropriée à éliminer.
   - **Éliminer avec avertissements de travaux en cours** : activez cette option pour fournir une notification lorsqu'une estimation associée à un travail en cours (WIP) va être supprimée. Lorsque cette option n'est pas activée, l'élimination ne peut pas se poursuivre lorsque des transactions non estimées existent. 
   > [!NOTE]
   > Cette option n'est disponible que lorsque l'élimination est appliquée à un projet d'estimation. Elle n'est pas disponible si vous utilisez des validations périodiques. Ce paramètre fonctionne avec les paramètres de l'onglet **Estimation** de la page **Paramètres du projet**, dans le groupe de champs **Autoriser l'élimination lorsque des transactions non estimées existent**.
   - **Définir la phase sur Terminé** : activez cette option pour définir la phase du projet d'estimation sur **Terminé** après avoir exécuté l'élimination.
   - **Imprimer la liste d'estimations** : sélectionnez les informations à inclure lors de l'impression de la liste des projets d'estimation.
   - **Afficher la page Infos** : activez cette option pour afficher la page Infos.
   - **Date de validation** : choisissez la date de validation dans la comptabilité de l'estimation.

4.  Cliquez sur **OK**.
5. Une fois le processus d'élimination terminé, le projet d'estimation éliminé s'affiche avec une valeur négative. 

Si vous n'aviez pas l'intention d'éliminer une estimation, vous pouvez sélectionner l'estimation éliminée et sélectionner **Annuler l'élimination**.   
