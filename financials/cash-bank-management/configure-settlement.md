---
title: "Configurer un règlement"
description: "La manière et le moment où les transactions sont réglées peuvent être des sujets complexes. Il est donc essentiel que vous compreniez et définissiez correctement les paramètres afin de répondre à vos exigences métier. Cet article décrit les paramètres utilisés pour le règlement de la Comptabilité fournisseur et de la Comptabilité client."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 059513de66827aa3a839b9eb06973ec4c1549f73
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017


---

# <a name="configure-settlement"></a>Configurer un règlement

[!include[banner](../includes/banner.md)]


La manière et le moment où les transactions sont réglées peuvent être des sujets complexes. Il est donc essentiel que vous compreniez et définissiez correctement les paramètres afin de répondre à vos exigences métier. Cet article décrit les paramètres utilisés pour le règlement de la Comptabilité fournisseur et de la Comptabilité client. 

Les paramètres suivants affectent la manière dont les règlements sont traités dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Le règlement est le processus qui consiste à régler une facture à l'aide d'un paiement ou d'un avoir. Ces paramètres sont situés dans la zone **Règlement** des pages **Paramètres de la comptabilité client** et **Paramètres de la comptabilité fournisseur**.

-   **Règlement automatique** – Définissez cette option sur **Oui** si une transaction doit être réglée automatiquement avec d'autres transactions en cours lors de sa validation. Si cette option est définie sur **Non**, les utilisateurs peuvent régler manuellement les transactions lorsqu'ils entrent des paiements, ou ultérieurement, à l'aide de la page **Règlement des transactions**.
-   **Administration d'escompte de règlement** – Spécifiez comment un [escompte de règlement est géré lorsqu'une facture est surpayée](cash-discount-handling-overpayments.md). Pour un trop-perçu, l'escompte de règlement peut être réduit, il peut être considéré comme une différence, ou peut rester en compte pour le fournisseur ou le client.
    -   **Non spécifique** – Le montant de l'escompte de règlement est réduit à hauteur du montant de trop-perçu. Ce comportement est toujours utilisé, peu importe que le montant du trop-perçu soit supérieur ou inférieur au montant entré dans le champ **Trop-perçu ou moins-perçu maximal**.
    -   **Spécifique** – Le montant du trop-perçu est validé dans un compte général des différences d'escompte de règlement ou reste un solde dans le compte du client ou du fournisseur. Le comportement spécifique dépend de si le montant du trop-perçu est compris entre 0.00 et le montant qui est entré dans le champ **Trop-perçu ou moins-perçu maximal**, ou si le montant du trop-perçu est supérieur au montant du **Trop-perçu ou moins-perçu maximal**.
-   **Différence minime maximale** – Permet d'entrer la différence minime maximale autorisée pour les transactions réglées. Si la différence est égale ou inférieure à la différence minime spécifiée dans ce champ, la différence sera validée sur le compte général de différence minime spécifié dans la page **Comptes pour transactions automatiques**.
-   **Trop-perçu ou moins-perçu maximal** – Permet d'entrer le montant accepté pour le trop-perçu et le moins-perçu. Pour calculer la taxe sur le trop-perçu ou le moins-perçu, dans la page **Paramètres de comptabilité**, cliquez sur **Taxe**, puis sélectionnez l'option **Taxe sur trop-perçu ou moins-perçu**.
    -   Si le trop-perçu ou le moins-perçu entraîne une différence inférieure à celle définie dans le champ **Différence minime maximale**, le montant de la différence minime est validé sur le compte de différence minime.
    -   Si le trop-perçu ou le moins-perçu entraîne une différence supérieure à celle définie dans le champ **Différence minime maximale**, le montant de la différence est validé sur le compte de différence sélectionné pour le type de validation **Client - Escompte de règlement** ou **Fournisseur - Escompte de règlement** sur le **Comptes pour transactions automatiques**.
