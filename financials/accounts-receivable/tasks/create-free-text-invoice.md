--- 
title: "Créer une facture financière"
description: "Ce guide de tâche illustre la création d'une facture financière."
author: mikefalkner
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a9f9a780868926009f30cee6aa634c53ca870b3f
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-free-text-invoice"></a>Créer une facture financière

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche illustre la création d'une facture financière. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité client > Factures > Toutes factures financières.
2. Cliquez sur Nouveau.
3. Sélectionnez une valeur dans le champ Compte client.
    * Le compte de facturation sera par défaut identique à celui utilisé pour le compte client.   
    * Le statut comptable commence par En cours si la facture n'est pas validée.   
    * Le numéro de facture sera affecté lors de la validation de la facture.  
    * Si vous utilisez des mandats SEPA, le mandat de débit direct sera automatiquement complété avec un mandat lorsque vous sélectionnez le compte client.  
4. Dans le champ Description, entrez une valeur.
5. Spécifiez un numéro de compte sans dimensions dans le champ Compte principal.
    * Vous pouvez également entrer un ou plusieurs caractères pour le compte principal et utiliser la recherche pour trouver votre compte. Vous entrerez des dimensions ultérieurement dans ce guide.  
6. Développez le raccourci Détails de ligne afin de pouvoir ajouter des dimensions à votre compte principal.
7. Cliquez sur l'onglet Ligne de dimension financière.
    * Les dimensions concernent la ligne sélectionnée uniquement.    
    * Le contenu du groupe de taxe provient du client. Si le client n'a pas de groupe de taxe, celui du compte principal est utilisé.  
    * Le contenu du groupe de taxe des articles est rempli à partir du compte principal. Si le compte principal n'a pas de groupe de taxe d'article, le groupe de taxe d'article des paramètres de taxe de comptabilité est utilisé.    
8. Dans le champ Quantité, entrer un numéro.
    * La quantité est facultative.  
9. Entrez un nombre dans le champ Prix unitaire.
    * Le prix unitaire est facultatif.  
    * Le montant est calculé comme suit : quantité multipliée par prix unitaire. Toutefois, vous pouvez remplacer ce calcul et entrer un montant.  
10. Cliquez sur Taxe pour afficher les taxes calculées pour votre facture.
    * Vous pouvez afficher les montants de taxe sur cette page ou remplacer les montants sous l'onglet Ajustement.  
11. Cliquez sur OK.
12. Cliquez sur Frais pour ajouter des frais à votre facture. 
13. Tapez une valeur dans le champ Codes frais.
14. Entrez un nombre dans le champ Valeur des frais.
15. Fermez la page.
16. Cliquez sur Totaux pour afficher les totaux et les détails de la facture de synthèse.
17. Cliquez sur Fermer.
18. Cliquez sur Valider pour valider la facture. Vous pourrez annuler avant de valider.
    * Pour modifier l'échéance d'impression de la facture : sélectionnez Actuel pour imprimer chaque facture dès qu'elle est mise à jour ou Après pour imprimer toutes les factures une fois qu'elles ont été mises à jour.  
    * Si vous souhaitez modifier la manière dont la limite de crédit du client est activée avant la validation, modifiez le type de limite de crédit.  
    * Pour imprimer la facture, sélectionnez Oui.  
    * Pour valider la facture, sélectionnez Oui. Vous pouvez imprimer la facture sans la valider.  
19. Cliquez sur OK.


