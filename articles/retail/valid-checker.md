---
title: Vérificateur de cohérence des transactions de vente au détail
description: Cette rubrique décrit la fonctionnalité Vérificateur de cohérence des transactions de vente au détail dans Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: db01a12b92574b41f1f4fe7281c23992e0d36027
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "302283"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="c958a-103">Vérificateur de cohérence des transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="c958a-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="c958a-104">Cette rubrique décrit la fonctionnalité Vérificateur de cohérence des transactions de vente au détail introduite dans Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span><span class="sxs-lookup"><span data-stu-id="c958a-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="c958a-105">Le vérificateur de cohérence identifie et isole les transactions incohérentes avant leur prélèvement par le processus de validation des relevés.</span><span class="sxs-lookup"><span data-stu-id="c958a-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="c958a-106">Lorsqu'un relevé est validé dans Retail, la validation peut échouer en raison de données incohérentes dans les tables de transactions de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="c958a-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="c958a-107">Ce problème de données peut être causé par des problèmes imprévus dans l'application POS, ou si les transactions ont été mal importées à partir de systèmes POS tiers.</span><span class="sxs-lookup"><span data-stu-id="c958a-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="c958a-108">Voici des exemples de cas où ces incohérences peuvent apparaître :</span><span class="sxs-lookup"><span data-stu-id="c958a-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="c958a-109">Le total des transactions dans la table des en-têtes ne correspond pas au total des transactions sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="c958a-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="c958a-110">Le nombre de lignes dans la table des en-têtes ne correspond pas au nombre de lignes dans la table des transactions.</span><span class="sxs-lookup"><span data-stu-id="c958a-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="c958a-111">Les taxes dans la table des en-têtes ne correspondent pas au montant des taxes sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="c958a-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="c958a-112">Lorsque des transactions incohérentes sont prélevées par le processus de validation des relevés, des factures client et des journaux de paiement incohérents sont créés, et l'ensemble du processus de validation des relevés échoue.</span><span class="sxs-lookup"><span data-stu-id="c958a-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="c958a-113">La récupération des relevés de cet état implique des correctifs de données complexes sur plusieurs tables de transactions.</span><span class="sxs-lookup"><span data-stu-id="c958a-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="c958a-114">Le vérificateur de cohérence des transactions de vente au détail empêche ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="c958a-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="c958a-115">Le graphique suivant illustre le processus de validation avec le vérificateur de cohérence des transactions.</span><span class="sxs-lookup"><span data-stu-id="c958a-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="c958a-116">![Processus de validation des relevés avec le vérificateur de cohérence des transactions](./media/validchecker.png "Processus de validation des relevés avec le vérificateur de cohérence des transactions")</span><span class="sxs-lookup"><span data-stu-id="c958a-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transsaction consistency checker")</span></span>

<span data-ttu-id="c958a-117">Le processus de traitement par lots **Valider les transactions en magasin** vérifie la cohérence des tables de transactions de vente au détail pour les scénarios suivants.</span><span class="sxs-lookup"><span data-stu-id="c958a-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="c958a-118">Compte client - Valide que le compte client dans les tables de transactions de vente au détail existe dans les données principales client HQ.</span><span class="sxs-lookup"><span data-stu-id="c958a-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="c958a-119">Nombre de lignes - Valide que le nombre de lignes capturées dans la table des en-têtes de transaction correspond au nombre de lignes dans les tables de transactions de vente.</span><span class="sxs-lookup"><span data-stu-id="c958a-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="c958a-120">Paramétrer le vérificateur de cohérence</span><span class="sxs-lookup"><span data-stu-id="c958a-120">Set up the consistency checker</span></span>
<span data-ttu-id="c958a-121">Configurez le processus de traitement par lots « Valider les transactions en magasin » sous **Vente au détail \> Informatique au détail \> Validation POS** pour les exécutions périodiques.</span><span class="sxs-lookup"><span data-stu-id="c958a-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="c958a-122">Le traitement par lots peut être planifié en fonction de la hiérarchie d'organisation du magasin, qui est similaire au mode de paramétrage des processus « Calculer les relevés en mode de traitement par lots » et « Valider les relevés en mode de traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="c958a-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="c958a-123">Il est recommandé de configurer ce processus de traitement par lots pour qu'il s'exécute plusieurs fois par jour et de le planifier pour qu'il s'exécute à la fin de l'exécution de chaque tâche P.</span><span class="sxs-lookup"><span data-stu-id="c958a-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="c958a-124">Résultats du processus de validation</span><span class="sxs-lookup"><span data-stu-id="c958a-124">Results of validation process</span></span>
<span data-ttu-id="c958a-125">Les résultats du contrôle de validation par le processus de traitement par lots sont référencés dans la transaction de vente au détail appropriée.</span><span class="sxs-lookup"><span data-stu-id="c958a-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="c958a-126">Le champ **Statut de validation** dans l'enregistrement de la transaction de vente au détail est défini sur **Réussite** ou **Erreur**, et la date de la dernière exécution de la validation s'affiche dans le champ **Heure de la dernière validation**.</span><span class="sxs-lookup"><span data-stu-id="c958a-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="c958a-127">Pour afficher un texte plus descriptif de l'erreur associée à un échec de validation, sélectionnez l'enregistrement de transaction de vente au détail approprié et cliquez sur le bouton **Erreurs de validation**.</span><span class="sxs-lookup"><span data-stu-id="c958a-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="c958a-128">Les transactions qui échouent au contrôle de validation et les transactions qui n'ont pas encore été validées ne seront pas extraites dans des relevés.</span><span class="sxs-lookup"><span data-stu-id="c958a-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="c958a-129">Au cours du processus « Calcul du relevé », les utilisateurs seront informés si des transactions auraient dû être incluses dans le relevé.</span><span class="sxs-lookup"><span data-stu-id="c958a-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="c958a-130">Si une erreur de validation est détectée, le seul moyen de corriger l'erreur est de contacter le support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c958a-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="c958a-131">Dans une prochaine version, la fonctionnalité sera ajoutée afin que les utilisateurs puissent corriger les enregistrements en échec via l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c958a-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="c958a-132">Les fonctionnalités de journalisation et d'audit seront également disponibles pour suivre l'historique des modifications.</span><span class="sxs-lookup"><span data-stu-id="c958a-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="c958a-133">Des règles de validation supplémentaires pour prendre en charge d'autres scénarios seront ajoutées dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="c958a-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
