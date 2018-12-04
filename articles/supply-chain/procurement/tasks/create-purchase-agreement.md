--- 
title: "Créer un contrat d'achat"
description: "Cette procédure vous guide via la création d'un contrat d'achat."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0d0cc6508071bea3f622bc21f06aa55d2b757b6f
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-purchase-agreement"></a>Créer un contrat d'achat

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide via la création d'un contrat d'achat. Cela est généralement effectué par un gestionnaire des achats. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Vous devez avoir configuré des classifications de contrat d'achat avant de commencer. Une fois que vous avez créé un accord, vous pouvez l'utiliser lorsque vous créez une commande fournisseur. Cela copiera les conditions du contrat d'achat dans l'en-tête et sur toutes les lignes de la commande qui sont affectées par l'accord.


## <a name="create-a-new-purchase-agreement"></a>Créer un contrat d'achat
1. Accédez à Approvisionnements > Contrats d'achat > Contrats d'achat.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Classifications des contrats d'achat, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Développez la section Général.
10. Dans le champ Date d'expiration, entrez une date.
    * Cette date d'expiration est la valeur par défaut pour toutes les lignes d'engagement et détermine la durée pendant laquelle chaque engagement spécifique est valide.  
11. Dans le champ Titre du document, entrez un nom pour votre contrat d'achat.
    * Laissez le champ Engagement par défaut configuré sur Engagement à la quantité de produits (ou modifiez-le s'il n'est pas défini ainsi).  
    * La valeur d'engagement par défaut détermine les options dans les lignes d'accord. Si vous avez besoin d'un type d'engagement lorsque vous créez des lignes d'accord, vous devez modifier l'engagement par défaut sous l'en-tête.  Il y a 4 types d'engagements : Engagement de quantité de produits (pour une quantité spécifique d'un produit) ; Engagement de valeur de produit (pour un montant en devise spécifique d'un produit) ; Engagement de valeur de catégorie de produit (pour un montant en devise spécifique dans une catégorie d'approvisionnement, avec un montant qui peut être celui d'un article du catalogue ou celui d'un article ne faisant pas partie du catalogue) ; Engagement de valeur (pour un montant en devise spécifique qui peut être atteint par tout produit ou par n'importe quelle catégorie d'approvisionnement).  
12. Cliquez sur OK.

## <a name="add-a-commitment"></a>Ajouter un engagement
1. Cliquez sur Ajouter une ligne.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez le produit auquel vous souhaitez ajouter un engagement.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Quantité, entrer un numéro.
    * Il s'agit de la quantité totale que vous avez acceptée d'acheter auprès de votre fournisseur.  
7. Entrez un nombre dans le champ Prix unitaire.
8. Développez la section Détails de ligne.
9. Définissez l'option Le max. est appliqué sur Oui.
    * L'option Le max. est appliqué limite l'utilisation de l'engagement. Vous pouvez acheter jusqu'à la quantité spécifiée dans le champ Quantité pour la ligne.  
10. Réduisez la section Détails de ligne.

## <a name="add-header-conditions"></a>Ajouter des conditions d'en-tête
1. Dans le volet Actions, cliquez sur Options.
2. Cliquez sur Changer de vue.
3. Cliquez sur Vue de l'en-tête.
4. Développez la section Conditions.
5. Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les conditions de paiement du compte fournisseur sont indiquées ici par défaut.       
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Mode de livraison, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Dans le champ Conditions de livraison, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="confirm-and-activate-the-agreement"></a>Confirmer et activer le contrat de vente
1. Dans le volet Action, cliquez sur Contrat d'achat.
2. Cliquez sur Confirmation.
    * Définissez l'option Marquer l'accord comme effectif sur oui.  
3. Cliquez sur OK.
4. Dans le volet Action, cliquez sur Contrat d'achat.
5. Cliquez sur Confirmations de contrat d'achat.
    * L'option Aperçu/Imprimer permet de générer un document pour le contrat d'achat que vous pouvez ensuite imprimer ou envoyer au fournisseur. Si vous mettez à jour l'accord ultérieurement et le confirmez à nouveau, les deux versions sont indiquées ici.  
6. Fermez la page.


