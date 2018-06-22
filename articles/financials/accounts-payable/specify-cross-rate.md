---
title: "Spécification du taux croisé"
description: "Cette rubrique donne des informations sur les taux croisés dans Microsoft Dynamics 365 for Finance and Operations."
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: 112f77738b33aae94babe0cf8e9e61ff2ea3d004
ms.contentlocale: fr-fr
ms.lasthandoff: 05/22/2018

---

# <a name="specify-the-cross-rate"></a><span data-ttu-id="afa98-103">Spécification du taux croisé</span><span class="sxs-lookup"><span data-stu-id="afa98-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afa98-104">Cette rubrique décrit l'objectif d'un taux croisé, et comment spécifier le taux croisé lorsque vous réglez un paiement avec une facture.</span><span class="sxs-lookup"><span data-stu-id="afa98-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="afa98-105">Utilisez un taux croisé lorsque tous les critères suivants s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="afa98-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="afa98-106">Vous réglez un paiement avec une facture.</span><span class="sxs-lookup"><span data-stu-id="afa98-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="afa98-107">La ligne de paiement et la ligne de facture utilisent des devises différentes.</span><span class="sxs-lookup"><span data-stu-id="afa98-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="afa98-108">Aucune de ces devises n'est la devise comptable.</span><span class="sxs-lookup"><span data-stu-id="afa98-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="afa98-109">Le taux croisé n'est pas utilisé pour calculer la conversion de la devise de la transaction de paiement en devise comptable de paiement.</span><span class="sxs-lookup"><span data-stu-id="afa98-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="afa98-110">À la place, les taux de change des tables de taux de change sont extraits pour calculer la valeur du montant en devise de transaction de paiement et du montant en devise comptable de paiement.</span><span class="sxs-lookup"><span data-stu-id="afa98-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="afa98-111">Par exemple, la devise comptable est USD, la devise de facturation est CAD, et la devise de paiement est EUR.</span><span class="sxs-lookup"><span data-stu-id="afa98-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="afa98-112">Le taux croisé vous permet d'entrer un taux de change pour convertir directement les dollars canadiens en euros et ne pas passer par les dollars américains.</span><span class="sxs-lookup"><span data-stu-id="afa98-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="afa98-113">Lorsque vous sélectionnez une facture et un paiement principal, vous pouvez entrer un taux croisé pour la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="afa98-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="afa98-114">Le taux croisé est le taux de change entre les devises pour ces transactions jusqu'à la date de règlement.</span><span class="sxs-lookup"><span data-stu-id="afa98-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="afa98-115">Accédez à l'une des pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="afa98-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="afa98-116">**Comptabilité client > Commun > Clients > Tous les clients**</span><span class="sxs-lookup"><span data-stu-id="afa98-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="afa98-117">**Comptabilité fournisseur > Commun > Fournisseurs > Tous les fournisseurs**</span><span class="sxs-lookup"><span data-stu-id="afa98-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="afa98-118">**Approvisionnements > Commun > Fournisseurs > Tous les fournisseurs**</span><span class="sxs-lookup"><span data-stu-id="afa98-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="afa98-119">Sélectionnez le client ou le fournisseur dont vous réglez les transactions en cours.</span><span class="sxs-lookup"><span data-stu-id="afa98-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="afa98-120">Pour un client, dans la page de liste **Tous les clients**, accédez à **Collecter > Régler les transactions en cours**.</span><span class="sxs-lookup"><span data-stu-id="afa98-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="afa98-121">Pour un fournisseur, dans la page de liste **Tous les fournisseurs**, accédez à **Facture > Régler les transactions en cours**.</span><span class="sxs-lookup"><span data-stu-id="afa98-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="afa98-122">Sélectionnez la transaction qui est le paiement principal, puis cliquez sur **Marquer le paiement**.</span><span class="sxs-lookup"><span data-stu-id="afa98-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="afa98-123">La case à cocher dans la colonne **Marquer** est activée et une icône d'information s'affiche dans la colonne **Paiement principal**.</span><span class="sxs-lookup"><span data-stu-id="afa98-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="afa98-124">Dans le champ **Taux croisé**, entrez le taux de change entre la devise de la facture et la devise de paiement, à compter de la date de règlement.</span><span class="sxs-lookup"><span data-stu-id="afa98-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 

