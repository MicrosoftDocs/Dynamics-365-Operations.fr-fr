--- 
title: "Paramétrer une option de menu d'appareil mobile pour enregistrer les articles reçus"
description: "Cette tâche consiste à réaliser le paramétrage d'une option de menu d'appareil mobile."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 7b5d757361c1163bbd0300abd3da4e0a2dd6b0e0
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Paramétrer une option de menu d'appareil mobile pour enregistrer les articles reçus

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche consiste à réaliser le paramétrage d'une option de menu d'appareil mobile. Cette option de menu est utilisée pour l'enregistrement de la réception des articles commandés via des commandes fournisseur. 

Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF. Cette procédure est destinée au gestionnaire d'entrepôts.


## <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d'appareil mobile
1. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.
2. Cliquez sur Nouveau.
3. Saisissez une valeur dans le champ Nom de l'option de menu.
    * Il s'agit de l'identificateur unique pour cette option de menu d'appareil mobile. Par exemple, vous pouvez taper « Mon enregistrement de CF ».  
4. Tapez une valeur dans le champ Titre.
    * Il s'agit du titre qui sera affiché pour l'utilisateur sur l'appareil mobile. Par exemple, vous pouvez taper « Enregistrement de CF ».  
5. Dans le champ Mode, Sélectionnez « Travail ».
    * L'enregistrement des quantités disponibles reçues pour une ligne de commande fournisseur va créer le travail de déplacement des articles de la zone de réception vers le stock. Le travail n'est pas créé tant que les articles ne sont pas enregistrés.  Par conséquent, laissez l'option Utiliser un travail existant sur Non.  
6. Développez ou réduisez la section Général.
7. Dans le champ Processus de création du travail, sélectionnez « Réception d'article de commande fournisseur ».
    * Une ligne de commande fournisseur doit être identifiée de manière unique avant que la disponibilité puisse être enregistrée dans l'entrepôt. Dans ce scénario, l'appareil mobile va enregistrer le numéro de commande fournisseur et le numéro d'article, ce qui permettra au système d'identifier la ligne de CF. Le travail de rangement sera créé et pourra être sélectionné par un autre employé.    La méthode de création de travail que vous sélectionnez détermine les champs qui deviennent disponibles dans l'onglet rapide Général.  
    * Si vous sélectionnez l'option Utiliser les données par défaut, le bouton Données par défaut est activé. Ici, vous pouvez sélectionner les champs qui affichent les données dont un collaborateur a généralement besoin dans son travail quotidien, de manière à ce que ces données apparaissent sur l'appareil mobile.  
    * Le paramètre de regroupement de contenant fonctionne en association avec le groupe de séquences affecté à l'article en cours de réception. Vous pouvez indiquer si les réceptions de plus ou moins d'une palette doivent être regroupées dans un contenant ou divisées en un contenant distinct pour chaque unité.  
    * Si vous sélectionnez l'option Générer un contenant, cela génère un numéro unique de contenant dépendant de la sélection de la souche de numéros.   
    * Vous pouvez sélectionner le modèle à utiliser lorsque le travail est créé. Par exemple, si vous enregistrez un article pour une commande fournisseur, le travail de rangement sera généré selon le modèle de travail. Si vous ne sélectionnez pas de modèle de travail ici, le système affectera un modèle fondé sur les critères de requête associés aux modèles.  
    * Si des codes disposition sont affichés sur l'appareil mobile, les employés peuvent évaluer le statut ou la qualité des articles et sélectionner le code approprié. Les règles du code disposition déterminent si les articles sont disponibles à d'autres processus d'entrepôt. Les règles déterminent également quelle directive d'emplacement est utilisée pour le travail créé.   
    * Si vous sélectionnez l'option Codes disposition de lot, les employés peuvent évaluer le statut ou la qualité d'un lot et sélectionner le code de disposition approprié.  Les règles définies avec le code disposition de lot déterminent si le lot est disponible à d'autres processus d'entrepôt.  
    * Si vous sélectionnez l'option Imprimer les étiquettes, une étiquette de contenant sera imprimée automatiquement lorsque des articles seront reçus.  
8. Cliquez sur Enregistrer.
9. Fermez la page.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Ajouter l'option de menu à un menu d'appareil mobile
1. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile.
2. Utilisez le filtre rapide pour filtrer sur le champ Nom avec une valeur de « Entrant ».
3. Cliquez sur Modifier.
4. Dans l'arborescence, sélectionnez « Dans l'arborescence des articles et le menu disponibles, sélectionner l'option de menu créée précédemment. ».
    * Sélectionnez l'option de menu que vous avez créée précédemment.  
5. Cliquez sur la flèche qui pointe vers la droite.
6. Cliquez sur Enregistrer.
7. Fermez la page.


