---
title: Codes motif d’inventaire de stock
description: Cette rubrique décrit comment paramétrer et appliquer des codes motif pour les tâches d’inventaire.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4c178ddf342b13a0ef8fee8b8b958554a9a31069
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500588"
---
# <a name="reason-codes-for-inventory-counting"></a>Codes motif d’inventaire de stock

[!include [banner](../includes/banner.md)]

Les codes motif permettent d’analyser les résultats d’un processus d’inventaire et les écarts qui surviennent lors de ce processus. Vous pouvez indiquer le motif du comptage, tel qu’une palette brisée ou un ajustement du stock basé sur des exemples de stock. En même temps, vous pouvez utiliser la fonctionnalité d’ajustement pour valider la valeur des ajustements de stock disponible sur le compte de contrepartie approprié, en fonction du motif de chaque ajustement de stock.

## <a name="recommendation"></a>Recommandation

Avant de paramétrer le système, nous vous recommandons de définir une stratégie pour l’utilisation des codes motif. Par exemple, essayez de répondre aux questions suivantes :

- Les codes motif doivent-ils être obligatoires dans les entrepôts ?
- Les codes motif doivent-ils être obligatoires ou facultatifs pour certains articles ?
- De combien de codes motif avez-vous besoin ?
- Devez-vous présélectionner une liste limitée de codes de motif pour les ajustements ?
- Comment les utilisateurs des lecteurs de codes-barres doivent-ils utiliser les codes motif ? Les codes motif doivent-ils être présélectionnés, obligatoires, ou non modifiables ?
- Les magasiniers ont-ils besoin de différents comportements de code motif sur les scanneurs mobiles ? Si la réponse est oui, vous pouvez créer plusieurs éléments de menu et les affecter à différentes personnes.
- Les codes motif doivent-ils conduire à la comptabilisation du compte de contrepartie financière ?

## <a name="turn-on-reason-code-features-in-your-system"></a>Activer les fonctionnalités de code motif dans votre système

Si vous ne voyez pas toutes les fonctionnalités décrites dans cette rubrique dans votre système, vous devez probablement activer la fonctionnalité *Valider les ajustements en stock à l’aide de codes de motif configurables connectés aux comptes de contrepartie*. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Valider les ajustements en stock à l’aide de codes de motif configurables connectés aux comptes de contrepartie*

## <a name="set-up-reason-codes"></a>Paramétrer des codes motif

### <a name="set-up-reason-code-policies"></a>Paramétrer des stratégies de codes motif

Vous pouvez créer plusieurs stratégies de code de motif pour contrôler quand et comment les codes de motif de comptage sont appliqués. Chaque stratégie de code de motif peut avoir l’un des deux types de code de motif d’inventaire (*Facultatif* ou *Obligatoire*). Les stratégies de codes motif d’inventaire peuvent être utilisées au niveau de l’entrepôt ou au niveau de l’article.

Pour créer une stratégie de code motif, procédez comme suit.

1. Aller à **Gestion des stocks** \> **Configurer** \> **Stock** \> **Stratégies de code de motif d’inventaire**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une stratégie à la grille.
1. Définissez le champ **Nom** pour la nouvelle stratégie.
1. Dans le champ **Type de code motif d’inventaire**, sélectionnez *Obligatoire* ou *Facultatif* pour spécifier si la sélection d’un code motif doit être facultative ou obligatoire dans l’un des processus d’inventaire suivants :

    - Inventaire tournant (appareil mobile)
    - Inventaire ponctuel (appareil mobile)
    - Inventaire de seuil (appareil mobile)
    - Ajustement en entrée (appareil mobile)
    - Ajustement en sortie (appareil mobile)
    - Journal d’inventaire (Rich Client)
    - Ajustement de quantité/inventaire en ligne (client riche)

Vous pouvez également paramétrer des stratégies de codes motif pour des entrepôts et des produits individuels. La configuration du code raison pour un produit peut annuler la configuration de l’entrepôt du produit.

> [!NOTE]
> Pour les entrepôts et les articles où le champ **Stratégie de code motif d’inventaire** est défini sur *Obligatoire*, le journal d’inventaire ne peut pas être rempli et clôturé tant qu’un code motif n’est pas fourni. Pour plus d’informations, voir la section suivante.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>Affecter des stratégies de code motif d’inventaire aux entrepôts

