---
title: Télécharger les configurations ER depuis le référentiel global du service de configuration
description: Cette rubrique explique comment télécharger des configurations de gestion des états électroniques (ER) à partir du référentiel global du service de configuration.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: a96e78a64fe0559ae5f3bfddabf3fe1cad8a3dcb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679556"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>Télécharger les configurations ER depuis le référentiel global du service de configuration

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment télécharger des [configurations de gestion des états électroniques (ER)](general-electronic-reporting.md#Configuration) à partir du référentiel global du service de configuration. Pour plus d’informations, voir [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, service de configuration](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Ouvrir le référentiel de configurations

1. Connectez-vous à l’application Dynamics 365 Finance en utilisant l’un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

2. Accédez à **Administration d’organisation > Espaces de travail > États électroniques**.
3. Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
3. Dans la vignette **Microsoft**, sélectionnez **Référentiels**.

    ![Espace de travail des états électroniques](./media/er-download-configurations-global-repo-er-workspace.png)

4. Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **Global**. Si ce référentiel n’apparaît pas dans la grille, procédez comme suit :

    1. Sélectionnez **Ajouter** pour ajouter un nouveau référentiel.
    2. Sélectionnez **Global** comme type de référentiel, puis sélectionnez **Créer un référentiel**.
    3. Si vous recevez une invite, suivez les instructions d’autorisation.
    4. Saisissez un nom et une description pour le référentiel, puis sélectionnez **OK** pour confirmer la nouvelle entrée de référentiel.
    5. Dans la grille, sélectionnez le nouveau référentiel de type **Global**.

5. Sélectionnez **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné.

    ![Page des référentiels de configurations](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Importer une configuration unique

1. Dans la page **Référentiels de configurations**, dans l’arborescence des configurations, sélectionnez la configuration ER souhaitée.
2. Dans l’organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.
3. Sélectionnez **Importer** pour télécharger la version sélectionnée depuis le référentiel global vers l’instance Finance and Operations actuelle.

    > [!NOTE]
    > Le bouton **Importer** n’est pas disponible pour les versions de configuration de gestion des états électroniques qui sont déjà présentes dans l’instance Finance actuelle.

    ![Page du référentiel de configuration](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Importer des configurations filtrées

1. Dans la page **Référentiels de configurations**, dans l’arborescence des configurations, développez le raccourci **Filtre**.
2. Dans la grille **Balises**, ajoutez les balises nécessaires.
3. Dans le champ **Applicabilité par pays/région**, sélectionnez les codes de pays/région appropriés, puis sélectionnez **Appliquer le filtre**.

    > [!NOTE]
    > Le raccourci **Configurations** affiche toutes les configurations qui satisfont aux conditions de sélection spécifiées.

4. Dans le raccourci **Configurations**, sélectionnez **Importer** pour télécharger les configurations filtrées depuis le référentiel global vers l’instance actuelle.
5. Dans le raccourci **Configurations**, sélectionnez **Réinitialiser le filtre** pour effacer les conditions de sélection spécifiées.

    ![Page du référentiel de configuration](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> Selon les paramètres d’états électroniques, les configurations sont validées après leur importation. Il est possible que vous soyez averti des problèmes d’incohérences qui sont détectés. Avant de pouvoir utiliser la version de configuration importée, vous devez résoudre les problèmes. Pour plus d’informations, voir la liste des ressources associées pour cette rubrique.

> [!NOTE]
> Les configurations de gestion des états électroniques peuvent être configurées comme dépendantes d’autres configurations. Par conséquent, d’autres configurations peuvent être automatiquement importées avec une configuration sélectionnée. Pour plus d’informations sur les dépendances des configurations, voir [Définir la dépendance des configurations ER à d’autres composants](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)
