---
title: "Dimensions financières"
description: "Cet article décrit les différents types de dimensions financières et leurs paramétrages."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Dimensions financières

Cet article décrit les différents types de dimensions financières et leurs paramétrages.

La page Dimensions financières permet de créer les dimensions financières à utiliser en tant que segments de compte pour les plans de comptes partagés. Il existe deux types de dimensions financières, les dimensions personnalisées et les dimensions soutenues par une entité. Les dimensions personnalisées sont partagées dans les entités juridiques et les valeurs sont saisies et mises à jour par l'utilisateur. Les dimensions soutenues par l'entité sont des dimensions dont les valeurs sont définies ailleurs dans le système, tels que les clients ou les magasins. Certaines dimensions soutenues par l'entité sont partagées au sein des entités juridiques, et certaines dimensions soutenues par l'entité sont spécifiques à la société. 

Une fois les dimensions financières créées, la page Valeurs de dimensions financières permet d'affecter des propriétés supplémentaires à chacune d'elles. 

Bien que vous puissiez utiliser les dimensions financières pour représenter les entités juridiques sans créer les entités juridiques de Microsoft Dynamics 365 pour les opérations, des dimensions financières ne sont pas conçues pour satisfaire l'opérationnel ou l'entreprise des entités juridiques. La fonctionnalité de comptabilité interunités dans Microsoft Dynamics 365 pour les opérations est conçue pour corriger uniquement les écritures comptables créées par chaque transaction. 

Avant de paramétrer les dimensions financières comme entités juridiques, évaluez vos processus entreprise dans les zones suivantes pour déterminer si ce paramétrage fonctionnera pour votre organisation :

-   Stock
-   Ventes et achats entre les dimensions financières et les entités juridiques
-   Calcul de la taxe et génération d'états
-   Génération d'états opérationnels

Voici des exemples des limitations :

-   Vous ne pouvez utiliser la fonctionnalité de taxe qu'avec des entités juridiques, pas avec les dimensions financières.
-   Certains états n'incluent pas les dimensions financières, vous ne pouvez donc pas toujours déclarer par dimension financière, sauf si ces états sont modifiés.

**Custom dimensions** 

Pour créer une dimension financière définie par l'utilisateur, qui valeurs d'utilisation du champ, sélectionnez &lt; la dimension personnalisée &gt;. Vous pouvez également spécifier un compte pour limiter la quantité et le type d'informations que vous pouvez entrer pour les valeurs de dimension. Vous pouvez entrer des caractères qui restent identiques pour chaque valeur de dimension, telles que des lettres ou un trait d'union. Vous pouvez également entrer des signes dièse (\#) et les perluètes (et) comme espaces réservés pour les lettres et des chiffres qui sont modifiées chaque fois qu'une valeur de dimension est créée. Utilisez un symbole numérique (\#) comme espace réservé pour un numéro et une esperluette (et) comme espace réservé pour une lettre. 

**Exemple** 

Pour limiter la valeur de dimension aux lettres cc et à trois chiffres, vous entrez cc\#\#\# comme le masque de format. Ce champ est disponible uniquement lorsque vous sélectionnez &lt; la dimension spécifiée &gt; dans valeurs de champ utilisé. 

** Dimensions soutenues par entité ** 

Pour créer une entité a soutenu la dimension financière, dans valeurs d'utilisation du champ, sélectionnez une entité définie par le système sur laquelle baser la dimension financière. Les valeurs de dimension financière sont créées depuis cette sélection. Par exemple, pour créer des valeurs de dimension pour les projets, sélectionnez Projets. Une valeur de dimension est créée pour chaque nom de projet. La page des valeurs de dimension indique les valeurs de l'entité et, si elles sont propres à la société, la société pour la valeur. 

** L'activation de dimensions ** 

L'activation de la dimension financière met à jour la table avec le nom de dimension financière et supprime les dimensions supprimées. Vous pouvez entrer des valeurs de dimension avant d'activer une dimension financière, mais une dimension financière ne peut pas être consommée tant qu'elle n'est pas activée. Par exemple, vous ne pouvez pas ajouter de dimension financière à une structure de compte tant que la dimension financière n'a pas été activée. Cliquez sur Activer mettra à jour toutes les dimensions avec les changements de statut. 

**Translations** 

La page de traduction de texte vous permet d'entrer le texte à afficher dans différentes langues pour la dimension financière sélectionnée. La page Conversion de compte principal vous permet de saisir le texte à afficher dans différentes langues pour le compte principal. 

**Legal entity overrides** 

Toutes les dimensions sont valides pour toutes les entités juridiques et certains peuvent uniquement être appropriés pour une période spécifique. Dans ce scénario, la section Remplacements des entités juridiques peut être utilisée pour identifier les sociétés pour lesquelles la dimension doit être suspendue, le propriétaire et la période d'activité de la dimension.




