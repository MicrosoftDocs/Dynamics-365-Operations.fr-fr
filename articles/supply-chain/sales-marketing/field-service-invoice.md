---
title: Synchroniser des factures d'accord de Field Service sur des factures financières dans Finance and Operations
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les factures d'accord de Microsoft Dynamics 365 for Field Service sur les factures financières dans Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 55301ba39dd28fbae5b6c21b1da3c3d9cf6afd8a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560161"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a><span data-ttu-id="6785f-103">Synchroniser des factures d'accord de Field Service sur des factures financières dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6785f-103">Synchronize agreement invoices in Field Service to free text invoices in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6785f-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les factures d'accord de Microsoft Dynamics 365 for Field Service sur les factures financières dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6785f-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Microsoft Dynamics 365 for Field Service to free text invoices in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="6785f-105">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="6785f-105">Templates and tasks</span></span>

<span data-ttu-id="6785f-106">Le modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des factures d'accord de Field Service sur les factures financières de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6785f-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Finance and Operations.</span></span>

<span data-ttu-id="6785f-107">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="6785f-107">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="6785f-108">Factures d'accord (Field Service vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6785f-108">Agreement invoices (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="6785f-109">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="6785f-109">**Names of the tasks in the Data integration project:**</span></span>

- <span data-ttu-id="6785f-110">En-têtes de facture</span><span class="sxs-lookup"><span data-stu-id="6785f-110">Invoice headers</span></span>
- <span data-ttu-id="6785f-111">Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="6785f-111">Invoice lines</span></span>

<span data-ttu-id="6785f-112">La synchronisation suivante est requise avant que la synchronisation des factures d'accord puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="6785f-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="6785f-113">Comptes (Sales vers Fin and Ops) - Direct</span><span class="sxs-lookup"><span data-stu-id="6785f-113">Accounts (Sales to Fin and Ops) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="6785f-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="6785f-114">Entity set</span></span>

| <span data-ttu-id="6785f-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="6785f-115">Field Service</span></span>  | <span data-ttu-id="6785f-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6785f-116">Finance and Operations</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="6785f-117">factures</span><span class="sxs-lookup"><span data-stu-id="6785f-117">invoices</span></span>       | <span data-ttu-id="6785f-118">En-têtes de facture financière client CDS</span><span class="sxs-lookup"><span data-stu-id="6785f-118">CDS customer free text invoice headers</span></span> |
| <span data-ttu-id="6785f-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="6785f-119">invoicedetails</span></span> | <span data-ttu-id="6785f-120">Lignes de facture financière client CDS</span><span class="sxs-lookup"><span data-stu-id="6785f-120">CDS customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="6785f-121">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="6785f-121">Entity flow</span></span>

<span data-ttu-id="6785f-122">Les factures qui sont créées à partir d'un accord dans Field Service peuvent être synchronisées sur Finance and Operations via un projet d'intégration de données Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="6785f-122">Invoices that are created from an agreement in Field Service can be synchronized to Finance and Operations via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="6785f-123">Les mises à jour à ces factures sont synchronisées sur les factures financières dans Finance and Operations si le statut comptable des factures financières est **En cours**.</span><span class="sxs-lookup"><span data-stu-id="6785f-123">Updates to these invoices will be synchronized to the free text invoices in Finance and Operations if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="6785f-124">Une fois les factures financières validées dans Finance and Operations, et que le statut comptable est mis jour sur **Terminé**, vous ne pouvez plus synchroniser les mises à jour dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="6785f-124">After the free text invoices are posted in Finance and Operations, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="6785f-125">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="6785f-125">Field Service CRM solution</span></span>

