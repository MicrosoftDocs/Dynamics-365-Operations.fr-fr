---
title: Créer et utiliser des champs personnalisés
description: Cette rubrique présente comment Microsoft Dynamics 365 for Finance and Operations autorise certains utilisateurs à créer des champs pour personnaliser l'application afin qu'elle réponde à leur activité.
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 18402579789c17de7b46dd7a013b3b6327ea5d4f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "348018"
---
# <a name="create-and-work-with-custom-fields"></a>Créer et utiliser des champs personnalisés

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations fournit un ensemble étendu de champs prédéfinis pour gérer une large éventail de processus d'entreprise, mais une société doit parfois suivre des informations supplémentaires dans le système. Pour répondre à ce besoin, Finance and Operations vous permet de créer des champs personnalisés pour adapter l'application à votre entreprise, à condition que vous disposiez des autorisations appropriées pour la fonction.

La capacité d'ajouter des champs personnalisés est disponible dans la mise à jour de la plateforme 13 et versons ultérieures.

Cette vidéo montre comment il est facile d'ajouter un champ personnalisé à une page : [Ajouter des champs personnalisés dans Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Création de champs personnalisés

Une fois que vous avez identifié les informations supplémentaires que vous souhaitez suivre dans l'application, vous pouvez créer le champ personnalisé dans la table appropriée et afficher ce nouveau champ sur une page.

Les étapes suivantes décrivent comment créer un champ personnalisé et l'insérer dans un écran.

1. Accédez à l'écran où le nouveau champ doit être inséré.
2. Comme l'objectif final est d'afficher le champ personnalisé dans un écran, le point d'entrée de la création de champs personnalisés existe dans l'expérience de personnalisation. Ouvrez la barre d'outils de personnalisation en sélectionnant **Options**, puis **Personnaliser cet écran**.
3. Cliquez sur **Insérer**, puis sur **Champ**.
4. Sélectionnez la zone de l'écran où vous souhaitez afficher le nouveau champ. Après la sélection, la boîte de dialogue **Insérer des champs** affiche la liste des champs existants qui peuvent être insérés dans la zone sélectionnée de l'écran.
5. Vérifiez que le champ qui vous intéresse n'existe pas déjà dans la liste. Si tel est le cas, vous pouvez simplement sélectionner ce champ dans la liste et cliquer sur **Insérer**.
6. Cliquez sur le bouton **Créer un champ** au-dessus de la liste pour lancer le processus de création d'un champ personnalisé. La boîte de dialogue **Créer un champ** s'ouvre.

    Si le bouton **Créer un champ** ne s'affiche pas, vous ne disposez pas des autorisations nécessaires pour utiliser cette fonction.

7. Dans la boîte de dialogue **Créer un champ**, entrez les informations suivantes.

    1. Sélectionnez la table de base de données où ce champ doit être ajouté. Notez que seules les tables qui prennent en charge les champs personnalisés s'affichent dans la liste déroulante. Consultez la section ci-après pour obtenir des informations techniques sur les tables prises en charge.
    2. Sélectionnez le type de données pour le nouveau champ. Les types de données disponibles sont case à cocher, date, date et heure, décimal, nombre, liste de sélection et texte.

        - Si vous choisissez le type de données Texte, vous pouvez également spécifier la longueur maximale du texte qui peut être saisi dans ce champ.
        - Si vous choisissez le type de données Liste de sélection, vous pouvez également sélectionner l'ensemble des valeurs valides pour le champ.

    3. Indiquez un nom, un libellé et un texte d'aide pour le champ. Le nom correspond au nom physique du champ dans la base de données, tandis que le libellé et le texte d'aide correspondent au texte utilisé pour représenter ce champ dans l'interface utilisateur.

