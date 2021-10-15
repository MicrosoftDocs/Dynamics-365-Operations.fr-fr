---
title: Stratégies de travail
description: Cette rubrique explique comment paramétrer des politiques de travail.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1d4ee3f1bffaf00c20758f6a3f399451d3122291
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571159"
---
# <a name="work-policies"></a>Stratégies de travail

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer le système et l’application mobile Gestion des entrepôts afin qu’ils prennent en charge les stratégies de travail. Vous pouvez utiliser cette fonctionnalité pour enregistrer rapidement un stock sans créer de travail de rangement lorsque vous recevez des commandes fournisseur ou de transfert, ou lorsque vous terminez des processus de fabrication. Cette rubrique fournit des informations générales. Pour obtenir des informations détaillées sur la réception des contenants, consultez [Réception du contenant via l’application mobile Gestion des entrepôts](warehousing-mobile-device-app-license-plate-receiving.md).

Une stratégie de travail contrôle si le travail d’entrepôt est créé lorsqu’un article manufacturé est déclaré comme terminé ou lorsque les marchandises sont reçues à l’aide de l’application mobile Gestion des entrepôts. Vous configurez chaque stratégie de travail en définissant les conditions dans lesquelles elle s’applique : les types et processus d’ordre de travail, l’emplacement du stock et (éventuellement) les produits. Par exemple, une commande fournisseur pour un produit *A0001* doit être reçue à l’emplacement *RECV* dans l’entrepôt *24*. Plus tard, le produit est consommé dans un autre processus à l’emplacement *RECV*. Dans ce cas, vous pouvez configurer une stratégie de travail pour empêcher la création du travail de rangement lorsqu’un collaborateur signale un produit *A0001* reçu à l’emplacement *RECV*.

> [!NOTE]
> - Pour qu’une stratégie de travail soit active, vous devez définir au moins un emplacement pour elle sur l’organisateur **Emplacements de stock** de la page **Stratégies de travail**. 
> - Vous ne pouvez pas spécifier le même emplacement pour plusieurs stratégies de travail.
> - L’option **Imprimer l’étiquette** pour les options de menu des appareils mobiles n’imprimera pas d’étiquette de contenant sans création de travail.

## <a name="activate-the-features-in-your-system"></a>Activez les fonctionnalités de votre système

Pour rendre toutes les fonctionnalités décrites dans cette rubrique disponibles dans votre système, activez les deux fonctionnalités suivantes dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- Amélioration de la réception de contenants
- Améliorations de la stratégie de travail pour le travail entrant

## <a name="the-work-policies-page"></a>Page Stratégies de travail

Pour configurer des stratégies de travail, accédez à **Gestion d’entrepôt \> Paramètres \> Travail \> Stratégies de travail**. Ensuite, sur chaque organisateur, définissez les champs comme décrit dans les sous-sections suivantes.

### <a name="the-work-order-types-fasttab"></a>Organisateur Types d’ordres de travail

Sur l’organisateur **Types d’ordres de travail**, ajoutez tous les types d’ordres de travail et les processus de travail associés auxquels la stratégie de travail s’applique. Les types d’ordres de travail suivants et les processus de travail associés sont pris en charge pour les stratégies de travail.

| Type d’ordre d’exécution | Processus de travail |
|---|---|
| Prélèvement de matières premières| Tous les processus associés |
| Rangement des coproduits et des sous-produits | Tous les processus associés |
| Rangement des produits finis | Tous les processus associés |
| Réception du transfert | Réception (et rangement) de contenant |
| Commandes fournisseur | <ul><li>Réception (et rangement) de contenant</li><li>Réception (et rangement) des articles du chargement</li><li>Réception (et rangement) de la ligne de commande fournisseur</li><li>Réception (et rangement) de l’article de commande fournisseur</li></ul> |

Pour configurer une stratégie de travail afin qu’elle s’applique à plusieurs processus de travail du même type d’ordre de travail, ajoutez une ligne distincte pour chaque processus de travail à la grille.

Pour chaque ligne de la grille, définissez le champ **Méthode de création de travail** sur l’une des valeurs suivantes :

