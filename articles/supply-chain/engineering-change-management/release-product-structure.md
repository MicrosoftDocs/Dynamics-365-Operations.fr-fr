---
title: Lancer les structures de produit
description: Cette rubrique explique comment vous pouvez lancer des structures produit complètes en plus de lancer des produits avec leurs versions d'ingénierie. De cette manière, vous pouvez vous assurer que les données produit pertinentes pour l'ingénierie peuvent facilement être réutilisées dans différentes entités juridiques.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 68f091cca9c3c2baa03813553127ee41abe6d522
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4428343"
---
# <a name="release-product-structures"></a>Lancer les structures de produit

[!include [banner](../includes/banner.md)]

Pour vous assurer que les données produit pertinentes pour l'ingénierie peuvent facilement être réutilisées dans différentes entités juridiques, vous pouvez lancer des structures produit complètes en plus de lancer des produits avec leurs versions d'ingénierie. Par conséquent, vous pouvez valider les structures de nomenclature à plusieurs niveaux avec le parent en une seule action de validation. Dans ce cas, la nomenclature et les produits de niveau inférieur sont également validés.

Les produits d'ingénierie sont créés et entretenus par leur société d'ingénierie de manière à répondre aux exigences de qualité au fur et à mesure de leur conception. Chaque entreprise opérationnelle qui fabrique un produit a besoin du même produit et de la même nomenclature sous-jacente. Selon l'installation de production, la gamme peut être créé localement. Dans ce cas, vous ne lancez pas de gamme avec le produit. Pour les entités juridiques qui vendront les produits mais ne les fabriqueront pas, la nomenclature peut ne pas être requise.

Pour rendre le processus plus efficace, toutes les données relatives à l'ingénierie peuvent être communiquées à d'autres sociétés opérationnelles en même temps. Ces données incluent la structure du produit. Au cours du processus de validation, vous pouvez choisir quelle partie des données produit doit être validée.

