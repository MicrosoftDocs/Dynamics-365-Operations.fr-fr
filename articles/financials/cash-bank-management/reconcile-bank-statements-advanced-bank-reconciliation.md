---
title: "Rapprochement de relevés bancaires à l'aide du rapprochement bancaire avancé"
description: "La fonctionnalité de rapprochement bancaire avancée vous permet d'importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Cette rubrique explique le processus de rapprochement."
author: saraschi2
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 263bfe858f2ca5f7fe2f7426565938899d98130f
ms.openlocfilehash: bdd9d24ed64f583394ab67e1deec84d1d776962f
ms.contentlocale: fr-fr
ms.lasthandoff: 01/11/2018

---

# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a><span data-ttu-id="6628d-104">Rapprochement de relevés bancaires à l'aide du rapprochement bancaire avancé</span><span class="sxs-lookup"><span data-stu-id="6628d-104">Reconcile bank statements by using advanced bank reconciliation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6628d-105">La fonctionnalité de rapprochement bancaire avancée vous permet d'importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6628d-105">The Advanced bank reconciliation feature lets you import electronic bank statements and automatically reconcile them with bank transactions in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="6628d-106">Cette rubrique explique le processus de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-106">This topic explains the reconciliation process.</span></span>  

<a name="import-an-electronic-bank-statement"></a><span data-ttu-id="6628d-107">Importer un relevé bancaire électronique</span><span class="sxs-lookup"><span data-stu-id="6628d-107">Import an electronic bank statement</span></span>
-----------------------------------

<span data-ttu-id="6628d-108">Vous importez vos relevés bancaires à l’aide de l'action **Importer un relevé** sur la page **Relevés bancaires**.</span><span class="sxs-lookup"><span data-stu-id="6628d-108">You import your bank statements by using the **Import statement** action on the **Bank statements** page.</span></span> <span data-ttu-id="6628d-109">Sur le relevé bancaire, le compte bancaire est identifié grâce à une combinaison de valeurs qui sont définies sur les détails du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-109">On the bank statement, the bank account is identified through a combination of values that are set on the bank account details.</span></span> <span data-ttu-id="6628d-110">Ces valeurs comprennent le nom de la banque, le numéro du compte bancaire, le numéro de routage, le code SWIFT et le numéro IBAN.</span><span class="sxs-lookup"><span data-stu-id="6628d-110">These values include the bank name, bank account number, routing number, Society for Worldwide Interbank Financial Telecommunication (SWIFT) code, and International Bank Account Number (IBAN).</span></span> 

<span data-ttu-id="6628d-111">Vous pouvez télécharger un relevé bancaire qui contient des informations pour un ou plusieurs comptes.</span><span class="sxs-lookup"><span data-stu-id="6628d-111">You can upload a bank statement that contains information for either a single account or multiple accounts.</span></span> <span data-ttu-id="6628d-112">S'il existe plusieurs comptes, les comptes peuvent être dans plusieurs entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="6628d-112">If there are multiple accounts, the accounts can be in different legal entities.</span></span>

-   <span data-ttu-id="6628d-113">Pour importer un fichier de relevé bancaire unique pour un seul compte, définissez l'option **Importer le relevé bancaire pour plusieurs comptes bancaires dans toutes les entités juridiques** sur **Non** et sélectionnez le compte bancaire associé au relevé.</span><span class="sxs-lookup"><span data-stu-id="6628d-113">To import a single bank statement file for a single account, set the **Import statement for multiple bank accounts in all legal entities** option to **No**, and select the bank account that is associated with the statement.</span></span> <span data-ttu-id="6628d-114">Cliquez sur **Parcourir** pour sélectionner le fichier de relevé bancaire associé, puis cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="6628d-114">Click **Browse** to select the associated bank statement file, and then click **Upload**.</span></span>
-   <span data-ttu-id="6628d-115">Pour importer un fichier de relevé bancaire unique pour plusieurs comptes, définissez l'option **Importer le relevé bancaire pour plusieurs comptes bancaires dans toutes les entités juridiques** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6628d-115">To import a single bank statement file for multiple accounts, set the **Import statement for multiple bank accounts in all legal entities** option to **Yes**.</span></span> <span data-ttu-id="6628d-116">Cliquez sur **Parcourir** pour sélectionner le fichier de relevé bancaire associé, puis cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="6628d-116">Click **Browse** to select the associated bank statement file, and then click **Upload**.</span></span>

