---
title: Modèles de jalon
description: Cette rubrique explique comment configurer la fonctionnalité de facturation jalonnée dans la facturation des abonnements.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ecc4ddbb4d22eefac36f8cf8205d3b6084bd7d9d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686489"
---
# <a name="milestone-billing"></a>Facturation jalonnée

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment définir des modèles pour la fonctionnalité de facturation jalonnée dans la facturation des abonnements. Pour chaque ligne du modèle de jalonnement, vous pouvez définir le pourcentage ou le montant de la répartition. Vous pouvez ensuite affecter le modèle de jalonnement aux éléments de l’échéancier de facturation qui utilisent la fonctionnalité de facturation jalonnée.

## <a name="add-a-template"></a>Ajouter un modèle

Pour ajouter un modèle de jalonnement, procédez comme suit.

1. Accédez à **Facturation d’abonnement \> Facturation contractuelle récurrente \> Configuration \> Modèles par jalons**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Modèle de jalonnement**, entrez un identificateur unique pour le nouveau modèle.
4. Entrez une description dans le champ **Description**.
5. Dans le champ **Méthode de répartition**, sélectionnez une méthode de répartition.
6. Facultatif : dans le champ **Montant total**, spécifiez le montant total pour le modèle.
7. Pour ajouter une ligne, sélectionnez **Ajouter**. Ensuite, dans le champ **Numéro d’article**, sélectionnez le numéro d’article pour la nouvelle ligne.
8. Suivez l’une des procédures suivantes, selon la valeur que vous avez sélectionnée dans le champ **Méthode de répartition** :

    - Si vous avez sélectionné **Pourcentage** comme méthode de répartition, dans le champ **Pourcentage**, spécifiez le pourcentage de répartition pour chaque ligne. Si vous spécifiez des pourcentages, la somme des pourcentages qui s’affiche dans le champ **Pourcentage total** doit être égale à **100**.
    - Si vous avez sélectionné **Montant variable** comme méthode de répartition, dans le champ **Montant**, spécifiez le montant pour chaque ligne.
    - Si vous avez sélectionné **Même montant** comme méthode de répartition, vous n’avez pas à spécifier de montant. Chaque ligne sera mise à jour avec le pourcentage et le montant corrects, en fonction du nombre d’éléments ajoutés au modèle.

9. Cliquez sur **Enregistrer**.

## <a name="delete-a-template"></a>Supprimer un modèle

Pour supprimer un modèle de jalonnement, procédez comme suit.

1. Sélectionnez une ou plusieurs lignes à supprimer, puis sélectionnez **Supprimer**.
2. Lorsque vous êtes invité à confirmer l’action, sélectionnez **Oui**.

## <a name="milestone-template-fields"></a>Champs du modèle de jalonnement

La page **Modèle de jalonnement** contient les champs suivants.

