---
title: Créer et mettre à jour une stratégie de retour et de remboursement pour un canal
description: Cet article explique comment configurer une stratégie de retour et de remboursement pour un canal.
author: ShalabhjainMSFT
ms.date: 07/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.custom: ''
ms.search.industry: Retail
ms.openlocfilehash: d01ad490301dd2f4103b8bd3f702db12b93a45a8
ms.sourcegitcommit: bd7b1ffe90b25eb4c68d6aaebd063bf33e09d9cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2022
ms.locfileid: "9627494"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Créer et mettre à jour une stratégie de retour et de remboursement pour un canal

[!include [banner](includes/banner.md)]

La stratégie de retour de canal dans Dynamics 365 Commerce permet aux détaillants de définir des mesures d’exécution sur lesquelles les offres de paiement peuvent être autorisées pour le traitement d’un retour sur un point de vente (PDV).  

Cet article donne les étapes permettant de configurer une stratégie de retour et de remboursement pour un canal.

La portée de la politique se limite actuellement à la définition des offres de paiement qui peuvent être autorisées pour un canal. La liste « autorisée » est basée sur les modes de paiement utilisés pour effectuer l’achat. Par exemple :

- Si un achat a été effectué à l’aide d’une carte-cadeau, la stratégie du magasin consiste à traiter les remboursements uniquement sur une nouvelle carte-cadeau ou à accorder un crédit au magasin. 
- Si une vente a est effectuée en espèces, les options de remboursement autorisées sont les espèces, les cartes-cadeaux et le compte client, mais pas les cartes de crédit. 

## <a name="enable-return-policy"></a>Activer la stratégie de retour

Par défaut, cette fonctionnalité est activée. Vous la trouverez dans l’espace de travail **Gestion des fonctionnalités** en recherchant **Activer les stratégies de retour du canal** dans la liste des noms de fonctionnalités.


## <a name="configure-return-policy"></a>Configurer la stratégie de retour

Suivez ces étapes pour configurer une politique de retour pour un magasin de détail ou un canal de vente en ligne.

1. Accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Retours** \> **Politique de retour de canal**.

1. Sélectionnez **Nouveau** pour créer un modèle de stratégie de retour. Pour utiliser un modèle existant, sélectionnez le modèle dans le volet de gauche. Pour les nouveaux modèles, ajoutez un nom et une description qui vous aideront à identifier la stratégie lorsqu’elle est appliquée au canal.

   ![Ajouter une nouvelle stratégie de retour.](media/Return-policy-page1.png)
     
   
1. Dans la section **Modes de paiement des remboursements autorisés**, définissez les offres de paiement de retour **autorisés** pour chaque mode de paiement.
   ![Définir les modes de paiement autorisés par type de paiement.](media/Return-policy-page2.png)
   
    > [!IMPORTANT]
    > - Les modes de paiement sont dérivés des modes de paiement définis pour l’organisation.
    > - L’ajout d’un type d’offre de retour autorisé pour chaque mode de paiement répertorié garantit que les retours peuvent être effectués pour le type d’offre de retour autorisé.
    
1. Associez le modèle de stratégie de retour avec les magasins où il est utilisé. Sélectionnez **Ajouter** dans l’onglet **Canaux de vente au détail** et associez les canaux disponibles. 

    - Dans la boîte de dialogue **Choisir des nœuds d’organisation**, sélectionnez les magasins, les régions et les organisations auxquels le modèle doit être associé.
    - Un seul modèle de stratégie de retour peut être associé avec chaque magasin.
    - Utilisez les boutons de flèche pour sélectionner les magasins, les régions ou les organisations.
    - La date d’entrée en vigueur de la stratégie est la date à laquelle les stratégies sont appliquées aux canaux et les travaux de canal sont exécutés. 

    ![Boîte de dialogue Choisir des nœuds d’organisation.](media/Return-policy-page3.png)

1. Dans la page **Programme de distribution**, exécutez la tâche **1070** pour mettre la stratégie de retour de canal à la disposition du PDV.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Aperçu de la stratégie de retour du canal dans le PDV

Suivez les étapes de l’un des exemples suivants pour afficher les types d’offre de retour autorisés dans le PDV.

1. Connectez-vous au point de vente en tant que caissier ou gestionnaire.
1. Sous **Équipes et tiroirs-caisses**, sélectionnez **Afficher le journal**.
1. Sélectionnez la transaction qui fait partie du retour. 
1. Sélectionnez les articles à rembourser et choisissez le mode de paiement.  
    - Si l’offre de paiement sélectionnée figure dans la liste autorisée des types d’offre de retour, le caissier peut terminer la transaction.
    - Si l’offre de paiement sélectionnée n’est pas autorisée, un message d’erreur s’affiche.
    - Sélectionnez **Montant dû** pour afficher une liste de tous les types d’offre de retour autorisés.

- ou -

1. Connectez-vous au point de vente en tant que caissier ou gestionnaire.
1. Sélectionnez **Transaction de retour** et saisissez l’ID du ticket de caisse à l’aide d’un scanner de codes-barres ou manuellement. 
1. Sélectionnez la transaction qui fait partie du retour. 
1. Sélectionnez les articles à rembourser et choisissez le mode de paiement.  
    - Si l’offre de paiement sélectionnée figure dans la liste autorisée des types d’offre de retour, le caissier peut terminer la transaction.
    - Si l’offre de paiement sélectionnée n’est pas autorisée, un message d’erreur s’affiche.
    - Sélectionnez **Montant dû** pour afficher une liste de tous les types d’offre de retour autorisés.

![Type de remboursement non autorisé.](media/Return-policy-page6.png)



![Types de remboursement autorisés.](media/Return-policy-page5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
