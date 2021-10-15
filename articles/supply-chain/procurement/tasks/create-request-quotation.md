---
title: Créer un appel d’offre
description: Cette procédure décrit comment créer un appel d’offre.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0e9e4d7c31b1e6905abeac03e462ac185f3f489
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565373"
---
# <a name="create-a-request-for-quotation"></a>Créer un appel d’offre

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment créer un appel d’offre. Cette action est généralement effectuée par un agent des achats. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Vous devez disposer de types de sollicitation avant de commencer. Une fois que vous avez terminé cette tâche et que vous avez créé et soumis un appel d’offre, vous pouvez ensuite entrer les réponses par fournisseur, les comparer, et attribuer le contrat.


## <a name="prepare-a-new-rfq"></a>Préparer un nouvel appel d’offre
1. Allez dans **Volet de navigation > Modules > Approvisionnements > Demandes de devis > Toutes les demandes de devis**.
2. Cliquez sur **Nouveau**.
    Les types d’achat suivants sont disponibles : Commande fournisseur (valeur par défaut) : document qui confirme l’offre d’achat de produits, ou l’acceptation d’une offre de vente de produits en échange d’un paiement. Demande d’achat : ce type est sélectionné automatiquement si vous créez une demande de devis directement à partir d’une demande d’achat. Si vous sélectionnez manuellement cette option, vous recevez un message d’erreur. Contrat d’achat : accord sur l’achat d’une quantité ou d’une valeur spécifique d’un produit. Si vous sélectionnez cette option, vous devez sélectionner l’intervalle de dates qui s’applique au contrat d’achat.  
3. Tapez une valeur dans le champ **Titre du document**.
4. Saisissez ou sélectionnez une valeur dans le champ **Type de sollicitation**.
    + Si une méthode d’attribution de score est associée au type de sollicitation, alors il s’agira de la méthode d’attribution de score par défaut pour l’appel d’offre que vous créez. Il est possible de modifier la méthode d’attribution de score ultérieurement.  
    + Dans le champ **Date de livraison**, entrez une date.  
    + Sélectionnez la date à laquelle vous souhaitez recevoir les articles.  
    + Entrez une date et une heure dans le champ **Date et heure d’expiration**.  
    + Spécifiez la date et l’heure auxquelles les fournisseurs doivent répondre à l’appel d’offre.  
5. Entrez ou sélectionnez une valeur dans le champ **Entrepôt**. L’adresse de livraison sera l’adresse de l’entrepôt par défaut.  
6. Cliquez sur **OK**.

## <a name="add-lines"></a>Ajouter des lignes

Après avoir défini les informations de base sur votre appel d’offre, vous spécifiez les biens ou services sur lesquels vous souhaitez que les fournisseurs fassent des offres. Article est le type de ligne par défaut.

1. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**. Si vous utilisez USMF, vous pouvez sélectionner T0020.  
2. Entrez un nombre dans le champ **Quantité**.
3. Cliquez sur **Ajouter une ligne**.
4. Sélectionnez Catégorie dans le champ **Type de ligne**. Vous pouvez utiliser le type de ligne Catégorie pour créer des appels d’offre pour des biens hors stock ou des services. Vous devez ensuite sélectionner le type de biens ou de services à partir d’une hiérarchie de catégories d’approvisionnement.  
5. Saisissez ou sélectionnez une valeur dans le champ **Catégorie d’approvisionnement**.
6. Dans le champ **Nom du produit**, saisissez une valeur.
7. Entrez un nombre dans le champ **Quantité**.
8. Saisissez ou sélectionnez une valeur dans le champ **Unité**.

## <a name="add-vendors"></a>Ajouter des fournisseurs
1. Cliquez sur l’en-tête pour passer de la vue Lignes à la vue **En-tête**. 
2. Développer la section **Fournisseur**.
3. Cliquez sur **Ajouter automatiquement des fournisseurs**. Vous pouvez ajouter des fournisseurs à l’appel d’offre automatiquement, selon la catégorie d’approvisionnement des articles demandés. S’il n’y a aucun fournisseur approuvé pour les catégories comprises dans les lignes, vous pouvez ajouter manuellement des fournisseurs.  
4. Cliquez sur **Ajouter**.
5. Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.
6. Cliquez sur **Ajouter**.
7. Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur. Une fois que vous avez sélectionné un fournisseur, le statut est créé. Cela signifie que les informations sur le fournisseur ont été enregistrées dans la demande de devis mais que cette dernière n’a pas été envoyée au fournisseur. Vous pouvez ajouter un fournisseur à une demande de devis, indépendamment du statut du fournisseur.  

## <a name="send-the-rfq-to-vendors"></a>Envoyer l’appel d’offre aux fournisseurs
1. Cliquez sur **Envoyer** dans le volet **Actions**. Dans la page Envoi de l’appel d’offre, vérifiez que les fournisseurs de la liste sont ceux qui doivent recevoir l’appel d’offre.  
2. Cliquez sur **Imprimer**. Cette boîte de dialogue vous permet d’imprimer l’appel d’offre. Si vous choisissez d’imprimer une feuille de réponse, le contenu de cette opération sera défini dans les paramètres d’approvisionnements. Pour choisir comment imprimer des feuilles de réponse, une fois que vous avez ouvert la boîte de dialogue Imprimer, cliquez sur Options d’impression avancées. Un appel d’offre sera imprimé pour chaque fournisseur contenant des lignes dont le statut est Créé ou Envoyé. Les lignes annulées et celles avec des réponses enregistrées ne sont pas imprimées.   
3. Cliquez sur **Annuler**.
4. Cliquez sur **OK**.
5. Fermez la page.
6. Fermez la page.

## <a name="view-the-rfq-journal"></a>Afficher le journal d’appels d’offre
1. Accédez à **Approvisionnements > Demandes de devis > Suivi de la demande de devis > Journaux d’appel d’offre**.
2. Cliquez sur **Aperçu/Imprimer**.
3. Cliquez sur **Aperçu d’origine**.
4. Fermez la page.
5. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]