<span data-ttu-id="6628d-117">Si aucun relevé du fichier électronique ne peut être associé à un compte bancaire à l'aide de les champs d'identification, ils ne sont pas importés.</span><span class="sxs-lookup"><span data-stu-id="6628d-117">If any statements in the electronic file can't be associated with a bank account by using the identifying fields, they won't be imported.</span></span> <span data-ttu-id="6628d-118">Toutefois, les autres relevés du fichier peuvent encore être importés.</span><span class="sxs-lookup"><span data-stu-id="6628d-118">However, other statements in the file can still be imported.</span></span> <span data-ttu-id="6628d-119">L'utilisateur reçoit un message indiquant que l'importation des relevés bancaires était un échec pour des comptes bancaires spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6628d-119">The user then receives a message that states that the import of bank statements was unsuccessful for specific bank accounts.</span></span> <span data-ttu-id="6628d-120">Notez que l'utilisateur qui importe le fichier de relevé bancaire doit avoir accès à une entité juridique pour importer les relevés des comptes bancaires de cette entité juridique.</span><span class="sxs-lookup"><span data-stu-id="6628d-120">Note that the user who is importing the bank statement file must have access to a legal entity to import statements for that legal entity's bank accounts.</span></span> 

<span data-ttu-id="6628d-121">Vous pouvez utiliser un fichier compressé pour télécharger plusieurs fichiers de relevé dans Finance and Operations en un seul processus.</span><span class="sxs-lookup"><span data-stu-id="6628d-121">You can use a zip file to upload multiple statement files to Finance and Operations in a single process.</span></span> <span data-ttu-id="6628d-122">Pour importer plusieurs fichiers de relevé bancaire pour plusieurs comptes, combinez tous les fichiers de relevé bancaire en un seul fichier zip.</span><span class="sxs-lookup"><span data-stu-id="6628d-122">To import multiple bank statement files for multiple accounts, combine all the bank statement files into one zip file.</span></span> <span data-ttu-id="6628d-123">Dans la boîte de dialogue **Importez les relevés bancaires**, définissez l'option **Importer le relevé bancaire pour plusieurs comptes bancaires dans toutes les entités juridiques** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6628d-123">In the **Import bank statements** dialog box, set the **Import statement for multiple bank accounts in all legal entities** option to **Yes**.</span></span> <span data-ttu-id="6628d-124">Cliquez sur **Parcourir** pour sélectionner le fichier zip contenant les fichiers de relevé bancaire, puis cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="6628d-124">Click **Browse** to select the zip file that contains the bank statement files, and then click **Upload**.</span></span> <span data-ttu-id="6628d-125">Le processus d'importation identifiera le fichier compressé et téléchargera chaque relevé inclus dans celui-ci, indépendamment de l'entité juridique du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-125">The import process will recognize the zip file and upload each statement that is included in it, regardless of the legal entity of the bank account.</span></span> 

<span data-ttu-id="6628d-126">Une option **Rapprocher après importation** est disponible.</span><span class="sxs-lookup"><span data-stu-id="6628d-126">A **Reconcile after import** option is available.</span></span> <span data-ttu-id="6628d-127">Lorsque vous définissez cette option sur **Oui**, le système valide automatiquement le relevé bancaire, crée un nouveau rapprochement bancaire et une feuille de calcul et exécute l’ensemble de règles de correspondance par défaut quand le relevé bancaire est chargé.</span><span class="sxs-lookup"><span data-stu-id="6628d-127">When you set this option to **Yes**, the system automatically validates the bank statement, creates a new bank reconciliation and worksheet, and runs the Default matching rule set when the bank statement is uploaded.</span></span> <span data-ttu-id="6628d-128">Cette fonctionnalité automatise le processus jusqu’au point où les transactions doivent être manuellement mises en correspondance.</span><span class="sxs-lookup"><span data-stu-id="6628d-128">This functionality automates the process up to the point where transactions must be manually matched.</span></span>

