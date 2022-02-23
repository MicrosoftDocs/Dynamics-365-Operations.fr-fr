---
title: Configurer le traitement de la vague
description: Cette rubrique décrit la procédure de paramétrage des critères qui déterminent le travail généré pour un entrepôt lorsqu'une vague est traitée et si les vagues sont traitées manuellement ou automatiquement.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa193f6d62613893f9d5da4351d43a810dbf1596
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428276"
---
# <a name="configure-wave-processing"></a>Configurer le traitement de la vague

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit la procédure de paramétrage des critères qui déterminent le travail généré pour un entrepôt lorsqu'une vague est traitée et si les vagues sont traitées manuellement ou automatiquement. Vous devez spécifier les critères en paramétrant des modèles de vague et des requêtes qui correspondent à une vague avec des lignes libérées dans des commandes client, des ordres de fabrication ou de kanbans. Le traitement de vague est utilisé dans des entrepôts qui utilisent la fonctionnalité dans le module Gestion des entrepôts, et non ceux qui utilisent la fonctionnalité dans le module Gestion des stocks. Vous pouvez exécuter cette procédure dans les données de démonstration de la société fictive USMF.

1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Vagues > Modèles de vague**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Nom du modèle de vague**. Lorsque vous paramétrez un modèle de vague, vous devez spécifier l'ordre dans lequel les modèles sont mis en correspondance avec les lignes finales pour les commandes client, les ordres de fabrication ou les kanbans. Lorsqu'une ligne est lancée dans l'entrepôt ou en production, elle utilise le premier modèle de vague pour lequel la ligne respecte les critères. Il est recommandé de placer le modèle avec les critères les plus spécifiques en haut de la liste. Plus les critères sont larges, plus une ligne sera susceptible d'y répondre et cela peut entraîner l'affectation de lignes à la mauvaise vague.  
4. Tapez une valeur dans le champ **Description du modèle de vague**.
5. Entrez ou sélectionnez une valeur dans le champ **Site**. Si vous utilisez USMF, vous pouvez sélectionner site 2.  
6. Entrez ou sélectionnez une valeur dans le champ **Entrepôt**. Si vous utilisez USMF, vous pouvez sélectionner l'entrepôt 24.  
7. Définissez le champ **Création automatique de vagues** sur **Oui**. Sélectionnez cette option pour créer automatiquement une vague lorsqu'une commande client, un ordre de fabrication, ou un kanban est libéré dans l'entrepôt.  
8. Définissez l'option **Traiter la vague à la sortie dans l'entrepôt** sur **Oui**. Sélectionnez cette option pour traiter automatiquement la vague et créer le travail lorsqu'une ligne est libérée pour l'entrepôt.  
9. Définissez l'option **Sortie automatique de vagues** sur **Oui**. Sélectionnez cette option pour libérer automatiquement la vague. Le travail de prélèvement est créé et rendu disponible sur les appareils mobiles.  
10. Définissez l'option **Affecter à des vagues en cours** sur **Oui**. Les lignes sont affectées aux vagues en fonction du filtre de requête du modèle de vague.  
11. Définissez l'option **Traiter la vague automatiquement au seuil** sur **Oui**. Sélectionnez cette option pour traiter automatiquement la vague lorsque ses valeurs atteignent les seuils pour le poids, l'expédition, et les lignes spécifiées dans le groupe de champs Seuils de vague. Cette option est uniquement disponible si l'option Expédition est sélectionnée dans le champ Type de modèle de vague.  
12. Définissez l'option **Automatiser la libération du travail de réapprovisionnement** sur **Oui**. Sélectionnez cette option pour créer un travail de réapprovisionnement basé sur la demande et le libérer automatiquement. Vous devez ajouter la méthode de vague de réapprovisionnement au modèle de vague, puis créer un modèle de réapprovisionnement du type Demande de vague.  
13. Développez la section **Méthodes**.

    - Avec les méthodes de modèle de vague, contrôlez la séquence d'activités exécutée par chaque vague lorsqu'elle est traitée. Par exemple, vous pouvez avoir une méthode pour le réapprovisionnement de vague. Lorsque vous ajoutez une méthode, elle est automatiquement répertoriée dans l'emplacement adapté dans la suite d'étapes. Si vous avez défini l'option Automatiser la libération du travail de réapprovisionnement sur Oui, vous devez ajouter la méthode de réapprovisionnement ici.  
    - Les attributs de vague agissent en tant que filtres, pour limiter le type d'article pouvant utiliser la vague. Vous pouvez par exemple spécifier un groupe d'articles.  
14. Cliquez sur **Enregistrer**.
15. Fermez la page.
16. Accédez à **Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts**.
17. Développez la section **Traitement de vague**.
18. Entrez ou sélectionnez une valeur dans le champ **Groupe de traitements par lots pour le traitement de la vague**.
19. Définissez l'option **Traiter les vagues dans des traitements par lots** sur **Oui**.
20. Entrez un nombre dans le champ **Attendre le verrouillage (ms)**. Permet d'entrer le temps, exprimé en millisecondes, pendant lequel une étape de répartition attendra une ressource système qui est verrouillée par une autre étape de répartition. Lorsque ce temps est dépassé, la vague n'est pas traitée et un message d'erreur s'affiche.  
21. Cliquez sur **Enregistrer**.
22. Fermez la page.
23. Allez dans **Volet de navigation > Modules > Contrôle de la production > Paramétrage > Paramètres de contrôle de la production**.
24. Sélectionnez une option dans le champ **Libérer dans l'entrepôt**.

Pour les commandes client et des commandes kanban, le stock doit être réservé avant que la commande ne soit libérée dans l'entrepôt. Sinon, les articles ou les lignes de répartition ne pourront pas être traités dans une vague. Pour les ordres de fabrication, vous avez également la possibilité de choisir Autoriser une réservation partielle. Par exemple, cela peut s'avérer utile si vous disposez des matières premières nécessaires pour démarrer une production, et si pouvez attendre jusqu'à ce que les matières premières supplémentaires deviennent disponibles pour terminer le processus. Si vous sélectionnez cette option, vous devez répéter manuellement le processus de libération dans l'entrepôt lorsque des matières premières supplémentaires deviennent disponibles.  
25. Fermez la page.

