---
title: Planifier le nettoyage des données de l’historique des ventes
description: Cet article décrit comment améliorer les performances du système en programmant la tâche périodique Nettoyage de l'historique de mise à jour des ventes pour qu'elle s'exécute à intervalles réguliers.
author: myvakalo
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1b2c9436fbb5020065f8f6ec30eedeca342d8aa9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900823"
---
# <a name="schedule-sales-history-data-cleanup"></a>Planifier le nettoyage des données de l’historique des ventes

[!include [banner](../includes/banner.md)]

Dans le cadre de son fonctionnement standard, Microsoft Dynamics 365 Supply Chain Management génère et stocke en permanence des données de mise à jour de l'historique des ventes. Au fil du temps, une grande quantité de données d'historique des ventes obsolètes peut s'accumuler dans votre système. Ces données accumulées peuvent entraîner des problèmes de performances et de fonctionnement lors de la validation des documents liés aux commandes client. (Ces documents comprennent les confirmations de commandes client, les bons de livraison, les listes de prélèvement et les factures). Par conséquent, vous devez configurer et planifier la tâche périodique *Nettoyage de l'historique des mises à jour des ventes* pour qu'elle s'exécute à intervalle régulier. Cette tâche supprimera toutes les données de mise à jour de l'historique des ventes qui ne sont plus nécessaires.

Si vous utilisez la tâche périodique *Nettoyage de l'historique des mises à jour des ventes*, nous vous recommandons d'activer la fonctionnalité *Améliorations des performances du nettoyage de l'historique des ventes*, ce qui rend l'exécution de la tâche plus efficace. (Néanmoins, vous pouvez également exécuter la tâche sans activer cette fonctionnalité.)

## <a name="turn-on-the-sales-history-cleanup-features"></a>Activer les fonctionnalités de nettoyage de l'historique des ventes

Pour configurer et utiliser la tâche périodique *Nettoyage de l'historique des mises à jour des ventes* avec toutes les fonctionnalités décrites dans cet article, vous devez activer les fonctionnalités *Améliorations des performances du nettoyage de l'historique des ventes* et *Nettoyer l'historique des mises à jour des ventes en fonction de l'âge* dans la Gestion des fonctionnalités, comme décrit dans les sous-sections suivantes.

### <a name="sales-history-cleanup-performance-improvements"></a>Améliorations des performances du nettoyage de l’historique des ventes

Le traitement par lots périodique du **nettoyage de l’historique des ventes** peut prendre beaucoup de temps s’il est rarement exécuté dans les environnements avec un volume important de mises à jour des ventes. Dans ces situations, la fonctionnalité *Améliorations des performances de nettoyage de l’historique des ventes* peut aider à réduire la durée d’exécution et à améliorer la fiabilité.

La fonctionnalité améliore le travail de nettoyage existant des manières suivantes :

- Il divise le nettoyage en lots (vous pouvez modifier la taille du lot via des personnalisations).
- Il fonctionnera pendant un maximum de 2 heures (vous pouvez modifier la durée via les personnalisations).
- Dans la mesure du possible, les capacités de la base de données seront exploitées pour réduire les conflits de blocage et éviter de joindre des tables transactionnelles pendant le nettoyage.

Après avoir activé la fonctionnalité, le traitement par lots **Nettoyage de l’historique des mises à jour des ventes** (**Ventes et marketing \> Tâches périodiques \> Nettoyer \> Nettoyage de l’historique des mises à jour des ventes**) fonctionnera comme avant, mais avec de meilleures performances et pour un maximum de 2 heures. Cela signifie qu’il peut avoir besoin de s’exécuter plusieurs fois pour nettoyer toutes les données pendant une période de conservation spécifique.

Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Ventes et marketing*
- **Nom de la fonctionnalité :** *Améliorations des performances de nettoyage de l’historique des ventes*

### <a name="clean-up-sales-update-history-based-on-age"></a>Nettoyer l’historique des mises à jour de ventes selon l’âge