## <a name="validate-the-bank-statement"></a><span data-ttu-id="6628d-129">Valider le relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="6628d-129">Validate the bank statement</span></span>
<span data-ttu-id="6628d-130">Pour valider un relevé, cliquez sur **Valider** sur la page **Relevés bancaires**.</span><span class="sxs-lookup"><span data-stu-id="6628d-130">To validate a statement, on the **Bank statements** page, click **Validate**.</span></span> <span data-ttu-id="6628d-131">Les relevés bancaires doivent être validés avant de pouvoir être rapprochés.</span><span class="sxs-lookup"><span data-stu-id="6628d-131">Bank statements must be validated before they can be reconciled.</span></span> <span data-ttu-id="6628d-132">Cette étape est effectuée automatiquement si vous avez défini l'option **Rapprocher après l'importation** sur **Oui** au moment de l’importation.</span><span class="sxs-lookup"><span data-stu-id="6628d-132">This step is automatically completed if you set the **Reconcile after import** option to **Yes** at the time of import.</span></span> 

<span data-ttu-id="6628d-133">La validation du relevé bancaire permet de vérifier les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6628d-133">Bank statement validation verifies the following details:</span></span>

-   <span data-ttu-id="6628d-134">Le relevé bancaire correspond au compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6628d-134">The bank statement matches the selected bank account.</span></span>
-   <span data-ttu-id="6628d-135">La devise du relevé bancaire correspond à la devise du compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6628d-135">The bank statement currency matches the bank account currency.</span></span>
-   <span data-ttu-id="6628d-136">Le solde d’ouverture du relevé correspond au solde de clôture du relevé précédent du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-136">The opening balance of the statement equals the closing balance of the previous statement for the bank account.</span></span>
-   <span data-ttu-id="6628d-137">La date ne chevauche pas la date d’un autre relevé bancaire pour le même compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-137">The date doesn’t overlap the date for another bank statement for the same bank account.</span></span>
-   <span data-ttu-id="6628d-138">Il n’existe aucun écart dans les dates de relevés pour le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-138">There are no gaps in the dates for statements for the bank account.</span></span>
-   <span data-ttu-id="6628d-139">Les dates sur les lignes du relevé se situent entre la date de début et de date de fin du relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-139">Dates on the statement lines are between the from-date and to-date of the bank statement.</span></span>
-   <span data-ttu-id="6628d-140">Le solde d’ouverture et les montants des lignes récapitulatives sont égaux au solde de fin.</span><span class="sxs-lookup"><span data-stu-id="6628d-140">The opening balance and summarized line amounts equal the ending balance.</span></span>

<span data-ttu-id="6628d-141">Lorsque la validation est terminée, le statut du relevé bancaire est mis à jour sur **Validé**.</span><span class="sxs-lookup"><span data-stu-id="6628d-141">When the validation is completed, the status of the bank statement is updated to **Validated**.</span></span> <span data-ttu-id="6628d-142">Un relevé bancaire doit être validé avant de pouvoir être rapproché.</span><span class="sxs-lookup"><span data-stu-id="6628d-142">A bank statement must be validated before it can be reconciled.</span></span>

## <a name="reconcile-the-bank-statement"></a><span data-ttu-id="6628d-143">Rapprochez le relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-143">Reconcile the bank statement</span></span>
<span data-ttu-id="6628d-144">Une fois que vous avez importé un relevé bancaire électronique et validé le relevé sur la page **Relevés bancaires**, vous pouvez rapprocher le relevé bancaire à l’aide des pages **Rapprochement bancaire** et **Feuille de calcul de rapprochement bancaire**.</span><span class="sxs-lookup"><span data-stu-id="6628d-144">After you’ve imported an electronic bank statement and validated the statement on the **Bank statements** page, you can reconcile the bank statement by using the **Bank reconciliation** and **Bank reconciliation worksheet** pages.</span></span> 