8. Si ce champ est le seul que vous devez créer pour cet écran, cliquez sur **Enregistrer**. Si vous devez créer des champs supplémentaires, cliquez sur **Enregistrer et créer** et retournez à l'étape 7. Notez qu'il existe actuellement une limite de **20 champs personnalisés par table**.
9. Si vous fermez la boîte de dialogue **Créer un champ**, vous êtes redirigé vers la boîte de dialogue **Insérer des champs**. Les champs personnalisés qui viennent d'être ajoutés sont automatiquement marqués dans la liste des champs à insérer dans l'écran.
10. Cliquez sur **Insérer** pour insérer les champs marqués dans la zone sélectionnée de l'écran.
11. **Facultatif :** activez le mode **Déplacer** dans la barre d'outils de personnalisation pour déplacer les nouveaux champs vers l'emplacement souhaité dans la zone sélectionnée. Consultez [Personnaliser l'expérience utilisateur](personalize-user-experience.md) pour plus d'informations sur l'utilisation des différentes fonctions de personnalisation pour optimiser un écran pour votre utilisation personnelle.

## <a name="sharing-custom-fields-with-other-users"></a>Partage de champs personnalisés avec d'autres utilisateurs

Une fois que vous avez créé un champ personnalisé et l'avez affiché dans un écran, vous pouvez partager cette vue de page mise à jour contenant le nouveau champ avec d'autres utilisateurs du système. Cette opération peut être effectuée de deux manières à l'aide des fonctions de personnalisation du produit :

- La méthode recommandée est par le biais de l'administrateur système, qui peut envoyer une personnalisation à tous les utilisateurs ou à un sous-ensemble d'utilisateurs. Consultez [Personnaliser l'expérience utilisateur](personalize-user-experience.md) pour plus d'informations.
- Vous pouvez également exporter vos modifications (appelées *personnalisations*), les envoyer à un ou plusieurs utilisateurs qui peuvent ensuite les importer. L'option **Gérer** dans la barre d'outils de personnalisation vous permet d'exporter et d'importer des personnalisations.

## <a name="managing-custom-fields"></a>Gestion des champs personnalisés

La gestion de tous les champs personnalisés du système peut être effectuée via la page **Champs personnalisés** du module Administration du système. Cette page permet aux utilisateurs d'accéder à de nombreuses fonctions, notamment :

- Affichage de la liste de tous les champs personnalisés du système.
- Modification limitée des champs personnalisés existants.
- Suppression de champs personnalisés.
- Affichage des champs personnalisés des entités de données.
- Affichage des traductions des libellés et du texte d'aide des champ personnalisés.

### <a name="viewing-all-custom-fields"></a>Affichage de tous les champs personnalisés

La page **Champs personnalisés** fournit une visibilité sur tous les champs personnalisés qui ont été définis dans le système. Sélectionnez uniquement la table qui vous intéresse pour la mettre à jour et afficher la liste des champs personnalisés qui lui sont associés. Lorsque vous sélectionnez un champ personnalisé dans la liste, tous les détails associés s'affichent.

### <a name="editing-custom-fields"></a>Modification de champs personnalisés

Une fois qu'un champ personnalisé a été créé, seules certaines informations sur le champ personnalisé peuvent être modifiées dans la page **Champs personnalisés**.

Vous *pouvez* modifiez les attributs suivants :

- Étiquette
- Texte d'aide
- Longueur, pour les champs de texte

Vous *ne pouvez pas* modifier les attributs suivants :

- Nom du champ
- Type de données

En outre, pour les champs de liste de sélection, l'ensemble des valeurs valides pour le champ personnalisé peut être réorganisé et de nouvelles valeurs peuvent être ajoutées. Toutefois, les valeurs existantes du champ de liste de sélection ne peuvent pas être supprimées. N'oubliez pas de cliquer sur **Appliquer les modifications** une fois que vous avez fini de modifier les champs d'une table spécifique pour enregistrer les modifications.

### <a name="exposing-custom-fields-on-data-entities"></a>Affichage des champs personnalisés des entités de données

Il peut également être important de rendre visibles certains champs personnalisés des entités de données. Les entités de données sont utilisées dans la fonction [Ouvrir dans Office](../../dev-itpro/office-integration/office-integration.md), ainsi que pour les scénarios d'importation/exportation des données.

Procédez comme suit pour afficher un champ personnalisé d'une entité de données :

1. Sélectionnez le champ personnalisé dans l'écran **Champs personnalisés**.
2. Développez la section **Entités** pour afficher l'ensemble des entités appropriées.
3. Cliquez sur le bouton **Modifier**.
4. Modifiez le champ **Activé** à sélectionner pour chaque entité qui doit afficher ce champ.
5. Cliquez sur **Appliquer les modifications** pour enregistrer vos sélections.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Affichage des champs personnalisés dans d'autres langues

Comme les champs personnalisés doivent être accessibles par les utilisateurs dans différentes langues, la page **Champs personnalisés** fournit un mécanisme permettant de traduire le libellé et le texte d'aide d'un champ personnalisé dans d'autres langues.

Les étapes suivantes décrivent comment traduire les champs personnalisés dans d'autres langues :

1. Sélectionnez le champ personnalisé dans la page **Champs personnalisés**.
2. Sélectionnez le bouton **Traductions** dans le volet Actions. Un menu déroulant s'ouvre avec les traductions existantes pour ce champ.
3. Le menu déroulant **Langue** affiche l'ensemble des langues pour lesquelles des traductions ont déjà été fournies.

    Si vous souhaitez modifier une traduction existante, sélectionnez la langue souhaitée dans le menu et modifiez les valeurs du libellé et du texte d'aide.

    Sinon, cliquez sur le bouton **Ajouter une langue**, sélectionnez la langue souhaitée dans le menu, puis entrez les valeurs traduites pour le libellé et le texte d'aide.

4. Cliquez sur **OK** lorsque vous avez terminé.

### <a name="deleting-custom-fields"></a>Suppression de champs personnalisés

Dans de rares cas, vous pouvez décider qu'un champ personnalisé n'est plus nécessaire. Dans ce cas, un administrateur système peut choisir de supprimer le champ de la page **Champs personnalisés**. Pour ce faire, vérifiez que le champ correct est sélectionné, cliquez sur **Supprimer**, sur **Oui** pour confirmer la suppression, puis sur **Appliquer les modifications**.

> [!NOTE]
> Cette action ne peut pas être annulée et entraînera la suppression définitive des données associées au champ de la base de données.

## <a name="appendix"></a>Annexe

### <a name="who-can-create-custom-fields"></a>Qui peut créer des champs personnalisés ?

Par mesure de protection du système, seuls les administrateurs système peuvent créer des champs personnalisés par défaut. Toutefois, un administrateur système peut octroyer des droits de création de champs personnalisés aux utilisateurs avec pouvoir à l'aide du rôle de sécurité **Utilisateur avec pouvoir de personnalisation de l'exécution**, si l'organisation le juge nécessaire. Les utilisateurs qui ne disposent pas de ce rôle de sécurité ne pourront pas créer de champs personnalisés, mais pourront quand même visualiser les champs personnalisés ajoutés par d'autres utilisateurs du système et interagir avec eux.

### <a name="what-tables-support-custom-fields"></a>Quelles tables prennent en charge les champs personnalisés ?

Pour des raisons de performances et techniques, seules les tables qui répondent aux conditions suivantes prennent en charge actuellement l'ajout de champs personnalisés.

- La table doit être référencée comme l'un des groupes suivants :

    - Groupe
    - WorksheetHeader
    - Principal
    - Divers
    - Paramètre
    - Référence
    - TransactionHeader

- La table ne peut pas étendre une autre table.
- La table ne peut pas être marquée comme une table système.
- La table ne peut pas être une table temporaire.
