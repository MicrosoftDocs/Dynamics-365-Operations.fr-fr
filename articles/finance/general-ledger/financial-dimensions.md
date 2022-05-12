---
title: Dimensions financières
description: Cette rubrique décrit les différents types de dimensions financières et leur configuration.
author: aprilolson
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 36e667e8dd1282e788eb40cd392baa9db824cec2
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644357"
---
# <a name="financial-dimensions"></a>Dimensions financières

[!include [banner](../includes/banner.md)]

Cette rubrique explique les différents types de dimensions financières et leur configuration.

La page **Dimensions financières** permet de créer les dimensions financières à utiliser en tant que segments de compte pour les plans de comptes partagés. Il existe deux types de dimensions financières : les dimensions personnalisées et les dimensions soutenues par une entité. Les dimensions personnalisées sont partagées dans les entités juridiques et les valeurs sont saisies et mises à jour par les utilisateurs. Pour les dimensions soutenues par une entité, les valeurs sont définies ailleurs dans le système, par exemple dans les entités Clients ou Magasins. Certaines dimensions soutenues par l’entité sont partagées au sein des entités juridiques, tandis que d’autres dimensions soutenues par l’entité sont spécifiques à la société.

Une fois les dimensions financières créées, la page **Valeurs de dimensions financières** permet d’affecter des propriétés supplémentaires à chacune d’elles.

Vous pouvez utiliser des dimensions financières pour représenter les entités juridiques. Vous ne devez pas créer les entités juridiques dans Dynamics 365 Finance. Toutefois, les dimensions financières ne sont pas conçues pour répondre aux exigences opérationnelles ou métier des entités juridiques. La fonctionnalité de comptabilité interunité dans Finance est conçue pour uniquement pour les écritures comptables créées par chaque transaction.

Avant de paramétrer les dimensions financières comme entités juridiques, évaluez vos processus entreprise dans les zones suivantes pour déterminer si ce paramétrage fonctionnera pour votre organisation :

- Stock
- Ventes et achats entre les dimensions financières et les entités juridiques
- Calcul de la taxe et génération d’états
- Génération d’états opérationnels

Voici certaines des limitations :

- Vous ne pouvez utiliser la fonctionnalité de taxe qu’avec des entités juridiques, pas avec les dimensions financières.
- Certains états n’incluent pas les dimensions financières. Par conséquent, pour générer des états par dimension financière, vous devez modifier les états.

## <a name="custom-dimensions"></a>Dimensions personnalisées

Pour créer une dimension financière définie par l’utilisateur, dans le champ **Utiliser les valeurs à partir de**, sélectionnez **Dimension personnalisée**.

