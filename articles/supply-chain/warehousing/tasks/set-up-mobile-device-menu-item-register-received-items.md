---
title: Paramétrer une option de menu d'appareil mobile pour enregistrer les articles reçus
description: Cette rubrique consiste à réaliser le paramétrage d'une option de menu d'appareil mobile.
author: ShylaThompson
manager: tfehr
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 146eb0822566a9bae59d486e39c8227938eb2375
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216848"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Paramétrer une option de menu d'appareil mobile pour enregistrer les articles reçus

[!include [banner](../../includes/banner.md)]

Cette rubrique consiste à réaliser le paramétrage d'une option de menu d'appareil mobile. Cette option de menu est utilisée pour l'enregistrement de la réception des articles commandés via des commandes fournisseur. 

Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF. Cette procédure est destinée au gestionnaire d'entrepôts.


## <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d'appareil mobile
1. Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom de l'option de menu**, saisissez une valeur. Il s'agit de l'identificateur unique pour cette option de menu d'appareil mobile. Par exemple, vous pouvez saisir `My PO registration`.  
4. Dans le champ **Titre**, saisissez une valeur. Il s'agit du titre qui sera affiché pour l'utilisateur sur l'appareil mobile. Par exemple, vous pouvez saisir `PO registration`.  
5. Dans le champ **Mode**, sélectionnez **Travail**. L'enregistrement des quantités disponibles reçues pour une ligne de commande fournisseur va créer le travail de déplacement des articles de la zone de réception vers le stock. Le travail n'est pas créé tant que les articles ne sont pas enregistrés. Par conséquent, laissez l'option **Utiliser un travail existant** sur **Non**.
6. Dans le champ **Processus de création du travail** de la section **Général**, sélectionnez **Réception d'article de commande fournisseur**.
    - Une ligne de commande fournisseur doit être identifiée de manière unique avant que la disponibilité puisse être enregistrée dans l'entrepôt. Dans ce scénario, l'appareil mobile va enregistrer le numéro de commande fournisseur et le numéro d'article, ce qui permettra au système d'identifier la ligne de CF. Le travail de rangement sera créé et pourra être sélectionné par un autre employé. La méthode de création de travail que vous sélectionnez détermine les champs qui deviennent disponibles dans l'onglet rapide **Général**.  
    - Si vous sélectionnez l'option **Utiliser les données par défaut**, le bouton **Données par défaut** est activé. Ici, vous pouvez sélectionner les champs qui affichent les données dont un collaborateur a généralement besoin dans son travail quotidien, de manière à ce que ces données apparaissent sur l'appareil mobile.  
    - Le paramètre de **regroupement de contenant** fonctionne en association avec le groupe de séquences affecté à l'article en cours de réception. Vous pouvez indiquer si les réceptions de plus ou moins d'une palette doivent être regroupées dans un contenant ou divisées en un contenant distinct pour chaque unité.  
    - Si vous sélectionnez l'option **Générer un contenant**, cela génère un numéro unique de contenant dépendant de la sélection de la souche de numéros.  
    - Vous pouvez sélectionner le modèle à utiliser lorsque le travail est créé. Par exemple, si vous enregistrez un article pour une commande fournisseur, le travail de rangement sera généré selon le modèle de travail. Si vous ne sélectionnez pas de modèle de travail ici, le système affectera un modèle fondé sur les critères de requête associés aux modèles.  
    - Si des codes disposition sont affichés sur l'appareil mobile, les employés peuvent évaluer le statut ou la qualité des articles et sélectionner le code approprié. Les règles du code disposition déterminent si les articles sont disponibles à d'autres processus d'entrepôt. Les règles déterminent également quelle directive d'emplacement est utilisée pour le travail créé.   
    - Si vous sélectionnez l'option **Codes disposition de lot**, les employés peuvent évaluer le statut ou la qualité d'un lot et sélectionner le code de disposition approprié. Les règles définies avec le code disposition de lot déterminent si le lot est disponible à d'autres processus d'entrepôt.  
    - Si vous sélectionnez l'option **Imprimer les étiquettes**, une étiquette de contenant sera imprimée automatiquement lorsque des articles seront reçus.  
7. Sélectionnez **Enregistrer**.
8. Fermez la page.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Ajouter l'option de menu à un menu d'appareil mobile
1. Dans le volet de navigation, allez dans **Modules > Gestion des entrepôts > Configuration > Appareil mobile > menu d'appareil mobile**.
2. Utiliser le **filtre rapide** pour filtrer sur le champ **Nom** avec une valeur de `inbound`.
3. Sélectionnez **Modifier**.
4. Dans l'arborescence des articles et les menus disponibles, sélectionner l'option de menu créée précédemment.
5. Sélectionnez la flèche qui pointe vers la droite.
6. Sélectionnez **Enregistrer**.
7. Fermez la page.

