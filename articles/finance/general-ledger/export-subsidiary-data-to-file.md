---
title: Exportation des données d'une filiale dans des fichiers
description: Cette rubrique explique comment préparer l'exportation de données à partir de Microsoft Dynamics 365 Finance et comment les importer dans une entité juridique consolidée.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 179a401178935b8a76d6718a7fb1f63e08344f50
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968677"
---
# <a name="export-subsidiary-data-to-files"></a>Exportation des données d'une filiale dans des fichiers

[!include [banner](../includes/banner.md)]

Vous devez utiliser la page **Exporter** (**Administration du système \> Espaces de travail \> Importer/Exporter**) pour préparer l'exportation des données d'une filiale vers des fichiers qui peuvent ensuite être importés dans une entité juridique consolidée. Pour plus d’informations sur les processus d'importation et d'exportation, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Créez une entité juridique pour le processus de consolidation. Pour plus d’informations sur la création d’entités juridiques, consultez [Créer une entité juridique](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Pour plus d'informations, voir [Préparer une entité juridique en vue de son utilisation dans le processus de consolidation](prepare-company-for-consolidation.md) et [Paramétrer une entité juridique filiale pour la consolidation](set-up-subsidiary-company-for-consolidation.md). 

2. Accédez à **Consolidations \> Exporter soldes de la société**. Sur la page **Exporter soldes de la société**, sur l'onglet **Critères**, spécifiez les détails de la consolidation en définissant les champs suivants.

    | Champ                             | Description |
    |-----------------------------------|-------|
    | Compte principal                      | Spécifiez les comptes à consolider. Pour inclure tous les comptes, laissez ce champ vide. |
    | Utiliser le compte de consolidation         | Si vous avez spécifié des comptes de consolidation, définissez cette option sur **Oui**. |
    | Sélectionner le compte de consolidation dans | Sélectionnez soit **Compte principal** ou **Groupe de comptes de consolidation**. |
    | Groupe de comptes de consolidation       | Sélectionnez un groupe de comptes de consolidation pour le compte de consolidation que vous sélectionnez. |
    | Période de consolidation              | Spécifiez les dates « De » et « À » pour la consolidation. |
    | Inclure les montants réels            | Définissez cette option sur **Oui** pour inclure les montants réels. |
    | Inclure les montants du budget            | Définissez cette option sur **Oui** pour inclure les montants budgétaires dans les consolidations. |
    | Modèles de budget                     | Spécifiez le modèle de budget à inclure. |

3. Sous l'onglet **Dimensions financières**, spécifiez les détails de la consolidation :

    - Spécifiez les informations de dimension financière qui doivent être transférées des transactions des comptes de filiale vers les transactions de l'entité juridique consolidée.
    - Sélectionnez les dimensions financières dans la liste.
    - Identifiez la spécification correcte pour chaque dimension financière consolidée. Les options disponibles comprennent **Dimension**, **Dimension de groupe**, **Comptes société**, et **Compte**.

        > [!NOTE]
        > L'option **Dimension de groupe** vous permet de définir la valeur de dimension utilisée par le groupe de sociétés en cours de consolidation.

    - Spécifiez l'ordre des segments dans lequel consolider.

4. Sur l'onglet **Entités juridiques**, procédez comme suit pour spécifier l'entité juridique que vous exportez :

    1. Sélectionnez **Nouveau**.
    2. Entrez l'entité juridique dans le champ **Entité juridique source**.

        Si un même critère s'applique à plusieurs filiales d'une même base de données, vous pouvez transférer les données de ces filiales afin de séparer les fichiers d'exportation en une seule opération :

        1. Créez une ligne pour chaque entité juridique filiale dont les comptes doivent être exportés vers des fichiers. Ces fichiers seront importés dans l'entité juridique consolidée ultérieurement.
        2. Pour chaque filiale, entrez le nom de la filiale et le nom du fichier d'exportation qui sera créé au cours de la tâche d'exportation.

    3. Dans le champ **Type de compte des différences de conversion**, sélectionnez **Résultat** ou **Bilan**.
    4. Entrez un nom de fichier pour le fichier d'exportation qui sera créé.

5. Sélectionnez **OK** pour lancer l'exportation.

À la fin de l'exportation, vous recevez un message montrant le nombre d'enregistrements sauvegardés dans chaque fichier. Vous pouvez ensuite importer les fichiers dans l'entité juridique consolidée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]