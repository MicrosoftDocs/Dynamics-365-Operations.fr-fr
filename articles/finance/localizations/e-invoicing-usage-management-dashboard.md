---
title: Tableau de bord de gestion de l’utilisation
description: Cette rubrique explique comment utiliser le tableau de bord de gestion de l’utilisation pour surveiller l’utilisation du service Facturation électronique et préserver la conformité.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130504"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="5cbf6-103">Tableau de bord de gestion de l’utilisation</span><span class="sxs-lookup"><span data-stu-id="5cbf6-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cbf6-104">Le tableau de bord **Gestion de l’utilisation** vous aide à surveiller l’utilisation du service Facturation électronique et aide donc votre organisation à rester conforme en termes d’utilisation mensuelle.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="5cbf6-105">La conformité est déterminée en calculant le volume d’envois et en le comparant avec le volume d’envois acheté pour identifier les écarts entre le volume acquis et le volume utilisé.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="5cbf6-106">Le tableau de bord comprend les indicateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="5cbf6-107">Un indicateur de coût que vous pouvez utiliser pour surveiller la consommation à des fins de conformité des licences :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="5cbf6-108">Utilisation mensuelle (exportation)</span><span class="sxs-lookup"><span data-stu-id="5cbf6-108">Usage per month (export)</span></span>

- <span data-ttu-id="5cbf6-109">Trois indicateurs opérationnels permettant de suivre l’utilisation du service Facturation Electronique à des fins de gestion :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="5cbf6-110">Utilisation par fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="5cbf6-110">Usage by feature</span></span>
    - <span data-ttu-id="5cbf6-111">Utilisation par environnement</span><span class="sxs-lookup"><span data-stu-id="5cbf6-111">Usage by environment</span></span>
    - <span data-ttu-id="5cbf6-112">Utilisation mensuelle (importation)</span><span class="sxs-lookup"><span data-stu-id="5cbf6-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="5cbf6-113">Portée de la mesure</span><span class="sxs-lookup"><span data-stu-id="5cbf6-113">Measurement scope</span></span>

- <span data-ttu-id="5cbf6-114">Unité de mesure :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-114">Unit of measure:</span></span> 

    <span data-ttu-id="5cbf6-115">Le tableau de bord **Gestion de l’utilisation** comptabilise l’envoi de documents commerciaux et de factures électroniques importées.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="5cbf6-116">Organisation :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-116">Organization:</span></span> 

    <span data-ttu-id="5cbf6-117">Le comptage est résumé par ID de locataire de votre organisation, quel que soit le nombre d’instances de Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management, ou le nombre d’entités juridiques où le service Facturation électronique est activé.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="5cbf6-118">Indicateur : Utilisation par mois (exportation)</span><span class="sxs-lookup"><span data-stu-id="5cbf6-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="5cbf6-119">Cet indicateur fournit des détails sur les factures électroniques que votre organisation émet au cours d’une période définie.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="5cbf6-120">Étendue</span><span class="sxs-lookup"><span data-stu-id="5cbf6-120">Scope</span></span>
- <span data-ttu-id="5cbf6-121">Le nombre de documents commerciaux soumis par Finance et Supply Chain Management au service Facturation électronique, quel que soit le nombre de lignes que contiennent ces documents commerciaux.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="5cbf6-122">Le nombre de documents commerciaux envoyés qui sont traités avec succès par le service Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="5cbf6-123">Un document est considéré comme traité avec succès lorsque le flux d’actions défini dans la configuration de la fonctionnalité est terminé.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="5cbf6-124">Lorsqu’une facture électronique est soumise à un service web externe, le comptage est indépendant des résultats du traitement du service web (accepté, rejeté ou erreur de validation de schéma).</span><span class="sxs-lookup"><span data-stu-id="5cbf6-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="5cbf6-125">Si le service web a reçu et répondu à la demande du service Facturation électronique, la soumission est considérée comme un comptage valide.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="5cbf6-126">**Exception :** les documents commerciaux ne sont pas pris en compte s’ils sont resoumis de Finance et Supply Chain Management au service Facturation électronique, comme dans les scénarios où une nouvelle soumission du même document commercial est requise pour modifier le statut de la facture électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="5cbf6-127">Par exemple, l’émission d’une facture électronique brésilienne (document fiscal) est comptée comme valide, mais la demande d’annulation pour celle-ci n’est pas comptée.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="5cbf6-128">Calcul</span><span class="sxs-lookup"><span data-stu-id="5cbf6-128">Calculation</span></span>

<span data-ttu-id="5cbf6-129">Le calcul du solde est calculé comme suit :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="5cbf6-130">Solde = Gratuit + Acheté - Utilisé</span><span class="sxs-lookup"><span data-stu-id="5cbf6-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="5cbf6-131">Où :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-131">Where:</span></span>

