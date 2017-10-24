---
title: "Journaux d'opérations diverses"
description: "Cet article décrit les fonctionnalités de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition qui vous permettent d'effectuer le traitement du journal des opérations diverses, ainsi que de garantir que les données correctes sont capturées et que le contrôle interne n'est pas compromis."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 68da281cb4793ed83f70c68d061d327aa8a8c772
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="general-journal-processing"></a><span data-ttu-id="1f91e-103">Journaux d'opérations diverses</span><span class="sxs-lookup"><span data-stu-id="1f91e-103">General journal processing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1f91e-104">Cet article décrit les fonctionnalités de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition qui vous permettent d'effectuer le traitement du journal des opérations diverses, ainsi que de garantir que les données correctes sont capturées et que le contrôle interne n'est pas compromis.</span><span class="sxs-lookup"><span data-stu-id="1f91e-104">This articles describes capabilities in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition that can help make general journal processing easier, and that can also help guarantee that correct data is captured and internal control isn't compromised.</span></span>  

<span data-ttu-id="1f91e-105">Noms de journal</span><span class="sxs-lookup"><span data-stu-id="1f91e-105">Journal names</span></span>

<span data-ttu-id="1f91e-106">Les noms des journaux font partie des zones les plus importantes à paramétrer.</span><span class="sxs-lookup"><span data-stu-id="1f91e-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="1f91e-107">Il est judicieux de définir des noms de journaux spécifiques pour chaque objectif (intersociétés, régularisation et correction d'erreurs, par exemple).</span><span class="sxs-lookup"><span data-stu-id="1f91e-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="1f91e-108">Vous pouvez modifier chaque nom de journal pour faciliter et sécuriser la saisie de données pour chaque objectif.</span><span class="sxs-lookup"><span data-stu-id="1f91e-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="1f91e-109">Vous pouvez paramétrer les éléments suivants sur la page **Noms des journaux** :</span><span class="sxs-lookup"><span data-stu-id="1f91e-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="1f91e-110">**Approbation du workflow** : Pour augmenter le contrôle interne, définissez les workflows de journal qui établissent des seuils d'importance pour les étapes d'approbation et de révision, selon des critères tels que le montant débiteur total.</span><span class="sxs-lookup"><span data-stu-id="1f91e-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="1f91e-111">Vous devez paramétrer les workflows pour les journaux des opérations diverses dans la page **Workflows de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="1f91e-111">You set up workflows for the general journals on the** General ledger workflows** page.</span></span>
-   <span data-ttu-id="1f91e-112">**Valeurs par défaut** : Sélectionnez les valeurs par défaut pour les comptes de contrepartie, la devise et les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="1f91e-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="1f91e-113">**Contrôle des journaux** : Vous pouvez paramétrer des restrictions au niveau de la société et du type de compte, ainsi que les valeurs de segment.</span><span class="sxs-lookup"><span data-stu-id="1f91e-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="1f91e-114">**Exemples**</span><span class="sxs-lookup"><span data-stu-id="1f91e-114">**Examples**</span></span>