<span data-ttu-id="6628d-145">Sur la page **Rapprochement bancaire**, cliquez sur **Nouveau** pour créer un rapprochement, puis sélectionnez le compte bancaire du relevé qui a été importé.</span><span class="sxs-lookup"><span data-stu-id="6628d-145">On the **Bank reconciliation** page, click **New** to create a new reconciliation, and then select the bank account of the statement that was imported.</span></span> <span data-ttu-id="6628d-146">Un compte bancaire peut avoir uniquement un rapprochement bancaire en cours.</span><span class="sxs-lookup"><span data-stu-id="6628d-146">A bank account can have only one open bank reconciliation.</span></span> <span data-ttu-id="6628d-147">La date limite détermine les transactions de relevé bancaire et les transactions bancaires d'Operations qui figurent sur la feuille de calcul de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-147">The cut-off date determines the bank statement transactions and Operations bank transactions that are included on the reconciliation worksheet.</span></span> <span data-ttu-id="6628d-148">Par défaut, la date système actuelle est utilisée comme date limite, mais vous pouvez modifier la date de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-148">By default, the current system date is used as the cut-off date, but you can change the date for the reconciliation.</span></span> <span data-ttu-id="6628d-149">Les informations d’en-tête restantes sont automatiquement extraites du relevé.</span><span class="sxs-lookup"><span data-stu-id="6628d-149">The remaining header information is automatically taken from the statement.</span></span> <span data-ttu-id="6628d-150">Cette étape est effectuée automatiquement si vous avez défini l'option **Rapprocher après l'importation** sur **Oui** au moment de l’importation.</span><span class="sxs-lookup"><span data-stu-id="6628d-150">This step is automatically completed if you set the **Reconcile after import** option to **Yes** at the time of import.</span></span> 

<span data-ttu-id="6628d-151">Sur la page **Rapprochement bancaire**, cliquez sur **Feuille de calcul** pour ouvrir la page **Feuille de calcul de rapprochement bancaire**.</span><span class="sxs-lookup"><span data-stu-id="6628d-151">On the **Bank reconciliation** page, click **Worksheet** to open the **Bank reconciliation worksheet** page.</span></span> <span data-ttu-id="6628d-152">Si vous avez défini l'option **Rapprocher après l'importation** sur **Oui**, l'ensemble de règles de correspondance par défaut est exécuté automatiquement pour le rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-152">If you set the **Reconcile after import** option to **Yes**, the Default matching rule set is automatically run for the reconciliation.</span></span> <span data-ttu-id="6628d-153">Pour exécuter manuellement des règles de correspondance, cliquez sur **Exécuter les règles de correspondance** pour sélectionner les ensembles de règles de correspondance ou les règles de correspondance à vérifier par rapport aux relevés bancaires.</span><span class="sxs-lookup"><span data-stu-id="6628d-153">To manually run matching rules, click **Run matching rules** to select the matching rule sets or matching rules to run against the bank transactions.</span></span> <span data-ttu-id="6628d-154">Si vous avez de nombreuses transactions à traiter, vous pouvez effectuer cette étape sous forme de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="6628d-154">If you have many transactions to process, you can complete this step as a batch process.</span></span> 

<span data-ttu-id="6628d-155">La page **Feuille de calcul de rapprochement bancaire** comporte quatre grilles qui contiennent des transactions.</span><span class="sxs-lookup"><span data-stu-id="6628d-155">The **Bank reconciliation worksheet** page has four grids that contain transactions.</span></span> <span data-ttu-id="6628d-156">Les deux grilles supérieures affichent les transactions du relevé bancaire et d'Operations qui n’ont pas encore été associées.</span><span class="sxs-lookup"><span data-stu-id="6628d-156">The two upper grids show transactions from the bank statement and Operations that haven’t yet been matched.</span></span> <span data-ttu-id="6628d-157">Les deux grilles inférieures affichent les transactions rapprochées.</span><span class="sxs-lookup"><span data-stu-id="6628d-157">The two lower grids show matched transactions.</span></span> <span data-ttu-id="6628d-158">L'onglet **Détails de transaction de relevé bancaire** affiche les détails de la transaction de relevé bancaire non rapprochée qui est sélectionnée dans la grille supérieure.</span><span class="sxs-lookup"><span data-stu-id="6628d-158">The **Bank statement transaction details** tab shows details for the unmatched bank statement transaction that is selected in the upper grid.</span></span> 

<span data-ttu-id="6628d-159">Il existe trois méthodes pour mettre en correspondance ou pour rapprocher des transactions de relevé bancaire :</span><span class="sxs-lookup"><span data-stu-id="6628d-159">There are three ways to match or reconcile bank statement transactions:</span></span>

