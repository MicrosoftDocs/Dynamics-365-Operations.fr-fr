---
title: Créer et utiliser des champs personnalisés
description: Cet article vous indique comment autoriser certains utilisateurs à créer des champs via l’interface utilisateur pour personnaliser l’application afin qu’elle réponde à votre activité.
author: jasongre
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 18e7e8525352e8fdc397621c381ed4297837e30c
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887285"
---
# <a name="create-and-work-with-custom-fields"></a>Créer et utiliser des champs personnalisés

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Tandis qu’il y a un ensemble étendu de champs prédéfinis pour gérer une large éventail de processus d’entreprise, une société doit parfois suivre des informations supplémentaires dans le système. Alors que les programmeurs peuvent être utilisés pour ajouter ces champs en tant qu’extensions dans les outils de développement, la fonctionnalité des champs personnalisés permet d’ajouter des champs directement à partir de l’interface utilisateur, vous permettant d’adapter l’application à votre entreprise à l’aide de votre navigateur Web.

*Seuls les utilisateurs avec des autorisations spéciales ont accès à cette fonctionnalité.*

Cette vidéo montre comment il est facile d’ajouter un champ personnalisé à une page : [Ajouter des champs personnalisés](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Création de champs personnalisés

Une fois que vous avez identifié les informations supplémentaires à suivre dans l’application, vous pouvez créer le champ personnalisé dans la table appropriée et afficher ce nouveau champ sur une page.

Les étapes suivantes décrivent comment créer un champ personnalisé et l’insérer dans une page.

1. Accédez à la page où le nouveau champ doit être inséré.
2. Comme l’objectif final est d’afficher le champ personnalisé dans un écran, le point d’entrée de la création de champs personnalisés existe dans l’expérience de personnalisation. Ouvrez la barre d’outils de personnalisation en sélectionnant **Options**, puis **Personnaliser cet écran**.
3. Cliquez sur **Insérer**, puis sur **Champ**.
4. Sélectionnez la zone de l’écran où vous souhaitez afficher le nouveau champ. Après la sélection, la boîte de dialogue **Insérer des champs** affiche la liste des champs existants qui peuvent être insérés dans la zone sélectionnée de la page.
5. Confirmez que le champ qui vous intéresse n’existe pas déjà dans la liste. Si tel est le cas, vous pouvez simplement sélectionner ce champ dans la liste et cliquer sur **Insérer**.
6. Cliquez sur le bouton **Créer un champ** au-dessus de la liste pour lancer le processus de création d’un champ personnalisé. La boîte de dialogue **Créer un champ** s’ouvre.

    Si le bouton **Créer un champ** ne s’affiche pas, vous ne disposez pas des autorisations nécessaires pour utiliser cette fonction.

7. Dans la boîte de dialogue **Créer un champ**, entrez les informations suivantes.
   
    1. Sélectionnez la table de base de données où ce champ doit être ajouté. Notez que seules les tables qui prennent en charge les champs personnalisés s’affichent dans la liste déroulante. Consultez la section ci-après pour obtenir des informations techniques sur les tables prises en charge.

    2. Sélectionnez le type de données pour le nouveau champ. Les types de données disponibles sont case à cocher, date, date et heure, décimal, nombre, liste de sélection et texte.

        - Si vous choisissez le type de données Texte, vous pouvez également spécifier la longueur maximale du texte qui peut être saisi dans ce champ.
        - Si vous choisissez le type de données Liste de sélection, vous pouvez également sélectionner l’ensemble des valeurs valides pour le champ.

    3. Indiquez un nom, un libellé et un texte d’aide pour le champ. Le nom correspond au nom physique du champ dans la base de données, tandis que le libellé et le texte d’aide correspondent au texte utilisé pour représenter ce champ dans l’interface utilisateur.

8. Si ce champ est le seul que vous devez créer pour cette page, cliquez sur **Enregistrer**. Si vous devez créer des champs supplémentaires, cliquez sur **Enregistrer et créer** et retournez à l’étape 7. 

>[!Note] 
> Actuellement, il existe une limite de **20 champs personnalisés par table**.

9. Si vous fermez la boîte de dialogue **Créer un champ**, vous êtes redirigé vers la boîte de dialogue **Insérer des champs**. Les champs personnalisés qui viennent d’être ajoutés sont automatiquement marqués dans la liste des champs à insérer dans la page.
10. Cliquez sur **Insérer** pour insérer les champs marqués dans la zone sélectionnée de la page.
11. **Facultatif :** activez le mode **Déplacer** dans la barre d’outils de personnalisation pour déplacer les nouveaux champs vers l’emplacement souhaité dans la zone sélectionnée. Consultez [Personnaliser l’expérience utilisateur](personalize-user-experience.md) pour plus d’informations sur l’utilisation des différentes fonctions de personnalisation pour optimiser un écran pour votre utilisation personnelle.

> [!WARNING]
> La possibilité de saisir des valeurs dans un champ personnalisé ajouté à une page dépend du fait que la table associée au champ personnalisé est modifiable ou en lecture seule. Lorsque la table associée est en lecture seule, tous les champs liés à cette table, y compris les champs personnalisés, seront également en lecture seule.


## <a name="sharing-custom-fields-with-other-users"></a>Partage de champs personnalisés avec d’autres utilisateurs

Une fois un champ personnalisé créé et affiché sur une page, vous pouvez partager cette vue de page mise à jour contenant le nouveau champ avec d’autres utilisateurs du système. Cette opération peut être effectuée de deux manières à l’aide des fonctions de personnalisation du produit :

- La méthode recommandée est de **publier une [vue enregistrée](saved-views.md)** avec le champ personnalisé ajouté à la page sur l’ensemble d’utilisateurs approprié. Si la fonction de vues enregistrées n’est pas activée, l’administrateur système peut appliquer la personnalisation aux utilisateurs souhaités à partir de la page **Personnalisation**. Pour plus d’informations, consultez [Personnaliser l’expérience utilisateur](personalize-user-experience.md).
- Vous pouvez également exporter vos modifications (appelées *personnalisations*), les envoyer à un ou plusieurs utilisateurs qui peuvent ensuite les importer. L’option **Gérer** dans la barre d’outils de personnalisation vous permet d’exporter et d’importer des personnalisations.

## <a name="managing-custom-fields"></a>Gestion des champs personnalisés

La gestion de tous les champs personnalisés peut être effectuée via la page **Champs personnalisés** du module Administration du système. Cette page permet aux utilisateurs d’accéder à de nombreuses fonctions, notamment :

- Affichage de la liste de tous les champs personnalisés du système.
- Modification limitée des champs personnalisés existants.
- Suppression de champs personnalisés.
- Affichage des champs personnalisés des entités de données.
- Affichage des traductions des libellés et du texte d’aide des champ personnalisés.

### <a name="viewing-all-custom-fields"></a>Affichage de tous les champs personnalisés

La page **Champs personnalisés** fournit une visibilité sur tous les champs personnalisés qui ont été définis dans le système. Sélectionnez la table qui vous intéresse pour la mettre à jour et afficher la liste des champs personnalisés qui lui sont associés. Lorsque vous sélectionnez un champ personnalisé dans la liste, tous les détails associés s’affichent.

### <a name="editing-custom-fields"></a>Modification de champs personnalisés

Une fois qu’un champ personnalisé a été créé, seules certaines informations sur le champ personnalisé peuvent être modifiées dans la page **Champs personnalisés**.

Vous *pouvez* modifiez les attributs suivants :

- Libellé
- Texte d’aide
- Longueur, pour les champs de texte

Vous *ne pouvez pas* modifier les attributs suivants :

- Nom de champ
- Type de données

En outre, pour les champs de liste de sélection, l’ensemble des valeurs valides pour le champ personnalisé peut être réorganisé et de nouvelles valeurs peuvent être ajoutées. Toutefois, les valeurs existantes du champ de liste de sélection ne peuvent pas être supprimées. Cliquez sur **Appliquer les modifications** une fois que vous avez fini de modifier les champs d’une table spécifique pour enregistrer les modifications.

### <a name="exposing-custom-fields-on-data-entities"></a>Affichage des champs personnalisés des entités de données

Il peut également être important de rendre visibles certains champs personnalisés des entités de données. Les entités de données sont utilisées dans la fonction [Vue d’ensemble de l’intégration Office](../../dev-itpro/office-integration/office-integration.md) et pour les scénarios d’importation/exportation des données.

Procédez comme suit pour afficher un champ personnalisé d’une entité de données :

1. Sélectionnez le champ personnalisé dans la page **Champs personnalisés**.
2. Développez la section **Entités** pour afficher l’ensemble des entités appropriées.
3. Cliquez sur le bouton **Modifier**.
4. Modifiez le champ **Activé** à sélectionner pour chaque entité qui doit afficher ce champ.
5. Cliquez sur **Appliquer les modifications** pour enregistrer vos sélections.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Affichage des champs personnalisés dans d’autres langues

Comme les champs personnalisés doivent être accessibles par les utilisateurs dans différentes langues, la page **Champs personnalisés** fournit un mécanisme permettant de traduire le libellé et le texte d’aide d’un champ personnalisé dans d’autres langues.

Les étapes suivantes décrivent comment traduire les champs personnalisés dans d’autres langues :

1. Sélectionnez le champ personnalisé dans la page **Champs personnalisés**.
2. Sélectionnez le bouton **Traductions** dans le volet Actions. Un menu déroulant s’ouvre avec les traductions existantes pour ce champ.
3. Le menu déroulant **Langue** affiche l’ensemble des langues pour lesquelles des traductions ont déjà été fournies.

    Si vous souhaitez modifier une traduction existante, sélectionnez la langue dans le menu et modifiez les valeurs du libellé et du texte d’aide.

    Sinon, cliquez sur le bouton **Ajouter une langue**, sélectionnez la langue souhaitée dans le menu, puis entrez les valeurs traduites pour le libellé et le texte d’aide.

4. Cliquez sur **OK** lorsque vous avez terminé.

### <a name="deleting-custom-fields"></a>Suppression de champs personnalisés

Quand vous décidez qu’un champ personnalisé n’est plus nécessaire, un administrateur système peut choisir de supprimer le champ de la page **Champs personnalisés**. Pour supprimer un champ personnalisé, cliquez sur le champ à supprimer, cliquez sur **Supprimer**, sur **Oui** pour confirmer la suppression, puis sur **Appliquer les modifications**.

> [!NOTE]
> Cette action ne peut pas être annulée et entraînera la suppression définitive des données associées au champ de la base de données.

## <a name="appendix"></a>Annexe

### <a name="why-cant-i-enter-a-value-in-my-custom-field"></a>Pourquoi ne puis-je pas saisir de valeur dans mon champ personnalisé ? 

Si vous ne pouvez pas saisir de valeur dans le champ personnalisé lorsque la page est en mode **Édition**, cela peut être dû au fait que la table à laquelle le champ a été ajouté est actuellement en lecture seule. Tous les champs d’une table passent en lecture seule si la table de sauvegarde est actuellement configurée en lecture seule sur la page.   

### <a name="who-can-create-custom-fields"></a>Qui peut créer des champs personnalisés ?

Seuls les administrateurs système peuvent créer des champs personnalisés par défaut. Toutefois, un administrateur système peut octroyer des droits de création de champs personnalisés aux utilisateurs avec pouvoir à l’aide du rôle de sécurité **Utilisateur avec pouvoir de personnalisation de l’exécution**, si l’organisation le juge nécessaire. Les utilisateurs qui ne disposent pas de ce rôle de sécurité ne pourront pas créer de champs personnalisés, mais pourront quand même visualiser les champs personnalisés ajoutés par d’autres utilisateurs du système et interagir avec eux.

### <a name="what-tables-support-custom-fields"></a>Quelles tables prennent en charge les champs personnalisés ?

Pour des raisons de performances et techniques, seules les tables qui répondent aux conditions suivantes prennent en charge actuellement l’ajout de champs personnalisés.

- La table doit être référencée comme l’un des groupes suivants :

    - Groupe
    - WorksheetHeader
    - Principal
    - Autre(s)
    - Paramètre
    - Référence
    - TransactionHeader

- La table ne peut pas étendre une autre table.
- La table ne peut pas être marquée comme une table système.
- La table ne peut pas être une table temporaire.

### <a name="can-i-reference-custom-fields-from-the-developer-tools"></a>Puis-je référencer des champs personnalisés à partir des outils de développement ?  

Les champs personnalisés ne peuvent être gérés que via l’interface utilisateur et ne peuvent pas être référencés par du code. 

### <a name="how-can-i-move-custom-fields-between-environments"></a>Comment puis-je déplacer des champs personnalisés entre les environnements ? 

La recommandation actuelle pour déplacer des champs personnalisés entre des environnements consiste à recréer manuellement les champs personnalisés dans l’environnement cible. Pour afficher la liste complète des champs personnalisés d’une table particulière :
1. Accédez à la page **Champs personnalisés**, sélectionnez cette table dans la liste déroulante. 
2. Dans l’environnement cible, suivez le processus décrit précédemment dans cet article pour recréer chaque champ. 
3. Une fois tous les champs créés, cliquez sur **Appliquer les modifications**.  
4. Déplacez toutes les personnalisations contenant des champs personnalisés en exportant ces personnalisations depuis l’environnement d’origine et en les important dans l’environnement cible.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
