---
title: Évaluation de la condition
description: Cette rubrique explique comment créer un modèle et un enregistrement d’évaluation de condition dans un actif dans Gestion des actifs.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 082a2bfd8818e511095e9ab2dcc22de59eb98d31
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808422"
---
# <a name="condition-assessment"></a>Évaluation de la condition

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique comment créer un modèle et un enregistrement d’évaluation de condition dans un actif dans Gestion des actifs. L’évaluation de la condition est effectuée à intervalles réguliers et l’objectif principal est de créer et de gérer des données de condition sur les actifs. Du point de vue de la maintenance préventive, il est important de surveiller les informations clés telles que l’état actuel et la durée de vie restante. En outre, si vous effectuez l’évaluation des conditions à intervalles réguliers, vous pouvez surveiller et comparer les conditions sur les machines dans votre usine.

L’évaluation des conditions peut être utilisée pour mesurer et surveiller de nombreuses conditions sur votre équipement. Exemple : Vous pouvez mesurer les vibrations sur vos machines. Une fois que vous avez enregistré les mesures de vibration dans Gestion des actifs sur différents types d’équipements, vous pouvez rechercher la dernière évaluation enregistrée et afficher les mesures de vibration.

L’évaluation des conditions est créée sur les actifs. Vous paramétrez un modèle d’évaluation des conditions d’un type d’actif avant d’effectuer la procédure d’évaluation des conditions. Le motif de l’utilisation des modèles pour l’évaluation des conditions est d’éviter la variation des données de condition sur les actifs similaires. La séquence de configuration et d’utilisation de l’évaluation des conditions dans Gestion des actifs est la suivante : vous devez tout d’abord configurer les modèles d’évaluation des conditions requis. Ensuite, vous associez des modèles à l’actif dans l’écran **Types d’actifs**. Enfin, vous pouvez créer des enregistrements d’évaluation de condition dans un actif dans l’écran **Actif**.

## <a name="create-a-condition-assessment-template"></a>Créer un modèle d’évaluation de la condition

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Types d’actifs** > **Évaluation des conditions**.
2. Sélectionnez **Nouveau** pour créer un modèle.
3. Insérez un ID pour le modèle dans le champ **Modèle**.
4. Insérez un nom pour le modèle dans le champ **Nom**.
5. Dans l’organisateur **Lignes d’évaluation de la condition**, ajoutez les lignes requises pour l’évaluation de la condition, notamment la sélection de l’unité appropriée de type et de mesure de la condition.
6. Dans l’organisateur **Types d’actifs**, ajoutez des types d’actifs devant utiliser le modèle d’évaluation des conditions.
7. Dans les champs **Lignes** et **Types d’actifs** du groupe **Détails** en haut de l’écran, vous verrez le nombre de lignes d’évaluation et les types d’actifs liés au modèle d’évaluation de conditions sélectionné.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Création d’un enregistrement d’évaluation des conditions dans un actif

1. Sélectionnez **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.
2. Dans la liste, sélectionnez l’actif pour lequel vous souhaitez créer un enregistrement d’évaluation des conditions.
3. Sous l’onglet **Général**, cliquez sur **Évaluation de la condition**.
4. Cliquez sur **Nouveau** pour créer un nouvel enregistrement.
5. Permet de sélectionner la date d’évaluation de la condition dans le champ **Date**.
6. Sélectionnez le nom du collaborateur ayant effectué l’enregistrement d’évaluation dans le champ **Collaborateur**.
7. Dans le champ **Lignes**, vous voyez le nombre de lignes d’évaluation paramétrées pour l’évaluation de la condition.
8. Sélectionnez un modèle d’évaluation de la condition dans le champ **Modèle**. Le nom du modèle est automatiquement inséré dans le champ **Nom**, et les lignes d’enregistrement associées sont insérées dans l’organisateur **Lignes d’évaluation de la condition**.
9. Vous pouvez insérer des notes concernant l’évaluation de la condition sélectionnée dans l’organisateur **Détails**.
10. Pour chaque ligne d’évaluation de la condition, insérez des données de mesure dans le champ **Valeur**.
11. Vous pouvez insérer un commentaire concernant la ligne de l’enregistrement dans l’organisateur **Lignes d’évaluation de la condition** > champ **Commentaires**. Si vous ajoutez un commentaire dans une ligne, la case à cocher **Commentaire** est automatiquement activée.

Après avoir effectué un enregistrement d’évaluation de la condition dans un actif, vous pouvez imprimer un état d’évaluation de la condition.

>[!NOTE]
>Vous pouvez également enregistrer l’évaluation des conditions sur un ordre de travail (**Évaluation de la condition** > **Gestion des actifsCommun** > **Ordres de travail** > **Tous les ordres de travail** > **Bouton Évaluation de la condition**.)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]