Vous pouvez également spécifier un masque de compte pour limiter la quantité et le type d’informations qu peuvent être entrées pour les valeurs de dimension. Vous pouvez entrer des caractères qui restent identiques pour chaque valeur de dimension, telles que des lettres ou un trait d’union (-). Vous pouvez également entrer des symboles dièse (\#) et des esperluettes (&) comme espaces réservés pour les caractères qui changent chaque fois qu’une valeur de dimension est créée. Utilisez un symbole dièse (\#) comme espace réservé pour un nombre et une esperluette (&) comme espace réservé pour une lettre. Le champ du masque de format est disponible uniquement quand vous sélectionnez **Dimension personnalisée** dans le champ **Utiliser les valeurs à partir de**.

**Exemple**

Pour limiter la valeur de dimension aux lettres « CC » et trois chiffres, entrez **CC-\#\#\#** comme masque de format.

## <a name="entity-backed-dimensions"></a>Dimensions soutenues par l’entité

Pour créer une dimension financière soutenue par l’entité, dans le champ **Utiliser les valeurs à partir de**, sélectionnez une entité définie par le système sur laquelle baser la dimension financière. Les valeurs de dimension financière sont alors créées depuis cette entité. Par exemple, pour créer des valeurs de dimension pour les projets, sélectionnez **Projets**. Une valeur de dimension est alors créée pour chaque nom de projet. La page **Valeurs de dimensions financières** affiche les valeurs de l’entité. Si ces valeurs sont spécifiques à une société, la page indique également la société.

## <a name="activating-dimensions"></a>Activer les dimensions

Quand vous activez une dimension financière, la table est mise à jour pour afficher le nom de la dimension financière. Les dimensions supprimées sont retirées. Vous pouvez entrer des valeurs de dimension avant d’activer une dimension financière. Toutefois, une dimension financière ne peut pas être consommée partout tant qu’elle n’est pas activée. Par exemple, vous ne pouvez pas ajouter de dimension financière à une structure de compte tant que la dimension financière n’a pas été activée. Quand vous sélectionnez **Activer**, toutes les dimensions sont mises à jour et affichent les changements de statut.

## <a name="translations"></a>Traductions

Dans la page **Traduction de texte**, vous pouvez entrer du texte pour la dimension financière sélectionnée dans différentes langues. Dans la page **Conversion de compte principal**, vous pouvez entrer du texte pour le compte principal dans différentes langues. 

## <a name="legal-entity-overrides"></a>Remplacements des entités juridiques

Toutes les dimensions ne sont pas valides pour toutes les entités juridiques. En outre, certaines dimensions ne peuvent être appropriées que pour une période spécifique. Dans ces cas, vous pouvez utiliser la section **Remplacements des entités juridiques** pour identifier les sociétés pour lesquelles la dimension doit être suspendue, le propriétaire et la période d’activité de la dimension.

## <a name="deleting-financial-dimensions"></a>Suppression des dimensions financières

Pour aider à gérer l’intégrité référentielle des données, les dimensions financières peuvent rarement être supprimées. Si vous tentez de supprimer une dimension financière, les critères suivants sont évalués :

- La dimension financière a-t-elle été utilisée dans les transactions validées ou non validées, ou dans un type de combinaison de valeurs de dimension ?
- La dimension financière est -elle utilisée dans une structure de compte active, une structure de règle avancée ou un ensemble de dimensions financières ?
- La partie de dimension financière fait-elle partie d’un format d’intégration de dimension financière par défaut ?
- La dimension financière a-t-elle été paramétrée comme dimension par défaut ?
- La dimension financière a-t-elle été désélectionnée dans la configuration de Financial Reporting ? 

Si un critère est réuni, vous ne pourrez pas supprimer la dimension financière.

> [!NOTE]
> À compter de la version 10.0.27 de Finance, les dimensions financières ne seront plus automatiquement sélectionnées pour la configuration de Financial Reporting à leur création. 

## <a name="default-dimension-values"></a>Valeurs de dimension par défaut

Vous pouvez utiliser les valeurs des enregistrements principaux, tels que les enregistrements client et fournisseur, comme valeurs par défaut dans de nouvelles dimensions. Quand les nouvelles dimensions sont créées, l’ID enregistrement principal est entré dans les valeurs de dimension pour ces enregistrements principaux. Par exemple, quand vous créez un nouveau client, l’ID client est entré dans la dimension client. Quand vous créez des commandes client, des factures ou d’autres documents nécessitant un ID client, les règles par défaut existantes sont utilisées, et l’ID client est ajouté au document.

Cette fonctionnalité est contrôlée par un paramètre de la dimension. Ce paramètre est appelé **Copier les valeurs dans cette dimension pour chaque nouveau DimensionName créé**, où **DimensionName** est le nom de la dimension. Par défaut, la fonctionnalité est désactivée. Toutefois, elle peut être activée à tout moment.

Si des enregistrements existent déjà pour la dimension, les enregistrements principaux sont mis à jour quand vous activez la fonctionnalité. Toutefois, les documents et les transactions existants ne sont pas mis à jour.

Si vous utilisez un modèle pour créer un enregistrement principal, vérifiez que la valeur du modèle de la dimension principale est vide. Par exemple, si vous créez des clients à partir d’un modèle, vérifiez que la dimension du client dans le modèle est vide. La valeur de la dimension du client est par défaut celle du nouveau numéro de client quand vous créez le client.  

## <a name="derived-dimensions"></a>Dimensions dérivées

Vous pouvez configurer une dimension afin que les informations des autres dimensions soient automatiquement saisies quand vous entrez cette dimension dans un document. Par exemple, si vous entrez le centre de coût 10, la valeur **20** peut être automatiquement entrée dans la dimension de département.

Vous pouvez paramétrer des valeurs dérivées sur la page des dimensions.

1. Sélectionnez une dimension, puis **Dimensions dérivées**.

    La page **Dimensions dérivées** contient une grille. Le segment de dimension sélectionné est la première colonne de cette grille.

2. Ajoutez les segments qui doivent être dérivés. Chaque segment s’affiche sous forme de colonne.

Entrez les combinaisons de dimensions qui doivent être dérivées de la dimension dans la première colonne. Par exemple, pour utiliser le centre de coût comme dimension d’où sont dérivées le département et l’emplacement, entrez le centre de coût 10, le département 20 et l’emplacement 30. Ensuite, quand vous entrez le centre de coût 10 dans un enregistrement principal ou sur une page de transaction, le département 20 et l’emplacement 30 sont entrés par défaut.

### <a name="overriding-existing-values-with-derived-dimensions"></a>Remplacement des valeurs existantes par des dimensions dérivées
 
Par défaut, le processus de dimension dérivée ne remplace pas les valeurs existantes des dimensions dérivées. Par exemple, si vous entrez le centre de coût 10 et qu’aucune autre dimension n’est entrée, le département 20 et l’emplacement 30 sont entrés par défaut. Cependant, si vous modifiez le centre de coût, les valeurs qui ont déjà été établies ne sont pas modifiées. Par conséquent, vous pouvez établir des dimensions par défaut sur les enregistrements principaux, et ces dimensions ne seront pas modifiées par les dimensions dérivées.

Vous pouvez modifier le comportement des dimensions dérivées pour remplacer les valeurs existantes en activant la case à cocher **Remplacer les valeurs de dimension existantes par les valeurs dérivées** sur la page **Dimensions dérivées**. Si ce champ est sélectionné, vous pouvez entrer une dimension avec des valeurs de dimension dérivées et ces valeurs de dimension dérivées remplacent toutes les valeurs déjà existantes. À l’aide de l’exemple précédent, si vous entrez le centre de coût 10 et qu’aucune autre dimension n’est entrée, le département 20 et l’emplacement 30 sont entrés par défaut. Toutefois, si les valeurs étaient déjà le département 50 et l’emplacement 60, les valeurs sont désormais modifiées avec le département 20 et l’emplacement 30.
 
Les dimensions dérivées avec ce paramètre ne remplacent pas automatiquement les valeurs de dimensions par défaut existantes quand des valeurs de dimension sont utilisées par défaut. Les valeurs de dimension seront uniquement remplacées quand vous entrerez une nouvelle valeur de dimension sur une page et qu’il existera des valeurs dérivées pour cette dimension sur la page.

### <a name="preventing-changes-with-derived-dimensions"></a>Empêcher des modifications avec des dimensions dérivées
 
Quand vous utilisez **Ajouter un segment** sur **Page de dimensions dérivées** pour ajouter un segment comme dimension dérivée, une option est fournie au bas de la page **Ajouter un segment** vous permettant d’empêcher que des modifications soient apportées à cette dimension quand  elle est dérivée sur une page. Le paramètre par défaut est désactivé afin de ne pas empêcher les valeurs de dimension dérivées d’être modifiées. Modifiez le paramètre sur **Oui** si vous voulez empêcher la dimension d’être modifiée après avoir été dérivée. Par exemple, si la valeur de la dimension Département est dérivée de la valeur de la dimension Centre de coût, la valeur Département ne peut pas être modifiée si le paramètre **Empêcher les modifications** est **Oui**. 
 
Le paramètre n’empêche pas les modifications si la valeur de dimension est valide mais qu’elle n’est pas répertoriée dans la liste de dimensions dérivées. Par exemple, si le département 20 est dérivé du centre de coût 10 et que vous entrez le centre de coût 10, vous ne pourrez pas modifier le département 20. Toutefois, si vous entrez le centre de coût 20 et qu’il n’est pas dans la liste des dimensions dérivées pour le centre de coût, vous pouvez modifier la valeur Département. 
 
Dans tous les cas, la valeur du compte et toutes les valeurs des dimensions seront validées par rapport aux structures de compte une fois les valeurs de dimensions dérivées appliquées. Si vous utilisez des dimensions dérivées et que leur validation échoue une fois utilisées sur une page, vous devez modifier les valeurs de dimensions dérivées sur la page de dimensions dérivées avant de pouvoir les utiliser dans les transactions. 
 
Quand vous modifiez les dimensions de l’organisateur **Dimensions financières**, la dimension marquée pour empêcher les modifications ne sera pas modifiable. Si vous entrez un compte et des dimensions dans le contrôle d’entrée segmenté d’une page, les dimensions sont modifiables. Toutefois, quand vous déplacez la mise en surbrillance du contrôle d’entrée segmenté et que vous passez à un autre champ ou effectuez une action, le compte et les dimensions seront validés par rapport à la liste de dimensions dérivées et les structures de compte pour s’assurer que vous avez entré les valeurs appropriées. 

### <a name="derived-dimensions-and-entities"></a>Dimensions dérivées et entités

Vous pouvez paramétrer les segments et les valeurs des dimensions dérivées à l’aide d’entités.

- L’entité Dimensions dérivées paramètre les dimensions pilotes et les segments utilisés pour ces dimensions.
- L’entité Valeur de dimensions dérivées permet d’importer les valeurs qui doivent être dérivées pour chaque dimension pilote.

Quand vous utilisez une entité pour importer des données, si cette entité importe des dimensions, les règles des dimensions dérivées sont appliquées pendant l’importation sauf si l’entité remplace spécifiquement ces dimensions.

Pour plus d’informations, voir les rubriques suivantes :

- [Définir des dimensions financières](tasks/define-financial-dimensions.md)
- [Tenir à jour les modèles par défaut de dimension financière](tasks/maintain-financial-dimension-default-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
