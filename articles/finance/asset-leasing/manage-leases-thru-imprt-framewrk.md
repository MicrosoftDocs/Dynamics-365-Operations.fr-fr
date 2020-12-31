---
title: Gérez les baux via l’environnement d’importation de baux
description: Cette rubrique explique comment utiliser la structure d’importation de baux pour ajuster plusieurs baux en même temps.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d7a7d2afd8f352bc167ec8c0a354ee4ac0a9e77b
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443376"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Gérez les baux via l’environnement d’importation de baux

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment utiliser la structure d’importation de baux pour ajuster plusieurs baux en une étape. En utilisant cette fonctionnalité, vous pouvez gagner du temps et vous pouvez également garantir des ajustements plus précis en réduisant le risque d’erreur humaine. De plus, cette capacité peut connecter Microsoft Dynamics 365 Finance avec des entités de données externes pour télécharger efficacement les données.

Les entités de données suivantes peuvent être utilisées pour intégrer la location d’actifs à des systèmes externes :

- Échelonnement du bail
- Échelonnement du contrat de paiement
- Échelonnement du contrat exécutoire

Vous pouvez utiliser le processus d’importation pour ajuster un bail, mettre à jour des informations non financières ou ajouter de nouveaux baux. Vous pouvez afficher et modifier les données de location avant de les importer.

Le système peut exécuter les trois processus suivants via la suite d’importation de bail.

| Type de processus  | Description |
|---------------|-------------|
| Ajouter un enregistrement    | Les baux migrés qui ont ce type de processus créent un bail dans le système. L’échéancier de paiement doit être confirmé manuellement et l’écriture de journal de reconnaissance initiale doit être validée manuellement après la migration. |
| Mettre à jour l’enregistrement | Les baux migrés qui ont ce type de processus mettent à jour les valeurs de champ pour un bail qui se trouve déjà dans le système. Seuls les champs sélectionnés sur la page **Mettre à jour la sélection des champs** sont mis à jour. Nous vous recommandons de sélectionner des champs non financiers dans la page **Mettre à jour la sélection des champs**, car ce type de processus n’ajuste pas le bail. |
| Ajuster l’enregistrement | Les baux migrés qui ont ce type de processus ajustent le bail. Cet ajustement entraîne une modification du crédit-bail du bail. Une fois la location traitée, le système crée un échéancier de paiement en utilisant les nouvelles données de la suite d’importation de location. Le système ne confirme pas l’échéancier de paiement ou n’enregistre pas l’écriture au journal d’ajustement. |

Une fois les informations chargées via l’espace de travail **Gestion de données**, ouvrez la page **Importer l’en-tête** (**Location d’actifs \> Cadre d’importation de bail \> Importer l’en-tête**). Cette page répertorie toutes les importations des trois entités de données répertoriées précédemment.

Pour afficher les données de préparation du bail avant l’exécution du traitement, sélectionnez **Données de mise en lots**.

La fonction de comparaison vous permet de comparer un enregistrement que vous importez avec l’enregistrement correspondant qui se trouve déjà dans votre système. Pour comparer un enregistrement de bail individuel, sélectionnez un bail, puis **Comparer**. Vous devez terminer cette étape pour générer un rapport **Différences** avant de migrer les enregistrements de bail. La fonctionnalité Comparer compare les valeurs des données mises en lots aux valeurs des baux actuellement dans le système.

> [!NOTE]
> La fonctionnalité Comparer ne fonctionne pas pour les baux qui ont le type de processus **Ajouter un enregistrement**, car il n’y a rien à comparer avec ce bail.
>
> Pour comparer plusieurs baux en même temps, accédez à **Location d’actifs \> Cadre d’importation de bail \> Périodique \> Comparer** et sélectionnez **Comparer**.

Pour chaque entité, vous pouvez afficher les différences entre ce qui se trouve actuellement dans le système et ce qui se trouve dans les tables intermédiaires. Pour chaque entité des tables mises en lots, sélectionnez **Voir les différences**. La boîte de dialogue qui apparaît affiche la valeur actuelle et la valeur mise en lots proposée.

Vous pouvez également mettre à jour la valeur mise en lots en la modifiant dans la colonne **Nouvelle valeur** puis en sélectionnant **Mettre à jour de la mise en lots**.

Vous pouvez valider les baux pour vous assurer que les enregistrements peuvent être introduits dans le système sans introduire d’erreurs. Avant la migration d’un enregistrement de bail, le système exécute plusieurs validations pour s’assurer que l’enregistrement sera importé avec succès. Pour valider un bail individuel, sélectionnez **Valider**.

> [!NOTE]
> Pour valider plusieurs baux en même temps, accédez à **Location d’actifs \> Cadre d’importation de bail \> Périodique \> Valider** et sélectionnez **Comparer**.

Pour traiter un bail individuel, sélectionnez **Migrer les enregistrements de bail** sur la page **Importer l’en-tête**. Lorsqu’un bail est migré, le système exécute l’action spécifiée dans le champ **Type de processus**.

> [!NOTE]
> Pour valider plusieurs baux en même temps, accédez à **Location d’actifs \> Cadre d’importation de bail \> Périodique \> Valider** et sélectionnez **Comparer**.

Une fois les baux comparés, vous pouvez exécuter un rapport pour afficher les différences pour chaque bail inclus dans l’ID d’importation. Pour exécuter le rapport pour un bail, sélectionnez ce bail dans les données mise en lots, puis sélectionnez **Comparer et afficher le rapport \> Rapport des différences**.

> [!NOTE]
> Pour valider plusieurs baux en même temps, accédez à **Location d’actifs \> Recherches et états \> États sur les différences** et sélectionnez **Comparer**.

## <a name="set-up-update-fields"></a>Paramétrer les champs de mise à jour

Si vous utilisez la structure d’importation de baux pour mettre à jour les baux et que le type de processus est **Mettre à jour l’enregistrement**, vous pouvez sélectionner des champs spécifiques à mettre à jour.

1. Aller à **Location d’actifs \> Structure d’importation de bail \> Configurer \> Mettre à jour la sélection de champ**.
2. Sur la page qui s’affiche, sélectionnez les champs à mettre à jour, puis sélectionnez la flèche verte pour les déplacer vers la liste **Champs sélectionnés**. Seuls les champs de la liste **Champs sélectionnés** peut être mise à jour à l’aide de la suite d’importation de bail.