| Champ | Description |
|-------|-------------| 
| Modèle de jalon | Identificateur unique du modèle de jalonnement. |
| Description | Description du modèle de jalonnement. |
| Mode de répartition | <p>Sélectionnez la méthode de répartition :</p><ul><li>**Pourcentage d’achèvement** – Une valeur d’achèvement cumulée est utilisée pour chaque ligne.</li><li>**Pourcentage** – Un pourcentage peut être spécifié pour la répartition. La somme de tous les pourcentages doit être égale à 100.</li><li>**Montant variable** – Un montant peut être spécifié pour la répartition. Le montant de la répartition est spécifié au niveau de la transaction.</li><li>**Même montant** – Les pourcentages de répartition sont calculés automatiquement et répartis équitablement entre les éléments du modèle.</li></ul> |
| Montant total | Spécifiez le montant du jalon pour le modèle. |
| **Lignes** | |
| Numéro d’article | Sélectionnez le numéro d’article pour le modèle de jalonnement. |
| Nom produit | Nom de l’article. |
| Pourcentage | <p>Entrez le pourcentage de répartition pour la ligne :</p><ul><li>Si le champ **Méthode de répartition** est défini sur **Pourcentage**, spécifiez le pourcentage pour la ligne.</li><li>Si le champ **Méthode de répartition** est défini sur **Même montant**, le pourcentage est automatiquement divisé en pourcentages égaux, en fonction du nombre d’éléments dans le modèle.</li></ul><p>La somme de tous les pourcentages doit être égale à 100.</p><p>Si une valeur **Montant total** est spécifiée sur l’en-tête, et que vous modifiez la valeur **Pourcentage** de la ligne, la valeur **Montant** est mise à jour. A l’inverse, si vous modifiez la valeur **Montant**, la valeur **Pourcentage** est mise à jour.</p> |
| Montant | <p>Le montant de répartition pour la ligne :</p><ul><li>Si le champ **Méthode de répartition** est défini sur **Montant variable**, spécifiez le montant pour la ligne.</li><li>Si le champ **Méthode de répartition** est défini sur **Même montant**, le montant est automatiquement divisé en montants égaux, en fonction du nombre d’articles dans le modèle et de la valeur **Montant total** spécifiée dans l’en-tête.</li></ul><p>La somme de tous les montants doit être égale à la valeur **Montant total** spécifiée dans l’en-tête.</p><p>Si une valeur **Montant total** est spécifiée sur l’en-tête, et que vous modifiez la valeur **Montant** de la ligne, la valeur **Pourcentage** est mise à jour. A l’inverse, si vous modifiez la valeur **Pourcentage**, la valeur **Montant** est mise à jour.</p> |
| **Totaux** | |
| Pourcentage total | La somme des pourcentages. La somme de tous les pourcentages doit être égale à 100. |
| Montant total | La somme des valeurs **Montant** pour toutes les lignes. Cette somme doit être égale à la valeur **Montant total** spécifiée dans l’en-tête. |
| Montant restant | Montant restant. La valeur est calculée comme la valeur **Montant total** de l’en-tête moins la somme des valeurs **Montant** pour toutes les lignes.|

## <a name="milestone-allocation"></a>Répartition des jalons

Avant de commencer à utiliser la fonctionnalité de jalonnement, vous devez effectuer ces tâches.

1. Ajoutez un ou plusieurs modèles de jalonnement.
2. Créer un groupe de calendriers de facturation. Spécifiez **Jalon** comme type d’article, puis sélectionnez un modèle.
3. Sur la page **Configuration de l’article** (**Facturation d’abonnement \> Facturation contractuelle récurrente \> Configuration \> Articles**), sélectionnez une relation d’article et un modèle de jalonnement pour la configuration de l’article.

Après avoir créé les modèles de jalonnement, les groupes de calendrier de facturation et les articles, vous pouvez créer un calendrier de facturation qui utilise la fonctionnalité de jalonnement.

Pour configurer un calendrier de facturation qui utilise des jalons, procédez comme suit.

1. Dans la liste **Tous/Calendriers de facturation actifs** sur la page **Calendriers de facturation**, sélectionnez **Nouveau**.
2. Sur la page **Tous les calendriers de facturation**, créez un nouveau calendrier de facturation et spécifiez un compte client et une date de début.
3. Dans la section **Lignes de calendrie de facturation**, sélectionnez **Ajouter une ligne**. Ajoutez ensuite un numéro d’article et définissez le champ **Type d’article** sur **Jalon**.

    Si un modèle de jalonnement par défaut est configuré pour l’article, les événements de jalon sont automatiquement ajoutés aux lignes de l’échéancier de facturation. Les dates de fin sont vides pour les lignes de jalon.

    Si aucun modèle de jalon n’est configuré pour l’article, sélectionnez **Répartition jalonnée**. Ensuite, sur la page **Répartition jalonnée**, sélectionnez un modèle de jalonnement et effectuez les mises à jour nécessaires. Sélectionnez ensuite **Fermer** pour revenir au calendrier de facturation et terminer la création du calendrier de facturation.

