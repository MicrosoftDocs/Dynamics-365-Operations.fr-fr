---
title: Configurer et gérer la journalisation de la base de données
description: Vous pouvez suivre les modifications apportées aux tables et aux champs dans Dynamics 365 Human Resources avec la journalisation de la base de données.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8faf0be5f094f18b75f2263fa622c9b7f3983274
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899761"
---
# <a name="configure-and-manage-database-logging"></a>Configurer et gérer la journalisation de la base de données


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez suivre les modifications apportées aux tables et aux champs dans Dynamics 365 Human Resources avec la journalisation de la base de données. Cet article décrit comment :

- Gérer la sécurité et les performances pour la journalisation de la base de données
- Paramétrer la connexion de la base de données
- Nettoyer les journaux de base de données

## <a name="overview-of-database-logging"></a>Présenter la journalisation de la base de données

La journalisation de la base de données effectue le suivi des modifications apportées aux tables et aux champs dans Microsoft Dynamics 365 Human Resources. Ces modifications incluent l’insertion, la mise à jour ou la suppression. La journalisation de la base de données stocke un enregistrement des modifications apportées aux tables ou aux champs dans la table de journal de la base de données.

Les utilisations commerciales de la journalisation de la base de données comprennent :

- Création d’un enregistrement d’audit des modifications apportées à des tables spécifiques contenant des informations sensibles.
- Suivi des transactions uniques. La journalisation de la base de données n’est pas destinée au suivi des transactions automatisées qui s’exécutent dans des travaux par lots.

## <a name="security-for-database-logging"></a>Sécurité pour la journalisation de la base de données

Les journaux de base de données peuvent contenir des données confidentielles. Limitez l’accès pour inclure uniquement les rôles de sécurité qui ont besoin d’accéder aux données du journal.

## <a name="database-logging-and-performance"></a>Journalisation et performances de la base de données

Bien que précieuse d’un point de vue commercial, la journalisation de la base de données peut être coûteuse en termes d’utilisation et de gestion des ressources. Les implications de performance de la journalisation de la base de données comprennent :

- La table des journaux de la base de données peut croître rapidement et entraîner une augmentation de la taille de la base de données. La croissance dépend de la quantité de données enregistrées que vous décidez de conserver. Par défaut, la table des journaux de la base de données ne conserve que 30 jours de données de journal. 

- La journalisation de la base de données peut nuire aux processus automatisés de longue durée, tels que les importations de données de longue durée.

### <a name="best-practices"></a>Utilisation optimale

Pour améliorer les performances, limitez les entrées de journal en sélectionnant des champs spécifiques à enregistrer au lieu de tables entières. Pour aider à maintenir les performances globales, la journalisation de la base de données est limitée à 20 tables.

> [!NOTE]
> Seules les mises à jour peuvent être enregistrées pour des champs individuels.

## <a name="set-up-database-logging"></a>Paramétrer la connexion de la base de données

Vous pouvez utiliser l’assistant **Consignation des modifications de base de données** pour configurer la journalisation de la base de données. L’assistant offre un moyen flexible de configurer la journalisation des tables ou des champs.

1. Accédez à **Administration système> liens> Base de données> Configuration du journal de base de données**. Sélectionnez **Nouveau** pour démarrer l’assistant **Consignation des modifications de base de données**.
2. Sélectionnez **Suivant**. 
3. Sur la page **Tables et champs** de l’assistant, sélectionnez les tables et les champs sur lesquels vous souhaitez activer la journalisation de la base de données, puis sélectionnez **Suivant**.

   > [!Note]
   > La journalisation de la base de données n’est pas disponible sur toutes les tables de la base de données Human Resources. Le fait de sélectionner **Afficher toutes les tables** sous la liste développe la liste des tables et des champs ; cela affiche toutes les tables de base de données pour lesquelles la journalisation de base de données est disponible, mais il s’agit d’un sous-ensemble de la liste complète des tables de base de données.

4. Sur la page **Types de modification** de l’assistant, sélectionnez les opérations de données pour lesquelles vous souhaitez suivre les modifications pour chacune des tables et chacun des champs, puis sélectionnez **Suivant**. Consultez le tableau ci-dessous pour voir une description des opérations sur les données disponibles pour la journalisation.
5. Sur la page **Terminer**, passez en revue les modifications qui seront apportées, puis sélectionnez **Terminer**.

| Opération | Description |
| -- | -- |
| Suivre les nouvelles transactions | Créez un journal pour les nouveaux enregistrements créés dans la table. |
| Mise à jour | Créez un journal pour les mises à jour des enregistrements de la table ou les mises à jour des champs sélectionnés individuellement dans la table. Si vous choisissez de consigner les mises à jour de la table, un enregistrement de journal est créé chaque fois qu’une mise à jour est effectuée sur n’importe quel champ de n’importe quel enregistrement de la table. Si vous choisissez de consigner les mises à jour pour des champs spécifiques, un enregistrement de journal est créé uniquement lorsque des mises à jour sont effectuées sur ces champs des enregistrements de la table. |
| Retirer | Créez un journal pour les enregistrements supprimés de la table. |
| Renommer la clé | Créez un enregistrement de journal lorsqu’une clé de table est renommée. |


## <a name="clean-up-database-logs"></a>Nettoyer les journaux de base de données

Vous pouvez supprimer tout ou partie des journaux de la base de données à l’aide des options suivantes :

- Sélectionnez tous les journaux pour une table particulière.
- Sélectionnez des types spécifiques de journal de base de données.
- Sélectionnez une date et une heure de création d’un journal.

Pour paramétrer le nettoyage des journaux de base de données, procédez comme suit : 

1. Accédez à **Administration système> liens> Base de données> Journal de base de données**. Sélectionnez **Nettoyer le journal**.
2. Sous l’en-tête **Enregistrements à inclure**, sélectionnez **Filtrer**.
3. Choisissez la méthode qui sera utilisée pour sélectionner les feuilles à supprimer. Entrez l’une des options suivantes :

   - ID table
   - Type de journal
   - Date et heure de création

4. Utilisez l’onglet **Nettoyage des journaux de base de données** pour déterminer quand exécuter la tâche de nettoyage des journaux. Par défaut, les journaux de base de données sont disponibles pendant 30 jours.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
