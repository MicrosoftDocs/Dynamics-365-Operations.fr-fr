---
title: Créer des postes techniques
description: Cette rubrique explique comment créer un poste technique dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d1f9714f57d19a13444fea9864d72c3341b15ea
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783268"
---
# <a name="create-functional-locations"></a>Créer des postes techniques

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Cette rubrique explique comment créer un poste technique dans le module Gestion des actifs.

Lorsque vous créez une structure de poste technique, notez qu'après l'opération, vous ne pourrez pas revenir à l'emplacement d'origine. Cela signifie que vous devez réfléchir soigneusement à la structure de vos postes techniques avant de commencer à les créer dans le module Gestion des actifs. Si vous regrettez un poste technique, vous pouvez le supprimer, à condition qu'il n'ait pas encore été utilisé.

Pour pouvoir utiliser des postes techniques, commencez par créer deux « catégories » de postes techniques :

- Créez *un* poste technique par défaut sans sous-emplacement. Ce poste technique est uniquement utilisé comme emplacement standard pour les actifs lors de la création de nouveaux actifs.  
- Créez des structures de postes techniques requises pour gérer des tâches de maintenance au sein de votre société.

## <a name="create-a-default-functional-location"></a>Créer un poste technique par défaut

Lorsque vous utilisez des postes techniques, commencez par créer un emplacement par défaut à utiliser lors de la création de nouveaux actifs. Ce poste technique est celui sélectionné via **Gestion des actifs** > **Paramétrage** > **Paramètres de gestion des actifs** > **lien Actifs** >champ **Poste technique par défaut**. Le poste technique par défaut peut être utilisé lors de la création de nouveaux actifs, et vous n'avez pas encore mis en place de structure de poste technique pour ces actifs.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Postes techniques** > **Tous les postes techniques**.  
2. Dans **Tous les postes techniques**, sélectionnez **Nouveau**.
3. Insérez un ID dans le champ **Poste technique**, par exemple, « 0000 » ou « valeur par défaut », pour indiquer qu'il s'agit d'un poste technique spécial.
4. Insérez le nom du poste technique par défaut dans le champ **Nom**.
5. Ne sélectionnez *pas* de parent dans le champ **Parent** – laissez ce champ vide.
6. Dans le champ **Type de poste technique**, sélectionnez le type de poste technique à utiliser pour le poste technique par défaut. Voir [Types de poste techniques](../setup-for-functional-locations/functional-location-types.md) pour plus d'informations sur la définition des types de postes techniques.
7. Cliquez sur **OK**. Vous ne devez pas ajouter de données supplémentaires à ce poste technique car il ne sert que d'emplacement temporaire pour les nouveaux actifs jusqu'à ce que vous installiez les actifs sur les postes techniques utilisés par votre société.

## <a name="create-functional-locations"></a>Créer des postes techniques

La procédure suivante décrit comment vous créez les postes techniques requis pour la gestion de la maintenance de votre société.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Postes techniques** > **Tous les postes techniques**. Vous pouvez créer un poste technique à partir de la vue Grille ou de la vue Détails.
2. Sélectionnez le bouton **Nouveau**.
3. Insérez un ID dans le champ **Poste technique**.
4. Insérez un nom de poste technique dans le champ **Nom**.
5. Si le poste technique est un sous emplacement dans une structure, sélectionnez l'emplacement parent dans le champ **Parent**.
6. Sélectionnez un type dans le champ **Type de poste technique**.
7. Cliquez sur **OK**.
8. Sélectionnez le poste technique et cliquez sur le bouton **Modifier** pour ajouter davantage d'informations.

>[!NOTE]
>En fonction de votre paramétrage d'états de cycle de vie du poste technique, vous devrez peut-être créer tous les sous-emplacements pour un poste technique, puis modifier l'état du cycle de vie du poste technique avant de démarrer l'installation des actifs. Voir [Installer des actifs et des postes techniques](../functional-locations/install-objects-on-functional-locations.md) pour plus d'informations sur l'installation des actifs. Voir [États du cycle de vie du poste technique](../setup-for-functional-locations/functional-location-stages.md) pour en savoir plus sur le paramétrage des états du cycle de vie du poste technique.