La fonctionnalité *Nettoyer l’historique des mises à jour de ventes selon l’âge* vous permet de spécifier l'âge maximal des enregistrements à conserver lors de l'exécution de la tâche périodique *Nettoyage de l’historique des mises à jour des ventes*. Les enregistrements plus anciens seront supprimés. Cette fonctionnalité est utile lorsque vous configurez la tâche pour qu’elle s’exécute périodiquement, car l’âge est toujours calculé par rapport au moment d’exécution de la tâche. Si vous n'utilisez pas cette fonctionnalité, vous ne pouvez définir qu’une date spécifique pour les enregistrements les plus anciens à conserver.

Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Ventes et marketing*
- **Nom de la fonctionnalité :** *Nettoyer l’historique des mises à jour de ventes selon l’âge*

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Configurer et planifier la tâche périodique de nettoyage de l'historique des ventes

Pour configurer et planifier la tâche périodique *Nettoyage de l'historique des ventes*, procédez comme suit.

1. Analysez les besoins de votre entreprise pour déterminer le nombre de jours de données de l'historiques de validation des commandes clients que vous devez conserver. Nous vous recommandons généralement d'exécuter la tâche de nettoyage tous les trois mois et au maximum tous les six mois.
1. Accédez à **Ventes et marketing \> Tâches périodiques \> Nettoyage \> Nettoyage de l'historique des mises à jour des ventes**.
1. Dans la boîte de dialogue **Nettoyer l'historique de mises à jour des ventes**, sur le raccourci **Paramètres**, définissez les champs suivants :

    - **Nettoyer** : sélectionnez l'une des valeurs suivantes pour spécifier le type d'enregistrements à nettoyer :

        - **Réalisé** : supprime uniquement les enregistrements qui ont été entièrement traités. Étant donné qu'il est peu probable que vous utilisiez davantage ces enregistrements, cette option est la plus sûre.
        - **Réalisé et erroné** : supprime à la fois les enregistrements entièrement traités et les enregistrements où une erreur s'est produite. Cette option est la plus couramment utilisée. Vous voudrez peut-être inspecter et même corriger les enregistrements erronés au lieu de les faire nettoyer automatiquement. Cependant, de nombreuses entreprises choisissent de nettoyer également ces enregistrements après environ un mois, car ils ne sont probablement plus pertinents à ce moment-là.
        - **Tous** : supprime les enregistrements exécutés, erronés et en attente. Les dossiers d'attente sont valides mais n'ont pas encore été entièrement traités. Dans la plupart des cas, vous ne souhaitez probablement pas qu'ils soient supprimés automatiquement. Cependant, dans certaines situations, vous pouvez choisir de les supprimer automatiquement après un certain laps de temps.

    - **Conserver les enregistrements en fonction de l'âge** : spécifie si vous souhaitez nettoyer les enregistrements en fonction de leur ancienneté au jour de l'exécution de la tâche ou supprimer les enregistrements créés avant une date fixe. Si vous planifiez le nettoyage en tant que tâche récurrente, vous devez définir cette option sur *Oui*, car l'âge est toujours calculé par rapport à la date d'exécution de la tâche.

        - Définissez cette option sur *Oui* pour activer le champ **Âge maximal**. Vous utilisez ce champ pour spécifier l'âge maximum des enregistrements à conserver à chaque exécution de la tâche. Le champ **Créé jusqu'à** est ignoré.
        - Définissez cette option sur *Non* pour activer le champ **Créé jusqu'à**. Vous utilisez ce champ pour spécifier la date de création la plus ancienne des enregistrements à conserver lors de l'exécution de la tâche. Le champ **Âge maximal** est ignoré.

    - **Créé jusqu'à** : ce paramètre s'applique uniquement lorsque l'option **Conserver les enregistrements en fonction de l'âge** est définie sur *Non*. Spécifiez la date de création la plus ancienne des enregistrements à conserver lors de l'exécution de la tâche. Les enregistrements créés avant cette date seront supprimés.
    - **Âge maximal** : ce paramètre s'applique uniquement lorsque l'option **Conserver les enregistrements en fonction de l'âge** est définie sur *Oui*. Spécifiez l'âge maximum (en jours) des enregistrements à conserver à chaque exécution de la tâche. Les enregistrements plus anciens seront supprimés.

1. Sur l’organisateur **Exécuter en arrière-plan**, spécifiez comment, quand et à quelle fréquence la tâche est exécutée. Utilisez ces paramètres pour implémenter la planification que vous avez déterminée à l'étape 1. Les champs fonctionnent comme pour d’autres types de [tâches de traitement par lots](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Sélectionnez **OK** pour appliquer vos paramètres et fermer la boîte de dialogue.
