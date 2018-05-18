---
title: "Paramétrer et traiter des factures récurrentes"
description: "Cet article explique comment paramétrer et traiter les factures récurrentes. Vous pouvez utiliser des factures récurrentes si vous devez facturer des clients pour le même montant régulièrement."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5f095b74df8b680f6e7e54520f9684298ec51aad
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-and-process-recurring-invoices"></a>Paramétrer et traiter des factures récurrentes

[!include [banner](../includes/banner.md)]

Cet article explique comment paramétrer et traiter les factures récurrentes. Vous pouvez utiliser des factures récurrentes si vous devez facturer des clients pour le même montant régulièrement.

<a name="create-a-recurring-free-text-invoice-template"></a>Création d'un modèle de facture financière récurrente
---------------------------------------------

Pour facturer régulièrement des clients pour les mêmes services, vous devez définir un modèle de facture financière pouvant être réutilisé pour créer les factures. Ce modèle contient les informations suivantes :

-   Les informations d'en-tête, telles que les groupes de taxe, les conditions de paiement et le mode de paiement
-   Les informations de ligne, telles que la description des services, les comptes de produit, le prix unitaire et le montant de la facture
-   Les frais d'expédition ou de gestion
-   Les répartitions comptables avec les informations de dimension financière, par exemple les centres de coût et les unités commerciales

En réalité, vous créez une facture entière et l'enregistrez comme modèle. Vous pouvez paramétrer les modèles à l'aide de la page **Factures récurrentes**.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Affectation d'un modèle de facture financière à un client et saisie des détails récurrents
Une fois le modèle créé, vous devez affecter le modèle aux clients à facturer. En outre, vous devez spécifier quand et la fréquence à laquelle la facture est utilisée. Vous pouvez affecter des modèles dans l'onglet **Facture** de la page **Clients**. Ajoutez le modèle à la liste et mettez à jour les informations suivantes :

-   La date de début et, éventuellement, la date de fin de la facturation récurrente
-   La fréquence de la facturation récurrente (par exemple, chaque jour ou une fois par mois)
-   Le montant maximal de facturation (si cette information est requise)

Un client peut avoir plusieurs modèles qui ont différentes fréquences.

## <a name="generate-the-recurring-invoices"></a>Générer les factures répétitives
Dans la page **Factures récurrentes**, il existe une tâche qui traite les modèles de factures récurrentes. Vous spécifiez la date de facture et le modèle à partir duquel générer les factures. Les factures sont générées et un même numéro d'identification de récurrence est affecté pour chaque groupe de factures traité.
Validation de factures financières récurrentes
---------------------------------

Une fois les factures récurrentes générées, les ID de récurrence de facture s'affichent dans une tâche de validation dans la page **Factures récurrentes**. Vous pouvez afficher toutes les factures pour un ID de récurrence en cliquant sur le lien. Lors de la révision des factures pour l'ID de récurrence, vous pouvez supprimer les factures individuelles. Les paramètres de récurrence du client seront réinitialisés pour ce modèle, afin qu'il puisse être régénéré ultérieurement. Vous pouvez valider une, plusieurs ou toutes les factures pour un ID de récurrence. Si des workflows sont activés, vous devez cliquer sur **Envoyer** avant de pouvoir valider les factures.
Impression de factures financières récurrentes
----------------------------------

Une fois les factures récurrentes validées, vous pouvez imprimer les factures à partir de la page de liste des factures financières. Vous pouvez imprimer les factures sélectionnées ou sélectionner une plage de factures à imprimer.




