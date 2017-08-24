--- 
title: "Classer les tâches de production pour le traitement de la production"
description: "Cette procédure utilise la peinture comme exemple pour indiquer comment séquencer des ordres prévisionnels selon la priorité en matière de couleur et de taille de colis."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f37b561188cf9c6d90c25e395ba30aa979136590
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Classer les tâches de production pour le traitement de la production

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure utilise la peinture comme exemple pour indiquer comment séquencer des ordres prévisionnels selon la priorité en matière de couleur et de taille de colis. Les données fictives utilisées pour créer cette procédure correspondent à la société USPI. Cette procédure est destinée au gestionnaire de production.


## <a name="run-master-planning-for-uspi"></a>Exécuter la planification pour USPI
1. Accédez à Planification > Planification > Exécuter > Planification.
2. Dans le champ Plan général, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez Programme.  
4. Cliquez sur OK.
    * Cela démarre la planification, notamment le processus de séquence. Ce processus peut prendre quelques minutes.  

## <a name="view-planned-orders-for-the-paint-products"></a>Afficher les ordres prévisionnels pour la peinture
1. Accédez à Planification > Planification > Ordres prévisionnels.
2. Développez le récapitulatif Détails de l'article.
3. Développez le récapitulatif Détails du programme.
4. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez Programme.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Utilisez le filtre rapide pour filtrer sur le champ Numéro d'article avec une valeur de « P300 ».
    * Déverrouillez pour faire défiler vers la droite pour consulter la date de commande et la date de livraison. Notez que ces articles ont une date de commande définie sur Aujourd'hui et les dates de livraison pour les ordres prévisionnels ne sont pas séquencées après la priorité de couleur et la taille du colis, comme indiqué dans le nom de produit. Vous pouvez pointer sur un numéro d'article pour afficher le nom du produit et la priorité.  

## <a name="sequence-planned-orders-for-paint"></a>Séquencer les ordres prévisionnels pour la peinture
1. Fermez la page.
2. Accédez à Planification > Planification > Ordre prévisionnel séquencé.
3. Développez le récapitulatif Détails de l'article.
4. Développez le récapitulatif Détails du programme.
    * Remarque : Ici vous voyez que la date/l'heure de début pour les ordres prévisionnels sont séquencées selon la couleur et la taille du colis dans un intervalle de 28 jours. Ces périodes sont définies par un numéro dans le champ Campagne. L'écran Ordres prévisionnels séquencés agit comme l'écran d'ordre prévisionnel classique, et le responsable de production peut y confirmer les ordres prévisionnels.  
5. Marquez toutes les lignes.
6. Cliquez sur Accepter.
    * Cela mettra les ordres prévisionnels à jour avec l'action de séquence sélectionnée, soit Ajourner soit Avancer.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Vérifier la séquence des ordres prévisionnels
1. Fermez la page.
2. Accédez à Planification > Planification > Ordres prévisionnels.
3. Développez le récapitulatif Détails de l'article.
4. Développez le récapitulatif Détails du programme.
5. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez Programme.  
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Utilisez le filtre rapide pour filtrer sur le champ Numéro d'article avec une valeur de « P300 ».
    * Notez que les commandes sont désormais séquencées selon la priorité en matière de couleur et de taille et les ordres prévisionnels démarrent à la date de commande et de livraison au plus tôt. Validez la colonne Date de commande ou la date de début dans le volet Détails du programme.  


