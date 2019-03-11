---
title: Vue d'ensemble des paiements fournisseurs
description: Ce guide de tâche décrit diverses méthodes permettent de créer des paiements fournisseurs, notamment l'utilisation d'une proposition de paiement ou la saisie manuelle d'un paiement unique.
author: kweekley
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d892366a11edcd92f34f37b3e855631820ba816b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "359955"
---
# <a name="vendor-payment-overview"></a>Vue d'ensemble des paiements fournisseurs

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche décrit diverses méthodes permettent de créer des paiements fournisseurs, notamment l'utilisation d'une proposition de paiement ou la saisie manuelle d'un paiement unique. La société fictive USMF sert d'exemple dans cette procédure.

1. Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Sélectionnez le journal des paiements dans lequel enregistrer les paiements fournisseurs. 
4. Sélectionnez le journal ou entrez-le manuellement.
5. Cliquez sur Lignes.
6. Cliquez sur Proposition de paiement.
7. Cliquez sur Créer une proposition de paiement.
    * La proposition de paiement est une requête utilisée pour sélectionner des factures pour le paiement. Vous pouvez modifier la liste des factures à payer avant de créer ou de générer des paiements fournisseurs.  
8. Sélectionnez les factures du paiement par date d'échéance, escompte de règlement ou les deux. 
9. Entrez la date (pour la comparer à la date d'échéance) ou l'escompte de règlement. 
10. Facultatif : entrez une date de paiement utilisée pour tous les paiements.
    * La date entrée ici est la date de paiement pour tous les paiements créés, indépendamment de la date d'échéance ou d'escompte de règlement.  
11. Facultatif : entrez une date de paiement minimale qui peut être utilisée comme date de paiement.
    * La date de paiement minimale est la date la plus proche utilisée lorsque vous créez des paiements. Par exemple, si une facture a une date d'échéance après la date de paiement minimale, la date d'échéance deviendra la date de paiement au lieu de la date de paiement minimale afin de payer la facture le dernier jour possible.  
12. Entrez des restrictions de requête supplémentaires dans Enregistrements à inclure.
    * Le filtre est souvent utilisé pour limiter les factures sélectionnées pour le paiement par groupe de fournisseurs ou par mode de paiement. Par exemple, vous pouvez ajouter un filtre uniquement aux factures de salaire par chèque dans ce cycle de paie.  
13. Entrez des restrictions de requête ou des valeurs de paiement par défaut supplémentaires. 
    * Les paramètres supplémentaires peuvent être utilisés pour définir la devise de paiement ou pour activer les paiements centralisés pour ce cycle de paie.  
14. Cliquez sur OK.
    * Après avoir cliqué sur OK, les résultats de la requête s'affichent. Si vous ne souhaitez pas afficher un aperçu de la liste des factures sélectionnées à payer, vous pouvez revenir à l'onglet Paramètre et modifier le paramètre Création de paiements sans Aperçu de facture = Oui.  
15. Choisissez le bouton Afficher la vue d'ensemble du paiement pour afficher les paiements qui seront créés pour le fournisseur sur la facture sélectionnée.
16. Choisissez le bouton Masquer la vue d'ensemble du paiement pour masquer les paiements. 
17. Cliquez sur Créer des paiements.
    * Avant de choisir Créer des paiements, vous pouvez cliquer avec le bouton droit dans la grille et exporter la liste des factures vers Excel. Le bouton Créer des paiements crée les paiements fournisseurs dans le journal des paiements.  
18. Numérisez les paiements et vérifiez que le mode de paiement est défini pour tous les paiements. 
    * Si vous générez les paiements (impression d'un chèque ou création d'un paiement électronique), le mode de paiement doit être défini. Le mode de paiement prendra également par défaut le compte bancaire à partir duquel le paiement est effectué.  
19. Cliquez sur Nouveau pour créer un paiement unique.
    * Un paiement unique peut être ajouté à un journal des paiements à tout moment avant la validation. Cela est effectué en cliquant sur le bouton Nouveau et en ajoutant les informations de paiement manuellement, plutôt que via la proposition de paiement.  
20. Sélectionnez le fournisseur auquel le paiement sera effectué.
21. Si une facture doit être payée, sélectionnez Régler les transactions pour sélectionner la facture pour le paiement.
    * S'il s'agit d'un acompte, cette étape est facultative. Vous pouvez créer le paiement sans sélectionner de facture.  
22. Marquez toutes les factures qui seront payées.
    * Si vous utilisez Régler les transactions pour sélectionner des factures pour le paiement, le montant du paiement est automatiquement calculé en fonction des factures marquées pour le paiement et du montant que vous entrez dans le montant à régler.  
23. Cliquez sur OK.
24. Pour supprimer un paiement, marquez la ligne.
25. Cliquez sur Supprimer.
    * La suppression d'un paiement ne supprimera que le paiement. Toutes les factures marquées pour le paiement resteront disponibles pour être payées lors d'un autre paiement.  
26. Cliquez sur Oui.
27. Choisissez Générer le paiement pour imprimer des chèques ou pour créer le fichier de paiement électronique.
28. Sélectionnez le mode de paiement que vous souhaitez générer.
    * Le journal des paiements contient des paiements à la fois pour les chèques et les paiements électroniques, mais vous ne pouvez générer qu'un type de paiement à la fois.  
29. Sélectionnez le compte bancaire à partir duquel générer des paiements.
30. Cliquez sur OK.
    * Les paiements sont générés uniquement pour ceux qui correspondent au mode de paiement et au compte bancaire sélectionnés.  
31. Si vous générez des chèques, choisissez Document pour vérifier la bonne destination d'impression pour les chèques.
32. Cliquez sur OK.
33. Cliquez sur OK pour générer les paiements.
34. Cliquez sur Valider si tous les paiements sont approuvés et générés. 