-   <span data-ttu-id="6628d-160">Mettre en correspondance les transactions avec les transactions bancaires Operations.</span><span class="sxs-lookup"><span data-stu-id="6628d-160">Match the transactions with Operations bank transactions.</span></span>
-   <span data-ttu-id="6628d-161">Mettre en correspondance les transactions avec une transaction de relevé bancaire de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="6628d-161">Match the transactions with a reversal bank statement transaction.</span></span>
-   <span data-ttu-id="6628d-162">Marquer les transactions comme **Nouveau**, afin de les valider ultérieurement comme transactions bancaires dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6628d-162">Mark the transactions as **New**, so that they can be posted later as a bank transaction in Finance and Operations.</span></span>

<span data-ttu-id="6628d-163">Pour mettre en correspondance des transactions manuellement, sélectionnez les transactions dans la grille **Transactions de relevé bancaire**, sélectionnez les transactions correspondantes dans la grille **Transactions bancaires Operations**, puis cliquez sur **Correspondance**.</span><span class="sxs-lookup"><span data-stu-id="6628d-163">To manually match transactions, select the transactions in the **Bank statement transactions** grid, select the corresponding transactions in the **Operations bank transactions** grid, and then click **Match**.</span></span> <span data-ttu-id="6628d-164">Les transactions sélectionnées sont déplacées dans les grilles supérieures pour les opérations non rapprochées vers les grilles inférieures pour les transactions rapprochées.</span><span class="sxs-lookup"><span data-stu-id="6628d-164">The selected transactions are moved from the upper grids for unmatched transactions to the lower grids for matched transactions.</span></span> <span data-ttu-id="6628d-165">En outre, le total des montants rapprochés et non rapprochés sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="6628d-165">Additionally, the matched and unmatched total amounts are updated.</span></span> <span data-ttu-id="6628d-166">Vous pouvez avoir des correspondances de transactions une à une, plusieurs-à-une et plusieurs-à-plusieurs.</span><span class="sxs-lookup"><span data-stu-id="6628d-166">You can have one-to-one, many-to-one, and many-to-many transaction matches.</span></span> <span data-ttu-id="6628d-167">Les correspondances doivent suivre les règles de différences de dates autorisées et de mappage de type de transaction.</span><span class="sxs-lookup"><span data-stu-id="6628d-167">Matches must follow the rules for allowed date differences and transaction type mapping.</span></span> <span data-ttu-id="6628d-168">Ces règles sont définies sur la page **Paramètres de gestion de la trésorerie et de la banque**.</span><span class="sxs-lookup"><span data-stu-id="6628d-168">These rules are set on the **Cash and bank management parameters** page.</span></span>

<span data-ttu-id="6628d-169">Des différences minimes peuvent se produire pendant le rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-169">Penny differences might occur in your reconciliation.</span></span> <span data-ttu-id="6628d-170">Vous pouvez mettre en correspondance une transaction de relevé bancaire unique et une transaction bancaire Operations unique qui présentent des différences minimes si celles-ci sont comprises dans le montant de tolérance défini par le champ **Différence minime autorisée** sur le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-170">You can match a single bank statement transaction and a single Operations bank transaction that have penny differences if the penny differences are within the tolerance amount that is defined by the **Allowed penny difference** field on the bank account.</span></span> <span data-ttu-id="6628d-171">Le montant est affiché dans le champ **Montant de la correction** de la transaction bancaire Operations mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="6628d-171">The amount is shown in the **Correction amount** field on the matched Operations bank transaction.</span></span> <span data-ttu-id="6628d-172">Lorsque le rapprochement bancaire est marqué comme rapproché, les corrections sont automatiquement validées à l'aide du compte principal défini dans le type de transaction bancaire associé.</span><span class="sxs-lookup"><span data-stu-id="6628d-172">When the bank reconciliation is marked as reconciled, corrections are automatically posted by using the main account that is defined on the associated bank transaction type.</span></span> <span data-ttu-id="6628d-173">Les corrections ne sont pas prises en charge pour les types de document **Chèque** et **Dépôt**.</span><span class="sxs-lookup"><span data-stu-id="6628d-173">Corrections aren't supported for the **Check** and **Deposit** document types.</span></span> 

