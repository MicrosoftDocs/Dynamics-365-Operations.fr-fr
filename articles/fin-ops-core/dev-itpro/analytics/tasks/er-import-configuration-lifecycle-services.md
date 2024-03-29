---
title: Importer une configuration à partir de Lifecycle Services
description: Cet article décrit comment importer une nouvelle version d’une configuration pour la gestion des états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
ms.openlocfilehash: 92c5d010430b38cb6c11a87283a2f7d4c29484f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290362"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Importer une configuration à partir de Lifecycle Services

[!include [banner](../../includes/banner.md)]

Cet article explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut importer une nouvelle version d’une configuration pour la [génération d’états électroniques (ER)](../general-electronic-reporting.md#Configuration) à partir de la [bibliothèque d’actifs au niveau du projet](../../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> L’utilisation de LCS comme référentiel de stockage pour les configurations ER est en cours [d’abandon](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Pour plus d’informations, voir [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).

Dans cet exemple, vous allez sélectionner la version souhaitée de la configuration ER et l’importer pour un exemple société nommée Litware, Inc. Ces étapes peuvent être réalisées dans n’importe quelle société, car les configurations ER sont partagées entre les sociétés. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure [Charger une configuration dans Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). L’accès à LCS est également requis.

1. Se connecter à l’application en utilisant l’un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Administrateur système

2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques**.
3. Sélectionnez **Configurations**.

<a name="accessconditions"></a>
> [!NOTE]
> Assurez-vous que l’utilisateur Dynamics 365 Finance actuel est membre du projet LCS qui contient la bibliothèque d’actifs à laquelle l’utilisateur souhaite [accéder](../../lifecycle-services/asset-library.md#asset-library-support) pour importer des configurations ER.
>
> Vous ne pouvez pas accéder à un projet LCS à partir d’un référentiel ER qui représente un domaine différent du domaine utilisé dans Finance. Si vous essayez, une liste vide de projets LCS s’affichera et vous ne pourrez pas importer de configurations ER à partir de la bibliothèque d’actifs au niveau du projet dans LCS. Pour accéder aux bibliothèques d’actifs au niveau du projet à partir d’un référentiel ER utilisé pour importer des configurations ER, connectez-vous à Finance en utilisant les informations d’identification d’un utilisateur qui appartient au client (domaine) pour lequel l’instance Finance actuelle a été provisionnée.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Supprimer une version partagée d’une configuration du modèle de données

1. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Exemple de configuration de modèle**.

    Vous avez créé la première version d’un exemple de configuration de modèle de données et l’avez publiée dans LCS après avoir exécuté les étapes [Charger une configuration dans Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). Dans cette procédure, vous supprimerez cette version de la configuration ER. Vous importerez ensuite cette version de LCS plus loin dans cet article.

2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.

    Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**. Ce statut indique que la configuration a été publiée dans LCS.

3. Sélectionnez **Modifier le statut**.
4. Sélectionnez **Interrompre**.

    En modifiant le statut de la version sélectionnée de **Partagé** à **Interrompu**, vous rendez la version disponible pour la suppression.

5. Cliquez sur **OK**.
6. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.

    Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Interrompu**.

7. Sélectionnez **Supprimer**.
8. Cliquez sur **Oui**.

    Notez que seule la version temporaire 2 de la configuration de modèle de données sélectionnée est maintenant disponible.

9. Fermez la page.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Importer une version partagée d’une configuration du modèle de données à partir de LCS

1. Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.

2. Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**.

3. Dans la vignette **Litware, Inc.**, sélectionnez **Référentiels**.

    Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.

4. Cliquez sur **Ouvrir**.

    Pour cet exemple, sélectionnez le référentiel **LCS** et ouvrez-le. Vous devez avoir [accès](#accessconditions) au projet LCS et à la bibliothèque d’actifs accessible par le référentiel ER sélectionné.

5. Dans la liste, marquer la ligne sélectionnée.

    Pour cet exemple, sélectionnez la première version **Exemple de configuration de modèle** dans la liste des versions.

6. Sélectionnez **Importer**.
7. Cliquez sur **Oui** pour confirmer l’importation de la version sélectionnée de LCS.

    Un message d’information confirme que la version sélectionnée a été importée avec succès.

8. Fermez la page.
9. Fermez la page.
10. Sélectionner **Configurations**.
11. Dans l’arborescence, sélectionnez **Exemple de configuration de modèle**.
12. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.

    Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.

    Notez que seule la version partagée 1 de la configuration de modèle de données sélectionnée est également disponible.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
