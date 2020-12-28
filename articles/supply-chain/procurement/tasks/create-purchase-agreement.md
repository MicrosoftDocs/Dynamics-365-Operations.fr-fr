---
title: Créer un contrat d'achat
description: Cette rubrique vous guide tout au long de la création d'un contrat d'achat.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427831"
---
# <a name="create-a-purchase-agreement"></a>Créer un contrat d'achat

[!include [banner](../../includes/banner.md)]

Cette rubrique vous guide tout au long de la création d'un contrat d'achat. Cela est généralement effectué par un gestionnaire des achats. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Vous devez avoir configuré des classifications de contrat d'achat avant de commencer. Une fois que vous avez créé un accord, vous pouvez l'utiliser lorsque vous créez une commande fournisseur. Cela copiera les conditions du contrat d'achat dans l'en-tête et sur toutes les lignes de la commande qui sont affectées par l'accord.


## <a name="create-a-new-purchase-agreement"></a>Créer un contrat d'achat
1. Allez dans **Volet de navigation > Modules > Approvisionnements > Contrats d'achat > Contrats d'achat**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Compte fournisseur**, sélectionnez l'enregistrement souhaité dans le menu déroulant qui s'affiche.
4. Dans le champ **Classification de contrat d'achat**, sélectionnez l'enregistrement souhaité dans le menu déroulant qui s'affiche.
5. Développez l'organisateur **Général**.
6. Entrez une date dans le champ **Date d'expiration**.

    - Cette date d'expiration est la valeur par défaut pour toutes les lignes d'engagement et détermine la durée pendant laquelle chaque engagement spécifique est valide.  

7. Entrez un nom pour votre contrat d'achat dans le champ **Titre du document**.

    - Laissez le champ **Engagement par défaut** configuré sur **Engagement à la quantité de produits** (ou modifiez-le s'il n'est pas défini ainsi).  
    - La valeur d'engagement par défaut détermine les options dans les lignes d'accord. Si vous avez besoin d'un type d'engagement lorsque vous créez des lignes d'accord, vous devez modifier l'engagement par défaut sous l'en-tête. Il y a 4 types d'engagements : **Engagement de quantité de produits** (pour une quantité spécifique d'un produit) ; **Engagement de valeur de produit** (pour un montant en devise spécifique d'un produit) ; **Engagement de valeur de catégorie de produit** (pour un montant en devise spécifique dans une catégorie d'approvisionnement, avec un montant qui peut être celui d'un article du catalogue ou celui d'un article ne faisant pas partie du catalogue) ; **Engagement de valeur** (pour un montant en devise spécifique qui peut être atteint par tout produit ou par n'importe quelle catégorie d'approvisionnement).  

8. Cliquez sur **OK**.

## <a name="add-a-commitment"></a>Ajouter un engagement
1. Sélectionnez **Ajouter la ligne**.
2. Dans le champ **Numéro d'article**, sélectionnez l'enregistrement souhaité dans le menu déroulant.
3. Entrez un nombre dans le champ **Quantité**. Il s'agit de la quantité totale que vous avez acceptée d'acheter auprès de votre fournisseur.  
4. Entrez un nombre dans le champ **Prix unitaire**.
5. Développez la section **Détails de ligne**.
6. Définissez l'option **Le max. est appliqué** sur **Oui**. L'option **Le max. est appliqué** limite l'utilisation de l'engagement. Vous pouvez acheter au plus la quantité spécifiée dans le champ **Quantité** pour la ligne.  

## <a name="add-header-conditions"></a>Ajouter des conditions d'en-tête
1. Dans le volet Actions, sélectionnez **Options**.
2. Sélectionnez **Modifier la vue**.
3. Sélectionnez **Vue de l'en-tête**.
4. Développez la section **Conditions**.
5. Dans le champ **Mode de paiement**, sélectionnez l'enregistrement souhaité dans le menu déroulant. Les conditions de paiement du compte fournisseur sont indiquées ici par défaut.  
6. Dans le champ **Mode de livraison**, sélectionnez l'enregistrement souhaité dans le menu déroulant.
7. Dans le champ **Conditions de livraison**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.

## <a name="confirm-and-activate-the-agreement"></a>Confirmer et activer le contrat de vente
1. Dans le volet Actions, cliquez sur **Contrat d'achat**.
2. Sélectionnez **Confirmation**. Définissez l'option **Marquer l'accord comme effectif** sur **Oui**.  
3. Cliquez sur **OK**.
4. Dans le volet Actions, cliquez sur **Contrat d'achat**.
5. Sélectionnez **Confirmations de contrat d'achat**. L'option **Aperçu/Imprimer** permet de générer un document pour le contrat d'achat que vous pouvez ensuite imprimer ou envoyer au fournisseur. Si vous mettez à jour l'accord ultérieurement et le confirmez à nouveau, les deux versions sont indiquées ici.  
6. Fermez la page.

