--- 
title: Entrer des contrats de vente
description: "Cette procédure vous explique comment créer un contrat de vente qui engage l'un de vos clients à acheter un produit pour un montant convenu sur une période définie en échange de remises spéciales."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8c11164f7edb8e05b93f3c58b9707c0bf2482228
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="enter-sales-agreements"></a>Entrer des contrats de vente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous explique comment créer un contrat de vente qui engage l'un de vos clients à acheter un produit pour un

montant convenu sur une période définie en échange de remises spéciales. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-sales-agreement-header"></a>Paramétrer un en-tête de contrat de vente
1. Accédez à Ventes et marketing > Contrats de vente > Contrats de vente.
2. Cliquez sur Nouveau.
3. Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Classification du contrat de vente, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Développez la section Général.
9. Dans le champ Engagement par défaut, sélectionnez « Engagement à la valeur du produit ».
    * Un type d'engagement est un critère obligatoire que vous devez affecter à l'accord afin de définir la manière dont l'objectif du contrat est atteint. Les quatre types prédéfinie vous permettent de paramétrer la cible de l'engagement du client, exprimée comme une quantité ou une valeur. Le type d'engagement à la quantité peut uniquement être appliqué à un produit spécifique, mais les types basés sur la valeur s'appliquent aux ventes des produits spécifiques et non spécifiques.  
10. Dans le champ Date d'expiration, définissez la date à une date future à laquelle vous souhaitez que l'accord arrive à expiration.
11. Cliquez sur OK.

## <a name="set-up-product-value-commitment-lines"></a>Paramétrer des lignes d'engagement à la valeur du produit
1. Cliquez sur Ajouter une ligne.
2. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Le type d'engagement que vous avez choisi pour l'accord affecte le type d'informations que vous pouvez spécifier pour les lignes d'accord. Par exemple, pour un accord basé sur des valeurs vous devez spécifier le montant net total (dans la devise acceptée) pour lequel le client s'engage à vous acheter des marchandises. Dans cet exemple, les champs Quantité et Unité de la ligne sont indisponibles car vous êtes en train de créer un accord pour que le client achète une valeur spécifique d'un produit.   
5. Dans le champ Montant net, spécifiez le montant en devises pour lequel le client s'est engagé en matière d'achat.
6. Dans le champ Pourcentage de remise, entrez une valeur en pourcentage qui s'appliquera aux lignes de commande du client liées à cet accord.
7. Développez la section Détails de ligne.
8. Dans le champ Le max. est appliqué, sélectionnez Oui.
    * Sélectionnez l'option « Le max. est appliqué » signifie que le montant total de toutes les lignes de commande client qui utilisent les prix spéciaux, les remises et/ou les conditions de paiement de l'engagement ne doit pas dépasser le montant spécifié dans l'engagement.  
    * Les montants de lancement minimal et maximal spécifient une plage de valeurs qui doivent être vendues sur chaque commande client qui utilise l'accord sélectionné.   
9. Développez la section En-tête de contrat de vente.
    * À moins que le statut de l'accord soit défini à Effectif, les commandes client ne peuvent pas être associées à l'accord et ne peuvent donc pas contribuer à l'accomplissement de cet accord. À ce stade, vous pouvez modifier le statut manuellement. Toutefois, le statut serait normalement modifié lorsque vous confirmez l'accord pour le client.  
10. Dans le volet Actions, cliquez sur Contrats de vente.
11. Cliquez sur Confirmation.
    * Assurez-vous que l'option Marquer l'accord comme effectif est définie à Oui.  
12. Dans le champ Imprimer un état, sélectionnez Oui.
13. Cliquez sur OK.
14. Fermez la page.
    * L'accord est désormais effectif et vous pouvez commencer à lier les commandes du client à l'accord, à déduire de la cible de l'engagement.  