Dans la vue Détails, vous verrez les organisateurs dans lesquels vous pouvez ajouter et modifier des informations sur le poste technique.

## <a name="general-information"></a>Informations générales

Cette section fournit une vue d'ensemble des informations parent et enfant dans la structure du poste technique. Dans la section **Détails**, vous pouvez afficher le nombre d'attributs d'actifs, de plans de maintenance et d'actifs associés au poste technique. Dans la section **Stock**, vous pouvez sélectionner le site et l'entrepôt auxquels le poste technique est lié. Le site et l'entrepôt sont utilisés en relation avec les prévisions d'articles d'ordres de travail. En créant une prévision d'article, les informations de site et d'entrepôt relatives au poste technique de l'actif sont automatiquement utilisées. Dans la section **État du cycle de vie**, les informations sur l'état du cycle de vie du poste technique sont affichées.

## <a name="installed-assets"></a>Actifs installés

Voir [Installer des actifs et des postes techniques](../functional-locations/install-objects-on-functional-locations.md) pour plus d'informations sur l'installation des actifs. Vous pouvez utiliser le bouton **Afficher** dans cet organisateur pour afficher plus de champs de l'organisateur. Les champs **Début de validité** et **Sous-actif** peuvent être affichés dans la grille.

## <a name="asset-attribute-requirements"></a>Exigences d'attribut d'actif

Cet organisateur vous permet d'ajouter des exigences d'attributs spécifiques pour les actifs que vous installez sur le poste technique. Ces exigences sont à titre indicatif. Elles ne vous empêchent pas d'installer des actifs avec d'autres exigences d'attributs. Sélectionnez **Ajouter la ligne**, puis sélectionnez le type d'attribut. Puis vous insérez la **valeur** nécessaire, sélectionnez un seuil dans le champ **Critères de seuil** et sauvegardez l'enregistrement.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Plans de maintenance et visites de maintenance

Vous pouvez ajouter des plans de maintenance et des visites de maintenance au poste technique, notamment une date de début. Les actifs installés sur un poste technique peuvent avoir l'autre paramétrage des plans de maintenance. Tous les plans de maintenance et les visites de maintenance peuvent être utilisés pour planifier des entrées de calendrier d'actifs pour un poste technique et ses actifs actuellement installés.

>[!NOTE]
>Si vous mettez à jour le paramétrage des types d'actifs, de marques d’actifs et de modèles d’actifs dans les plans de maintenance en mode détaillé **Tous les postes techniques** > organisateur **Plans de maintenance** après avoir affecté des plans de maintenance, les entrées existantes du programme de maintenance associées à ce poste technique sont automatiquement supprimées. Pour créer des entrées de programme qui correspondent au paramétrage du plan de maintenance mis à jour dans le poste technique, vous devez exécuter un nouveau programme de plan de maintenance pour ce poste technique. 

## <a name="address"></a>Adresse

Insérez l'adresse du poste technique dans l'organisateur **Adresse**. Les adresses des postes techniques sont héritées, ce qui signifie que si un sous-emplacement n'a pas d'adresse définie, l'adresse du site parent sera utilisée.

## <a name="workers"></a>Collaborateurs

Sous cet organisateur, vous pouvez ajouter des collaborateurs au sein du poste technique, et vous pouvez sélectionner un poste technique comme principal pour le collaborateur. 

## <a name="attributes"></a>Attributs

Sous cet onglet, vous pouvez définir les valeurs définies pour les attributs du poste technique. Ces attributs peuvent être utilisés pour décrire des propriétés ou des caractéristiques pertinentes pour le poste technique, telles que des propriétés structurelles, un type de création, une description de zone ou un emplacement au-dessus ou au-dessous du sol.