<span data-ttu-id="6785f-126">Le champ **A des lignes provenant d'un accord** a été ajouté à l'entité **Facture**.</span><span class="sxs-lookup"><span data-stu-id="6785f-126">The **Has Lines With Agreement Origin** field has been added to the **Invoice** entity.</span></span> <span data-ttu-id="6785f-127">Ce champ permet de garantir que seules les factures créées à partir d'un accord sont synchronisées.</span><span class="sxs-lookup"><span data-stu-id="6785f-127">This field helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="6785f-128">La valeur est **vrai** si la facture contient au moins une ligne de facture qui provient d'un accord.</span><span class="sxs-lookup"><span data-stu-id="6785f-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="6785f-129">Le champ **Provient d'un accord** a été ajouté à l'entité **Ligne de facture**.</span><span class="sxs-lookup"><span data-stu-id="6785f-129">The **Has Agreement Origin** field has been added to the **Invoice Line** entity.</span></span> <span data-ttu-id="6785f-130">Ce champ permet de garantir que seules les lignes de facture créées à partir d'un accord sont synchronisées.</span><span class="sxs-lookup"><span data-stu-id="6785f-130">This field helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="6785f-131">La valeur est **vrai** si la ligne de facture provient d'un accord.</span><span class="sxs-lookup"><span data-stu-id="6785f-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="6785f-132">**Date de facture** est un champ obligatoire dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6785f-132">**Invoice date** is a mandatory field in Finance and Operations.</span></span> <span data-ttu-id="6785f-133">Par conséquent, le champ doit spécifier une valeur dans Field Service avant que la synchronisation se produise.</span><span class="sxs-lookup"><span data-stu-id="6785f-133">Therefore, the field must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="6785f-134">Pour répondre à cette exigence, la logique suivante est ajoutée :</span><span class="sxs-lookup"><span data-stu-id="6785f-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="6785f-135">Si le champ **Date de facture** est vide sur l'entité **Facture** (c'est-à-dire qu'il n'a pas de valeur), il est défini sur la date actuelle lorsqu'une une ligne de facture provenant d'un accord est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="6785f-135">If the **Invoice Date** field is blank on the **Invoice** entity (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="6785f-136">L'utilisateur peut modifier le champ **Date de facture**.</span><span class="sxs-lookup"><span data-stu-id="6785f-136">The user can change the **Invoice Date** field.</span></span> <span data-ttu-id="6785f-137">Toutefois, lorsque l'utilisateur essaie d'enregistrer une facture qui provient d'un accord, il reçoit une erreur du processus d'entreprise si le champ **Date de facture** est vide sur la facture.</span><span class="sxs-lookup"><span data-stu-id="6785f-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** field is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="6785f-138">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="6785f-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="6785f-139">Dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6785f-139">In Finance and Operations</span></span>

<span data-ttu-id="6785f-140">Une origine de facture doit être paramétrée pour l'intégration, afin de distinguer les factures financières de Finance and Operations créées à partir de factures d'accord dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="6785f-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Finance and Operations that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="6785f-141">Lorsqu'une facture a une origine de facture de type **Intégration de la facture à l'accord**, le champ **Numéro de facture externe** s'affiche dans l'en-tête **Facture client**.</span><span class="sxs-lookup"><span data-stu-id="6785f-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="6785f-142">En plus de s'afficher dans l'en-tête de facture, l'information **Numéro de facture externe** peut être utilisée pour garantir que les factures qui sont créées à partir de factures d'accord de Field Service sont ignorées lors de la synchronisation de facture entre Finance and Operations et Field Service.</span><span class="sxs-lookup"><span data-stu-id="6785f-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Finance and Operations to Field Service.</span></span>

1. <span data-ttu-id="6785f-143">Accédez à **Comptabilité client** \> **Paramétrage** \> **Codes d'origine de la facture**.</span><span class="sxs-lookup"><span data-stu-id="6785f-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="6785f-144">Sélectionnez **Nouveau** pour créer une origine de facture.</span><span class="sxs-lookup"><span data-stu-id="6785f-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="6785f-145">Dans le champ **Origine de la facture**, entrez un nom pour l'origine de la facture, par exemple **FS**.</span><span class="sxs-lookup"><span data-stu-id="6785f-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="6785f-146">Dans le champ **Description**, entrez une description, comme **Facture d'accord Field Service**.</span><span class="sxs-lookup"><span data-stu-id="6785f-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="6785f-147">Activez la case à cocher **Affectation du type d'origine**.</span><span class="sxs-lookup"><span data-stu-id="6785f-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="6785f-148">Définissez le champ **Type d'origine de la facture** sur **Intégration de la facture à l'accord**.</span><span class="sxs-lookup"><span data-stu-id="6785f-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="6785f-149">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6785f-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="6785f-150">Dans le projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="6785f-150">In the Data Integration project</span></span>

<span data-ttu-id="6785f-151">Tâche : **Lignes de facture**</span><span class="sxs-lookup"><span data-stu-id="6785f-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="6785f-152">Assurez-vous que la valeur par défaut du champ Finance and Operations **Valeur d'affichage du compte principal** est mise à jour pour correspondre à la valeur souhaitée.</span><span class="sxs-lookup"><span data-stu-id="6785f-152">Make sure that the default value for the Finance and Operations field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="6785f-153">Le modèle de valeur par défaut est **401100**.</span><span class="sxs-lookup"><span data-stu-id="6785f-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="6785f-154">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="6785f-154">Template mapping in Data integration</span></span>

<span data-ttu-id="6785f-155">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="6785f-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a><span data-ttu-id="6785f-156">Factures d'accord (Field Service vers Fin and Ops) : En-têtes de facture</span><span class="sxs-lookup"><span data-stu-id="6785f-156">Agreement invoices (Field Service to Fin and Ops): Invoice headers</span></span>

<span data-ttu-id="6785f-157">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="6785f-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a><span data-ttu-id="6785f-158">Factures d'accord (Field Service vers Fin and Ops) : Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="6785f-158">Agreement invoices (Field Service to Fin and Ops): Invoice lines</span></span>

<span data-ttu-id="6785f-159">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="6785f-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>