<span data-ttu-id="6628d-174">Les contrepassations de transaction de relevé bancaire sont mises en correspondance à l’aide de la feuille de calcul de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-174">Bank statement transaction reversals are matched by using the reconciliation worksheet.</span></span> <span data-ttu-id="6628d-175">Deux lignes de relevé peuvent être mises en correspondance si les montants sont opposés, et si l'une des transactions est marquée comme une contrepassation.</span><span class="sxs-lookup"><span data-stu-id="6628d-175">Two statement lines can be matched if the amounts are opposite, and if one of the transactions is marked as a reversal.</span></span> <span data-ttu-id="6628d-176">Vous pouvez également définir une règle de correspondance pour l'action **Effacer les lignes de relevés de contrepassation**.</span><span class="sxs-lookup"><span data-stu-id="6628d-176">You can also set up a matching rule for the **Clear reversal statement lines** action.</span></span>

<span data-ttu-id="6628d-177">Les transactions bancaires Operations de contrepassation doivent être rapprochées à l’aide de la page **Transactions bancaires Operations**.</span><span class="sxs-lookup"><span data-stu-id="6628d-177">Reversed Operations bank transactions must be reconciled by using the **Operations bank transactions** page.</span></span> <span data-ttu-id="6628d-178">Vous pouvez rapprocher deux transactions bancaires Operations ensemble si les documents ont un compte bancaire, un type de document et une référence de paiement identiques, et s’ils ont des montants opposés.</span><span class="sxs-lookup"><span data-stu-id="6628d-178">You can reconcile two Operations bank transactions together if the documents have the same bank account, document type, and payment reference, and if they have opposite amounts.</span></span> <span data-ttu-id="6628d-179">Vous pouvez également rapprocher un chèque annulé unique pour empêcher ces transactions de figurer sur la feuille de calcul de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-179">You can also reconcile a single canceled check to prevent those transactions from appearing on the reconciliation worksheet.</span></span> 

<span data-ttu-id="6628d-180">S’il y a des transactions initiées par la banque, telles que des intérêts, des commissions et des frais, qui ne sont pas encore dans Finance and Operations, vous pouvez les ajouter à un journal associé au rapprochement de relevé bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6628d-180">If there are new bank-initiated transactions, such as interest, fees, and charges, that aren’t yet in Finance and Operations, you can add them to a journal that is associated with the selected bank statement reconciliation.</span></span> <span data-ttu-id="6628d-181">Sélectionnez une transaction de relevé bancaire dans la grille **Transactions de relevé bancaire** pour les opérations non rapprochées, puis cliquez sur **Marquer comme nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6628d-181">Select a bank statement transaction in the **Bank statement transactions** grid for unmatched transactions, and then click **Mark as new**.</span></span> <span data-ttu-id="6628d-182">Le statut de la transaction est défini sur **Nouveau**, et la transaction est déplacée vers la grille **Transactions de relevé bancaire** pour les transactions rapprochées.</span><span class="sxs-lookup"><span data-stu-id="6628d-182">The status of the transaction is set to **New**, and the transaction is moved to the **Bank statement transactions** grid for matched transactions.</span></span> <span data-ttu-id="6628d-183">Vous validez les transactions marquées **Nouveau** ultérieurement, à partir de la page **Relevé bancaire**.</span><span class="sxs-lookup"><span data-stu-id="6628d-183">You will post transactions that are marked as **New** later, from the **Bank statement** page.</span></span> 

<span data-ttu-id="6628d-184">Vous pouvez supprimer la mise en correspondance des transactions qui ont été rapprochées incorrectement.</span><span class="sxs-lookup"><span data-stu-id="6628d-184">You can unmatch transactions that were incorrectly matched.</span></span> <span data-ttu-id="6628d-185">Sélectionnez la transaction de relevé bancaire correspondante, puis cliquez sur **Sans correspondance**.</span><span class="sxs-lookup"><span data-stu-id="6628d-185">Select the matched bank statement transaction, and then click **Unmatch**.</span></span> <span data-ttu-id="6628d-186">Toutes les transactions associées sont déplacées vers les grilles supérieures pour les opérations non rapprochées, et le total des montants correspondants et sans correspondance sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="6628d-186">All associated transactions are moved back to the upper grids for unmatched transactions, and the matched and unmatched total amounts are updated.</span></span> 

