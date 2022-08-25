---
title: Exemple de configuration de traitement des vagues
description: Cet article illustre la procédure de paramétrage des critères qui déterminent quel travail est généré pour un entrepôt lorsqu’une vague est traitée, et quelles vagues sont traitées manuellement ou automatiquement.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a8c088f8726573e4b1fcad1944676547391a9bf
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219626"
---
# <a name="configure-wave-processing-example"></a>Exemple de configuration de traitement des vagues

[!include [banner](../../includes/banner.md)]

Cet article illustre la procédure de paramétrage des critères qui déterminent quel travail est généré pour un entrepôt lorsqu’une vague est traitée, et quelles vagues sont traitées manuellement ou automatiquement. Vous devez spécifier les critères en paramétrant des modèles de vague et des requêtes qui correspondent à une vague avec des lignes libérées dans des commandes client, des ordres de fabrication ou de kanbans.

## <a name="enable-sample-data"></a>Activer les exemples de données

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. Vous devez également sélectionner l’entité juridique **USMF** avant de commencer.

## <a name="example-scenario-configure-wave-processing"></a>Exemple de scénario : configuration du traitement des vagues

Cet exemple de scénario décrit de nombreux paramètres divers qui affectent la manière dont les vagues sont créées, remplies, traitées et libérées.

1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Vagues > Modèles de vague**.
1. Sélectionnez **Nouveau**.
1. Tapez une valeur dans le champ **Nom du modèle de vague**. Lorsque vous paramétrez un modèle de vague, vous devez spécifier l’ordre dans lequel les modèles sont mis en correspondance avec les lignes finales pour les commandes client, les ordres de fabrication ou les kanbans. Lorsqu’une ligne est lancée dans l’entrepôt ou en production, elle utilise le premier modèle de vague pour lequel la ligne respecte les critères. Il est recommandé de placer le modèle avec les critères les plus spécifiques en haut de la liste. Plus les critères sont larges, plus une ligne sera susceptible d’y répondre et cela peut entraîner l’affectation de lignes à la mauvaise vague.  
1. Tapez une valeur dans le champ **Description du modèle de vague**.
1. Entrez ou sélectionnez une valeur dans le champ **Site**. Si vous utilisez USMF, vous pouvez sélectionner site 2.  
1. Entrez ou sélectionnez une valeur dans le champ **Entrepôt**. Si vous utilisez USMF, vous pouvez sélectionner l’entrepôt 24.  
1. Définissez le champ **Création automatique de vagues** sur **Oui**. Sélectionnez cette option pour créer automatiquement une vague lorsqu’une commande client, un ordre de fabrication, ou un kanban est libéré dans l’entrepôt.  
1. Définissez l’option **Traiter la vague à la sortie dans l’entrepôt** sur **Oui**. Sélectionnez cette option pour traiter automatiquement la vague et créer le travail lorsqu’une ligne est libérée pour l’entrepôt.  
1. Définissez l’option **Sortie automatique de vagues** sur **Oui**. Sélectionnez cette option pour libérer automatiquement la vague. Le travail de prélèvement est créé et rendu disponible sur les appareils mobiles.  
1. Définissez l’option **Affecter à des vagues en cours** sur **Oui**. Les lignes sont affectées aux vagues en fonction du filtre de requête du modèle de vague.  
1. Définissez l’option **Traiter la vague automatiquement au seuil** sur **Oui**. Sélectionnez cette option pour traiter automatiquement la vague lorsque ses valeurs atteignent les seuils pour le poids, l’expédition, et les lignes spécifiées dans le groupe de champs **Seuils de vague**. Cette option est uniquement disponible si l’option **Expédition** est sélectionnée dans le champ **Type de modèle de vague**.  
1. Définissez l’option **Automatiser la libération du travail de réapprovisionnement** sur **Oui**. Sélectionnez cette option pour créer un travail de réapprovisionnement basé sur la demande et le libérer automatiquement. Vous devez ajouter la méthode de vague de réapprovisionnement au modèle de vague, puis créer un modèle de réapprovisionnement utilisant le type **Demande de vague**.  
1. Utilisez les paramètres du groupe de champs **Valeurs par défaut** pour attribuer des attributs de vague. Les attributs de vague agissent en tant que filtres, pour limiter le type d’article pouvant utiliser la vague. Vous pouvez par exemple spécifier un groupe d’articles.  
1. Développez la section **Méthodes** et définissez les actions entreprises par le modèle de vague. Avec les méthodes de modèle de vague, contrôlez la séquence d’activités exécutée par chaque vague lorsqu’elle est traitée. Par exemple, vous pouvez avoir une méthode pour le réapprovisionnement de vague. Lorsque vous ajoutez une méthode, elle est automatiquement répertoriée dans l’emplacement adapté dans la suite d’étapes. Si vous avez défini l’option **Automatiser la libération du travail de réapprovisionnement** sur **Oui**, vous devez ajouter la méthode de réapprovisionnement ici.  
1. Sélectionnez **Enregistrer**.
1. Fermez la page.
1. Accédez à **Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts**.
1. Développez la section **Traitement de vague**.
1. Entrez ou sélectionnez une valeur dans le champ **Groupe de traitements par lots pour le traitement de la vague**.
1. Définissez l’option **Traiter les vagues dans des traitements par lots** sur **Oui**.
1. Entrez un nombre dans le champ **Attendre le verrouillage (ms)**. Permet d’entrer le temps, exprimé en millisecondes, pendant lequel une étape de répartition attendra une ressource système qui est verrouillée par une autre étape de répartition. Lorsque ce temps est dépassé, la vague n’est pas traitée et un message d’erreur s’affiche.  
1. Sélectionnez **Enregistrer**.
1. Fermez la page.
1. Allez dans **Volet de navigation > Modules > Contrôle de la production > Paramétrage > Paramètres de contrôle de la production**.
1. Sélectionnez une option dans le champ **Libérer dans l’entrepôt**.

    Pour les commandes client et des commandes kanban, le stock doit être réservé avant que la commande ne soit libérée dans l’entrepôt. Sinon, les articles ou les lignes de répartition ne pourront pas être traités dans une vague. Pour les ordres de fabrication, vous avez également la possibilité de choisir **Autoriser une réservation partielle**. Par exemple, cela peut s’avérer utile si vous disposez des matières premières nécessaires pour démarrer une production, et si pouvez attendre jusqu’à ce que les matières premières supplémentaires deviennent disponibles pour terminer le processus. Si vous sélectionnez cette option, vous devez répéter manuellement le processus de libération dans l’entrepôt lorsque des matières premières supplémentaires deviennent disponibles.
1. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Création et traitement des vagues](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
