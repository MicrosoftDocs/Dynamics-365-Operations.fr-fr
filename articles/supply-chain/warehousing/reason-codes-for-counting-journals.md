---
title: Codes motif d'inventaire de stock
description: Cette rubrique décrit comment paramétrer et appliquer des codes motif pour les tâches d'inventaire.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 1025dd00db2e8b87e3c76e3047a7cf470a2d6641
ms.sourcegitcommit: 8cbaeb6443ce47a4c4bc02b5e1a1212eb0056b38
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829799"
---
# <a name="reason-codes-for-inventory-counting"></a>Codes motif d'inventaire de stock

[!include [banner](../includes/banner.md)]

Les codes motif permettent d'analyser les résultats d'un processus d'inventaire et les écarts qui surviennent lors de ce processus. Vous pouvez indiquer le motif du comptage, tel qu'une palette brisée ou un ajustement du stock basé sur des exemples de stock.

## <a name="recommendation"></a>Recommandation

Avant de paramétrer le système, nous vous recommandons de définir une stratégie pour l'utilisation des codes motif. Par exemple, essayez de répondre aux questions suivantes :

- Les codes motif doivent-ils être obligatoires dans les entrepôts ?
- Les codes motif doivent-ils être obligatoires ou facultatifs pour certains articles ?
- De combien de codes motif avez-vous besoin ?
- Comment les utilisateurs des scanneurs de code-barres doivent-ils utiliser les codes motif ? Les codes motif doivent-ils être présélectionnés, obligatoires, ou non modifiables ?
- Les magasiniers ont-ils besoin de différents comportements de code motif sur les scanneurs mobiles ? Si la réponse est oui, vous pouvez créer plusieurs éléments de menu et les affecter à différentes personnes.

## <a name="where-reason-codes-apply"></a>Lorsque des codes motif s'appliquent

Vous pouvez créer plusieurs stratégies de code motif, et chaque stratégie de code motif peut comporter deux stratégies de code motif d'inventaire. Les stratégies de code motif d'inventaire peuvent être utilisées au niveau de l'entrepôt ou au niveau de l'article.

## <a name="set-up-reason-code-policies"></a>Paramétrer des stratégies de codes motif

1. Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Stock** \> **Stratégies de code motif d'inventaire**, puis créez une stratégie de code motif.
2. Dans le champ **Type de code motif d'inventaire**, sélectionnez **Obligatoire** ou **Facultatif** pour spécifier si la sélection d'un code motif doit être une action facultative ou obligatoire dans l'un des journaux d'inventaire suivants :

    - Inventaire tournant (appareil mobile)
    - Inventaire ponctuel (appareil mobile)
    - Inventaire de seuil (appareil mobile)
    - Ajustement en entrée (appareil mobile)
    - Ajustement en sortie (appareil mobile)
    - Journal d'inventaire (Rich Client)

Vous pouvez également paramétrer des codes motif pour des entrepôts et des produits individuels. Le paramétrage de codes motif pour les produits peut ignorer le paramétrage des entrepôts.

## <a name="mandatory-reason-codes"></a>Codes motif obligatoires

Si le paramètre **Obligatoire** est défini dans la configuration des codes motif pour les entrepôts et les articles, le journal d'inventaire ne peut pas être rempli et clôturé tant qu'un code motif n'est pas fourni.

### <a name="set-up-reason-codes-for-warehouses"></a>Définir les codes motif pour des entrepôts

1. Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Décomposition du stock** \> **Entrepôts**.
2. Dans l'onglet **Entrepôt**, dans le champ **Stratégie de code motif d'inventaire**, sélectionnez l'une des options suivantes :

    - **Vide** – Le paramètre défini pour l'article est utilisé pour déterminer si les journaux d'inventaire sont obligatoires pour le produit.
    - **Obligatoire** – Un code motif est toujours requis dans les journaux d'inventaire pour l'entrepôt.
    - **Facultatif** – Un code motif n'est pas requis dans les journaux d'inventaire pour l'entrepôt.

### <a name="set-up-reason-codes-for-products"></a>Définir les codes motif pour des produits

1. Sélectionnez **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.
2. Dans l'onglet **Produit**, sélectionnez **Stratégie de code motif d'inventaire**, puis l'une des options suivantes :

    - **Vide** – Le paramètre défini pour l'entrepôt est utilisé pour déterminer si les journaux d'inventaire sont obligatoires pour le produit.
    - **Obligatoire** – Un code motif est toujours requis dans les journaux d'inventaire pour le produit. Ce paramètre remplace le paramètre de code motif au niveau de l'entrepôt.
    - **Facultatif** – Un code motif n'est pas requis dans les journaux d'inventaire pour le produit. Ce paramètre remplace le paramètre de code motif au niveau de l'entrepôt.