Pour plus d'informations sur les sociétés d'ingénierie et les sociétés opérationnelles, voir [Sociétés d'ingénierie et règles de propriété des données](engineering-org-data-ownership-rules.md).

Notez que vous pouvez valider à la fois les produits standard et les produits d'ingénierie avec la structure de produit de validation. Au cours de ce processus, toute la structure du produit sera validée, même la nomenclature et la gamme de la société dans laquelle les produits sont lancés.

Pour un exemple de lancement d'un produit, voir [Lancer un produit d'ingénierie à une entreprise locale](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>Données publiées pour un produit lorsque la structure de produit de lancement est utilisée

Les données suivantes sont incluses dans la version des produits d'ingénierie :

- **Données du produit** – Un nouveau produit lancé est créé.
- **Données de version d'ingénierie** – La version d'ingénierie et ses données sont créées ou mises à jour. Notez que si vous remettez à nouveau la même version d'ingénierie à une société opérationnelle, les données d'ingénierie seront écrasées.
- **Attributs d'ingénierie** – Les attributs d'ingénierie et leurs valeurs sont créés ou mis à jour.
- **Nomenclature d'ingénierie** – La nomenclature d'ingénierie et ses lignes peuvent être créées ou mises à jour. Pour plus d'informations sur la propriété des données, voir [Propriétaires de produits](product-owner.md).
- **Gammes d'ingénierie** – Les gammes d'ingénierie et leurs opérations peuvent être créés ou mis à jour. Pour plus d'informations sur la propriété des données, voir [Propriétaires de produits](product-owner.md).
- **Documents d'ingénierie** – Les documents d'ingénierie liés à la version d'ingénierie sont créés ou mis à jour.

Lorsque vous activez la gestion des modifications techniques sur votre système, la structure du produit de version est disponible. En outre, les produits standard incluront leurs nomenclatures et leurs gammes lorsqu'ils seront lancés.

## <a name="product-acceptance"></a>Acceptation du produit

**Acceptation du produit** est un paramètre clé qui influence le processus de lancement. Vous pouvez définir ce paramètre pour chaque entreprise en accédant à **Gestion du changement d'ingénierie \> Installer \> Paramètres de gestion des modifications techniques**. Pour plus d'informations, consultez [Paramètres de gestion des modifications techniques](engineering-parameters.md).

### <a name="automatic-product-acceptance"></a>Acceptation automatique des produits

Chaque version de produits d'ingénierie commence lorsque quelqu'un de la société d'ingénierie sélectionne un produit à lancer. Quand le paramètre **Acceptation du produit** est défini sur *Automatique*, l'utilisateur de la société d'ingénierie décide quelles données produit doivent être automatiquement transmises aux sociétés opérationnelles. Le produit sera ensuite automatiquement distribué aux entreprises sélectionnées dans l'assistant de publication.

### <a name="manual-product-acceptance"></a>Acceptation manuelle du produit

Chaque version de produits d'ingénierie commence lorsque quelqu'un de la société d'ingénierie sélectionne un produit à lancer. Quand le paramètre **Acceptation du produit** est défini sur *Manuel*, l'utilisateur de la société d'ingénierie décide quelles données produit doivent être automatiquement transmises aux sociétés opérationnelles. Un utilisateur de chaque société opérationnelle examine ensuite les données du produit et décide d'accepter ou non la version. L'utilisateur de l'entreprise opérationnelle peut définir les options suivantes lors de la réception des données :

- Si les produits (mises à jour) ne sont pas pertinents pour l'entreprise opérationnelle, l'utilisateur peut choisir de ne pas accepter la version.
- L'utilisateur peut modifier le modèle d'article pour les nouveaux produits.
- L'utilisateur peut choisir si le produit doit être lancé avec sa nomenclature et/ou ses gammes, et s'il doit être lancé comme approuvé et actif.
- L'utilisateur peut modifier les dates de début de validité des produits.

Pour un exemple d'acceptation d'un produit, voir [Vérifiez et acceptez le produit avant de le commercialiser dans l'entreprise locale](engineering-scenarios.md#accept).

> [!NOTE]
> Pour les produits standard, vous pouvez passer de toute entité juridique à toute autre entité juridique. Pour les produits d'ingénierie, la seule entité juridique que vous pouvez libérer est la société d'ingénierie.

## <a name="release-policies"></a>Stratégies de publication

Toutes les entreprises opérationnelles n'ont pas besoin des mêmes données produit. En général, les entreprises opérationnelles qui fabriquent des produits d'ingénierie ont besoin d'une nomenclature, tandis que les entreprises opérationnelles qui ne vendent que des produits d'ingénierie n'ont pas besoin d'une nomenclature. Vous pouvez utiliser des stratégies de publication pour définir les paramètres utilisés pour la publication des produits.

Pour les produits d'ingénierie, la stratégie de lancement est affectée dans la catégorie de produit d'ingénierie et le champ est obligatoire. Pour les produits standard, la stratégie est affectée au produit partagé et le champ est facultatif.

Pour plus d'informations sur les catégories de produits d'ingénierie, voir [Versions d'ingénierie et catégories de produits d'ingénierie](engineering-versions-product-category.md).

Pendant le processus de validation, vous pouvez influencer les paramètres.

## <a name="create-and-manage-product-release-policies"></a>Créer et gérer des stratégies de lancement de produit

Pour utiliser les stratégies de lancement de produit, accédez à **Gestion du changement d'ingénierie \> Configurer \> Stratégies de lancement de produit**. Suivez ensuite l’une des procédures suivantes.

- Pour créer une stratégie, sélectionnez **Nouveau** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour modifier une stratégie existante, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour supprimer une stratégie existante, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** sur le volet Actions, puis sur le raccourci **Général**, assurez-vous que l'option **actif** est définie sur *Non*. Ensuite, sélectionnez **Supprimer** sur le volet Action.

### <a name="header"></a>En-tête

Définissez les champs suivants sur l'en-tête d'une stratégie de lancement de produit.

| Champ | Description |
|---|---|
| Nom | Permet d'entrer un nom pour la stratégie. |
| Description | Permet d'entrer une description de la stratégie. |

### <a name="general-fasttab"></a>Organisateur Général

Définissez les champs suivants sur le raccourci **Général** d'une stratégie de lancement de produit.

| Champ | Description |
|---|---|
| Type de produit | Sélectionnez si la stratégie s'applique aux produits du type *Article* ou *Service*. Vous ne pouvez pas modifier ce paramètre après avoir enregistré l'enregistrement. |
| Appliquer des modèles | Sélectionnez l'une des options suivantes pour spécifier si et comment les modèles de version de produit doivent être appliqués lorsque la stratégie est utilisée :<ul><li>**Toujours** – Un modèle de produit publié doit toujours être utilisé pour les versions. Si vous sélectionnez cette option, utilisez le raccourci **Tous les produits** pour spécifier le modèle utilisé pour chaque société dans laquelle vous publiez. Si vous ne spécifiez pas de modèle pour chaque entreprise répertoriée dans le raccourci **Tous les produits**, vous recevrez une erreur lorsque vous essayez d'enregistrer la stratégie.</li><li>**Facultatif** – Si un modèle de produit lancé est spécifié pour une entreprise répertoriée sur le raccourci **Tous les produits**, ce modèle sera utilisé lors de votre lancement dans cette société. Sinon, aucun modèle ne sera utilisé. Si vous sélectionnez cette option, vous pouvez enregistrer la stratégie sans attribuer de modèles à toutes les sociétés. (Aucun avertissement ne sera affiché.)</li><li>**Jamais** – Aucun modèle de produit lancé ne sera utilisé pour les compagnies dans lesquelles vous le lancez même si le modèle est spécifié pour les entreprises répertoriées sur le raccourci **Tous les produits**. Les colonnes du modèle ne seront pas disponibles.</li></ul> |
| Actif.ve | Utilisez cette option pour vous aider à maintenir vos politiques de publication. Définissez-le sur *Oui* pour toutes les politiques de publication que vous utilisez. Définissez-le sur *Non* pour marquer une stratégie de publication comme inactive lorsqu'elle n'est pas utilisée. Notez que vous ne pouvez pas désactiver une stratégie de version affectée à une catégorie de produit d'ingénierie et que vous ne pouvez supprimer que des stratégies de version inactives. |

### <a name="all-products-fasttab"></a>Raccourci Tous les produits

Sur le raccourci **Tous les produits**, ajoutez une ligne pour chaque société opérationnelle dans laquelle vous souhaitez utiliser cette stratégie pour publier. Utilisez les boutons du raccourci **Tous les produits** pour ajouter et supprimer des lignes selon vos besoins. Pour chaque ligne que vous ajoutez, définissez les champs suivants.

> [!NOTE]
> Les paramètres sur le raccourci **Tous les produits** s'applique à la fois aux produits d'ingénierie et aux produits standard.

| Champ | Description |
|---|---|
| ID compte société | Sélectionnez l'entreprise à laquelle s'applique la ligne. Les paramètres de la ligne s'appliqueront lorsque les produits seront lancés pour cette société. |
| Modèle de produit lancé | Ajouter un modèle pour le produit. |
| Copier l’approbation de nomenclature | Cochez cette case pour copier le statut d'approbation de la nomenclature dans la société destinataire. |
| Copier l’activation de nomenclature | Cochez cette case pour copier le statut d'activation de la nomenclature dans la société destinataire. |
| Copier l’approbation de gamme | Cochez cette case pour copier le statut d'approbation de la gamme dans la société destinataire.|
| Copier l’activation de gamme | Cochez cette case pour copier le statut d'activation de la gamme dans la société destinataire. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Paramètres d'option pour le raccourci des produits d'ingénierie

Chaque fois que vous ajoutez une ligne sur le raccourci **Tous les produits**, une ligne qui a une correspondance la valeur **ID de compte d'entreprise** est également créée sur le raccourci **Paramètres d'option pour les produits d'ingénierie**. Ensuite, si vous supprimez une ligne du raccourci **Tous les produits**, la ligne qui a une correspondance la valeur **ID de compte d'entreprise** est également supprimée du raccourci **Paramètres d'option pour les produits d'ingénierie**.

Pour chaque ligne affichée sur le raccourci **Paramètres d'option pour les produits d'ingénierie**, définissez les champs suivants.

> [!NOTE]
> Les paramètres sur le raccourci **Paramètres d'option pour les produits d'ingénierie** s'applique uniquement aux produits d'ingénierie.

| Champ | Description |
|---|---|
| Nomenclature des modèles | Lorsqu'un produit doté d'une nomenclature est lancé, les lignes du modèle de nomenclature spécifié sont ajoutées. Ce champ est utile pour ajouter des composants locaux, tels que des emballages ou des instructions dans la langue locale. |
| Gamme modèle | Lorsqu'un produit doté d'une gamme est lancé, les lignes du modèle spécifié sont ajoutées. |
| Copier la prise d'effet | Indiquez si les dates de validité doivent être copiées de la société d'ingénierie vers la société opérationnelle lorsque vous lancez des produits. |
| Ajouter automatiquement à la proposition de lancement | Cochez cette case pour les produits qui doivent être automatiquement lancés sur la demande de modification technique. De cette manière, les produits appartenant aux catégories de produits d'ingénierie qui utilisent cette stratégie de publication peuvent être automatiquement mis à la disposition des sociétés opérationnelles où cette option est configurée. (Pour plus d'informations, consultez [Gérer modifications des produits techniques](engineering-change-management.md).)

### <a name="review-each-product-when-you-release-it"></a>Passez en revue chaque produit lorsque vous le lancez

Lorsque des produits d'ingénierie qui ont des nomenclatures ou des gammes sont lancés, les paramètres sont définis sur les valeurs par défaut, comme indiqué dans la politique de lancement. En tant qu'utilisateur, vous pouvez influencer ce comportement du côté du lancement lorsque vous utilisez la structure produit de lancement.

Pour lancer des produits d'ingénierie, sur la page **Produits lancés**, sélectionnez les produits à lancer, puis sélectionnez **Lancer la structure du produit** pour ouvrir l'assistant de publication. La page **Sélectionner les produits d'ingénierie à lancer** montre les produits. Sélectionnez un seul produit, puis sélectionnez **Détails de la version** pour consulter les détails de la version du produit.

Sur la page **Détails de la version**, vous pouvez modifier la valeur des champs **Recevoir la nomenclature**, **Copier l'approbation de la nomenclature**, **Copier l'activation de la nomenclature**, **Recevoir la nomenclature**, **Copier l'approbation de la gamme** et **Copier l'activation de la gamme**. Dans le scénario de déplacement/extraction, vous pouvez modifier la valeur des mêmes champs côté réception, à condition que la nomenclature et la gamme soient validés.

## <a name="product-owners-and-product-releases"></a>Propriétaires de produits et versions de produits

Étant donné que les propriétaires de produit savent quelles entités juridiques ont besoin de leurs produits, un produit ne peut être lancé que par les membres du groupe de propriétaires de produit de ce produit. Les autres utilisateurs ne peuvent pas publier des produits dont ils ne sont pas propriétaires.

Ce comportement s'applique uniquement lorsqu'un produit est directement sélectionné pour la publication. Les produits qui font partie de la structure d'un autre produit via une nomenclature *peuvent* être lancés par des utilisateurs non propriétaires lorsqu'ils lancent le produit parent, à condition qu'ils soient propriétaires du produit parent.

Par exemple, le produit X est affecté au groupe de propriétaires de produits *Armoires design*. Le produit X fait également partie de la nomenclature du produit Y, qui est affectée au groupe de propriétaires de produits *Concevoir des haut-parleurs*. Si un utilisateur du groupe de propriétaires de produits *Concevoir des haut-parleurs* lance le produit Y et sa nomenclature, le produit X sera publié avec le produit Y.

Pour plus d’informations, voir [Propriétaires du produit](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]