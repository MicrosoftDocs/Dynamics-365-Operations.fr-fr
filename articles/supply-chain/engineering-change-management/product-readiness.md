---
title: Disponibilité du produit
description: Cette rubrique explique comment vous pouvez utiliser les vérifications de disponibilité pour vous assurer que les données principales requises sont complétées pour un produit avant son utilisation dans les transactions.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f7ab6165e85cd2b1165292b74cd036f1233b22b4
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103011"
---
# <a name="product-readiness"></a>Disponibilité du produit

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser les vérifications de disponibilité pour vous assurer que toutes les données principales requises ont été spécifiées pour un produit avant son utilisation dans les transactions. Lorsque des vérifications de disponibilité sont utilisés, un utilisateur ou une équipe est chargé de valider des données spécifiques prédéfinies liées au produit.

Vous pouvez cocher la case **Actif** d’un produit d’ingénierie, d’une variante ou d’une version qu’après que toutes les données requises ont été saisies et vérifiées, et après que toutes les vérifications de disponibilité ont été traités. Si une ou plusieurs vérifications n’ont pas été effectuées pour le produit, la version ou la variante, lorsque vous essayez de cocher la case **Actif**, vous recevez un message vous avertissant que toutes les vérifications n’ont pas été effectuées.

Vous pouvez créer des vérifications de disponibilité pour les nouveaux produits, les nouvelles variantes et les nouvelles versions d’ingénierie. Vous pouvez également appliquer des contrôles de préparation aux produits standard (non techniques) (voir aussi [Vérifications de l’état de préparation des produits standard](#standard-products)). 

Vous pouvez utiliser des produits standard dans les transactions même si tous les contrôles de préparation n’ont pas été effectués. Si vous devez empêcher l’utilisation d’un produit dans les transactions, utilisez son état de cycle de vie. Vous pouvez affecter un état de cycle de vie qui empêche l’utilisation d’un produit dans les transactions, puis, une fois tous les contrôles de préparation terminés, affecter un nouvel état de cycle de vie qui autorise les transactions requises.

## <a name="types-of-readiness-checks"></a>Types de vérifications de disponibilité

Il existe trois types de vérifications de disponibilité :

- **Vérification du système** – Le système vérifie s’il existe un enregistrement valide. Par exemple, l’enregistrement peut être une nomenclature active (BOM).
- **Vérification manuelle** – Un utilisateur vérifie si l’enregistrement est valide. Par exemple, une vérifications de disponibilité peut exiger la validation des paramètres de commande par défaut. Dans certains cas, par exemple lorsque le produit est encore en cours de conception et ne sera donc pas mis en stock, aucun paramètre de commande par défaut n’est requis. Cependant, des paramètres de commande par défaut peuvent être requis pour un autre produit du même type, car le produit peut être conservé en stock. L’utilisateur est responsable de savoir comment décider correctement si une vérification de disponibilité est nécessaire.
- **Liste de contrôle** – L’utilisateur répond à une série de questions à partir d’une liste de contrôle et le système détermine si les réponses répondent aux attentes. La liste de contrôle peut avoir n’importe quel sujet. Par exemple, elle peut être utilisée pour déterminer si les supports marketing ou la documentation produit sont complétés.

<a name="checks-engineering"></a>

## <a name="how-readiness-checks-are-created-for-a-new-engineering-product-variant-or-version"></a>Comment les vérifications de disponibilité sont créées pour un nouveau produit d’ingénierie, variante ou version

Les stratégies de vérification de la disponibilité peuvent être appliquées au niveau du produit lancé, au niveau de la variante lancée et au niveau de la version d’ingénierie.

Lorsque vous créez un nouveau *produit d’ingénierie*, le système détermine si une [stratégie de vérification de la disponibilité s’y applique](#assign-policy). Si une stratégie de vérification de la disponibilité s’applique, les événements suivants se produisent :

- Des vérifications de disponibilité sont créés pour le produit, conformément à la stratégie applicable.
- La version d’ingénierie est définie sur inactive pour empêcher l’utilisation du produit. Toutes les versions d’ingénierie du produit sont définies comme inactives.

Si une nouvelle *variante* est créée pour un produit, le système vérifie si une stratégie de vérification de la disponibilité s’y applique. Les vérifications de la disponibilité peuvent être appliquées au niveau de la variante lancée et au niveau de la version d’ingénierie. Si une stratégie s’applique, les événements suivants se produisent :

- Des vérifications de disponibilité sont créés pour le produit, conformément à la stratégie applicable.
- La version d’ingénierie et la variante sont définies comme inactives pour bloquer l’utilisation du produit.

Si une nouvelle *version* d’ingénierie est créée pour un produit, le système vérifie si une stratégie de vérification de la disponibilité s’y applique. (Les vérifications de la disponibilité peuvent être appliquées au niveau de la version d’ingénierie.) Si une stratégie s’applique, les événements suivants se produisent :

- Des vérifications de disponibilité sont créés pour le produit, conformément à la stratégie applicable.
- La version d’ingénierie est définie sur inactive pour empêcher l’utilisation du produit.

> [!NOTE]
> Vous pouvez également configurer des stratégies de vérification de la disponibilité pour les produits standard (autres que des produits d’ingénierie). Pour plus d’informations, consultez la section [Vérifications de la disponibilité des produits standard](#standard-products) plus loin dans cette rubrique.

## <a name="view-readiness-checks"></a>Afficher les vérifications de disponibilité

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Afficher les vérifications de disponibilité ouvertes pour un produit ou une version de produit

Pour rechercher les vérifications de disponibilité ouvertes pour un produit, ouvrez la page **Détails des produits lancés**. Puis, sur le volet Actions, sous l’onglet **Produit**, dans le groupe **vérifications de disponibilité**, cliquez sur **Attributs de produit**.

Pour rechercher les vérifications de disponibilité ouverts pour une version de produit, ouvrez la page **Versions d’ingénierie** pour un produit commercialisé et choisissez une version. Puis, sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Liste de contrôle**, cliquez sur **Attributs de produit**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Afficher les vérifications de disponibilité ouverts qui vous sont attribués

Pour afficher les vérifications de disponibilité ouverts qui vous sont attribués, suivez l’une de ces étapes.

- Aller à **Gestion du changement d’ingénierie \> Commun \> Préparation du produit \> Mes vérifications de disponibilité ouverts**.
- Aller à **Gestion des informations produit \> Espaces de travail \> Préparation du produit pour une fabrication discrète**.

La configuration qui spécifie à qui une vérification de disponibilité est affectée est effectuée pour la stratégie de disponibilité. Les vérifications de disponibilité peuvent être attribués à une personne ou à une équipe. Si une vérifications de disponibilité est attribué à une équipe, il y a une personne dans l’équipe qui doit traiter la vérifications de disponibilité.

## <a name="process-open-readiness-checks"></a>Traiter les vérifications de disponibilité ouverts

### <a name="process-system-and-manual-readiness-checks"></a>Contrôle du système de processus et de l’état de préparation manuel

Après avoir ouvert la page **vérifications de disponibilité**, vous pouvez afficher le sujet des vérifications de disponibilité du système et manuels en sélectionnant **Afficher les informations relatives** sur le volet Actions. Vous pouvez ensuite compléter et/ou valider les données pour la vérifications de disponibilité. Les vérifications de disponibilité ouverts ont une valeur de **Statut** de *En attente*. Cet état indique que la vérifications de disponibilité doit encore être traité. Pour traiter une vérifications de disponibilité, suivez l’une des étapes suivantes.

- Dans le volet Actions, sélectionnez **Vérifier/Terminer** pour examiner et terminer la vérification de l’état de préparation. Lorsque vous avez terminé, le champ **Statut** est mis à jour sur *Réussite*.
- Dans le volet Actions, sélectionnez **Ignorer** si vous souhaitez ignorer une vérification de l’état de préparation qui n’est pas obligatoire. Par exemple, vous configurez une vérifications de disponibilité pour les calculs de prix. Cependant, vous décidez d’ignorer cette vérification pendant que le produit est encore en phase de conception. Dans ce cas, la champ **Statut** est mis à jour sur *Ignoré*.

Selon la configuration de la stratégie de disponibilité, lorsque le champ **Statut** pour une vérifications de disponibilité est mis à jour sur *Réussite*, une étape supplémentaire peut être nécessaire pour approuver la vérification de l’état de préparation. Dans ce cas, sélectionnez **Approbation** pour terminer la vérifications de disponibilité. Cette étape d’approbation est toujours obligatoire lorsque la vérifications de disponibilité est ignoré.

Lorsque tous les vérifications de disponibilité ouverts pour un nouveau produit, une variante ou une version ont été traités et approuvés selon les besoins, l’article devient automatiquement actif et donc prêt à l’emploi.

### <a name="process-checklist-readiness-checks"></a>Traiter les vérifications de disponibilité de liste de contrôle

Pour ouvrir une liste de contrôle, ouvrez la page **vérifications de disponibilité**, puis, dans le volet Actions, sélectionnez **Liste de contrôle de démarrage**. Lorsque vous avez terminé la liste de contrôle, le système valide si la vérifications de disponibilité est réussie, en fonction des paramètres du questionnaire. Si la vérification est réussie, le champ **Statut** est mis à jour sur *réussite*. Si la vérifications de disponibilité n’est pas obligatoire, vous pouvez l’ignorer. Dans ce cas, la champ **Statut** est mis à jour sur *Ignoré*.

Selon la configuration de la stratégie de disponibilité, lorsque le champ **Statut** pour une vérifications de disponibilité est mis à jour sur *Réussite*, une étape supplémentaire peut être nécessaire pour approuver la vérification de l’état de préparation. Dans ce cas, sélectionnez **Approbation** pour terminer la vérifications de disponibilité. Cette étape d’approbation est toujours obligatoire lorsque la vérifications de disponibilité est ignoré.

Lorsque tous les vérifications de disponibilité ouverts pour un nouveau produit, une variante ou une version ont été traités et approuvés selon les besoins, l’article devient automatiquement actif et donc prêt à l’emploi.

## <a name="create-and-manage-product-readiness-policies"></a>Créer et gérer des stratégies de disponibilité

Utilisez les stratégies de disponibilité du produit pour gérer les vérifications de disponibilité qui s’appliquent à un produit. Chaque stratégie de disponibilité contient un ensemble de vérifications de disponibilité. Lorsqu’une stratégie de disponibilité est affectée à une catégorie de produits d’ingénierie ou à un produit partagé, tous les produits associés à cette catégorie ou ce produit partagé auront les vérifications de disponibilité incluses dans la stratégie de disponibilité.

Pour utiliser les stratégies de préparation de produit, accédez à **Gestion du changement d’ingénierie \> Configurer \> Disponibilité du produit**. Suivez ensuite l’une des procédures suivantes.

- Pour créer une stratégie, sélectionnez **Nouveau** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour modifier une stratégie existante, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour supprimer une stratégie existante, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** sur le volet Actions, puis sur le raccourci **Général**, assurez-vous que l’option **actif** est définie sur *Non*. Ensuite, sélectionnez **Supprimer** sur le volet Action.

### <a name="header"></a>En-tête

Définissez les champs suivants sur l’en-tête d’une stratégie de disponibilité de produit.

| Champ | Description |
|---|---|
| Nom | Permet d’entrer un nom pour la stratégie. |
| Description | Permet d’entrer une description de la stratégie. |

### <a name="general-fasttab"></a>Organisateur Général

Définissez les champs suivants sur le raccourci **Général** d’une stratégie de disponibilité de produit.

| Champ | Description |
|---|---|
| Type de produit | Sélectionnez si la stratégie s’applique aux produits du type *Article* ou *Service*. Vous ne pouvez pas modifier ce paramètre après avoir enregistré l’enregistrement. |
| Actif.ve | Utilisez cette option pour vous aider à maintenir vos stratégies de disponibilité. Définissez-le sur *Oui* pour toutes les stratégies de disponibilité que vous utilisez. Définissez-le sur *Non* pour marquer une stratégies de disponibilité comme inactive lorsqu’elle n’est pas utilisée. Notez que vous ne pouvez pas désactiver une stratégie de disponibilité affectée à une catégorie de produit d’ingénierie ou à un produit partagé et que vous ne pouvez supprimer que des stratégies de version inactives. |

### <a name="readiness-control-fasttab"></a>Raccourci Vérification de la disponibilité

Pour chaque type de vérification de la disponibilité que vous souhaitez inclure dans la stratégie, ajoutez une ligne sur le raccourci **Vérification de la disponibilité**. Utilisez les boutons suivants sur la barre d’outils du raccourci pour ajouter et supprimer des lignes selon vos besoins :

- **Ajouter une vérification** – Ajoutez une vérification de la disponibilité standard à la stratégie. Lorsque vous sélectionnez ce bouton, la boîte de dialogue **Ajouter une vérification** apparaît. Là, vous pouvez choisir parmi une liste de vérification disponibles.
- **Ajouter un questionnaire existant** – Ajoutez une ligne vide à la grille. Vous pouvez ensuite affecter un questionnaire existant en définissant les champs dans le tableau suivant.
- **Copier** – Ajoutez une copie de la ligne sélectionnée à la grille.
- **Supprimer** – Supprimer la ligne sélectionnée de la grille.

Pour chaque ligne que vous ajoutez, définissez les champs suivants.

| Champ | Description |
| --- | --- |
| Zone de traitement | Sélectionnez la zone à laquelle la vérification est liée. |
| Type | Sélectionnez si la vérification est une vérification du système, une vérification manuelle ou une liste de contrôle (questionnaire). |
| Nom | Si la vérification est une liste de contrôle, entrez un nom. Pour les vérifications système et manuels, ce champ est automatiquement défini. |
| Description | Si la vérification est une liste de contrôle, entrez une description. Pour les vérifications système et manuelles, ce champ est automatiquement défini et la description explique l’objectif de la vérification. |
| Appliquer les vérifications à | Indiquez si la ligne doit générer des vérification de la disponibilité en réponse à un nouveau produit lancé, une variante lancée ou une version lancée. |
| Exécuter dans | Sélectionnez si les vérification de la disponibilité générés par la ligne s’appliquent à toutes les sociétés ou à une seule société. |
| Société | Si vous définissez le champ **Exécuter dans** sur *Entreprise unique*, sélectionnez l’entreprise. |
| Type de propriétaire | Indiquez si les vérification de la disponibilité générés par la ligne doivent être attribués à une personne ou à une équipe. |
| Propriétaire | Indiquez la personne ou l’équipe à qui les vérification de la disponibilité générés par la ligne doivent être attribués. |
| Questionnaire | Sélectionnez le questionnaire à utiliser pour la liste de contrôle. La liste de contrôle est une liste de contrôle locale dans l’entreprise où la vérification de la disponibilité est effectué. Le système doit être en mesure d’évaluer si la liste de contrôle a reçu une réponse correcte. Par conséquent, la liste de contrôle doit être établie de manière à ce qu’une évaluation soit faite sur la base de réponses correctes. Pour plus d’informations sur la création de questionnaires, voir [Utilisation de questionnaires](/dynamicsax-2012/appuser-itpro/using-questionnaires) et ses sujets connexes. |
| Approbation automatique | Les registres de vérification de la disponibilité comprennent une case à cocher **Approuvé** qui indique l’état d’approbation. Cochez la case **Approbation automatique** pour les vérification qui doivent être définis sur Approuvé immédiatement après que l’utilisateur affecté les a terminés. Décochez cette case pour exiger une approbation explicite comme étape supplémentaire. |
| Obligatoire | Cochez cette case pour les vérifications qui doivent être effectuées par l’utilisateur affecté. Les vérifications obligatoires ne peuvent pas être ignorées. |

<a name="assign-policy"></a>

## <a name="assign-readiness-policies-to-standard-and-engineering-products"></a>Affecter des stratégies de disponibilité aux produits standard et d’ingénierie

Lorsque vous créez un nouveau produit basé sur une catégorie d’ingénierie, vous créez à la fois un *produit lancé* et un *produit partagé* associé. La manière dont les stratégies de préparation sont résolues pour un produit lancé dépend du fait que la fonctionnalité *Vérifications de la préparation des produits* est activée pour votre système (voir la section  [Contrôles de préparation des produits standards](#standard-products) plus loin dans cette rubrique pour plus de détails sur cette fonction et comment l’activer ou la désactiver).

- Lorsque la fonctionnalité *Vérifications de la disponibilité du produit* est *désactivée* dans votre système, la stratégie de disponibilité est définie et affichée uniquement sur les enregistrements de [catégorie d’ingénierie](engineering-versions-product-category.md). Pour savoir quelle stratégie s’applique à un produit lancé, le système vérifie le champ **Stratégie de disponibilité du produit** pour la catégorie d’ingénierie correspondante. Vous pouvez modifier la stratégie de disponibilité d’un produit existant en modifiant la catégorie d’ingénierie associée (et non le produit partagé).
- Lorsque la fonctionnalité *Vérifications de la disponibilité du produit* est *activée*, elle ajoute un champ **Stratégie de disponibilité du produit** à la page **Produit** (où les produits partagés sont configurés) et à la page **Produit lancé** (où la valeur est en lecture seule et extraite du produit partagé associé). Le système recherche la stratégie de disponibilité d’un produit lancé en vérifiant le produit partagé associé. Lorsque vous utilisez une catégorie d’ingénierie pour créer un nouveau produit d’ingénierie, le système crée à la fois un produit partagé et un produit lancé, puis copie tout paramètre **Stratégie de disponibilité du produit** de la catégorie d’ingénierie dans le nouveau produit partagé. Vous pouvez ensuite modifier la stratégie de disponibilité d’un produit existant en modifiant le produit partagé associé (et non la catégorie d’ingénierie lancée).

Pour affecter une stratégie de disponibilité à un produit partagé, procédez comme suit.

1. Accédez à **Informations sur les produits \> Produits \> Produits**.
1. Ouvrez ou créez le produit auquel vous souhaitez affecter une stratégie de disponibilité.
1. Dans le raccourci **Général**, définissez le champ **Stratégie de disponibilité du produit** sur le nom de la stratégie qui doit s’appliquer au produit.

Pour affecter une stratégie de disponibilité à une catégorie d’ingénierie, procédez comme suit.

1. Allez à **Gestion des modifications d’ingénierie \> Configuration \> Détails de la catégorie de produits d’ingénierie**.
1. Ouvrez ou créez la catégorie d’ingénierie à laquelle vous souhaitez affecter une stratégie de disponibilité.
1. Dans le raccourci **Stratégie de disponibilité du produit**, définissez le champ **Stratégie de disponibilité du produit** sur le nom de la stratégie qui doit s’appliquer à la catégorie d’ingénierie.

<a name="standard-products"></a>

## <a name="readiness-checks-on-standard-products"></a>Stratégies de disponibilité des produits standard

Vous pouvez activer les vérifications de la disponibilité des produits standard (autres que des produits d’ingénierie) en activant la fonctionnalité *Vérifications de la disponibilité du produit* dans Gestion des fonctionnalités. Cette fonctionnalité apporte quelques petits changements au système de vérification de la disponibilité afin qu’il prenne en charge les produits standard.

### <a name="enable-or-disable-readiness-checks-on-standard-products"></a>Activer ou désactiver les vérifications de disponibilité des produits standard

Cette fonctionnalité nécessite que les deux fonctionnalités *Gestion des modifications techniques* et *Vérifications de la préparation des produits* soient activées pour votre système. Pour plus d’informations sur l’activation ou la désactivation de ces fonctionnalités, reportez-vous à [Présentation de la gestion des modifications techniques](product-engineering-overview.md).

### <a name="create-readiness-policies-for-standard-products"></a>Créer des stratégies de disponibilité pour les produits standard

Vous créez des stratégies de disponibilité pour les produits standard comme vous le faites pour les produits d’ingénierie. Consultez les informations plus haut dans cette rubrique.

### <a name="assign-readiness-policies-to-standard-products"></a>Affecter des stratégies de disponibilité aux produits standard

Pour affecter une stratégie de disponibilité à un produit standard, ouvrez le produit partagé associé et définissez le champ **Stratégie de disponibilité du produit** sur le nom de la stratégie qui doit s’appliquer. Pour plus d’informations, consultez la section [Affecter des stratégies de disponibilité aux produits standard et d’ingénierie](#assign-policy) plus haut dans cette rubrique.

### <a name="view-and-process-readiness-checks-on-standard-products"></a>Afficher et traiter les vérifications de disponibilité des produits standard

Lorsque cette fonctionnalité est activée, vous affichez et traitez les vérifications de disponibilité des produits standard comme vous le faites pour les produits d’ingénierie. Consultez les informations plus haut dans cette rubrique.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
