---
title: Configurer et utiliser les paiements fournisseur Payer quand payé
description: Cette rubrique explique comment créer des conditions de Paiement si payé afin de pouvoir libérer des paiements partiels des fournisseurs, en fonction des paiements des clients.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284111"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Configurer et utiliser les paiements fournisseur Payer quand payé

[!include [banner](../includes/banner.md)]

Lorsque vous approuvez l'utilisation d'un fournisseur comme sous-traitant pour travailler, vous pouvez différer le paiement au fournisseur jusqu'à ce que vous receviez le paiement de votre client pour le projet en question. Pour prendre en charge ce scénario, vous pouvez définir la clause Paiement si payé lorsque vous paramétrez la commande fournisseur avec le fournisseur.

Par exemple, lorsqu'un client paie un montant d'une facture du projet, vous pouvez libérer le paiement d'une partie ou la totalité du montant de la facture fournisseur. Paramétrez simplement les conditions de Paiement si payé pour spécifier que le fournisseur sera payé après que vous aurez reçu un pourcentage du paiement du client. Si vous recevez un paiement partiel d'un client, vous pouvez déclencher manuellement le paiement de certaines des factures fournisseur associées.

L'exemple suivant décrit le processus lorsque des conditions de Paiement si payé sont utilisées.

## <a name="example"></a>Exemple

Votre organisation accepte de fournir à un client 100 ordinateurs sur lesquels un logiciel est installé, pour un prix de 150,00 dollars américains (USD) par ordinateur. Vous engagez ensuite un fournisseur pour vous fournir les ordinateurs sur lesquels le logiciel est installé. Selon le contrat, le client doit approuver la qualité des ordinateurs avant de payer votre organisation. La stratégie de votre organisation consiste à retenir le paiement des fournisseurs jusqu'à ce que le client vous ait payé. Par conséquent, vous configurez le projet de sorte qu'il ait un pourcentage de Paiement si payé de 100 %.

Le vendeur vous envoie les 100 ordinateurs sur lesquels un logiciel est installé, ainsi qu'une facture pour 10 000,00 USD. Du fait que les conditions de Paiement si payé étant définies pour votre projet, vous ne payez pas le fournisseur à la réception des ordinateurs. Au lieu de cela, vous envoyez les ordinateurs au client, accompagnés d'une facture de 15 000,00 $. Le client inspecte les ordinateurs et approuve la quantité totale de la facture du projet.

Après avoir reçu le paiement intégral du client, vous payez la somme de 10 000,00 $ au fournisseur, soit le montant total de la facture fournisseur.

## <a name="set-up-pwp-terms-for-a-project"></a>Définir des conditions Paiement si payé pour un projet

Lorsque vous définissez des conditions de Paiement si payé pour un projet, vous devez spécifier, en pourcentage, le montant minimum qu'un client doit vous payer pour le projet avant de payer le fournisseur. Cette somme est automatiquement calculée sur les factures client du projet. Pour paramétrer un pourcentage de seuil des conditions de Paiement si payé, procédez comme suit :

1. Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Tous les projets**.
2. Recherchez et ouvrez le projet pour lequel vous souhaitez configurer les conditions de Paiement si payé.
3. Dans l'organisateur **Accords fournisseur**, cliquez sur **Ajouter une ligne**.
3. Dans le champ **Code compte**, sélectionnez l'une des options suivantes :

    - **Tableau** - Les conditions de Paiement si payé s'appliquent à un seul fournisseur.
    - **Groupe** - Les conditions de Paiement si payé s'appliquent à tous les fournisseurs du groupe de fournisseurs.
    - **Tous** - Les conditions de Paiement si payé s'appliquent à tous les fournisseurs.

4. Si vous avez sélectionné **Table** ou **Groupe** à l'étape précédente, dans le champ **Fournisseur/Groupe de fournisseurs**, sélectionnez le fournisseur ou le groupe de fournisseurs auquel s'appliquent les conditions de Paiement si payé. Si vous avez sélectionné **Tous** à l'étape précédente, le champ **Fournisseur/Groupe de fournisseurs** ne peut pas être modifié.
5. Si des conditions de rétention fournisseur sont paramétrées pour le fournisseur dans le projet, dans le champ **Conditions de rétention fournisseur**, sélectionnez l'ID de règle pour les conditions de rétention.
6. Dans le champ **Pourcentage minimal de mise en œuvre de la clause Payer quand payé**, entrez le pourcentage minimal pour le projet. Le pourcentage que vous entrez pour le projet définit la somme minimale que vous devez recevoir du client avant de payer le fournisseur.

## <a name="create-a-po-that-has-pwp-terms"></a>Créer une commande fournisseur contenant des conditions de Paiement si payé

Lorsque vous validez une facture d'un fournisseur et que celui-ci est soumis aux conditions de Paiement si payé, ces conditions s'affichent dans les lignes de la commande fournisseur. Pour créer une commande fournisseur contenant des conditions de Paiement si payé, procédez comme suit.

1. Accédez à **Approvisionnements** \> **Commandes fournisseur** \> **Toutes les commandes fournisseur**.
2. Dans le volet Actions, sélectionnez **Nouveau**. Ensuite, dans la boîte de dialogue **Créer une commande fournisseur**, entrez les informations requises et sélectionnez **OK**.

    Sinon, ouvrez une commande fournisseur existante sur la page de liste **Toutes les commandes fournisseur**.

4. Sur la page **Commande fournisseur**, sur l'organisateur **Lignes de commande fournisseur**, affichez les détails de la ligne de commande fournisseur pour le fournisseur. L'option **Paiement si payé** est automatiquement activée et la valeur du champ **Pourcentage de seuil de conditions de Paiement si payé** est automatiquement copié à partir du champ **Pourcentage du seuil de conditions de Paiement si payé** sur la page **Projets**.
6. Si vous ne souhaitez pas appliquer les conditions de Paiement si payé au fournisseur pour une ligne de commande, décochez l'option **Paiement si payé**. Dans ce cas, le champ **Pourcentage de seuil de conditions de Paiement si payé** de la ligne de commande fournisseur sera remis à 0 (zéro).

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Mettre à jour un paiement client et payer le fournisseur

Lorsqu'un fournisseur termine de travailler sur un projet et vous envoie une facture, vous devez examiner le statut du projet et les factures client pour déterminer si les conditions de Paiement si payé ont bien été remplies pour le projet. Si les termes de la clause ont bien été respectés pour le fournisseur, vous pouvez déterminer quelles lignes de la facture fournisseur vous allez payer, en fonction des paiements client pour le projet. Si vous décidez de payer le fournisseur même si les conditions de Paiement si payé n'ont pas été respectées, vous pouvez supprimer ou modifier les conditions de Paiement si payé sur la page **Facture fournisseur avec Paiement si payé**.

1. Aller à **Gestion de projet et comptabilité** \> **Recherches et états** \> **Demandes de rétention** \> **Facture fournisseur avec Paiement si payé**.
2. Sur la page **Factures fournisseur avec Paiement si payé**, dans le champ de recherche, entrez des valeurs pour rechercher la facture fournisseur à revoir, puis cliquez sur **Rechercher**.
3. Sur l'organisateur **Lignes de facture fournisseur**, sélectionnez les lignes à modifier.
4. Si les conditions de **Paiement si payé** sont remplies pour la ligne de facture, cliquez sur **Libérer le paiement fournisseur**. Lorsque l'option **Paiement si payé** est décochée et que la valeur du champ **Prêt à payer** prend le statut **Oui**.
