---
title: Entrer des contrats de vente
description: Cette rubrique explique comment créer un contrat de vente qui incite l’un de vos clients à acheter un produit pour un montant convenu sur une période définie en échange de remises spéciales.
author: Henrikan
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee2c1494842c5fd2aa598546ba655c33d6fd3f16
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568301"
---
# <a name="enter-sales-agreements"></a>Entrer des contrats de vente

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment créer un contrat de vente qui incite l’un de vos clients à acheter un produit pour un montant convenu sur une période définie en échange de remises spéciales. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-sales-agreement-header"></a>Paramétrer un en-tête de contrat de vente
1. Dans le volet de navigation, accédez à **Modules > Ventes et marketing > Contrats de vente > Contrats de vente**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte client**, sélectionnez l’enregistrement souhaité dans le menu déroulant.
4. Dans le champ **Classification du contrat de vente**, sélectionnez l’enregistrement souhaité dans le menu déroulant.
5. Développez la section **Général**.
6. Dans le champ **Engagement par défaut**, sélectionnez **Engagement à la valeur du produit**. Un type d’engagement est un critère obligatoire que vous devez affecter à l’accord afin de définir la manière dont l’objectif du contrat est atteint. Les quatre types prédéfinie vous permettent de paramétrer la cible de l’engagement du client, exprimée comme une quantité ou une valeur. Le type d’engagement à la quantité peut uniquement être appliqué à un produit spécifique, mais les types basés sur la valeur s’appliquent aux ventes des produits spécifiques et non spécifiques.  
7. Dans le champ **Date d’expiration**, définissez la date à une date future à laquelle vous souhaitez que l’accord arrive à expiration.
8. Cliquez sur **OK**.

## <a name="set-up-product-value-commitment-lines"></a>Paramétrer des lignes d’engagement à la valeur du produit
1. Sélectionnez **Ajouter la ligne**.
2. Dans le champ **Numéro d’article**, sélectionnez l’enregistrement souhaité dans le menu déroulant. Le type d’engagement que vous avez choisi pour l’accord affecte le type d’informations que vous pouvez spécifier pour les lignes d’accord. Par exemple, pour un accord basé sur des valeurs vous devez spécifier le montant net total (dans la devise acceptée) pour lequel le client s’engage à vous acheter des marchandises. Dans cet exemple, les champs **Quantité** et **Unité** de la ligne sont indisponibles, car vous êtes en train de créer un accord pour que le client achète une valeur spécifique d’un produit.   
3. Dans le champ **Montant net**, spécifiez le montant en devises pour lequel le client s’est engagé à acheter.
4. Dans le champ **Pourcentage de remise**, entrez une valeur en pourcentage qui s’appliquera aux lignes de commande du client liées à cet accord.
5. Développez la section **Détails de ligne**.
6. Sélectionnez **Oui** dans le champ **Le max. est appliqué**.
    - La sélection de l’option **Le max. est appliqué** signifie que le montant total de toutes les lignes de commande client qui utilisent les prix spéciaux, les remises et/ou les conditions de paiement de l’engagement ne doit pas dépasser le montant spécifié dans l’engagement.  
    - Les montants de lancement minimal et maximal spécifient une plage de valeurs qui doivent être vendues sur chaque commande client qui utilise l’accord sélectionné.   
7. Développez la section **En-tête de contrat de vente**. À moins que le statut de l’accord soit défini sur **Effectif**, les commandes client ne peuvent pas être associées à l’accord et ne peuvent donc pas contribuer à l’accomplissement de cet accord. À ce stade, vous pouvez modifier le statut manuellement. Toutefois, le statut serait normalement modifié lorsque vous confirmez l’accord pour le client.  
8. Dans le volet Actions, cliquez sur **Contrats de vente**.
9. Sélectionnez **Confirmation**. Assurez-vous que l’option **Marquer l’accord comme effectif** est définie sur **Oui**.  
10. Sélectionnez **Oui** dans le champ **Imprimer un état**.
11. Cliquez sur **OK**.
12. Fermez la page. L’accord est désormais effectif. Vous pouvez commencer à lier les commandes du client à l’accord, à déduire de la cible de l’engagement.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]