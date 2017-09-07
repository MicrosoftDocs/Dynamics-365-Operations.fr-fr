---
title: "Dimensions financières"
description: "Cette rubrique décrit les différents types de dimensions financières et leur configuration."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: b5615a6d9003554593981ce65be0283a249a7d93
ms.contentlocale: fr-fr
ms.lasthandoff: 08/01/2017

---

# <a name="financial-dimensions"></a>Dimensions financières

[!include[banner](../includes/banner.md)]

Cette rubrique explique les différents types de dimensions financières et leur configuration.

La page **Dimensions financières** permet de créer les dimensions financières à utiliser en tant que segments de compte pour les plans de comptes partagés. Il existe deux types de dimensions financières : les dimensions personnalisées et les dimensions soutenues par une entité. Les dimensions personnalisées sont partagées dans les entités juridiques et les valeurs sont saisies et mises à jour par les utilisateurs. Pour les dimensions soutenues par une entité, les valeurs sont définies ailleurs dans le système, tels que les entités Clients ou Magasins. Certaines dimensions soutenues par l'entité sont partagées au sein des entités juridiques, tandis que d'autres dimensions soutenues par l'entité sont spécifiques à la société. 

Une fois les dimensions financières créées, la page **Valeurs de dimensions financières** permet d'affecter des propriétés supplémentaires à chacune d'elles. 

Vous pouvez utiliser des dimensions financières pour représenter les entités juridiques. Vous ne devez pas créer les entités juridiques de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Toutefois, les dimensions financières ne sont pas conçues pour résoudre les exigences opérationnelles ou métier des entités juridiques. La fonctionnalité de comptabilité interunités dans Finance and Operations est conçue pour uniquement pour les écritures comptables créées par chaque transaction. 

Avant de paramétrer les dimensions financières comme entités juridiques, évaluez vos processus entreprise dans les zones suivantes pour déterminer si ce paramétrage fonctionnera pour votre organisation :

- Stock
- Ventes et achats entre les dimensions financières et les entités juridiques
- Calcul de la taxe et génération d'états
- Génération d'états opérationnels

Voici certaines des limitations :

- Vous ne pouvez utiliser la fonctionnalité de taxe qu'avec des entités juridiques, pas avec les dimensions financières.
- Certains états n'incluent pas les dimensions financières. Par conséquent, pour générer des états par dimension financière, vous devez modifier les états.

## <a name="custom-dimensions"></a>Dimensions personnalisées

Pour créer une dimension financière définie par l'utilisateur, dans le champ **Utiliser les valeurs à partir de**, sélectionnez **&lt; Dimension personnalisée &gt;**. Vous pouvez également spécifier un compte pour limiter la quantité et le type d'informations que vous pouvez entrer pour les valeurs de dimension. Vous pouvez entrer des caractères qui restent identiques pour chaque valeur de dimension, telles que des lettres ou un trait d'union (-). Vous pouvez également entrer des signes dièse (\#) et des esperluettes (&) comme espaces réservés pour les lettres et les chiffres qui changent chaque fois qu'une valeur de dimension est créée. Utilisez un symbole dièse (\#) comme espace réservé pour un nombre et une esperluette (&) comme espace réservé pour une lettre. Le champ du masque de format est disponible uniquement lorsque vous sélectionnez **&lt; Dimension personnalisée &gt;** dans le champ **Utiliser les valeurs à partir de**.

**Exemple**

Pour limiter la valeur de dimension aux lettres « CC » et trois chiffres, entrez **CC-\#\#\#** comme masque de format.

## <a name="entity-backed-dimensions"></a>Dimensions soutenues par l'entité

Pour créer une dimension financière soutenue par l'entité, dans le champ **Utiliser les valeurs à partir de**, sélectionnez une entité définie par le système sur laquelle baser la dimension financière. Les valeurs de dimension financière sont alors créées depuis cette entité. Par exemple, pour créer des valeurs de dimension pour les projets, sélectionnez **Projets**. Une valeur de dimension est alors créée pour chaque nom de projet. La page **Valeurs de dimensions financières** affiche les valeurs de l'entité. Si ces valeurs sont spécifiques à une société, la page indique également la société.

## <a name="activating-dimensions"></a>Activer les dimensions

Lorsque vous activez une dimension financière, la table est mise à jour pour afficher le nom de la dimension financière. Les dimensions supprimées sont retirées. Vous pouvez entrer des valeurs de dimension avant d'activer une dimension financière. Toutefois, une dimension financière ne peut pas être consommée partout tant qu'elle n'est pas activée. Par exemple, vous ne pouvez pas ajouter de dimension financière à une structure de compte tant que la dimension financière n'a pas été activée. Lorsque vous cliquez sur **Activer**, toutes les dimensions sont mises à jour et le statut change. 

## <a name="translations"></a>Traductions

Dans la page **Traduction de texte**, vous pouvez entrer du texte pour la dimension financière sélectionnée dans différentes langues. Dans la page **Conversion de compte principal**, vous pouvez entrer du texte pour le compte principal dans différentes langues. 

## <a name="legal-entity-overrides"></a>Remplacements des entités juridiques

Toutes les dimensions ne sont pas valides pour toutes les entités juridiques. En outre, certaines dimensions ne peuvent être appropriées que pour une période spécifique. Dans ces cas, vous pouvez utiliser la section **Remplacements des entités juridiques** pour identifier les sociétés pour lesquelles la dimension doit être suspendue, le propriétaire et la période d'activité de la dimension.

## <a name="deleting-financial-dimensions"></a>Suppression des dimensions financières

Pour aider à gérer l'intégrité référentielle des données, les dimensions financières peuvent rarement être supprimées. Si vous tentez de supprimer une dimension financière, les critères suivants sont évalués :

- La dimension financière a-t-elle été utilisée dans les transactions validées ou non validées, ou un type de combinaisons de valeurs de dimension ?
- La dimension financière est -elle utilisée dans une structure de compte active, une structure de règle avancée ou un ensemble de dimensions financières ?
- La partie de dimension financière fait-elle partie d'un format d'intégration de dimension financière par défaut ?
- La dimension financière a-t-elle été paramétrée comme dimension par défaut ?

Si un critère est réuni, vous ne pourrez pas supprimer la dimension financière.


Pour plus d'informations, voir les rubriques suivantes :
- [Définir des dimensions financières](tasks/define-financial-dimensions.md)
- [Tenir à jour les modèles par défaut de dimension financière](tasks/maintain-financial-dimension-default-templates.md)

