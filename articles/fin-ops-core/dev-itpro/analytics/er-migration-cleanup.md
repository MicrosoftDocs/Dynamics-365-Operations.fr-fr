---
title: Nettoyage de migration ER
description: Cette rubrique explique comment utiliser la fonction de nettoyage de migration ER pour résoudre des problèmes avec les modèles ER.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8b6e81e47cd781bbe856676b1cecb50b8ee1adfc
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351047"
---
# <a name="er-migration-cleanup"></a>Nettoyage de migration ER 

[!include[banner](../includes/banner.md)]

Lorsque vous gérez vos instances Finance, vous pouvez décider de migrer votre instance actuelle vers un autre emplacement. Par exemple, vous pouvez migrer votre instance de production vers un nouvel environnement de bac à sable. So vous n’avez pas configuré la structure de la gestion des états électroniques (ER) pour stocker les modèles dans un stockage d’objets blob Microsoft Azure, la table **DocuValue** du nouvel environnement de bac à sable fait référence à l’instance de stockage d’objets blob dans l’environnement de production. Cependant, cette instance n’est pas accessible depuis l’environnement de bac à sable, car le processus de migration n’est pas compatible avec la migration des artefacts dans le stockage d’objets blob. On s’attend plutôt à ce que dans le nouvel environnement sandbox, vous vous référiez à l’instance de stockage Blob dans l’environnement sandbox qui n’obtient pas encore les modèles ER.

Si vous essayez d’exécuter un format de gestion d’états électroniques qui utilise un modèle pour générer des documents commerciaux, une exception survient et vous êtes averti du modèle manquant. Vous êtes également invité à utiliser l’option de nettoyage de migration pour supprimer, puis réimporter la configuration du format des états électroniques qui contient le modèle.

[![Exécution d’un format ER.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Vous recevrez une erreur similaire si vous accédez à la page **Configurations** (**Administration de l’organisation** \> **Rapports électroniques** \> **Configurations**) et dans l’arborescence des configurations, essayez de supprimer une configuration au format ER qui utilise un modèle.

[![Suppression d’un format ER.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Effectuez les étapes suivantes pour résoudre les problèmes avec les modèles ER auxquels vous ne pouvez pas accéder.

1.  Accédez à la page **Administration de l’organisation** \> **Périodique** \> **Nettoyage de la migration**.
2.  Sélectionnez une configuration au format ER qui ne peut pas être exécutée ou supprimée.
3.  Sélectionnez **Supprimer**.
4.  Confirmez la suppression de la configuration de format ER sélectionnée.
5.  [Importez](download-electronic-reporting-configuration-lcs.md) la configuration de format ER supprimée vers l’instance Finance actuelle.

## <a name="applicability"></a>Conditions d’application

> [Important] L’option **Nettoyage de la migration** est ciblée uniquement pour les configurations de format ER qui contiennent des modèles ER non accessibles. Lorsque vous supprimez une configuration au format ER à l’aide de l’option **Nettoyage de la migration**, ER supprime les modèles liés aux artefacts de configuration dans la seule base de données d’application. L’existence des fichiers physiques appropriés dans le stockage Blob n’est pas validée. Au lieu de cela, on suppose qu’il n’y en a pas. Par conséquent, n’utilisez pas l’option **Nettoyage de la migration** comme alternative à l’option de suppression de configuration ER sur la page **Configurations**. Utilisez l’option **Nettoyage de la migration** uniquement lorsque l’option de suppression de la configuration ER sur la page **Configurations** échoue.
>
> Si vous utilisez l’option **Nettoyage de migration** pour supprimer la configuration au format ER lorsque le modèle référencé est disponible dans le stockage Blob, vous ne supprimez que les artefacts de configuration dans la base de données d’application. Le fichier physique du modèle dans le stockage Blob reste. L’écrasement de fichiers dans le stockage Blob n’est plus autorisé. Pour plus d’informations, voir [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). De plus, vous ne pourrez plus réimporter les configurations supprimées à l’aide du nettoyage de migration dans cet environnement. Pour résoudre ce problème, vous devez rechercher le fichier correspondant dans le stockage Blob et le supprimer manuellement.

[![Importation d’un format ER.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Un problème similaire peut se produire si vous migrez votre instance d’application vers un autre emplacement qui a été utilisé comme cible de migration plusieurs fois et pour lequel le stockage Blob contient déjà des fichiers de modèle ER.

En raison des nombreuses configurations du format de gestion des états électroniques, ce processus peut se révéler chronophage. Par conséquent, en utilisant la fonctionnalité [stockage de sauvegarde des modèles ER](er-backup-storage-templates.md) pour récupérer automatiquement les modèles avec des références cassées est préférable.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]