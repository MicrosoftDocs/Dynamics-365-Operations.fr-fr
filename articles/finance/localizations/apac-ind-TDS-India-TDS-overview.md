---
title: Aperçu de l'impôt indien déduit à la source (TDS)
description: Cette rubrique fournit des informations détaillées sur l'impôt indien déduit à la source (TDS). La documentation TDS couvre la fonctionnalité de cette capacité.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023251"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="3a202-104">Aperçu de l'impôt indien déduit à la source (TDS)</span><span class="sxs-lookup"><span data-stu-id="3a202-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a202-105">Cette rubrique fournit des informations détaillées sur l'impôt indien déduit à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="3a202-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="3a202-106">La documentation TDS couvre la fonctionnalité de cette capacité.</span><span class="sxs-lookup"><span data-stu-id="3a202-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="3a202-107">Il explique également comment effectuer la configuration de base pour TDS, calculer TDS sur les transactions, terminer le processus de règlement TDS, enregistrer les numéros de certificat TDS et générer des requêtes TDS, des relevés TDS et des certificats TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="3a202-108">La documentation comprend les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a202-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="3a202-109">Paramétrage de base pour TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="3a202-110">Concepteur de formule et fonctionnalité de limite de seuil utilisées pour le calcul TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="3a202-111">Calcul du TDS sur les factures, les paiements, les billets à ordre et les transactions intersociétés</span><span class="sxs-lookup"><span data-stu-id="3a202-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="3a202-112">Processus de règlement périodique de TDS et règlement des montants TDS aux fournisseurs de l'autorité TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="3a202-113">Enregistrement et mise à jour des numéros et dates des certificats TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="3a202-114">Introduction à TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-114">Introduction to TDS</span></span>

<span data-ttu-id="3a202-115">Conformément à la loi de 1961 sur l'impôt sur le revenu, l'impôt sur le revenu est déduit à la source par le bénéficiaire du service au moment du paiement anticipé ou de la comptabilisation du crédit, selon la première éventualité.</span><span class="sxs-lookup"><span data-stu-id="3a202-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="3a202-116">La personne qui effectue le paiement doit déduire le montant de la taxe et ne payer que le solde net au fournisseur du service.</span><span class="sxs-lookup"><span data-stu-id="3a202-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="3a202-117">Le TDS est appliqué aux services que le gouvernement spécifie, et la taxe est déduite en utilisant les taux que le gouvernement spécifie pour une période.</span><span class="sxs-lookup"><span data-stu-id="3a202-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="3a202-118">Le taux de déduction est basé sur le statut de l'entité qui reçoit le paiement ou fournit le service.</span><span class="sxs-lookup"><span data-stu-id="3a202-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="3a202-119">Les statuts comprennent **Individuel**, **Famille indivise hindoue** (**HUF**), **Compagnie**, **Entreprise**, **Association de personnes** (**AOP**), **Corps d'individus** (**BOI**) et **Autorité locale**.</span><span class="sxs-lookup"><span data-stu-id="3a202-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="3a202-120">Les sections suivantes répertorient les services sur lesquels TDS est appliqué, comme spécifié par le gouvernement indien.</span><span class="sxs-lookup"><span data-stu-id="3a202-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="3a202-121">**Résidents**</span><span class="sxs-lookup"><span data-stu-id="3a202-121">**Residents**</span></span>