- **Jamais** – La stratégie de travail empêchera tout travail d’entrepôt d’être créé pour le type d’ordre d’exécution sélectionné et le processus de travail associé.
- **Cross-docking** – La stratégie de travail créera un travail de cross-docking en utilisant la stratégie que vous sélectionnez dans le champ **Nom de la stratégie de cross-docking**.

### <a name="the-inventory-locations-fasttab"></a>Organisateur Emplacements de stock

Sur l’organisateur **Emplacements de stock**, ajoutez tous les emplacements où cette stratégie de travail doit être appliquée. Si aucun emplacement n’est associé à une stratégie de travail, la stratégie de travail ne sera appliquée à aucun processus.

Vous ne pouvez pas spécifier le même emplacement pour plusieurs stratégies de travail.

Vous pouvez utiliser un emplacement d’entrepôt affecté à un profil d’emplacement lorsque l’option **Utiliser le suivi des contenants** est désactivée. Dans ce cas, les collaborateurs enregistreront directement le stock disponible.

### <a name="the-products-fasttab"></a>Organisateur Produits

Sur l’onglet **Produits**, définissez le champ **Sélection de produit** pour contrôler les produits auxquels la stratégie doit s’appliquer :

- **Tout** – La stratégie doit s’appliquer à tous les produits.
- **Sélectionné** – La stratégie doit s’appliquer uniquement aux produits répertoriés dans la grille. Utilisez la barre d’outils sur l’organisateur **Produits** pour ajouter des produits à la grille ou les supprimer de la grille.

## <a name="default-and-custom-to-locations"></a>Emplacements « Vers » par défaut et personnalisés

> [!NOTE]
> Pour rendre la fonctionnalité décrite dans cette section disponible dans votre système, vous devez activer les fonctionnalités *Améliorations de la réception des contenants* et *Améliorations de la stratégie de travail pour le travail entrant* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Auparavant, le système prenait en charge la réception uniquement à l’emplacement par défaut défini pour chaque entrepôt. Cependant, les éléments de menu de l’appareil mobile qui utilisent les processus de création de travail suivants fournissent désormais l’option **Utiliser les données par défaut**. Cette option vous permet d’attribuer un emplacement personnalisé « Vers » à un ou plusieurs éléments de menu. (Cette option était déjà disponible pour certains autres types d’options de menu.)

- Réception (et rangement) de contenant
- Réception (et rangement) des articles du chargement
- Réception (et rangement) de la ligne de commande fournisseur
- Réception (et rangement) de l’article de commande fournisseur

Le paramètre **Emplacement Vers** d’un élément de menu remplace le lieu de réception par défaut de l’entrepôt, pour toutes les commandes traitées à l’aide de cet élément de menu.

Pour configurer un élément de menu d’appareil mobile afin de prendre en charge la réception à un emplacement personnalisé, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Sélectionnez ou créez un élément de menu qui utilise l’un des processus de création de travail répertoriés plus haut dans cette section.
1. Dans l’organisateur **Général**, définissez l’option **Utiliser les données par défaut** sur **Oui**.
1. Sur le volet Action, sélectionnez **Données par défaut**.
1. Sur la page **Données par défaut**, définissez les valeurs suivantes :

    - **Champ Données par défaut :** Définissez ce champ sur *Emplacement Vers*.
    - **Entrepôt :** Sélectionnez l’entrepôt de destination à utiliser avec cet élément de menu.
    - **Emplacement :** Ce champ répertorie tous les ID emplacement disponibles pour l’entrepôt sélectionné. Cependant, le paramètre de ce champ n’a en fait aucun effet. Par conséquent, vous ne pouvez pas le laisser vide. Néanmoins, vous pouvez utiliser la liste pour confirmer l’ID que vous devez saisir dans le champ **Valeur codée en dur**.
    - **Valeur codée en dur :** Entrez l’ID emplacement de l’emplacement de réception qui s’applique à cet élément de menu.

> [!TIP]
> Une stratégie de travail ne peut être appliquée que si tous les emplacements de réception sont répertoriés dans la configuration de stratégie de travail appropriée. Cette exigence s’applique indépendamment du fait que vous utilisiez l’emplacement de réception de l’entrepôt par défaut ou un emplacement de destination personnalisé.

