---
title: Synchroniser des factures d’accord de Field Service sur des factures financières dans Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les factures d’accord de Dynamics 365 Field Service sur les factures financières dans Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 0942ce83060c186212d7f425f8dbd0a4ca2c09e7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252772"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="3f453-103">Synchroniser des factures d’accord de Field Service sur des factures financières dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3f453-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3f453-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les factures d’accord de Dynamics 365 Field Service sur les factures financières dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3f453-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="3f453-105">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="3f453-105">Templates and tasks</span></span>

<span data-ttu-id="3f453-106">Le modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des factures d’accord de Field Service sur les factures financières de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3f453-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="3f453-107">**Nom du modèle dans l’intégration des données**</span><span class="sxs-lookup"><span data-stu-id="3f453-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="3f453-108">Factures d’accord (Field Service vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="3f453-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="3f453-109">**Noms des tâches dans le projet d’intégration de données**</span><span class="sxs-lookup"><span data-stu-id="3f453-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="3f453-110">En-têtes de facture</span><span class="sxs-lookup"><span data-stu-id="3f453-110">Invoice headers</span></span>
- <span data-ttu-id="3f453-111">Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="3f453-111">Invoice lines</span></span>

<span data-ttu-id="3f453-112">La synchronisation suivante est requise avant que la synchronisation des factures d’accord puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="3f453-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="3f453-113">Comptes (Sales vers Supply Chain Management) - Direct</span><span class="sxs-lookup"><span data-stu-id="3f453-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="3f453-114">Ensemble d’entités</span><span class="sxs-lookup"><span data-stu-id="3f453-114">Entity set</span></span>

| <span data-ttu-id="3f453-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="3f453-115">Field Service</span></span>  | <span data-ttu-id="3f453-116">Gestion de la chaîne d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="3f453-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="3f453-117">factures</span><span class="sxs-lookup"><span data-stu-id="3f453-117">invoices</span></span>       | <span data-ttu-id="3f453-118">En-têtes de facture financière client Dataverse</span><span class="sxs-lookup"><span data-stu-id="3f453-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="3f453-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="3f453-119">invoicedetails</span></span> | <span data-ttu-id="3f453-120">Lignes de facture financière client Dataverse</span><span class="sxs-lookup"><span data-stu-id="3f453-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="3f453-121">Flux d’entité</span><span class="sxs-lookup"><span data-stu-id="3f453-121">Entity flow</span></span>

<span data-ttu-id="3f453-122">Les factures qui sont créées à partir d’un accord dans Field Service peuvent être synchronisées sur Supply Chain Management via un projet d’intégration de données Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3f453-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="3f453-123">Les mises à jour à ces factures sont synchronisées sur les factures financières dans Supply Chain Management si le statut comptable des factures financières est **En cours**.</span><span class="sxs-lookup"><span data-stu-id="3f453-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="3f453-124">Une fois les factures financières validées dans Supply Chain Management, et que le statut comptable est mis jour sur **Terminé**, vous ne pouvez plus synchroniser les mises à jour dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="3f453-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="3f453-125">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="3f453-125">Field Service CRM solution</span></span>

<span data-ttu-id="3f453-126">La colonne **A des lignes provenant d’un accord** a été ajoutée à la table **Facture**.</span><span class="sxs-lookup"><span data-stu-id="3f453-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="3f453-127">Cette colonne permet de garantir que seules les factures créées à partir d’un accord sont synchronisées.</span><span class="sxs-lookup"><span data-stu-id="3f453-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="3f453-128">La valeur est **vrai** si la facture contient au moins une ligne de facture qui provient d’un accord.</span><span class="sxs-lookup"><span data-stu-id="3f453-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="3f453-129">La colonne **Provient d’un accord** a été ajoutée à la table **Ligne facture**.</span><span class="sxs-lookup"><span data-stu-id="3f453-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="3f453-130">Cette colonne permet de garantir que seules les lignes factures créées à partir d’un accord sont synchronisées.</span><span class="sxs-lookup"><span data-stu-id="3f453-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="3f453-131">La valeur est **vrai** si la ligne de facture provient d’un accord.</span><span class="sxs-lookup"><span data-stu-id="3f453-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="3f453-132">**Date de facture** est un champ obligatoire dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3f453-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="3f453-133">Par conséquent, la colonne doit spécifier une valeur dans Field Service avant que la synchronisation se produise.</span><span class="sxs-lookup"><span data-stu-id="3f453-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="3f453-134">Pour répondre à cette exigence, la logique suivante est ajoutée :</span><span class="sxs-lookup"><span data-stu-id="3f453-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="3f453-135">Si la colonne **Date de facture** est vide sur la table **Facture** (c’est-à-dire qu’il n’a pas de valeur), il est défini sur la date actuelle lorsqu’une une ligne de facture provenant d’un accord est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="3f453-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="3f453-136">L’utilisateur peut modifier la colonne **Date de facture**.</span><span class="sxs-lookup"><span data-stu-id="3f453-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="3f453-137">Toutefois, lorsque l’utilisateur essaie d’enregistrer une facture qui provient d’un accord, il reçoit une erreur du processus d’entreprise si la colonne **Date de facture** est vide sur la facture.</span><span class="sxs-lookup"><span data-stu-id="3f453-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="3f453-138">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="3f453-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="3f453-139">Dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3f453-139">In Supply Chain Management</span></span>