Pour affecter une stratégie de code de motif d’inventaire à un entrepôt, procédez comme suit.

1. Accédez à **Gestion des stocks** \> **Paramétrage** \> **Décomposition du stock** \> **Entrepôts**.
1. Dans le volet de liste, sélectionnez un entrepôt.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Configuration**, cliquez sur **Stratégie de code de motif d’inventaire**. Ensuite, dans la boîte de dialogue déroulante **Attribuer une stratégie de code de motif d’inventaire**, suivez l’une des étapes suivantes :

    - Pour utiliser la configuration de stratégie pour chaque article afin de déterminer si les journaux de comptage sont obligatoires pour celui-ci, n’entrez aucune valeur (ou supprimez la valeur existante).
    - Pour exiger un code motif sur les journaux d’inventaire pour l’entrepôt, sélectionnez une stratégie de motif où le champ **Type de code de motif d’inventaire** est défini sur *Obligatoire*.
    - Si un code motif est facultatif sur les journaux d’inventaire pour l’entrepôt, sélectionnez une stratégie de motif où le champ **Type de code de motif d’inventaire** est défini sur *Facultatif*.

### <a name="assign-counting-reason-code-policies-to-products"></a>Affecter des stratégies de code motif d’inventaire aux produits

Pour affecter une stratégie de code de motif d’inventaire à un produit, procédez comme suit.

1. Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.
1. Sélectionnez un produit dans la grille.
1. Dans le volet Actions, sous l’onglet **Produit**, dans le groupe **Configuration**, cliquez sur **Stratégie de code de motif d’inventaire**. Ensuite, dans la boîte de dialogue déroulante **Attribuer une stratégie de code de motif d’inventaire**, suivez l’une des étapes suivantes :

    - Pour utiliser la configuration de stratégie pour l’entrepôt afin de déterminer si les journaux d’inventaire sont obligatoires pour le produit, n’entrez aucune valeur (ou supprimez la valeur existante).
    - Pour exiger un code motif sur les journaux d’inventaire pour le produit, sélectionnez une stratégie de motif où le champ **Type de code de motif d’inventaire** est défini sur *Obligatoire*. Ce paramètre remplace le paramètre de code motif au niveau de l’entrepôt.
    - Si un code motif est facultatif sur les journaux d’inventaire pour le produit, sélectionnez une stratégie de motif où le champ **Type de code de motif d’inventaire** est défini sur *Facultatif*. Ce paramètre remplace le paramètre de code motif au niveau de l’entrepôt.

### <a name="set-up-counting-reason-codes"></a>Paramétrer les codes motif d’inventaire

Pour paramétrer des codes de motif d’inventaire, procédez comme suit :

1. Aller à **Gestion des stocks** \> **Configurer** \> **Stock** \> **Codes de motif d’inventaire**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Définissez les champs **Code de motif d’inventaire** et **Description** pour la nouvelle ligne.
1. Pour affecter un compte de contrepartie, saisissez ou sélectionnez une valeur dans le champ **Compte de contrepartie**.

    > [!NOTE]
    > Si un compte de contrepartie est affecté à un code de motif d’inventaire, lorsque vous validez un journal d’inventaire utilise ce code de motif d’inventaire, la valeur est validée par rapport au compte de contrepartie affecté au lieu du compte de profil de validation de stock par défaut.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Paramétrage de groupes de codes motif d’inventaire