## <a name="example-scenario-warehouse-receiving"></a>Exemple de scénario : Réception en entrepôt

Tous les produits reçus par le processus *Réception (et rangement) de l’article de commande fournisseur* doivent être enregistrés à l’emplacement *FL-001*, et doivent être disponibles dans l’entrepôt *24*. Cependant, le travail ne doit pas être créé. Les produits reçus par tout autre processus (c’est-à-dire en utilisant d’autres éléments de menu de l’appareil mobile) doivent être enregistrés à l’emplacement de réception par défaut de l’entrepôt (*RECV*), et le travail doit être créé comme d’habitude. (Ce scénario n’affiche pas la configuration de réception par défaut.)

Ce scénario nécessite les éléments suivants :

- Une stratégie de travail pour le processus *Réception (et rangement) de l’article de commande fournisseur* à l’emplacement *FL-001*, pour tous les produits
- Un élément de menu d’appareil mobile qui a des données par défaut et qui définit le champ **Emplacement Vers** sur *FL-001*

### <a name="prerequisites"></a>Conditions préalables

Pour rendre la fonctionnalité décrite dans ce scénario disponible dans votre système, vous devez activer les fonctionnalités *Améliorations de la réception des contenants* et *Améliorations de la stratégie de travail pour le travail entrant* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Ce scénario utilise les données de démonstration standard. Par conséquent, si vous souhaitez l’exécuter à l’aide des valeurs fournies ici, vous devez utiliser un système dans lequel les données de démonstration sont installées. De plus, vous devez sélectionner l’entité juridique **USMF**.

### <a name="set-up-a-work-policy"></a>Paramétrer une stratégie de travail

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Stratégies de travail**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom de la stratégie de travail**, entrez *Aucun travail de rangement d’article d’achat*.
1. Sélectionnez **Enregistrer**.
1. Sur l’organisateur **Types d’ordres de travail**, sélectionnez **Ajouter** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - **Type d’ordre de travail :** *Commandes fournisseur*
    - **Processus de travail :** *Réception (et rangement) de l’article de commande fournisseur*
    - **Méthode de création de travail :** *Jamais*
    - **Nom de la stratégie de cross-docking :** Laissez ce champ vide.

1. Sur l’organisateur **Emplacements de stocks**, sélectionnez **Ajouter** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - **Entrepôt :** *24*
    - **Emplacement :** *FL-001*

1. Sur l’organisateur **Produits**, définissez le champ **Sélection de produit** sur *Tout*.
1. Sélectionnez **Enregistrer**.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Paramétrer une option de menu d’appareil mobile pour modifier l’emplacement de réception

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet de gauche, sélectionnez l’élément du menu **Réception d’achat**.
1. Dans l’organisateur **Général**, définissez l’option **Utiliser les données par défaut** sur *Oui*.
1. Sélectionnez **Enregistrer**.
1. Sur le volet Action, sélectionnez **Données par défaut**.
1. Sur la page **Données par défaut**, sur le volet Action, sélectionnez **Nouvelle** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - **Champ de données par défaut :** *Emplacement Vers*
    - **Entrepôt :** *24*
    - **Emplacement :** Laissez ce champ vide.
    - **Valeur codée en dur :** *FL-001*

1. Sélectionnez **Enregistrer**.

### <a name="receive-a-purchase-order-without-creating-work"></a>Recevez une commande fournisseur sans créer de travail

L’exemple de cette section montre comment recevoir un élément de commande fournisseur, mais sans créer de travail, à un emplacement qui diffère de l’emplacement de réception par défaut qui est configuré pour l’entrepôt. Cet exemple utilise la stratégie de travail et l’élément d’appareil mobile que vous avez créés précédemment dans ce scénario.

#### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :

    - **Compte fournisseur :** *US-101*
    - **Site :** *2*
    - **Entrepôt :** *24*

1. Sélectionnez **OK** pour fermer la boîte de dialogue et ouvrir la nouvelle commande fournisseur.
1. Sur l’organisateur **Lignes de commande fournisseur**, définissez les valeurs suivantes pour la ligne vide :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *1*

