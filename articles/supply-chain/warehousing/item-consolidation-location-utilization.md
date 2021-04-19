---
title: Consolidation des articles - Utilisation de l’emplacement
description: Cette rubrique fournit des informations sur les fonctionnalités qui permettent aux responsables d’entrepôt d’afficher et de filtrer facilement l’utilisation volumétrique des emplacements dans l’entrepôt. Les responsables peuvent sélectionner des emplacements et créer un travail de mouvement des stocks directement à partir de la page Consolidation des articles afin de regrouper des articles et ainsi mieux utiliser l’espace de l’entrepôt.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 892190ea7bad34dfd308796b93a1828e0e8e11b9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835567"
---
# <a name="item-consolidation---location-utilization"></a>Consolidation des articles - Utilisation de l’emplacement

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les fonctionnalités qui permettent aux responsables d’entrepôt d’afficher et de filtrer facilement l’utilisation volumétrique des emplacements dans l’entrepôt. Les responsables peuvent sélectionner des emplacements et créer un travail de mouvement des stocks directement à partir de la page **Consolidation des articles** afin de regrouper des articles et ainsi mieux utiliser l’espace de l’entrepôt.

## <a name="turn-on-the-features"></a>Activer les fonctionnalités

Avant de pouvoir utiliser les fonctionnalités décrites dans cette rubrique, vous devez les activer dans votre système. Les administrateurs peuvent utiliser l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de ces fonctionnalités et les activer si nécessaire. Activez les deux fonctionnalités, dans l’ordre dans lequel elles sont mentionnées. (Les deux fonctionnalités sont destinées au module **Gestion des entrepôts**.)

1. Statut de l’emplacement de l’entrepôt
2. Utilisation de l’emplacement de consolidation des articles

## <a name="warehouse-location-status"></a>Statut de l’emplacement de l’entrepôt

La fonctionnalité *Statut de l’emplacement de l’entrepôt* ajoute quatre nouveaux champs à la page **Emplacements** pour suivre des informations supplémentaires sur l’état actuel de l’emplacement :

- **Numéro d’article** - Article qui se trouve actuellement à l’emplacement. Si l’emplacement contient plusieurs articles, ce champ est vide.
- **Date et heure de la dernière activité** - Horodatage de la dernière transaction d’entrepôt effectuée à l’emplacement.
- **Date âgée** - Date à laquelle le stock de l’emplacement a été introduit dans l’entrepôt. Cette date est calculée en fonction de la date de vieillissement du contenant. Bien que cette date soit précise pour les emplacements suivis par contenant, elle peut ne pas être précise pour les emplacements qui ne font pas l’objet d’un suivi par contenant.
- **Statut de l’emplacement** - Statut de l’emplacement. Les quatre valeurs disponibles sont les suivantes :

    - **Indéterminé** - Le profil d’emplacement ne peut pas effectuer le suivi du statut. Par conséquent, le statut actuel est inconnu.
    - **Vide** - Il n’y a actuellement aucun stock à l’emplacement.
    - **Prélèvement** - Des transactions sortantes ont été effectuées à l’emplacement après qu’il a été vide pour la dernière fois.
    - **Stockage** - Seules des transactions sortantes ont été effectuées à l’emplacement depuis qu’il a été vide pour la dernière fois.

Ces champs permettent aux responsables d’entrepôt d’avoir une meilleure vue d’ensemble du statut des emplacements de l’entrepôt. Ils permettent également de générer des rapports et un filtrage plus avancés.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Paramétrage de la consolidation des articles et de l’utilisation de l’emplacement

Cette section décrit comment préparer votre système à utiliser la consolidation des articles et l’utilisation de l’emplacement. Les procédures utilisent des exemples de valeurs provenant des données de démonstration standard. Si vous envisagez de suivre l’exemple de scénario fourni plus loin dans cette rubrique, sélectionnez l’entité juridique **USMF** (qui contient les données de démonstration standard) et créez chaque enregistrement décrit dans cette section. Si vous ne prévoyez pas de suivre l’exemple de scénario, les valeurs fournies ici peuvent être considérées comme des exemples des types de paramètres à employer pour utiliser les fonctionnalités.

