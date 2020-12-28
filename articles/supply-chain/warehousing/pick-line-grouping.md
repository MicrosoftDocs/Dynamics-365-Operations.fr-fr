---
title: Regroupement des lignes de prélèvement
description: Cette rubrique fournit une vue d'ensemble du Regroupement des lignes de prélèvement.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428222"
---
# <a name="pick-line-grouping"></a>Regroupement des lignes de prélèvement

[!include [banner](../includes/banner.md)]

Dans le regroupement des lignes de prélèvement, plusieurs lignes de travail qui ont le même article et le même emplacement peuvent être combinées en un seul prélèvement présenté à l'utilisateur sur un appareil mobile. Par conséquent, les magasiniers peuvent recevoir les instructions les plus efficaces possibles, mais la séparation requise des lignes de travail dans le système est également maintenue (par exemple, pour différents conteneurs et commandes).

## <a name="set-up-pick-line-grouping"></a>Configurer le regroupement des lignes de prélèvement

### <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d'appareil mobile

1. Aller à **Gestion d'entrepôt \> Configurer \> Appareil mobile \> Options de menu d'appareil mobile** et créez une option de menu nommée **Prélèvement de ligne de groupe de vente - Dirigé par l'utilisateur**.
2. Sous **Options de menu pour l'appareil mobile**, définissez les valeur suivantes :

    - Dans le champ **Nom de l'option de menu**, entrez **Prélèvement de vente - Ligne de groupe**.
    - Dans le champ **Titre**, entrez **Prélèvement de vente - Ligne de groupe**.
    - Dans le champ **Mode**, sélectionnez **Travail**.
    - Définissez l'option **Utiliser un travail existant** sur **Oui**.

3. Dans l'organisateur **Général**, définissez les valeurs suivantes :

    - Dans le champ **Dirigé par**, sélectionnez **Dirigé par l'utilisateur**.
    - Définissez l'option **Générer un contenant** sur **Oui**.
    - Définissez l'option **Prélèvement de groupe** sur **Oui**.

4. Sur l'organisateur **Classes de travail**, procédez comme suit pour configurer les classes de travail valide pour cette option de menu d'appareil mobile :

    1. Sélectionnez **Nouveau**.
    2. Dans le champ **ID de classe de travail**, sélectionnez **Ventes** ou **Prélèvement CC**, en fonction de l'entrepôt que vous utiliserez.
    3. Dans le champ **Type d'ordre de travail**, sélectionnez **Commandes client**.

### <a name="set-up-a-mobile-device-menu"></a>Configurer un menu d'appareil mobile

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**. 
1. Ajoutez l'option de menu que vous venez de créer au menu souhaité.

### <a name="set-up-a-work-template"></a>Définir un modèle de travail

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Recherchez le modèle de travail à utiliser avec cette fonction. Pour cet exemple, sélectionnez le modèle de travail Contoso **51 Prélever pour échelonner**.
1. Dans le menu, sélectionnez **Modifier la requête**.
1. Sous l'onglet **Tri**, sélectionnez **Ajouter**, puis définissez les valeurs suivantes :

    - Dans le champ **Table**, sélectionnez **Transactions de travail temporaire**.
    - Dans le champ **Table dérivée**, sélectionnez **Transactions de travail temporaire**.
    - Dans le champ **Champ**, sélectionnez **Numéro d'article**.
    - Dans le champ **Direction de recherche**, sélectionnez **Ascendant**.

> [!NOTE]
> Pour que la fonctionnalité de regroupement des lignes de prélèvement fonctionne, les lignes de travail doivent être triées par ID article. Si les lignes qui ont les mêmes articles ne sont pas séquencées les unes après les autres, elles ne seront pas groupées.

## <a name="example"></a>Exemple

### <a name="create-picking-work"></a>Création de tâches de prélèvement

Avant de pouvoir configurer le regroupement des lignes de prélèvement, vous devez créer des travaux sortants éligibles.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
2. Sélectionnez **Nouveau** pour créer une commande client. 
3. Sélectionnez un client dans le champ **Compte client**. 
4. Dans l'organisateur **Général**, dans le champ **Entrepôt**, sélectionnez **51**. Puis sélectionnez **OK**.
5. En dessous de **Lignes de commande client**, ajoutez les six lignes suivantes :

    - **Ligne 1 :** Dans le champ **Numéro d'article**, sélectionnez **M9200**. Dans le champ **Quantité**, entrez **3**.
    - **Ligne 2 :** Dans le champ **Numéro d'article**, sélectionnez **M9201**. Dans le champ **Quantité**, entrez **3**. 
    - **Ligne 3 :** Dans le champ **Numéro d'article**, sélectionnez **M9202**. Dans le champ **Quantité**, entrez **2**. 
    - **Ligne 4 :** Dans le champ **Numéro d'article**, sélectionnez **M9200**. Dans le champ **Quantité**, entrez **1**. 
    - **Ligne 5 :** Dans le champ **Numéro d'article**, sélectionnez **M9200**. Dans le champ **Quantité**, entrez **3**.
    - **Ligne 6 :** Dans le champ **Numéro d'article**, sélectionnez **M9202**. Dans le champ **Quantité**, entrez **7**. 

    Voici un résumé des quantités totales pour chaque article :

    - **Article M9200 :** 7 chacun
    - **Article M9201 :** 3 chacun
    - **Article M9202 :** 9 chacun

6. Avant de lancer les commandes à l'entrepôt, vous devez vous assurer que les emplacements de prélèvement disposent d'un stock suffisant pour tous les articles de toutes les commandes. Revoir le paramètre **Instruction d'emplacement** pour déterminer les emplacements de prélèvement utilisés pour le prélèvement des commandes client.
7. Réservez l'inventaire et remettez-le à l'entrepôt. Un ID travail comportant six lignes est créé. Les lignes sont triées par numéro d'article.

### <a name="run-the-mobile-device-flow"></a>Exécuter le flux de l'appareil mobile

1. Sur l'appareil mobile, sélectionnez le menu qui inclut la nouvelle option de menu appareil mobile.
1. Sélectionnez l'option de menu **Prélèvement de vente - Ligne de groupe** et lancez le prélèvement.

    Après avoir sélectionné le menu et saisi l'ID travail, vous voyez l'étape de prélèvement où toutes les lignes de prélèvement pour l'article M9200 sont regroupées. Vous recevez une instruction pour choisir 7 de chaque article M9200.

1. Confirmez l'étape de prélèvement. 
1. Accédez à l'écran client du travail en cours et notez que les trois lignes de prélèvement pour l'article M9200 ont été clôturées simultanément.

    La ligne de travail 4 est présentée.

1. Confirmez l'étape de prélèvement.

    La dernière étape de prélèvement sur l'appareil mobile regroupe les deux dernières lignes de prélèvement de l'ordre de travail.

1. Terminez l'étape de prélèvement pour 9 de chaque article M9202.
1. Confirmez l'étape de placement et toute autre paire prélèvement/placement pour terminer le travail.

> [!NOTE]
> - Les lignes de travail ne peuvent être regroupées que si elles sont en séquence.
> - La fonctionnalité suivante n'est pas prise en charge :
>
>    - Articles en poids variable. S'il y a des articles en poids variable sur le travail, vous recevez un message d'erreur avant de commencer le prélèvement.
>    - Prélèvement de pièce.
>    - Lignes de travail qui ont des travaux de réapprovisionnement inachevés.
>    - Sur-prélèvement.
>    - Prélèvement partiel avec réaffectation des articles