- <span data-ttu-id="3a202-122">Revenus de salaires (en vertu de l'article 192)</span><span class="sxs-lookup"><span data-stu-id="3a202-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="3a202-123">Revenu des intérêts sur les titres (en vertu de l'article 193)</span><span class="sxs-lookup"><span data-stu-id="3a202-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="3a202-124">Revenus des dividendes (en vertu de l'article 194)</span><span class="sxs-lookup"><span data-stu-id="3a202-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="3a202-125">Revenus des intérêts (en vertu de l'article 194A)</span><span class="sxs-lookup"><span data-stu-id="3a202-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="3a202-126">Revenus de loteries ou de puzzles (en vertu de l'article 194B)</span><span class="sxs-lookup"><span data-stu-id="3a202-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="3a202-127">Gains courses hippiques, etc. (en vertu de l'article 194BB)</span><span class="sxs-lookup"><span data-stu-id="3a202-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="3a202-128">Entrepreneurs et sous-traitants (en vertu de l'article 194C)</span><span class="sxs-lookup"><span data-stu-id="3a202-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="3a202-129">Commission des assurances (en vertu de l'article 194D)</span><span class="sxs-lookup"><span data-stu-id="3a202-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="3a202-130">Revenu des dépôts dans le cadre du régime d'épargne national (en vertu de l'article 194EE)</span><span class="sxs-lookup"><span data-stu-id="3a202-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="3a202-131">Revenu provenant d'un fonds commun de placement ou d'une UTI (en vertu de l'article 194F)</span><span class="sxs-lookup"><span data-stu-id="3a202-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="3a202-132">Commission, rémunération, prix, etc., en vente ou à la loterie (en vertu de l'article 194G)</span><span class="sxs-lookup"><span data-stu-id="3a202-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="3a202-133">Paiement de la commission ou du courtage (en vertu de l'article 194H)</span><span class="sxs-lookup"><span data-stu-id="3a202-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="3a202-134">Loyer (en vertu de l'article 194I)</span><span class="sxs-lookup"><span data-stu-id="3a202-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="3a202-135">Service professionnel (en vertu de l'article 194J)</span><span class="sxs-lookup"><span data-stu-id="3a202-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="3a202-136">Revenus des unités (en vertu de l'article 194K)</span><span class="sxs-lookup"><span data-stu-id="3a202-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="3a202-137">Paiement d'une indemnité lors de l'acquisition de certains biens immobiliers (en vertu de l'article 194LA)</span><span class="sxs-lookup"><span data-stu-id="3a202-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="3a202-138">**Non résidents**</span><span class="sxs-lookup"><span data-stu-id="3a202-138">**Non-residents**</span></span>

- <span data-ttu-id="3a202-139">Paiements aux sportifs non résidents ou à une association sportive (en vertu de l'article 194E)</span><span class="sxs-lookup"><span data-stu-id="3a202-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="3a202-140">Autres sommes (en vertu de l'article 195)</span><span class="sxs-lookup"><span data-stu-id="3a202-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="3a202-141">Revenu relatif aux unités de non-résidents (en vertu de l'article 196A)</span><span class="sxs-lookup"><span data-stu-id="3a202-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="3a202-142">Revenu provenant d'obligations en devises ou d'actions d'une société indienne (en vertu de l'article 196C)</span><span class="sxs-lookup"><span data-stu-id="3a202-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="3a202-143">Revenus des investisseurs institutionnels étrangers provenant de titres (en vertu de l'article 196D)</span><span class="sxs-lookup"><span data-stu-id="3a202-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="3a202-144">Salaire et tous les autres revenus positifs sous n'importe quelle rubrique sur le revenu (article 192)</span><span class="sxs-lookup"><span data-stu-id="3a202-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="3a202-145">Intérêts sur les valeurs mobilières (article 193)</span><span class="sxs-lookup"><span data-stu-id="3a202-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="3a202-146">Intérêts autres que les intérêts sur les valeurs mobilières (article 194A)</span><span class="sxs-lookup"><span data-stu-id="3a202-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="3a202-147">Paiements aux prestataires et sous-traitants (Article 194C)</span><span class="sxs-lookup"><span data-stu-id="3a202-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="3a202-148">Gains de loterie ou de mots croisés (article 194B)</span><span class="sxs-lookup"><span data-stu-id="3a202-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="3a202-149">Gains courses hippiques, etc. (Article 194BB)</span><span class="sxs-lookup"><span data-stu-id="3a202-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="3a202-150">Commission des assurances couvrant tous les paiements pour l'acquisition des activités d'assurance (article 194D)</span><span class="sxs-lookup"><span data-stu-id="3a202-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="3a202-151">Tout intérêt autre que l'intérêt sur les titres payables à des non-résidents n'étant pas une société ou à une société étrangère (article 195)</span><span class="sxs-lookup"><span data-stu-id="3a202-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="3a202-152">Paiement à un sportif non-résident, y compris un athlète ou une association ou institution sportive.</span><span class="sxs-lookup"><span data-stu-id="3a202-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="3a202-153">En cas de sportif non-résident, les paiements au titre des publicités ainsi que des articles sur tout jeu/sport en Inde dans les journaux, magazines, etc.</span><span class="sxs-lookup"><span data-stu-id="3a202-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="3a202-154">Est inclus (article 194E)</span><span class="sxs-lookup"><span data-stu-id="3a202-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="3a202-155">Paiement au titre des dépôts sous NSS \[Régime national d'épargne\] (Article 194EE)</span><span class="sxs-lookup"><span data-stu-id="3a202-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="3a202-156">Paiement au titre du rachat de parts par un fonds commun de placement ou UTI (article 194F)</span><span class="sxs-lookup"><span data-stu-id="3a202-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="3a202-157">Paiement de la commission ou du courtage (Article 194H)</span><span class="sxs-lookup"><span data-stu-id="3a202-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="3a202-158">Paiement du loyer (article 194I)</span><span class="sxs-lookup"><span data-stu-id="3a202-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="3a202-159">Paiement d'honoraires pour services professionnels ou techniques (article 194J)</span><span class="sxs-lookup"><span data-stu-id="3a202-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="3a202-160">Commission à Stockiest, distributeurs, acheteurs et vendeurs de billets de loterie, y compris la rémunération ou le prix sur ces billets (article 194G)</span><span class="sxs-lookup"><span data-stu-id="3a202-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="3a202-161">Revenu provenant de parts achetées en devises ou gain en capital à long terme découlant du transfert de ces parts achetées en monnaie étrangère (chapitre 196B)</span><span class="sxs-lookup"><span data-stu-id="3a202-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="3a202-162">Paiement de tout revenu à des non-résidents au titre des intérêts ou des dividendes sur les obligations et les actions (article 196C)</span><span class="sxs-lookup"><span data-stu-id="3a202-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="3a202-163">Le TDS est calculé sur les achats, les ventes, les retours sur ventes, les notes de crédit, les acquisitions d'immobilisations, les paiements anticipés, les paiements anticipés, les billets à ordre, la taxe de travaux et les transactions intersociétés.</span><span class="sxs-lookup"><span data-stu-id="3a202-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="3a202-164">Dans le scénario fiscal indien actuel, le TDS n'est pas calculé sur les transactions de vente.</span><span class="sxs-lookup"><span data-stu-id="3a202-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="3a202-165">Cependant, le système comprend une disposition pour calculer le TDS récupérable sur les transactions de vente, en particulier pour les transactions intersociétés.</span><span class="sxs-lookup"><span data-stu-id="3a202-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="3a202-166">Le calcul de TDS prend toujours en compte le seuil et le seuil d'exception définis pour le composant TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="3a202-167">Le processus de règlement périodique de TDS doit être exécuté et les paiements TDS doivent être réglés aux fournisseurs autorisés de TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="3a202-168">Les numéros et dates des certificats TDS reçus des fournisseurs ou des clients peuvent être enregistrés et mis à jour.</span><span class="sxs-lookup"><span data-stu-id="3a202-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="3a202-169">De plus, les relevés trimestriels du formulaire 26Q et du formulaire 27Q, ainsi que le certificat du formulaire 16A pour TDS, peuvent être générés dans Finance.</span><span class="sxs-lookup"><span data-stu-id="3a202-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="3a202-170">Configuration et utilisation de TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-170">Setting up and working with TDS</span></span>