### <a name="released-product"></a>Produit lancé

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans le champ **Numéro d’article**, sélectionnez *M9201* et ouvrez la page des détails.
1. Dans le volet Action,s dans l’onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques**.
1. Sur la page **Dimension physique**, dans le volet Actions, sélectionnez **Nouveau**.

    Une nouvelle ligne est ajoutée à la grille. Le champ **Numéro d’article** est prédéfini.

1. Dans le champ **Unité**, sélectionnez *Unités*. Les champs restants de la ligne sont automatiquement définis.
1. Cliquez sur **Enregistrer**, puis fermez la page.

### <a name="location-profile"></a>Profil d’emplacement

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.
1. Dans la liste des profils d’emplacement, sélectionnez **FLOOR-05**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans l’organisateur **Général**, assurez-vous que les deux options suivantes sont définies sur *Oui* :

    - Activer l’article à l’emplacement
    - Activer le statut de l’emplacement

1. Sélectionnez **Enregistrer**.

    > [!IMPORTANT]
    > Si les options **Activer l’article à l’emplacement** et **Activer le statut de l’emplacement** étaient déjà définies sur *Oui*, passez directement aux instructions de configuration de l’organisateur **Dimensions** à l’étape 10. Si les options n’étaient pas déjà définies sur *Oui*, vous devez exécuter une vérification de cohérence pour le module **Gestion des entrepôts** après les avoir définies manuellement. Dans ce cas, passez à l’étape suivante.

1. Pour exécuter le contrôle de cohérence, accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence**.
1. Dans la boîte de dialogue **Contrôle de cohérence**, définissez les valeurs suivantes :

    - **Module :** *Gestion des entrepôts*
    - **Vérifier/réparer :** *Vérifier*
    - **Date de début :** Laissez ce champ vide.
    - **Vérification de la cohérence du statut des emplacements de l’entrepôt :** Cochez cette case.

1. Cliquez sur **OK**.

    > [!TIP]
    > Vous recevez une notification lorsque le contrôle de cohérence est terminé. Ouvrez le [Centre d’action](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) pour afficher le message. Sélectionnez **Détails du message** pour afficher les détails.
    >
    > Si le message pour le contrôle de cohérence indique «Informations de statut d’emplacement incorrectes trouvées pour l’emplacement XXXX dans l’entrepôt XX », vous devez réexécuter le contrôle de cohérence. Cette fois, définissez le champ **Vérifier/réparer** sur *Corriger les erreurs*. Affichez les messages pour vous assurer qu’aucune erreur n’a été trouvée.

1. Vous devez maintenant terminer la configuration du profil d’emplacement. Revenez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**, sélectionnez le profil d’emplacement **FLOOR-05** puis, dans le volet Actions, sélectionnez **Modifier**.
1. Dans l’organisateur **Dimensions**, définissez les valeurs suivantes :

    - **Pourcentage d’utilisation du volume :** *100*
    - **Méthode volumétrique utilisée pour l’emplacement du stock :** *Utiliser le volume de l’emplacement*
    - **Hauteur réelle de l’emplacement :** *10*
    - **Largeur réelle de l’emplacement :** *10*
    - **Profondeur réelle de l’emplacement :** *10*
    - **Poids maximal :** *100*

1. Sélectionnez **Enregistrer**.

### <a name="mobile-device-menu-items"></a>Options de menu d’appareil mobile

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un élément de menu pour le tri.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Nom de l’élément de menu :** *Ajuster à l’intérieur*
    - **Titre :** *Ajuster à l’intérieur*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Non*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Processus de création de travail :** *Ajustement à l’intérieur*
    - **Types d’ajustements de stock :** *Ajuster à l’intérieur*

1. Sélectionnez **Enregistrer**.

### <a name="mobile-device-menu"></a>Menu d’appareil mobile

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Dans la liste des menus, sélectionnez **Stock**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la liste **Menus et éléments de menus disponibles**, recherchez et sélectionnez l’élément de menu **Ajuster à l’intérieur**.
1. Sélectionnez le bouton en forme de flèche vers la droite pour déplacer **Ajuster à l’intérieur** vers la liste **Structure du menu**. De cette façon, vous ajoutez le nouvel élément de menu au menu sélectionné.
1. Sélectionnez **Enregistrer**.

### <a name="movement-types"></a>Types de mouvements

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Types de mouvements**.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :

    - **Code de type de mouvement :** *CONSOLIDER*
    - **Description :** *Regrouper les emplacements*
    - **ID classe de travail :** *InvMov*