- <span data-ttu-id="5cbf6-132">Gratuit :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-132">Free:</span></span>
  
    <span data-ttu-id="5cbf6-133">Un volume gratuit de documents commerciaux que le client peut soumettre par mois.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="5cbf6-134">Il comprend un ensemble de 100 documents commerciaux pouvant être soumis au service Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="5cbf6-135">Le volume gratuit n’est pas cumulatif et tout solde restant n’est pas reporté à la période suivante.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="5cbf6-136">Acheté :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-136">Purchased:</span></span>
  
    <span data-ttu-id="5cbf6-137">Un ensemble de 1 000 documents commerciaux pouvant être soumis au service Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="5cbf6-138">Ce forfait doit être acheté pour votre organisation sur une base mensuelle.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="5cbf6-139">Le volume acheté n’est pas cumulatif et tout solde restant n’est pas reporté à la période suivante.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="5cbf6-140">Utilisé :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-140">Used:</span></span> 

    <span data-ttu-id="5cbf6-141">Le nombre des soumissions de documents commerciaux au service Facturation Electronique selon des critères définis.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="5cbf6-142">Si votre organisation prévoit de dépasser le volume mensuel de 100 envois gratuits, achetez le volume maximal pour vous assurer de respecter la politique de licence de Microsoft pour le service Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="5cbf6-143">Actuellement, le volume acheté doit être saisi manuellement, selon la date d’acquisition, sous forme de plusieurs ensembles de 1 000 envois.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="5cbf6-144">Indicateur : utilisation par fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="5cbf6-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="5cbf6-145">Cet indicateur montre l’utilisation des fonctionnalités de facturation électronique pour l’émission de factures électroniques pendant une période définie.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="5cbf6-146">Calcul :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-146">Calculation:</span></span>
  
    <span data-ttu-id="5cbf6-147">Utilisé = Le nombre de fois que chaque fonction de facturation électronique a été utilisée lors de la soumission de documents commerciaux au service Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="5cbf6-148">Indicateur : utilisation par environnement</span><span class="sxs-lookup"><span data-stu-id="5cbf6-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="5cbf6-149">Cet indicateur montre l’utilisation des environnements de service de facturation électronique pendant une période définie.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="5cbf6-150">Calcul :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-150">Calculation:</span></span>
    
    <span data-ttu-id="5cbf6-151">Utilisé = Le nombre de fois que chaque environnement de service de facturation électronique a été utilisé lors de la soumission de documents commerciaux au service Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="5cbf6-152">Indicateur : Utilisation par mois (importation)</span><span class="sxs-lookup"><span data-stu-id="5cbf6-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="5cbf6-153">Cet indicateur présente le volume d’importation de factures électroniques par le service Facturation électronique dans Finance et Supply Chain Management pendant une période définie.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="5cbf6-154">Étendue :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-154">Scope:</span></span>

    <span data-ttu-id="5cbf6-155">Factures électroniques importées dans Finance et Supply Chain Management, quel que soit le nombre de lignes que contiennent ces factures électroniques.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="5cbf6-156">Calcul :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-156">Calculation:</span></span>

    <span data-ttu-id="5cbf6-157">Reçues = Le nombre de factures électroniques importées dans Finance et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="5cbf6-158">Fonctions</span><span class="sxs-lookup"><span data-stu-id="5cbf6-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="5cbf6-159">Achats</span><span class="sxs-lookup"><span data-stu-id="5cbf6-159">Purchase</span></span>

<span data-ttu-id="5cbf6-160">Sur l’onglet **Utilisation par mois (exportation)**, sélectionnez **Acheter** pour enregistrer manuellement le nombre de soumissions achetées.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="5cbf6-161">Pour une date donnée, sélectionnez **Nouveau** et entrez le nombre de **paquets** achetés à cette date.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="5cbf6-162">La **Quantité** est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="5cbf6-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="5cbf6-163">Quantité = Paquets \* 1 000</span><span class="sxs-lookup"><span data-stu-id="5cbf6-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="5cbf6-164">La **Quantité** calculée est répercutée dans l’élément **Acheté** de l’indicateur **Utilisation par mois (exportation)**.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="5cbf6-165">Mise à jour</span><span class="sxs-lookup"><span data-stu-id="5cbf6-165">Update</span></span>

<span data-ttu-id="5cbf6-166">Dans le volet Actions, sélectionnez **Mettre à jour** pour actualiser le calcul et mettre à jour les données affichées sur la page et dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="5cbf6-167">Réinitialiser les données de l’historique</span><span class="sxs-lookup"><span data-stu-id="5cbf6-167">Reset history data</span></span>

<span data-ttu-id="5cbf6-168">Dans le volet Actions, sélectionnez **Réinitialiser les données de l’historique** pour actualiser la base de données à partir de laquelle les indicateurs sont calculés.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="5cbf6-169">Le tableau de bord **Gestion de l’utilisation** n’affiche pas les montants en devise.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="5cbf6-170">Au lieu de cela, il affiche uniquement le volume des envois comptabilisés et des documents importés.</span><span class="sxs-lookup"><span data-stu-id="5cbf6-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