*Groupes de codes de motif d’inventaire* peut être utilisé dans le cadre des éléments de menu *Ajustement entrant* et *Ajustement sortant* dans l’application mobile Warehouse Management pour limiter la liste des codes de motif d’inventaire. (Pour plus d’informations sur les groupes de codes de motif d’inventaire, consultez la section [Configurer les éléments de menu de l’appareil mobile pour les ajustements d’entrée et de sortie](#setup-adjustment-in-out) plus loin dans cette rubrique.)

1. Aller à **Gestion des stocks** \> **Configurer** \> **Stock** \> **Groupes de codes de motif d’inventaire**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un groupe.
1. Définissez les champs **Groupe de motif d’inventaire** et **Description du groupe** pour le nouveau groupe.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans la section **Détails**, sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille. Définissez ensuite le champ **Code de motif d’inventaire** pour la nouvelle ligne. 
1. Répétez l’étape précédente pour attribuer plus de codes au besoin. Si vous devez supprimer un code du groupe, sélectionnez-le, puis sélectionnez **Supprimer** sur la barre d’outils.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Paramétrer des codes motif pour des éléments du menu d’appareil mobile

Vous pouvez configurer des codes de motif pour les types d’ajustement de stock suivants :

- Inventaire tournant
- Inventaire ponctuel
- Inventaire de seuil
- Ajustement en entrée
- Ajustement en sortie

Dans la plupart des cas, vous pouvez définir les informations suivantes pour chaque élément de menu d’appareil mobile pertinent :

- Si le code motif s’affiche pour l’utilisateur de l’appareil mobile pendant l’inventaire.
- Le code motif par défaut qui s’affiche sur un élément du menu d’appareil mobile.
- Si l’utilisateur peut modifier le code motif.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Paramétrer des éléments du menu d’appareil mobile pour un processus d’inventaire

Pour configurer un élément de menu d’appareil mobile pour un processus d’inventaire, procédez comme suit.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Options de menu d’appareil mobile**.
1. Sélectionnez l’élément de menu approprié dans le volet de liste ou créez un élément de menu.
1. Dans le volet Actions, sélectionnez **Inventaire tournant**.
1. Dans le champ **Code motif d’inventaire par défaut**, définissez le code motif par défaut à enregistrer lorsque l’élément de menu de l’appareil mobile est utilisé pour l’inventaire.
1. Dans le champ **Afficher le code motif de l’inventaire**, sélectionnez l’une des valeurs suivantes :

    - *Ligne* – Afficher le code motif après chaque écart est enregistré.
    - *Masquer* – Ne pas afficher le code motif.

1. Définissez **Modifier le code motif d’inventaire** sur *Oui* pour permettre au collaborateur de modifier le code motif lorsqu’il est affiché sur l’appareil mobile pendant l’inventaire. Réglez-le sur *Non* pour empêcher le collaborateur de modifier le code.

> [!NOTE]
> Le bouton **Inventaire tournant** peut être activé sur n’importe quel élément de menu d’appareil mobile sur lequel l’inventaire peut être effectué. Les éléments de menu comprennent les inventaires ponctuels, le travail dirigé par l’utilisateur, et le travail dirigé par le système, par exemple.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>Définir les éléments de menu de l’appareil mobile pour l’ajustement en entrée et l’Ajustement en sortie

Pour configurer un élément de menu d’appareil mobile pour un ajustement en entrée et un ajustement en sortie, procédez comme suit.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un élément de menu.
1. Définissez les champs **Nom de l’élément mobile** et **Titre** pour le nouvel élément de menu.
1. Définissez le champ **Mode** sur *Travail*.
1. Définissez l’option **Utiliser un travail existant** sur *Non*.
1. Dans le champ **Processus de création du travail**, sélectionnez *Ajustement en entrée* ou *Ajustement en sortie*.
1. Dans l’organisateur **Général**, définissez les champs suivants. (Tous ces champs sont ajoutés lorsque vous sélectionnez *Ajustement en entrée* ou *Ajustement en sortie* dans le champ **Processus de création de travail**.)

    - **Utiliser le guide de processus** – Si vous créez un processus d’*Ajustement en sortie*, assurez-vous de définir cette option sur *Oui*. Si vous créez un processus d’*Ajustement en sortie*, cette option est toujours définie sur *Oui*.
    - **Code motif d’inventaire par défaut** – Définissez le code motif par défaut à enregistrer lorsque l’élément de menu de l’appareil mobile est utilisé pour l’inventaire.
    - **Afficher le code motif de l’inventaire** – Sélectionnez l’une des valeurs suivantes :

        - *Ligne* – Afficher le code motif après chaque écart est enregistré.
        - *Masquer* – Ne pas afficher le code motif.

    - **Modifier le code motif d’inventaire** – Définissez cette option sur *Oui* pour permettre au collaborateur de modifier le code motif lorsqu’il est affiché sur l’appareil mobile pendant l’inventaire. Réglez-le sur *Non* pour empêcher le collaborateur de modifier le code.
    - **Groupe de codes de motif d’inventaire** – Sélectionnez un groupe de codes motif si vous souhaitez limiter la liste d’options présentée aux collaborateurs. Pour plus d’informations sur la configuration des groupes de codes de motif, consultez la section [Configurer des groupes de codes de motif d’inventaire](#reason-groups) plus haut dans cette rubrique. 

> [!NOTE]
> Lorsque vous affectez un groupe de codes de motif d’inventaire aux éléments de menu *Ajustement en entrée* et *Ajustement en sortie* où l’option **Utiliser le guide de processus** est définie sur *Oui*, vous pouvez obtenir une liste limitée des codes de motif d’inventaire dans le cadre du traitement dans l’application mobile Warehouse Management.
>
> L’option **Utiliser le guide de processus** peut également aider à empêcher de grandes quantités d’ajustement de se produire par erreur. (Par exemple, un collaborateur peut scanner accidentellement un code-barres d’un numéro d’article au lieu d’une valeur de quantité.) Pour configurer cette fonctionnalité, définissez l’option **Utiliser le guide de processus** sur *Oui* pour chaque élément de menu pertinent. Ensuite, allez à **Gestion d’entrepôt \> Paramétrer \> Collaborateur**, et définissez le champ **Limite de quantité d’ajustement** pour chaque magasinier concerné afin de spécifier la quantité d’ajustement maximale que le magasinier peut enregistrer.

## <a name="processing-that-uses-counting-reason-codes"></a>Traitement utilisant des codes de motif d’inventaire

Lorsque les collaborateurs utilisent l’application mobile Warehouse Management, les codes de motif sont enregistrés. À moins qu’un processus d’approbation d’inventaire n’ait été défini, les codes de motif enregistrés sont immédiatement utilisés dans le cadre de la comptabilisation du journal d’inventaire qui suit.

### <a name="cycle-count-approvals"></a>Approbations d’inventaire tournant

Avant qu’un inventaire soit approuvé, le collaborateur peut modifier le code motif associé à l’inventaire. Lorsque l’inventaire est approuvé, le code motif est entré sur les lignes du journal d’inventaire.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Modifier les codes de motif pour les approbations d’inventaire tournant

Pour modifier une approbation d’inventaire tournant, procédez comme suit.

1. Accédez à **Gestion des entrepôts** \> **Inventaire tournant** \> **Travail d’inventaire tournant en attente de révision**.
1. Sélectionnez un inventaire tournant dans la grille.
1. Dans le volet Actions, sous l’onglet **Travail**, sélectionnez **Inventaire tournant**. Ensuite, dans le champ **Code motif**, sélectionnez un nouveau code motif.

Les codes motif sont ajoutés aux lignes de journal dans les journaux d’inventaire de type *Journal d’inventaire*.

1. Accédez à **Gestion des stocks** \> **Entrées de journal** \> **Inventaire des articles** \> **Comptage**.
2. Dans les détails de ligne du journal d’inventaire, dans le champ **Code de motif d’inventaire**, sélectionnez le code de motif qui correspond à votre situation actuelle.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>Affichez les codes motif enregistrés dans l’historique d’inventaire

Pour afficher les codes motif enregistrés dans l’historique d’inventaire, procédez comme suit.

1. Accédez à **Gestion des stocks** \> **Recherches et états** \> **Historique d’inventaire**.
1. Sélectionnez un enregistrement d’inventaire d’articles dans le volet de liste.
1. Dans le champ **Code de motif d’inventaire**, affichez l’historique d’inventaire au moyen d’un code de motif.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Utiliser des codes de motif pour l’ajustement de la quantité ou l’inventaire en ligne

Pour utiliser un code motif pour un ajustement de quantité ou un inventaire en ligne, procédez comme suit.

1. Accédez à **Gestion des stocks \> Recherches et états \> Stock disponible**.
1. Sélectionnez **Ajustement de la quantité** dans le volet Actions.
1. Sélectionnez **Ajustement de la quantité**, puis, dans le champ **Code motif d’inventaire**, sélectionnez un code motif.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