1. Sélectionnez **Enregistrer**.
1. Prenez note du numéro de la commande fournisseur.

#### <a name="receive-a-purchase-order"></a>Recevoir une commande fournisseur

1. Sur l’appareil mobile, connectez-vous à l’entrepôt *24* en utilisant *24* comme ID d’utilisateur et *1* comme mot de passe.
1. Sélectionnez **Entrant**.
1. Sélectionnez **Réception d’achat**. Le champ **Emplacement** doit être défini sur *FL-001*.
1. Saisissez le numéro de commande fournisseur de la commande fournisseur que vous avez créée dans la procédure précédente.
1. Dans le champ **Numéro d’article**, saisissez *A0001*.
1. Cliquez sur **OK**.
1. Dans le champ **Quantité**, entrez *1*.
1. Cliquez sur **OK**.

La commande fournisseur est maintenant reçue, mais aucun travail ne lui est associé. Le stock disponible a été mis à jour et une quantité de *1* article *A0001* est maintenant disponible à l’emplacement *FL-001*.

## <a name="example-scenario-manufacturing"></a>Exemple de scénario : Fabrication

Dans l’exemple suivant, il existe deux ordres de fabrication, *PRD-001* et *PRD-002*. L’ordre de fabrication *PRD-001* a une opération qui est appelée *Assemblage*, où le produit *SC1* est déclaré terminé à l’emplacement *001*. L’ordre de fabrication *PRD-002* a une opération qui est appelée *Peinture* et consomme le produit *SC1* de l’emplacement *001*. L’ordre de fabrication *PRD-002* consomme également la matière première *RM1* de l’emplacement *001*. Les matières premières *RM1* sont stockées à l’emplacement d’entrepôt *BULK-001* et seront prélevées à l’emplacement *001* par le travail d’entrepôt pour le prélèvement de matières premières. Le travail de prélèvement est généré lorsque la production de *PRD-002* est lancée.