### <a name="use-reason-codes-in-counting-journals"></a>Utiliser des codes motif dans les journaux d'inventaire

Dans un journal d'inventaire, vous pouvez ajouter des codes motif pour les types suivants :

- Inventaire tournant
- Inventaire ponctuel
- Inventaire de seuil
- Ajustement en entrée
- Ajustement en sortie

Les codes motif sont ajoutés aux lignes de journal dans les journaux d'inventaire de type **Journal d'inventaire**.

1. Sélectionnez **Gestion des stocks** \> **Entrées de journal** \> **Inventaire des articles** \> **Inventaire**.
2. Dans les détails de ligne du journal d'inventaire, dans le champ **Code motif d'inventaire**, sélectionnez une option.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>Affichez l'historique d'inventaire tel qu'il est enregistré par codes motif

- Sélectionnez **Gestion des stocks** \> **Recherches et états** \> **Historique d'inventaire**, puis, dans le champ **Code motif d'inventaire**, affichez l'historique d'inventaire enregistré via un code motif.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Utiliser un code motif pour un ajustement de quantité

1. Dans la page **Stock disponible**, sélectionnez **Ajuster la quantité**. Vous pouvez ouvrir la page **Stock disponible** de plusieurs façons. Par exemple, sélectionnez **Gestion des stocks** \> **Recherches et états** \> **Stock disponible**.
2. Sélectionnez **Ajuster la quantité**, puis, dans le champ **Code motif d'inventaire**, sélectionnez un code motif.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Configurer des codes motif pour des éléments du menu d'appareil mobile

Vous pouvez configurer des codes motif pour tous les types d'inventaire sur un élément du menu d'appareil mobile. La configuration de l'élément de menu d'appareil mobile inclut les informations suivantes :

- Si le code motif s'affiche pour l'utilisateur de l'appareil mobile pendant l'inventaire.
- Le code motif par défaut qui s'affiche sur un élément du menu d'appareil mobile.
- Si l'utilisateur peut modifier le code motif.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Paramétrer des codes motif sur un appareil mobile

1. Sélectionnez **Gestion des entrepôts** \> **Configuration** \> **Appareil mobile** \> **Options de menu d'appareil mobile**.
2. Dans l'onglet **Inventaire tournant**, sélectionnez **Inventaire tournant**.
3. Dans le champ **Code motif d'inventaire par défaut**, définissez le code motif par défaut à enregistrer lorsque l'inventaire est effectué à l'aide de l'élément de menu de l'appareil mobile.
4. Dans le champ **Afficher le code motif d'inventaire**, sélectionnez **Ligne** pour afficher le code motif après chaque écart enregistré. Sinon, sélectionnez **Masquer** si le code motif ne doit pas être affiché.
5. Définissez l'option **Modifier le code motif d'inventaire** sur **Oui** ou **Non**. Si vous définissez cette option sur **Oui**, le collaborateur peut modifier le code motif lorsqu'il est affiché sur l'appareil mobile pendant l'inventaire.

> [!NOTE]
> Le bouton **Inventaire tournant** peut être activé sur n'importe quel élément de menu d'appareil mobile sur lequel l'inventaire peut être effectué. Les éléments de menu comprennent les inventaires ponctuels, le travail dirigé par l'utilisateur, et le travail dirigé par le système.

## <a name="cycle-count-approvals"></a>Approbations d'inventaire tournant

Avant qu'un inventaire soit approuvé, l'utilisateur peut modifier le code motif associé à l'inventaire. Lorsque l'inventaire est approuvé, le code motif est entré sur les lignes du journal d'inventaire.

### <a name="modify-cycle-count-approvals"></a>Modifier les approbations d'inventaire tournant

1. Sélectionnez **Gestion des entrepôts** \> **Inventaire tournant** \> **Travail d'inventaire tournant en attente de révision**.
2. Sélectionnez **Inventaire tournant**, puis, dans le champ **Code motif**, sélectionnez un nouveau code motif.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>Modifier l'élément de menu de l'appareil mobile pour l'Ajustement en entrée et l'Ajustement en sortie

1. Sélectionnez **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Options de menu d'appareil mobile**, puis **Ajustement en entrée et Ajustement en sortie**.
2. Définissez l'option **Utiliser un travail existant** sur **Non**.
3. Dans le champ **Processus de création du travail**, sélectionnez **Ajustement en entrée**.

Les champs suivants sont ajoutés aux options du menu de l'appareil mobile si **Ajustement en entrée** ou **Ajustement en sortie** est sélectionné lors du processus de création du travail :

- Code motif d'inventaire par défaut
- Afficher le code motif d'inventaire
- Modifier le code motif d'inventaire
