---
title: Optimiser les traitements par lots planifié BYOD
description: Cette rubrique explique comment optimiser les performances lorsque vous utilisez la fonctionnalité Apporter votre propre base de données (BYOD) avec Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: f21e9b94b5aa30b2cdb18692e8cc9c8d00f758d6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805032"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Optimiser les traitements par lots planifié BYOD

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique explique comment optimiser les performances lorsque vous utilisez la fonctionnalité Apporter votre propre base de données (BYOD). Pour plus d’informations sur BYOD, consultez [Apporter votre propre base de données (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json).

## <a name="performance-considerations-for-data-export"></a>Considérations relatives aux performances pour l’exportation de données

Une fois les entités publiées dans la base de données de destination, vous pouvez utiliser la fonction Exporter dans l’espace de travail **Gestion des données** pour déplacer des données. La fonction Exporter vous permet de définir une tâche de mouvement de données contenant une ou plusieurs entités. Pour plus d’informations sur l’utilisation de la gestion des données pour exporter des données, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json).

Vous pouvez utiliser la page **Exportation** pour exporter des données dans différents formats de données cibles, comme un fichier de valeurs séparées par des virgules (CSV). Cette page prend également en charge les bases de données SQL comme autre destination.

Vous pouvez créer un projet de données qui a plusieurs entités et utiliser un travail par lots pour planifier l’exécution de ce projet de données. Si vous sélectionnez l’option **Exporter par lots**, vous pouvez planifier l’exécution périodique du travail d’exportation de données.

Pour aider à préserver la fiabilité globale de l’exportation BYOD, vous devez être prudent lorsque vous ajoutez plusieurs entités à un projet d’exportation. Lorsque vous déterminez le nombre d’entités à ajouter au même projet, tenez compte des paramètres suivants :

- La complexité des entités
- Le volume de données attendu par entité
- Le temps global qui sera nécessaire pour terminer l’exportation au niveau de la tâche

Pour des performances optimales, évitez d’ajouter des centaines d’entités à un seul projet. Nous vous recommandons de créer plusieurs tâches, chacune contenant moins d’entités.

## <a name="scheduling-byod-batch-jobs"></a>Planification des traitements par lots BYOD

Pour réduire l’impact sur les utilisateurs de Microsoft Dynamics 365 Human Resources, exécutez des tâches par lots BYOD la nuit ou après les heures de bureau. Assurez-vous de vérifier le fuseau horaire des traitements par lots périodiques. Certains traitements par lots peuvent utiliser l’heure standard du Pacifique (PST).

Pour éviter les problèmes de performances, tenez compte des facteurs suivants lorsque vous configurez la fréquence de planification des tâches par lots BYOD :

- Le temps nécessaire pour terminer chaque tâche par lots
- Le besoin de l’entreprise pour les données en BYOD

Définissez la fréquence de chaque tâche par lots sur une valeur qui garantit que la tâche peut être terminée bien avant sa prochaine exécution planifiée. Évitez d’exécuter plusieurs tâches en parallèle, car cette approche peut affecter négativement les performances de Human Resources.

Pour des performances optimales, utilisez toujours l’option **Exporter par lots** sur la page **Exporter** pour planifier des tâches par lots BYOD. Évitez de planifier des exportations récurrentes avec **Gérer \> Gérer les tâches de données récurrentes**.

## <a name="incremental-export"></a>Exportation incrémentale

Lorsque vous ajoutez une entité pour l’exportation de données, vous pouvez effectuer une transmission incrémentielle (exportation) ou une transmission complète. Une transmission de type push complète supprime tous les enregistrements existants d’une entité dans la base de données BYOD. Elle insère ensuite l’ensemble d’enregistrements actuel provenant de l’entité Human Resources.

Pour effectuer une transmission de type push incrémentielle, vous devez activer le suivi des modifications pour chaque entité sur la page **Entités**. Pour plus d’informations, voir la [Activation du suivi des modifications pour les entités](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

Si vous sélectionnez une transmission de type push incrémentielle, la première est toujours complète. SQL suit les modifications depuis cette première transmission de type push complète. Lorsqu’un nouvel enregistrement est inséré, ou lorsqu’un enregistrement est mis à jour ou supprimé, la modification est reflétée dans l’entité de destination.

## <a name="time-outs"></a>Expiration

Voici les délais d’expiration par défaut pour les exportations BYOD :

- Dix minutes pour les opérations de troncation
- Une heure pour les opérations d’insertion en bloc

Lorsque les volumes sont élevés, ces paramètres de délai d’expiration peuvent ne pas être suffisants. Pour les mettre à jour, accédez à **Gestion de données \> Paramètres de la structure \> Apporter votre propre base de données**. Ces délais d’expiration sont spécifiques à l’entreprise et doivent être définis séparément pour chaque entreprise.

## <a name="known-limitations"></a>Limitations connues

Cette fonctionnalité BYOD a les restrictions suivantes :

- Il ne doit y avoir aucun verrouillage actif sur votre base de données pendant la synchronisation. Les verrouillages actifs peuvent entraîner des écritures lentes, voire l’échec de l’exportation des données vers votre Azure SQL Database.
- Vous ne pouvez pas exporter des entités composites dans votre propre base de données. Actuellement, les entités composites ne sont pas prises en charge. Vous devez exporter les entités individuelles qui composent l’entité composite. Cependant, vous pouvez exporter les deux entités dans le même projet de données.
- Les entités qui n’ont pas de clés uniques ne peuvent pas être exportées à l’aide de la transmission de type push incrémentielle. Vous pouvez être confronté à cette limitation, en particulier lorsque vous essayez d’exporter de manière incrémentielle des enregistrements à partir de quelques entités prêtes à l’emploi. Étant donné que ces entités ont été conçues pour permettre l’importation de données, elles n’ont pas de clé unique.

## <a name="troubleshooting"></a>Dépannage

### <a name="incremental-push-doesnt-work-correctly"></a>La transmission de type push incrémentielle ne fonctionne pas correctement

**Problème :** Lorsqu’une transmission de type push complète se produit pour une entité, un grand ensemble d’enregistrements s’affiche dans BYOD lorsque vous utilisez une instruction **select**. Cependant, lorsque vous effectuez une transmission de type push incrémentielle, vous ne voyez que quelques enregistrements dans BYOD. Il semble que la transmission de type push incrémentielle ait supprimé tous les enregistrements et ajouté uniquement les enregistrements modifiés dans BYOD.

**Solution :** Les tables de suivi des modifications SQL peuvent ne pas être dans l’état attendu. Dans les cas de ce type, nous vous recommandons de désactiver le suivi des modifications pour l’entité, puis de le réactiver. Pour plus d’informations, voir la [Activation du suivi des modifications pour les entités](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

## <a name="see-also"></a>Voir également :

[Vue d’ensemble de la gestion des données](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages?toc=/dynamics365/human-resources/toc.json)<br>
[Apporter votre propre base de données (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json)<br>
[Vue d’ensemble de tâches d’importation et d’exportation de données](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json)<br>
[Activer le suivi des modifications pour les entités](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]