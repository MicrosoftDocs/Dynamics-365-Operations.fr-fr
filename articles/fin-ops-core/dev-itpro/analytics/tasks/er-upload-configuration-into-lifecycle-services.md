---
title: Charger une configuration dans Lifecycle Services
description: Cet article explique comment créer une configuration pour la gestion des états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
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
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
ms.openlocfilehash: 28ad20956b4b621abdb74332187d8601c10ac164
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290062"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Charger une configuration dans Lifecycle Services

[!include [banner](../../includes/banner.md)]

Cet article explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une [configuration pour la génération d’états électroniques (ER)](../general-electronic-reporting.md#Configuration) et la charger dans la [bibliothèque d’actifs au niveau du projet](../../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> L’utilisation de LCS comme référentiel de stockage pour les configurations ER est en cours [d’abandon](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Pour plus d’informations, voir [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).

Dans cet exemple, vous allez créer une configuration et la charger dans LCS pour un exemple de société nommé Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société, car les configurations ER sont partagées entre les sociétés. Pour effectuer ces étapes, vous devez commencer par effectuer la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md). L’accès à LCS est également requis.

1. Se connecter à l’application en utilisant l’un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Administrateur système

2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Sélectionnez **Litware, Inc.** et marquez-le comme **Actif**.
4. Sélectionnez **Configurations**.

<a name="accessconditions"></a>
> [!NOTE]
> Assurez-vous que l’utilisateur Dynamics 365 Finance actuel est membre du projet LCS qui contient la [bibliothèque d’actifs](../../lifecycle-services/asset-library.md#asset-library-support) utilisée pour importer des configurations ER.
>
> Vous ne pouvez pas accéder à un projet LCS à partir d’un référentiel ER qui représente un domaine différent du domaine utilisé dans Finance. Si vous essayez, une liste vide de projets LCS s’affichera et vous ne pourrez pas importer de configurations ER à partir de la bibliothèque d’actifs au niveau du projet dans LCS. Pour accéder aux bibliothèques d’actifs au niveau du projet à partir d’un référentiel ER utilisé pour importer des configurations ER, connectez-vous à Finance en utilisant les informations d’identification d’un utilisateur qui appartient au client (domaine) pour lequel l’instance Finance actuelle a été provisionnée.

## <a name="create-a-new-data-model-configuration"></a>Créer une configuration de modèle de données

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Sur la page **Configurations**, sélectionnez **Créer une configuration** pour ouvrir la boîte de dialogue déroulante.

    Dans cet exemple, vous allez créer une configuration qui contient un modèle de données pour les documents électroniques. Cette configuration de modèle de données sera téléchargée dans LCS ultérieurement.

3. Dans le champ **Nom**, saisissez **Exemple de configuration de modèle**.
4. Dans le champ **Description**, saisissez **Exemple de configuration de modèle**.
5. Sélectionnez **Créer une configuration**.
6. Sélectionnez **Concepteur de modèle**.
7. Sélectionnez **Nouveau**.
8. Dans le champ **Nom**, entrez **Point d’entrée**.
9. Sélectionnez **Ajouter**.
10. Sélectionnez **Enregistrer**.
11. Fermez la page.
12. Sélectionnez **Modifier le statut**.
13. Sélectionnez **Terminer**.
14. Cliquez sur **OK**.
15. Fermez la page.

## <a name="register-a-new-repository"></a>Enregistrer un nouveau référentiel

1. Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.

2. Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**.

3. Dans la vignette **Litware, Inc.**, sélectionnez **Référentiels**.

    Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.

4. Sélectionnez **Ajouter** pour ouvrir la boîte de dialogue déroulante.

    Vous pouvez maintenant ajouter un nouveau référentiel.

5. Dans le champ **Entrée du référentiel de configuration**, sélectionnez **LCS**.
6. Sélectionnez **Créer un référentiel**.
7. Dans le champ **Projet**, saisissez ou sélectionnez une valeur.

    Pour cette exemple, sélectionnez le projet LCS souhaité. Vous devez avoir [accès](#accessconditions) au projet.

8. Cliquez sur **OK**.

    Effectuez une nouvelle entrée de référentiel.

9. Dans la liste, marquer la ligne sélectionnée.

    Pour cet exemple, sélectionnez l’enregistrement du référentiel **LCS**.

    Notez qu’un référentiel enregistré est marqué par le fournisseur actuel. En d’autres termes, seules les configurations appartenant à ce fournisseur peuvent être placées dans ce référentiel et donc chargées dans le projet LCS sélectionné.

10. Cliquez sur **Ouvrir**.

    Vous ouvrez le référentiel pour afficher la liste des configurations d’ER. Si le projet sélectionné n’a pas encore été utilisé pour le partage de configurations d’ER, la liste sera vide.

11. Fermez la page.
12. Fermez la page.

## <a name="upload-a-configuration-into-lcs"></a>Charger une configuration dans LCS

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Exemple de configuration de modèle**.

    Vous devez sélectionner une configuration qui est déjà terminée.

3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.

    Pour cet exemple, sélectionnez la version de la configuration sélectionnée dont le statut est **Terminé**.

4. Sélectionnez **Modifier le statut**.
5. Sélectionnez **Partager**.

    L’état de la configuration est modifié de **Terminé** à **Partagé** lorsque la configuration est publiée dans LCS.

6. Cliquez sur **OK**.
7. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.

    Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.

    Notez que le statut de la version sélectionnée est passé de **Terminé** à **Partagé**.

8. Fermez la page.
9. Sélectionnez **Référentiels**.

    Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.

10. Cliquez sur **Ouvrir**.

    Pour cet exemple, sélectionnez le référentiel **LCS** et ouvrez-le.

    Notez que la configuration sélectionnée est indiquée comme un actif du projet LCS sélectionné.

11. Ouvrez LCS en accédant à <https://lcs.dynamics.com>.
12. Ouvrez un projet qui a été utilisé précédemment pour l’enregistrement du référentiel.
13. Ouvrez la bibliothèque d’actifs du projet.
14. Sélectionnez le type d’actif **Configuration GER**.

    La configuration ER que vous avez chargée doit être répertoriée.

    Notez que la configuration LCS chargée peut être importée dans une autre instance si les fournisseurs ont accès à ce projet LCS.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
