---
title: Télécharger les configurations des états électroniques à partir de Lifecycle Services
description: Cette rubrique explique comment télécharger des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 49785835ee2da911d7b8d1360e1c42f850f1153f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771491"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Télécharger les configurations d'états électroniques à partir de Lifecycle Services

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment télécharger des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).

Ce didacticiel vous guide via le processus de téléchargement de la version la plus récente des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).

1. Se connecter à l'application en utilisant l'un des rôles suivants :

    - Développeur d'états électroniques
    - Consultant fonctionnel de gestion des états électroniques
    - Administrateur système

2. Allez dans **Administration d'organisation** &gt; **États électroniques**.
3. Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
4. Dans la vignette **Microsoft**, cliquez sur **Référentiels**.

    [![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **LCS**. Si ce référentiel n'apparaît pas dans la grille, procédez comme suit :

    1. Cliquez sur **Ajouter** pour ajouter un nouveau référentiel.
    2. Sélectionnez **LCS** comme type de référentiel.
    3. Cliquez sur **Créer un référentiel**.
    4. Si vous recevez une invite, suivez les instructions d'autorisation.
    5. Entrez un nom et une description pour le référentiel.
    6. Cliquez **OK** pour confirmer la nouvelle entrée de référentiel.
    7. Dans la grille, sélectionnez le nouveau référentiel de type **LCS**.

6. Cliquez sur **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné.

    [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

7. Dans l'arborescence de configurations du volet gauche, sélectionnez la configuration ER voulue.
8. Dans l'organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.
9. Cliquez sur **Importer** pour télécharger la version sélectionnée de LCS vers l'instance actuelle.

    > [!NOTE]
    > Le bouton **Importer** n'est pas disponible pour les versions de configuration des états électroniques qui sont déjà présentes dans l'instance actuelle.

    [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> Selon les paramètres d'états électroniques, les configurations sont validées après leur importation. Il est possible que vous soyez averti des problèmes d'incohérences qui sont détectés. Vous devez résoudre ces problèmes avant d'utiliser la version de configuration importée. Pour plus d'informations, voir la liste des articles associés pour cette rubrique.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des états électroniques (ER)](general-electronic-reporting.md)