<span data-ttu-id="3f453-140">Une origine de facture doit être paramétrée pour l’intégration, afin de distinguer les factures financières de Supply Chain Management créées à partir de factures d’accord dans Field Service.</span><span class="sxs-lookup"><span data-stu-id="3f453-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="3f453-141">Lorsqu’une facture a une origine de facture de type **Intégration de la facture à l’accord**, le champ **Numéro de facture externe** s’affiche dans l’en-tête **Facture client**.</span><span class="sxs-lookup"><span data-stu-id="3f453-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="3f453-142">En plus de s’afficher dans l’en-tête de facture, l’information **Numéro de facture externe** peut être utilisée pour garantir que les factures qui sont créées à partir de factures d’accord de Field Service sont ignorées lors de la synchronisation de facture entre Supply Chain Management et Field Service.</span><span class="sxs-lookup"><span data-stu-id="3f453-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="3f453-143">Accédez à **Comptabilité client** \> **Paramétrage** \> **Codes d’origine de la facture**.</span><span class="sxs-lookup"><span data-stu-id="3f453-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="3f453-144">Sélectionnez **Nouveau** pour créer une origine de facture.</span><span class="sxs-lookup"><span data-stu-id="3f453-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="3f453-145">Dans le champ **Origine de la facture**, entrez un nom pour l’origine de la facture, par exemple **FS**.</span><span class="sxs-lookup"><span data-stu-id="3f453-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="3f453-146">Dans le champ **Description**, entrez une description, comme **Facture d’accord Field Service**.</span><span class="sxs-lookup"><span data-stu-id="3f453-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="3f453-147">Activez la case à cocher **Affectation du type d’origine**.</span><span class="sxs-lookup"><span data-stu-id="3f453-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="3f453-148">Définissez le champ **Type d’origine de la facture** sur **Intégration de la facture à l’accord**.</span><span class="sxs-lookup"><span data-stu-id="3f453-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="3f453-149">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3f453-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="3f453-150">Dans le projet d’intégration des données</span><span class="sxs-lookup"><span data-stu-id="3f453-150">In the Data Integration project</span></span>

<span data-ttu-id="3f453-151">Tâche : **Lignes de facture**</span><span class="sxs-lookup"><span data-stu-id="3f453-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="3f453-152">Assurez-vous que la valeur par défaut du champ Supply Chain Management **Valeur d’affichage du compte principal** est mise à jour pour correspondre à la valeur souhaitée.</span><span class="sxs-lookup"><span data-stu-id="3f453-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="3f453-153">Le modèle de valeur par défaut est **401100**.</span><span class="sxs-lookup"><span data-stu-id="3f453-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3f453-154">Mise en correspondance de modèles dans l’intégration de données</span><span class="sxs-lookup"><span data-stu-id="3f453-154">Template mapping in Data integration</span></span>

<span data-ttu-id="3f453-155">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="3f453-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="3f453-156">Factures d’accord (Field Service vers Supply Chain Management) : En-têtes de facture</span><span class="sxs-lookup"><span data-stu-id="3f453-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="3f453-157">[![Mise en correspondance de modèles dans l’intégration de données](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="3f453-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="3f453-158">Factures d’accord (Field Service vers Supply Chain Management) : Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="3f453-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="3f453-159">[![Mise en correspondance de modèles dans l’intégration de données](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="3f453-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]