Sélectionnez **Ajouter la ligne**, puis sélectionnez le type d'attribut. Ensuite, insérez la **Valeur** associée au type d'attribut et sauvegardez l'enregistrement.

## <a name="financial-dimensions"></a>Dimensions financières

Vous pouvez sélectionner des dimensions financières pour le poste technique. Les [types de postes techniques](../setup-for-functional-locations/functional-location-types.md) peuvent être paramétrés pour autoriser une mise à jour automatique des dimensions financières d'un poste technique. Cela signifie que les actifs installés sur une dimension financière obtiennent automatiquement les dimensions financières pour le poste technique. Cela est utile si vous souhaitez des centres de coût, en fonction des emplacements.

Lorsque les données relatives à **Site**, **Entrepôt**, **Adresse** et **Dimensions financières** sont mises à jour sur un poste technique parent, les sous-postes techniques associés peuvent être mis à jour en conséquence si vous effectuez cette sélection lors de la mise à jour. Une boîte de dialogue s'ouvre et vous indique les options de mise à jour.

## <a name="copy-a-functional-location-structure"></a>Copier une structure de poste technique

Si votre société a plusieurs postes techniques avec les structures d'emplacement similaires, vous pouvez utiliser la fonction de copie dans la gestion des actifs pour créer rapidement un nombre de hiérarchies d'emplacements similaires. Lorsque vous copiez un poste technique spécifique ou une structure entière, le nouvel emplacement ou la nouvelle structure porte le même nom que celui ou celle que vous avez copié(e). Une fois la procédure de copie effectuée, vous pouvez aisément modifier le nom ou d'autres paramètres pour le nouveau poste technique, à condition que l'état fonctionnel du cycle de vie de l'emplacement sélectionné pour le nouveau poste technique le permette.

1. Dans **Tous les postes techniques**, sélectionnez le poste technique à copier. Par exemple, sélectionnez un emplacement principal (parent) si vous souhaitez copier toute la structure de poste technique, y compris les sous-emplacements.
2. Sélectionnez le bouton **Copier la structure du poste technique**. L'emplacement sélectionné dans la page de liste s'affiche dans le champ **Copier depuis**.
3. Insérez le nom du nouvel emplacement dans le champ **Nouveau poste technique**.
4. Dans le champ **Parent à coller sous**, vous ne devez insérer un ID parent que si l'emplacement que vous créez doit faire partie d'une structure de poste technique existante.
5. Cliquez sur **OK**. La nouvelle structure de poste technique est affichée dans **Tous les postes techniques**.

>[!NOTE]
>Lorsque vous copiez une structure de poste technique, les états du cycle de vie du poste technique dans la nouvelle structure sont définis au « premier état » créé pour les postes techniques. Le fait de renommer ou supprimer un poste technique à l'aide des boutons **Renommer** et **Supprimer** dans **Tous les postes techniques**, dépend de l'état actuel du cycle de vie du poste technique.

## <a name="delete-a-functional-location"></a>Supprimer un poste technique

Un poste technique avec des sous-emplacements associés peut être supprimé si aucun actif n'a été installé sur l'un des postes techniques que vous essayez de supprimer et si l'état du cycle de vie du poste technique actuel le permet.

1. Dans **Tous les postes techniques**, sélectionnez le poste technique à supprimer.
2. Le cas échéant, mettez le poste technique à jour à un état de cycle de vie de poste technique qui permette de supprimer un poste technique.
3. Sélectionnez **Supprimer**.

>[!NOTE]
>Si vous ne pouvez pas supprimer un poste technique, à la place vous pouvez gérer la suppression en paramétrant un état du cycle de vie de poste technique à cet effet. Par exemple, vous pouvez paramétrer le stade « Mis au rebut « ou « Supprimé », qui ne doit pas être un stade actif, dans l'écran **États du cycle de vie du poste technique**.