1. Sélectionnez **Enregistrer**.

## <a name="example-scenario"></a>Exemple de scénario

Le scénario suivant utilise l’application mobile Gestion des entrepôts sur un appareil mobile pour faire un *ajustement intérieur* sur le stock à deux emplacements dans l’entrepôt.

### <a name="add-inventory-to-locations"></a>Ajouter du stock dans des emplacements

1. Connectez-vous à l’appareil mobile en tant qu’utilisateur activé pour l’entrepôt *51*.
1. Accédez à **Stock \> Ajuster à l’intérieur**.

    Vous allez maintenant entrer le premier ajustement d’emplacement.

1. Dans la tâche **Ajustement à l’intérieur**, sélectionnez l’emplacement pour lequel effectuer l’ajustement de stock. Dans le champ **LOC**, sélectionnez *LP-001*.
1. Confirmez l’emplacement.
1. Créez un ID de contenant pour l’article qui sera ajouté à l’emplacement. Dans le champ **LP**, entrez *LP00101*.
1. Confirmez le contenant.
1. Entrez l’article qui sera ajouté au contenant. Dans le champ **ITEM**, entrez *M9201*.
1. Confirmez l’article.
1. Entrez la quantité de l’article qui sera ajoutée. Dans le champ **QTÉ**, entrez *10*.
1. Confirmez la quantité.

    Vous recevez un message « Travail terminé ». Vous allez maintenant entrer le deuxième ajustement d’emplacement.

1. Dans la tâche **Ajustement à l’intérieur**, sélectionnez l’emplacement pour lequel effectuer l’ajustement de stock. Dans le champ **LOC**, sélectionnez *LP-002*.
1. Confirmez l’emplacement.
1. Créez un ID de contenant pour l’article qui sera ajouté à l’emplacement. Dans le champ **LP**, entrez *LP00201*.
1. Confirmez le contenant.
1. Entrez l’article qui sera ajouté au contenant. Dans le champ **ITEM**, entrez *M9201*.
1. Confirmez l’article.
1. Entrez la quantité de l’article qui sera ajoutée. Dans le champ **QTÉ**, entrez *15*.
1. Confirmez la quantité.

    Vous recevez un message « Travail terminé ».

1. Sélectionnez le bouton Menu (parfois appelé hamburger ou bouton hamburger), puis sélectionnez **Annuler** pour quitter la tâche **Ajustement à l’intérieur**.

### <a name="consolidate-locations"></a>Regrouper les emplacements

1. Accédez à **Gestion des entrepôts \> Tâches périodiques \> Consolidation des articles**.
1. Dans l’en-tête, sélectionnez un entrepôt pour lequel effectuer la consolidation. Dans le champ **Entrepôt**, entrez *51*.

    Un enregistrement est affiché pour chaque emplacement où l’article *M9201* a été ajusté. La colonne **Pourcentage d’utilisation** montre l’utilisation volumétrique de chaque emplacement.

1. Pour consolider le stock, sélectionnez tous les emplacements qui doivent être regroupés puis, dans le volet Actions, sélectionnez **Regrouper le stock**.
1. Dans la boîte de dialogue **Regrouper le stock**, spécifiez l’emplacement et le type de mouvement à utiliser pour créer le travail pour le mouvement de stock. Définissez les valeurs suivantes :

    - **Emplacement :** *LP-001*
    - **Code de type de mouvement :** *CONSOLIDER*

1. Cliquez sur **OK**.
1. Vous recevez un message d’information présentant le travail de déplacement qui a été créé. Prenez note de l’ID du travail de déplacement.

### <a name="view-movement-work"></a>Afficher le travail de déplacement

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Affichez le travail qui a été créé. Utilisez l’ID de travail de déplacement issu du regroupement de stock pour filtrer ou la grille de travail ou y faire une recherche.

    Dans ce scénario, un emplacement existant contenant du stock a été utilisé comme emplacement de regroupement du stock. Par conséquent, un seul ID de travail a été créé.

    > [!NOTE]
   > Le système crée un ID de travail pour chaque déplacement qui doit être effectué. Si vous spécifiez un emplacement qui contient déjà du stock, un seul ID de travail est créé. Si vous spécifiez un nouvel emplacement, deux ID de travail sont créés.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]