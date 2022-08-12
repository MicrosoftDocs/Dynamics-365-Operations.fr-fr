---
title: Importer des versions mises à jour des configurations de gestion des états électroniques
description: Cet article explique comment importer des versions mises à jour des configurations de gestion des états électroniques depuis le référentiel global du service de configuration.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 0dac106a592a6a70aae6b245bce74d21c98cad10
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108437"
---
# <a name="import-updated-versions-of-er-configurations"></a>Importer des versions mises à jour des configurations de gestion des états électroniques

[!include [banner](../includes/banner.md)]

Les [référentiels](general-electronic-reporting.md#Repository) de gestion des états électroniques sont utilisés pour partager des [configurations de gestion des états électroniques](general-electronic-reporting.md#Configuration). Vous pouvez [importer](download-electronic-reporting-configuration-lcs.md) des configurations de gestion des états électroniques depuis différents référentiels vers votre instance de Microsoft Dynamics 365 Finance. Lorsque vous importez des configurations de gestion des états électroniques, les [fournisseurs de configuration](general-electronic-reporting.md#Provider) peuvent publier de nouveaux référentiels de [versions](general-electronic-reporting.md#component-versioning) afin de pouvoir les partager.

Cet article explique comment importer des versions mises à jour des configurations de gestion des états électroniques depuis le référentiel global du service de configuration. Pour plus d’informations, voir [Microsoft Dynamics 365 Finance – Regulatory Services, service de configuration](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>Consulter les versions mises à jour disponibles

1. Connectez-vous à Finance en utilisant l’un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Importer les mises à jour des versions de configurations**.

    ![Page Configurations de localisation.](./media/er-download-updated-versions-global-repo1.png)

4. Dans la boîte de dialogue **Importer les mises à jour des versions des configurations de gestion des états électroniques**, dans le champ **Mode d’exécution**, sélectionnez **Afficher uniquement les mises à jour disponibles**. Puis sélectionnez **OK**. 

    ![Champ Mode d’exécution défini sur Afficher uniquement les mises à jour disponibles.](./media/er-download-updated-versions-global-repo2.png)

5. Passez en revue les messages que vous recevez. Ces messages fournissent les informations suivantes sur les configurations de gestion des états électroniques dans l’instance actuelle de Finance et la façon de les comparer au contenu du référentiel global :

    - Le nombre total de configurations de gestion des états électroniques
    - Les configurations de gestion des états électroniques qui ne sont pas présentes dans le référentiel global
    - Les configurations de gestion des états électroniques pour lesquelles la dernière version est déjà disponible dans l’instance actuelle de Finance (Pour afficher la liste complète de ces configurations de gestion des états électroniques, sélectionnez le lien **Détails du message**.)

        ![Le message « Les dernières versions des configurations suivantes sont déjà importées » et les détails du message](./media/er-download-updated-versions-global-repo3.png)

    - Les configurations de gestion des états électroniques pour lesquelles la dernière version est disponible dans le référentiel global et qui peuvent être importées dans l’instance actuelle de Finance (Pour afficher la liste complète de ces configurations de gestion des états électroniques, sélectionnez le lien **Détails du message**.)

        ![Le message « Mises à jour disponibles » et les détails du message](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>Importer les versions mises à jour disponibles

1. Connectez-vous à Finance en utilisant l’un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Importer les mises à jour des versions de configurations**.
4. Dans la boîte de dialogue **Importer les mises à jour des versions des configurations de gestion des états électroniques**, dans le champ **Mode d’exécution**, sélectionnez **Importer les dernières mises à jour** pour importer les dernières versions des configurations de gestion des états électroniques depuis le référentiel global vers l’instance actuelle de Finance.
5. Pour planifier un traitement par lots pour l’importation, sur l’organisateur **Exécuter à l’arrière-plan**, définissez l’option **Traitement par lots** sur **Oui**. Si vous souhaitez répéter l’importation régulièrement, configurez la périodicité requise.

    ![Champ Mode d’exécution défini sur Importer les dernières mises à jour.](./media/er-download-updated-versions-global-repo5.png)

6. Cliquez sur **OK**.
7. Pour savoir quelles versions de configuration ont été importées, procédez comme suit :

    - Si vous exécutez l’importation de manière interactive au lieu d’utiliser un traitement par lots, consultez les messages que vous recevez.

        ![Messages reçus lors de l’exécution d’une importation interactive.](./media/er-download-updated-versions-global-repo6.png)

    - Si vous exécutez l’importation en mode de traitement par lots, procédez comme suit :

        1. Allez dans **Commun** \> **Recherches** \> **Traitements par lots** \> **Mes traitements par lots**.
        2. Recherchez et sélectionnez le travail **Importer les mises à jour des versions des configurations de gestion des états électroniques**, puis, dans le volet Actions, sous l’onglet **Traitement par lots**, sélectionnez **Historique des traitements par lots** pour afficher l’historique des travaux.
        3. Sur la page **Historique des traitements par lots**, sélectionnez **Journal**. Ensuite, dans le message que vous recevez, sélectionnez le lien **Détails du message** pour afficher le journal des travaux.

        ![Journal des travaux.](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> Il n’est pas recommandé de planifier un traitement par lots récurrent pour importer des versions mises à jour des configurations de gestion des états électroniques directement depuis le référentiel global vers un environnement de production, car les versions importées seront immédiatement disponibles pour utilisation. Utilisez plutôt cette approche pour déployer des versions des configurations de gestion des états électroniques dans un environnement de bac à sable. Elles peuvent ensuite être évaluées dans l’environnement de bac à sable avant d’être déployées dans un environnement de production.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des états électroniques](general-electronic-reporting.md)
- [Télécharger les configurations ER depuis le référentiel global du service de configuration](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