<span data-ttu-id="3a202-171">Voici un aperçu du processus de configuration et d'utilisation de TDS :</span><span class="sxs-lookup"><span data-stu-id="3a202-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="3a202-172">**Paramétrage TDS :**</span><span class="sxs-lookup"><span data-stu-id="3a202-172">**TDS setup:**</span></span>

    - <span data-ttu-id="3a202-173">Paramétrage :</span><span class="sxs-lookup"><span data-stu-id="3a202-173">Parameter setup:</span></span>

        - <span data-ttu-id="3a202-174">Dans Paramètres de Comptabilité, activez les paramètres liés à TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="3a202-175">Dans Paramètres de Comptabilité, configurez la souche de numéros pour les paiements de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="3a202-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="3a202-176">Définition des paramètres dans Comptabilité client et Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3a202-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="3a202-177">Paramétrage de base :</span><span class="sxs-lookup"><span data-stu-id="3a202-177">Basic setup:</span></span>

        - <span data-ttu-id="3a202-178">Configurez les numéros d'enregistrement TDS pour une entreprise, des clients et des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="3a202-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="3a202-179">Paramétrer des groupes de composants TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="3a202-180">Configurez les composants TDS, associez-leur des groupes de composants TDS et définissez leur seuil et leur seuil d'exception.</span><span class="sxs-lookup"><span data-stu-id="3a202-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="3a202-181">Configurez les autorités TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="3a202-182">Paramétrez des périodes de règlement TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="3a202-183">Configurez les codes de taxe TDS et associez-leur des composants TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="3a202-184">Configurez les groupes de taxes TDS et associez-leur des codes de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="3a202-185">Dans le concepteur de formules, définissez une formule pour calculer TDS pour un groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="3a202-186">Enregistrez les numéros de certificat de concession TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="3a202-187">Comptes généraux et configuration de la société :</span><span class="sxs-lookup"><span data-stu-id="3a202-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="3a202-188">Configurez la comptabilité fournisseur et comptabilité client TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="3a202-189">Configurez une déduction fiscale et un numéro de compte de recouvrement (TAN) et une catégorie de type de déducteur pour l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a202-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="3a202-190">Autre configuration :</span><span class="sxs-lookup"><span data-stu-id="3a202-190">Other setup:</span></span>

        - <span data-ttu-id="3a202-191">Configurez un calendrier de paiement qui inclut l'allocation TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="3a202-192">Paramétrer un type de frais de paiement pour les paiements TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="3a202-193">Configurez des informations sur les groupes TDS, les numéros de compte permanents (PAN) et les TAN pour les fournisseurs et les clients.</span><span class="sxs-lookup"><span data-stu-id="3a202-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="3a202-194">**Calcul de TDS dans les transactions :**</span><span class="sxs-lookup"><span data-stu-id="3a202-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="3a202-195">Factures et paiements</span><span class="sxs-lookup"><span data-stu-id="3a202-195">Invoices and payments</span></span>
    - <span data-ttu-id="3a202-196">Billets à ordre</span><span class="sxs-lookup"><span data-stu-id="3a202-196">Promissory notes</span></span>
    - <span data-ttu-id="3a202-197">Paiements anticipés</span><span class="sxs-lookup"><span data-stu-id="3a202-197">Advance payments</span></span>
    - <span data-ttu-id="3a202-198">Acomptes</span><span class="sxs-lookup"><span data-stu-id="3a202-198">Prepayments</span></span>

3. <span data-ttu-id="3a202-199">**Règlement TDS :**</span><span class="sxs-lookup"><span data-stu-id="3a202-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="3a202-200">Processus de règlement périodique de TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="3a202-201">Règlement des paiements TDS aux fournisseurs de l'autorité TDS et génération d'un challan TDS</span><span class="sxs-lookup"><span data-stu-id="3a202-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="3a202-202">**Demandes de renseignements, déclarations et certificat TDS :**</span><span class="sxs-lookup"><span data-stu-id="3a202-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="3a202-203">Enregistrez et mettez à jour des numéros et dates des certificats TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="3a202-204">Générez une demande TDS et une demande TDS validée.</span><span class="sxs-lookup"><span data-stu-id="3a202-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="3a202-205">Générez les relevés trimestriels des formulaires 27A, 26Q et 27Q TDS et e-TDS.</span><span class="sxs-lookup"><span data-stu-id="3a202-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="3a202-206">Générez un certificat de l'écran 16A.</span><span class="sxs-lookup"><span data-stu-id="3a202-206">Generate a Form 16A TDS certificate.</span></span>