4. Pour créer des factures pour le calendrier de facturation, vous devez mettre à jour la date de fin de chaque événement de jalon. Pour un calendrier de facturation unique, vous pouvez mettre à jour la date de fin de l’événement de jalon sur les lignes du calendrier de facturation. Pour mettre à jour plusieurs calendriers de facturation, sélectionnez **Processus de mise à jour de la date d’achèvement**.
5. Une fois la date de fin mise à jour, vous pouvez créer la facture. Pour un calendrier de facturation unique, sélectionnez **Générer une facture** sur la page **Tous les calendriers de facturation**. Pour créer des factures pour plusieurs calendriers de facturation, sélectionnez **Générer une facture** ou **Générer le traitement par lots de factures** en dessous de **Tâches périodiques**.

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Modifier la répartition des jalons sur une ligne d’échéancier de facturation

Pour modifier la répartition jalonnée sur une ligne d’échéancier de facturation, procédez comme suit.

1. Sur la page **Calendriers de facturation** > **Tous/Calendriers de facturation actifs**, dans le champ **Numérode calendrier**, sélectionnez le numéro de calendrier du calendrier de facturation.
2. Dans la section **Lignes d’échéancier de facturation**, entrez un article, spécifiez **Jalon** comme article, et sélectionnez **Répartition jalonnée**.
3. Dans le champ **Modèle de jalonnement**, sélectionnez un modèle de jalonnement.
4. Sélectionnez **Traiter**. Les lignes de modèle de jalonnement sont automatiquement ajoutées aux lignes d’échéancier de facturation.

## <a name="milestone-allocation-fields"></a>Champs de répartition des jalons

La page **Répartition jalonnée** contient les champs suivants.

| Champ | Description |
|-------|-------------|
| Article parent | Le numéro d’article du parent. |
| Prix global | <p>Le prix global de l’article. La valeur correspond à la valeur **Montant net** de la ligne de l’échéancier de facturation.</p></p>Pour un article de jalon parent, la valeur par défaut est la valeur **Montant total** spécifiée pour le modèle de jalonnement. Si le montant total est 0 (zéro), la valeur par défaut est la valeur **Montant net** de la ligne d’échéancier de facturation.</p> |
| Modèle de jalon | L’ID de modèle de jalonnement de l’article de la ligne. |
| Description du modèle | Description du modèle de jalonnement. |
| Mode de répartition | La méthode de répartition utilisée pour le modèle de jalonnement. |
| **Lignes** | Les valeurs par défaut pour toutes les lignes sont basées sur le modèle de jalonnement sélectionné. Vous pouvez les modifier selon les besoins. |
| Numéro d’article | Le numéro d’article pour le modèle de répartition jalonnée. |
| Nom produit | Le nom du produit. |
| Pourcentage | <p>Le pourcentage de répartition pour la ligne. La somme de tous les pourcentages doit être égale à 100.</p><p>Si vous modifiez la valeur **Pourcentage** pour la ligne, la valeur **Montant net** est mise à jour. A l’inverse, si vous modifiez la valeur **Montant net**, la valeur **Pourcentage** est mise à jour.</p> |
| Montant HT | <p>Le montant de répartition pour la ligne. La somme des montants nets de toutes les lignes doit être égale à la valeur **Prix global** spécifiée dans l’en-tête.</p><p>Si vous modifiez la valeur **Montant net** pour la ligne, la valeur **Pourcentage** est mise à jour. A l’inverse, si vous modifiez la valeur **Pourcentage**, la valeur **Montant net** est mise à jour.</p> |
| **Totaux** | |
| Pourcentage total | La somme des valeurs **Pourcentage** pour toutes les lignes. Cette somme doit être égale à 100. |
| Montant total | La somme des valeurs **Montant net** pour toutes les lignes. Cette somme doit être égale à la valeur **Prix global** spécifiée dans l’en-tête. |
| Montant restant | Montant restant. La valeur est calculée comme la valeur **Prix global** de l’en-tête moins la somme des valeurs **Montant net** pour toutes les lignes. Le montant final doit être 0 (zéro). |