<span data-ttu-id="6628d-187">Après avoir effectué votre processus de rapprochement, vous devez marquer la feuille de calcul de rapprochement bancaire comme étant rapprochée.</span><span class="sxs-lookup"><span data-stu-id="6628d-187">After completing your reconciliation process, you should mark the Bank reconciliation worksheet as reconciled.</span></span>  <span data-ttu-id="6628d-188">Ce processus valide automatiquement les montants de correction à l'aide des comptes définis sur la page **Type de transaction bancaire**.</span><span class="sxs-lookup"><span data-stu-id="6628d-188">This process will automatically post correction amounts using the accounts set on the **Bank transaction type** page.</span></span>  <span data-ttu-id="6628d-189">Le rapprochement bancaire pour un relevé peut être marqué comme rapproché à tout moment, même s'il existe des lignes de relevé bancaire qui n'ont pas encore été rapprochées.</span><span class="sxs-lookup"><span data-stu-id="6628d-189">The bank reconciliation for a statement can be marked as reconciled at any time, even if there are bank statement lines that have not yet been matched.</span></span>  <span data-ttu-id="6628d-190">Les transactions qui ne correspondent pas passeront automatiquement à la prochaine feuille de calcul de rapprochement en tant que transactions de relevé de compte non rapprochées à rapprocher.</span><span class="sxs-lookup"><span data-stu-id="6628d-190">The unmatched transactions will automatically move to the next reconciliation worksheet as unmatched bank statement transactions to be reconciled.</span></span>  <span data-ttu-id="6628d-191">Notez qu'une fois qu'un rapprochement de relevé bancaire a été marqué comme rapproché, il ne peut pas être annulé.</span><span class="sxs-lookup"><span data-stu-id="6628d-191">Note that once a bank statement reconciliation has been marked as reconciled, it cannot be undone.</span></span>  <span data-ttu-id="6628d-192">Le rapprochement ne sera plus modifiable et vous n'aurez plus la possibilité de mettre à jour ce rapprochement.</span><span class="sxs-lookup"><span data-stu-id="6628d-192">The reconciliation will no longer be editable and you will no longer have the ability to make updates to that reconciliation.</span></span>

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a><span data-ttu-id="6628d-193">Valider les transactions associées au rapprochement</span><span class="sxs-lookup"><span data-stu-id="6628d-193">Post new transactions that are associated with the reconciliation</span></span>
<span data-ttu-id="6628d-194">Les transactions de relevé bancaire qui vous avez marquées comme **Nouveau** sur la feuille de calcul de rapprochement sont validées sur la page **Relevé bancaire**.</span><span class="sxs-lookup"><span data-stu-id="6628d-194">Bank statement transactions that you marked as **New** on the reconciliation worksheet are posted on the **Bank statement** page.</span></span> <span data-ttu-id="6628d-195">Sur la page **Relevé bancaire**, sélectionnez l'ID de relevé pour afficher les détails du relevé.</span><span class="sxs-lookup"><span data-stu-id="6628d-195">On the **Bank statement** page, select the statement ID to view the statement details.</span></span> <span data-ttu-id="6628d-196">Sur le menu **Comptabilité**, vous pouvez utiliser les options **Afficher les distributions** et **Afficher la comptabilité** pour afficher des détails sur les nouvelles transactions et les écritures comptables associées.</span><span class="sxs-lookup"><span data-stu-id="6628d-196">On the **Accounting** menu, you can use the **View distributions** and **View accounting** options to view details behind the new transactions and the associated ledger entries.</span></span> <span data-ttu-id="6628d-197">Sélectionnez l'option **Valider** pour valider les lignes de relevé bancaire qui sont marquées comme **Nouveau** dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="6628d-197">Select the **Post** option to post the bank statement lines that are marked as **New** to the general ledger.</span></span> <span data-ttu-id="6628d-198">Notez que la validation ne peut être effectuée qu’une seule fois par relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="6628d-198">Note that posting can be completed only one time per bank statement.</span></span>