<span data-ttu-id="1f91e-115">Un nom de journal peut être utilisé uniquement pour les ajustements.</span><span class="sxs-lookup"><span data-stu-id="1f91e-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="1f91e-116">Dans ce cas, vous pouvez spécifier que seul le type de compte **Comptabilité** est valide dans toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="1f91e-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> <span data-ttu-id="1f91e-117">[![Types de comptes du contrôle des journaux](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="1f91e-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="1f91e-118">Un nom de journal peut être uniquement utilisé pour un segment spécifique ou pour une plage pour des comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="1f91e-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> <span data-ttu-id="1f91e-119">[![Segment de contrôle des journaux](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="1f91e-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="1f91e-120">L'option **Contrepassation automatique** est disponible dans les journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="1f91e-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="1f91e-121">Par exemple, vous avez un ajustement de régularisation dans lequel le document actif n'a pas encore été traité, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="1f91e-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="1f91e-122">[![Contrepassation du journal des opérations diverses](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="1f91e-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="1f91e-123">Le complément Microsoft Excel pour l'entrée de journal fournit un niveau supplémentaire d'automatisation et facilite la saisie des données.</span><span class="sxs-lookup"><span data-stu-id="1f91e-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="1f91e-124">L'action **Ouvrir les lignes dans Excel** est disponible dans les pages **Journal des opérations diverses** et **N° document de journal**.</span><span class="sxs-lookup"><span data-stu-id="1f91e-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="1f91e-125">Dans la page **Journaux périodiques**, vous pouvez paramétrer les journaux récurrents pour automatiser le traitement de journal.</span><span class="sxs-lookup"><span data-stu-id="1f91e-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="1f91e-126">Vous pouvez utiliser les modèles de document à tout moment.</span><span class="sxs-lookup"><span data-stu-id="1f91e-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="1f91e-127">Dans la page **Journaux des opérations diverses**, les actions **Enregistrer** et **Sélectionner le modèle de n° document** se trouvent dans la page **N° document de journal**, sous **Fonctions** pour les lignes de N° document.</span><span class="sxs-lookup"><span data-stu-id="1f91e-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="1f91e-128">Paramétrage associé</span><span class="sxs-lookup"><span data-stu-id="1f91e-128">Related setup</span></span>
<span data-ttu-id="1f91e-129">Le paramétrage suivant n'est pas spécifique aux journaux des opérations diverses, mais il aide à garantir que la saisie de données est correcte et facile.</span><span class="sxs-lookup"><span data-stu-id="1f91e-129">The following setup isn't specific to general journals, but will help guarantee that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="1f91e-130">Compte principal</span><span class="sxs-lookup"><span data-stu-id="1f91e-130">Main account</span></span>

<span data-ttu-id="1f91e-131">Le paramétrage de compte principal fournit de nombreuses options pour le traitement du journal des opérations diverses :</span><span class="sxs-lookup"><span data-stu-id="1f91e-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="1f91e-132">**Obligation de DB/CR** : Utilisez cette option si un compte principal est limité à des transactions de débit ou de crédit.</span><span class="sxs-lookup"><span data-stu-id="1f91e-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="1f91e-133">Le paramétrage est vérifié lors du contrôle ou de la validation du journal.</span><span class="sxs-lookup"><span data-stu-id="1f91e-133">The setup is verified when a journal is validated or posted.</span></span>
-   <span data-ttu-id="1f91e-134">**Compte de contrepartie par défaut**</span><span class="sxs-lookup"><span data-stu-id="1f91e-134">**Default offset account**</span></span>
-   <span data-ttu-id="1f91e-135">**Suspendu** : Permet d'interrompre un compte principal pour la saisie de données dans toutes les sociétés ou pour une société spécifique/des entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="1f91e-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entities.</span></span>
-   <span data-ttu-id="1f91e-136">**Ne pas autoriser la saisie manuelle** : Permet d'empêcher les utilisateurs d'entrer manuellement une valeur pour le compte dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="1f91e-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="1f91e-137">**Valeur par défaut/Contrôler la devise**</span><span class="sxs-lookup"><span data-stu-id="1f91e-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="1f91e-138">**Remplacements des entités juridiques** : Ce paramétrage est spécifique à la société/à l'entité juridique définie :</span><span class="sxs-lookup"><span data-stu-id="1f91e-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="1f91e-139">**Valeur par défaut/Valider une taxe**</span><span class="sxs-lookup"><span data-stu-id="1f91e-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="1f91e-140">**Dimension par défaut** : **Non fixe** ou **Valeur fixe**.</span><span class="sxs-lookup"><span data-stu-id="1f91e-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="1f91e-141">**Valeur fixe** : Aide à garantir que toutes les validations pour ce compte principal utilisent toujours une valeur de dimension paramétrée comme **Fixe**.</span><span class="sxs-lookup"><span data-stu-id="1f91e-141">**Fixed value** will help guarantee that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="1f91e-142">**Contrôle de validation**</span><span class="sxs-lookup"><span data-stu-id="1f91e-142">**Posting validation**</span></span>
    -   <span data-ttu-id="1f91e-143">**Contrôle utilisateur** : Cette option contrôle les utilisateurs qui sont autorisés à valider dans un compte principal.</span><span class="sxs-lookup"><span data-stu-id="1f91e-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="1f91e-144">**Contrôle des types de validation** : Cette option contrôle les types de validations qui sont autorisés pour un compte principal.</span><span class="sxs-lookup"><span data-stu-id="1f91e-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="1f91e-145">Structures de compte et structures de règles avancées</span><span class="sxs-lookup"><span data-stu-id="1f91e-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="1f91e-146">Les structures de compte et les structures de règles avancées sont extrêmement importantes pour garantir que les données requises pour la génération d'états financiers et le suivi de performance sont capturées lors du traitement du journal des opérations diverses et de toute documentation.</span><span class="sxs-lookup"><span data-stu-id="1f91e-146">Accounting structures and advanced rules structures are extremely important for guaranteeing that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="1f91e-147">Les structures de compte et les structures de règles avancées vous permettent d'adapter l'expérience de saisie de données.</span><span class="sxs-lookup"><span data-stu-id="1f91e-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="1f91e-148">Vous pouvez autoriser la saisie de données uniquement pour les dimensions financières pertinentes dans chaque cas, et également appliquer les conditions obligatoires et corriger les données qui sont capturées.</span><span class="sxs-lookup"><span data-stu-id="1f91e-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that mandatory and correct data always be captured.</span></span>

<span data-ttu-id="1f91e-149">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f91e-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="1f91e-150">[Planification : plan de comptes](plan-chart-of-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="1f91e-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="1f91e-151">Créer des règles avancées pour les journaux</span><span class="sxs-lookup"><span data-stu-id="1f91e-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="1f91e-152">Créer une entrée de journal à l'aide d'un modèle</span><span class="sxs-lookup"><span data-stu-id="1f91e-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="1f91e-153">Créer et valider des journaux</span><span class="sxs-lookup"><span data-stu-id="1f91e-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="1f91e-154">Valider des journaux périodiques</span><span class="sxs-lookup"><span data-stu-id="1f91e-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="1f91e-155">Traiter le journal de répartition comptable</span><span class="sxs-lookup"><span data-stu-id="1f91e-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)



