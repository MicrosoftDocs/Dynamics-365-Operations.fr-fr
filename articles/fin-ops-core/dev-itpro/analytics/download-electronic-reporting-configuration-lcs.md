---
title: Télécharger les configurations des états électroniques à partir de Lifecycle Services
description: Cette rubrique explique comment télécharger des configurations d’états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ea603d01d05e98ac69d5a0d12802b5f23ee34793bf4c9b4f885f0e4303f77d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762270"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Télécharger les configurations d’états électroniques à partir de Lifecycle Services

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment télécharger la dernière version de [Configurations de la génération d’états électroniques (ER)](general-electronic-reporting.md#Configuration) de la [Bibliothèque de ressources partagée](../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> L’utilisation de LCS comme référentiel de stockage pour les configurations ER est en cours [d’abandon](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Pour plus d’informations, voir [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).

1. Se connecter à l’application en utilisant l’un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

2. Accédez à **Administration d’organisation** &gt; **Espaces de travail** &gt; **États électroniques**.
3. Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
4. Dans la vignette **Microsoft**, sélectionnez **Référentiels**.

    [![Vignette Microsoft sur la page des configurations de localisation.](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **LCS**. Si ce référentiel n’apparaît pas dans la grille, procédez comme suit :

    1. Sélectionnez **Ajouter** pour ajouter un référentiel.
    2. Sélectionnez **LCS** comme type de référentiel.
    3. Sélectionnez **Créer un référentiel**.
    4. Si vous êtes invité à fournir une autorisation, suivez les instructions à l’écran.
    5. Entrez un nom et une description pour le référentiel.
    6. Cliquez sur **OK** pour confirmer la nouvelle entrée de référentiel.
    7. Dans la grille, sélectionnez le nouveau référentiel de type **LCS**.

6. Sélectionnez **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné.

    [![Page des référentiels de configurations.](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Si vous ne parvenez pas à accéder au référentiel LCS pour télécharger des configurations à partir de la bibliothèque d’actifs partagée dans LCS, vous pouvez télécharger des configurations à partir du [référentiel général](er-download-configurations-global-repo.md).

7. Dans l’arborescence de configurations du volet gauche, sélectionnez la configuration ER requise.
8. Dans l’organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.
9. Cliquez sur **Importer** pour télécharger la version sélectionnée de LCS vers l’instance actuelle.

    > [!NOTE]
    > Le bouton **Importer** n’est pas disponible pour les versions de configuration des états électroniques qui sont déjà présentes dans l’instance actuelle.

    [![Page du référentiel de configuration.](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> Selon les paramètres d’états électroniques, les configurations sont validées après leur importation. Il est possible que vous soyez averti des problèmes d’incohérences qui sont détectés. Vous devez résoudre ces problèmes avant d’utiliser la version de configuration importée. Pour plus d’informations, voir la liste des rubriques associées pour cette rubrique.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)

[Télécharger les configurations ER depuis le référentiel global du service de configuration](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