-   **Calculez les escomptes de règlement pour les paiements partiels** – Définissez cette option sur **Oui** pour activer les escomptes de règlement à calculer automatiquement pour les paiements partiels.
    -   Cet effet de cette option dépend de la valeur du champ **Utiliser un escompte de règlement** dans la page **Régler les transactions**. Si cette option est définie sur **Oui**, la remise est acceptée lorsque le champ **Utiliser un escompte de règlement** est défini sur **Normal**. Lorsque le champ **Utiliser un escompte de règlement** est défini sur **Toujours**, l'escompte de règlement est toujours accepté, quel que soit le paramètre de ce champ. Lorsque le champ **Utiliser un escompte de règlement** est défini sur **Jamais**, l'escompte de règlement n'est jamais accepté, quel que soit le paramètre de ce champ.
    -   Si cette option est définie sur **Oui** et qu'un utilisateur modifie la valeur dans le champ **Montant à régler** de la page **Régler les transactions**, la remise est calculée automatiquement et affichée comme entrée par défaut dans le champ **Montant de l'escompte de règlement à accepter**.
    -   Si cette option est définie sur **Non** et qu'un utilisateur modifie la valeur dans le champ **Montant à régler** de la page **Régler les transactions**, l'entrée par défaut du champ **Montant de l'escompte de règlement à accepter** est **0** (zéro).
-   **Calculez les escomptes de règlement pour les avoirs** – Définissez cette option sur **Oui** pour calculer automatiquement un escompte de règlement pour les avoirs. Dans Comptabilité client, une transaction d'avoir est une transaction négative ayant une valeur dans le champ **Facture** de la page **Facture financière** ou un retour dans la page **Commande client**.
    -   L'effet de cette option dépend de la valeur du champ **Utiliser un escompte de règlement** dans la page **Régler les transactions**. Si cette option est définie sur **Oui**, la remise est acceptée lorsque le champ ****Utiliser un escompte de règlement**** est défini sur **Normal**. Lorsque le champ ****Utiliser un escompte de règlement**** est défini sur **Toujours**, l'escompte de règlement est toujours accepté, quel que soit le paramètre de ce champ. Lorsque le champ ****Utiliser un escompte de règlement**** est défini sur **Jamais**, l'escompte de règlement n'est jamais accepté, quel que soit le paramètre de ce champ.
    -   Si cette option est définie sur **Oui** et qu'un avoir est marqué dans la page **Régler les transactions**, la remise est calculée automatiquement et affichée comme entrée par défaut dans le champ **Montant de l'escompte de règlement à accepter**.
    -   Si cette option est définie sur **Non** et qu'un avoir est marqué dans la page **Régler les transactions**, l'entrée par défaut du champ **Montant de l'escompte de règlement à accepter** est **0** (zéro).
-   **Comptes de contrepartie de remise (AP uniquement)** – Permet de définir le compte général par défaut pour l'escompte de règlement qui doit être utilisé pour l'écriture comptable des escomptes de règlement.
    -   **Utiliser le compte principal pour les remises fournisseur** – L'escompte de règlement est validé dans le compte principal défini dans la page **Paramétrage d'escompte de règlement**.
    -   **Comptes sur les lignes de facture** – L'escompte de règlement est validé dans les comptes généraux de la facture d'origine.
-   **Marquer des lignes sur des factures financières et des notes d'intérêts (AR uniquement)** – Définissez cette option sur **Oui** pour activer le bouton **Marquer les lignes de facture** dans les pages **Entrer les paiements client**, **N° document du journal des paiements** et **Régler les transactions**. Ce bouton permet aux utilisateurs de marquer des lignes individuelles pour règlement.
-   **Classer le règlement par ordre de priorité (AR uniquement)** – Définissez cette option sur **Oui** pour activer le bouton **Marque par priorité** dans les pages **Entrer les paiements client** et **Régler les transactions**. Ce bouton permet aux utilisateurs d'affecter la commande prédéterminée de règlement des transactions.  Une fois l'ordre de règlement appliqué à une transaction, vous pouvez modifier l'ordre et la répartition des paiements avant la validation.
-   **Utiliser la priorité pour les règlements automatiques** – Définissez cette option sur **Oui** pour utiliser l'ordre de priorité défini lorsque les transactions sont automatiquement réglées. Ce champ n'est disponible que si les options **Classer le règlement par ordre de priorité** et **Règlement automatique** sont définies **Oui**.