[![Stratégies de travail d’entrepôt.](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

Lorsque vous planifiez de configurer une stratégie de travail d’entrepôt pour ce scénario, vous devez prendre en compte les points suivants :

- Le travail d’entrepôt pour le rangement de produits finis n’est pas obligatoire lorsque vous déclarez le produit *SC1* comme terminé dans l’ordre de fabrication *PRD-001* à l’emplacement *001*. Cela s’explique par le fait que l’opération de *Peinture* pour l’ordre de fabrication *PRD-002* consomme le produit *SC1* au même emplacement.
- Le travail d’entrepôt pour le prélèvement de matières premières est requis pour déplacer la matière première *RM1* de l’emplacement d’entrepôt *BULK-001* vers l’emplacement *001*.

Voici un exemple de stratégie de travail que vous pouvez paramétrer, selon ces aspects :

- **Nom de la stratégie de travail :** *Aucun travail de rangement*
- **Types d’ordres de travail :** *Rangement des produits finis* et *Rangement des coproduits et sous-produits*
- **Emplacements de stocks :** Entrepôt *51* et emplacement *001*
- **Produits :** *SC1*

L’exemple de scénario suivant fournit des instructions pas-à-pas sur la configuration de la stratégie de travail d’entrepôt pour ce scénario.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Exemple de scénario : Déclarer un ordre de fabrication terminé à un emplacement qui n’est pas contrôlé par contenant

Ce scénario présente un exemple de déclaration d’un ordre de fabrication comme terminé à un emplacement qui n’est pas contrôlé par contenant.

Ce scénario utilise les données de démonstration standard. Par conséquent, si vous souhaitez l’exécuter à l’aide des valeurs fournies ici, vous devez utiliser un système dans lequel les données de démonstration sont installées. De plus, vous devez sélectionner l’entité juridique **USMF**.

### <a name="set-up-a-warehouse-work-policy"></a>Paramétrer une stratégie de travail d’entrepôt

Les processus d’entrepôt n’incluent pas systématiquement les tâches d’entrepôt. En définissant une stratégie de travail, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Stratégies de travail**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom de la stratégie de travail**, entrez *Aucun travail de rangement*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Sur l’organisateur **Types d’ordres de travail**, sélectionnez **Ajouter** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - **Type d’ordre de travail :** *Rangement des produits finis*
    - **Processus de travail :** *Tous les processus de travail associés*
    - **Méthode de création de travail :** *Jamais*
    - **Nom de la stratégie de cross-docking :** Laissez ce champ vide.

1. Sélectionnez **Ajouter** à nouveau pour ajouter une seconde ligne à la grille, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - **Type d’ordre de travail :** *Rangement des coproduits et des sous-produits*
    - **Processus de travail :** *Tous les processus de travail associés*
    - **Méthode de création de travail :** *Jamais*
    - **Nom de la stratégie de cross-docking :** Laissez ce champ vide.

1. Sur l’organisateur **Emplacements de stocks**, sélectionnez **Ajouter** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour la nouvelle ligne :

    - **Entrepôt :** *51*
    - **Rangement :** *001*

1. Sur l’organisateur **Produits**, définissez le champ **Sélection de produit** sur *Sélectionné*.
1. Sous l’organisateur **Produits**, sélectionnez **Ajouter** pour ajouter une ligne dans la grille.
1. Dans la nouvelle ligne, définissez le champ **Numéro d’article** sur *L0101*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-an-output-location"></a>Définir un emplacement de sortie

1. Allez dans **Administration d’organisation \> Ressources \> Groupes de ressources**.
1. Dans le volet gauche, sélectionnez le groupe de ressources **5102**.
1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Entrepôt de sortie :** *51*
    - **Emplacement de sortie :** *001*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

> [!NOTE]
> L’emplacement *001* n’est un emplacement qui fait l’objet d’un contrôle de contenant. Vous ne pouvez paramétrer un emplacement de sortie ne faisant pas l’objet d’un contrôle de contenant que si une stratégie de travail applicable existe pour l’emplacement.

### <a name="create-a-production-order-and-report-it-as-finished"></a>Créer un ordre de fabrication et le déclarer comme terminé

1. Allez dans **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication**.
1. Dans le volet Actions, sélectionnez **Nouvel ordre de fabrication**.
1. Dans la boîte de dialogue **Créer un ordre de fabrication**, définissez le champ **Numéro d’article** sur *L0101*.
1. Sélectionnez **Créer** pour créer l’ordre et fermez la boîte de dialogue.

    Un nouvel ordre de fabrication est ajouté à la grille sur la page **Tous les ordres de fabrication**.

    Gardez le nouvel ordre de fabrication sélectionné.

1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Processus**, sélectionnez **Estimer**.
1. Dans la boîte de dialogue **Estimer**, lisez l’estimation, puis sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Processus**, sélectionnez **Démarrer**.
1. Dans la boîte de dialogue **Démarrer**, sur l’onglet **Général**, définissez le champ **Consommation de nomenclature automatique** sur *Jamais*.
1. Sélectionnez **OK** pour enregistrer votre paramètre et fermer la boîte de dialogue.
1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Processus**, sélectionnez **Signaler comme terminé**.
1. Dans la boîte de dialogue **Signaler comme terminé**, sur l’onglet **Général**, définissez l’option **Accepter l’erreur** sur *Oui*.
1. Sélectionnez **OK** pour enregistrer votre paramètre et fermer la boîte de dialogue.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Général**, cliquez sur **Détails du travail**.

Lorsque l’ordre de fabrication est signalé comme terminé, aucun travail de rangement n’est généré. Ce comportement se produit, car une stratégie de travail est définie et empêche la tâche d’être générée lorsque le produit *L0101* est signalé comme terminé à l’emplacement *001*.

## <a name="more-information"></a>Informations supplémentaires

Pour plus d’informations sur les éléments de menu des appareils mobiles, voir [Configurer des appareils mobiles pour le travail en entrepôt](configure-mobile-devices-warehouse.md).

Pour plus d’informations sur la réception des contenants et les stratégies de travail, voir [Réception du contenant via l’application mobile Gestion des entrepôts](warehousing-mobile-device-app-license-plate-receiving.md).

Pour plus d’informations sur la gestion des chargements entrants, voir [Gestion en entrepôt des chargements entrants pour les commandes fournisseur](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]