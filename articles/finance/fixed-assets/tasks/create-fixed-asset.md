---
title: Création d’une immobilisation
description: Cet article explique comment créer un nouvel enregistrement d’immobilisation à partir de la page de liste des immobilisations.
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00c72081d20015737aa027cee9474a54e498cef4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868487"
---
# <a name="create-a-fixed-asset"></a>Création d’une immobilisation

[!include [banner](../../includes/banner.md)]

Cet article explique comment créer un nouvel enregistrement d’immobilisation à partir de la page de liste des **immobilisations**.

Le système attribue le numéro d’actif en fonction de la séquence de numéros affectée au groupe d’immobilisations. Si vous utilisez le modèle d’immobilisation pour importer des actifs via le complément Microsoft Excel, ou si vous utilisez une autre tâche d’importation, le système crée automatiquement des enregistrements d’immobilisation et incrémente le numéro d’actif.

Pour créer manuellement un enregistrement d’actif, procédez comme suit.

1. Allez dans **Volet de navigation \> Modules \> Immobilisations \> Immobilisations \> Immobilisations**.
2. Dans le **volet Actions**, sélectionnez **Nouveau**.
3. Entrez ou sélectionnez une valeur dans le champ **Groupe d’immobilisations**. Le champ **Numéro** sera défini par défaut si vous avez activé la fonctionnalité **Numéroter automatiquement les immobilisations**  dans les paramètres **Immobilisations** et dans le groupe d’**immobilisations**. Sinon, vous devez entrer un numéro unique pour identifier l’immobilisation.
4. Dans le champ **Nom**, entrez une valeur. Entrez les informations supplémentaires dont votre entreprise a besoin pour cette immobilisation.
5. Dans le volet **Actions**, sélectionnez sur **Registres**.
6. Entrez une date dans le champ **Date d’acquisition**.
7. Entrez un nombre dans le champ **Prix d’acquisition**.

    - Entrez les informations supplémentaires dont votre entreprise a besoin pour ce registre.
    - Entrez les informations supplémentaires dont votre entreprise a besoin pour les registres restants.

8. Fermez la page.

Vous pouvez également importer des immobilisations à l’aide du complément Excel ou en exécutant une tâche d’importation à partir de l’espace de travail **Gestion de données**. Avant d’exécuter l’importation, entrez les valeurs des champs obligatoires dans le modèle.

Si vous n’avez pas défini le numéro d’immobilisation dans le modèle du complément Excel ou dans Gestion des données, le système crée un numéro d’immobilisation pour chaque actif importé et incrémente automatiquement la séquence de numéros pour chacun. Cependant, si vous importez des actifs et définissez des numéros d’actifs dans le modèle, le système n’incrémente **pas** automatiquement la séquence de numéros. Dans ce cas, un administrateur devra peut-être mettre à jour manuellement la séquence de numéros. Si vous avez défini le numéro d’immobilisation dans le modèle du complément Excel, le système utilise le numéro d’immobilisation défini et incrémente la séquence de numéros.

> [!NOTE]                                                                                                         
> Après avoir comptabilisé l’amortissement, les champs **Mise en service** et **Date du cycle d’amortissement** seront verrouillés sur la page **Registre**. En outre, aucun des deux champs ne sera mis à jour à partir de l’entité de données.

> [!WARNING]
> L’enregistrement d’immobilisation ne sera pas supprimé si les transactions ont été validées dans le registre associé ou si l’immobilisation créée est saisie sur une ligne de journal mais pas validée. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
