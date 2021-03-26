---
title: Créer un classeur Excel pour modifier les transactions de vente au détail
description: Cette rubrique décrit la procédure de création d’un classeur Excel afin que vous puissiez modifier les transactions de vente au détail dans Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3a4bc0a91ee2215dcde2f18575d58ab1ef2f5581
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207941"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="b7ee0-103">Créer un classeur Excel pour modifier les transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="b7ee0-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7ee0-104">Cette rubrique décrit la procédure de création d’un classeur Excel afin que vous puissiez modifier les transactions de vente au détail dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b7ee0-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="b7ee0-105">Overview</span></span>

<span data-ttu-id="b7ee0-106">Il existe un modèle Excel prédéfini auquel les clients peuvent accéder à partir de différentes parties du système et utiliser pour modifier et vérifier les transactions de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="b7ee0-107">Cependant, les clients peuvent également créer un classeur Excel personnalisé à cet effet.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="b7ee0-108">Créer et configurer un classeur Excel</span><span class="sxs-lookup"><span data-stu-id="b7ee0-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="b7ee0-109">Pour créer et configurer un classeur Excel afin de pouvoir modifier les transactions de vente au détail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="b7ee0-110">Ouvrez Excel et créez un classeur vierge.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="b7ee0-111">Dans l’onglet **Insérer**, sélectionnez **Mes compléments**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="b7ee0-112">Dans le volet droit, sélectionnez le lien **Ajouter des informations sur le serveur**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="b7ee0-113">Entrez l’URL du serveur, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="b7ee0-114">Si vous recevez le message d’erreur « Aucun enregistrement d’applet trouvé », procédez comme suit pour résoudre le problème :</span><span class="sxs-lookup"><span data-stu-id="b7ee0-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="b7ee0-115">Dans Commerce, accédez à **Administration du système \> Paramétrage \> Paramètres des applications Office**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="b7ee0-116">Dans le raccourci **Paramètres d’application**, sélectionnez **Initialiser les paramètres d’application**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="b7ee0-117">Dans la zone de message de confirmation, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="b7ee0-118">Dans le raccourci **Applets enregistrées**, sélectionnez **Initialiser l’enregistrement de l’applet**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="b7ee0-119">Si nécessaire, répétez les trois étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="b7ee0-120">Sélectionnez **Design**, puis sélectionnez **Ajouter une table**.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="b7ee0-121">En fonction des données à modifier, sélectionnez les entités qui doivent être modifiées afin de les ajouter au classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="b7ee0-122">Utilisez la table suivante comme référence.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="b7ee0-123">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="b7ee0-123">Transaction type</span></span> | <span data-ttu-id="b7ee0-124">Entités de données à utiliser</span><span class="sxs-lookup"><span data-stu-id="b7ee0-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="b7ee0-125">Transactions au comptant sans livraison, commandes en ligne, commandes client asynchrones, devis clients asynchrones</span><span class="sxs-lookup"><span data-stu-id="b7ee0-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="b7ee0-126">Transaction (vérifiable), transaction de vente (vérifiable), transactions de paiement (vérifiables), transactions de taxe (vérifiables), transactions de remise (vérifiables), transactions de frais (vérifiables)</span><span class="sxs-lookup"><span data-stu-id="b7ee0-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="b7ee0-127">Remise en banque</span><span class="sxs-lookup"><span data-stu-id="b7ee0-127">Bank drop</span></span> | <span data-ttu-id="b7ee0-128">Transaction (vérifiable), transactions de paiement remises en banque (vérifiables)</span><span class="sxs-lookup"><span data-stu-id="b7ee0-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="b7ee0-129">Mise en coffre-fort</span><span class="sxs-lookup"><span data-stu-id="b7ee0-129">Safe drop</span></span> | <span data-ttu-id="b7ee0-130">Transaction (vérifiable), transactions de paiements remises en coffre-fort (vérifiables)</span><span class="sxs-lookup"><span data-stu-id="b7ee0-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="b7ee0-131">Comptage de caisse</span><span class="sxs-lookup"><span data-stu-id="b7ee0-131">Tender declaration</span></span> | <span data-ttu-id="b7ee0-132">Transaction (vérifiable), transactions de comptage de caisse (vérifiables)</span><span class="sxs-lookup"><span data-stu-id="b7ee0-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="b7ee0-133">Revenu/dépense</span><span class="sxs-lookup"><span data-stu-id="b7ee0-133">Income, Expense</span></span> | <span data-ttu-id="b7ee0-134">Transaction (vérifiable), transactions de revenus/dépenses (vérifiables), transactions de paiement (vérifiables)</span><span class="sxs-lookup"><span data-stu-id="b7ee0-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="b7ee0-135">Déclarer le montant de départ, Vider la caisse, Entrée de fond de caisse, Rendu-monnaie, Facture à payer, Dépôt client</span><span class="sxs-lookup"><span data-stu-id="b7ee0-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="b7ee0-136">Transaction (vérifiable), transactions de paiement (vérifiables)</span><span class="sxs-lookup"><span data-stu-id="b7ee0-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="b7ee0-137">Il est important que vous n’ajoutiez qu’une seule entité de données à chaque classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="b7ee0-138">En outre, tous les champs marqués par un symbole de clé doivent être ajoutés au classeur approprié.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="b7ee0-139">Une fois le classeur configuré, appliquez les filtres requis.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="b7ee0-140">Assurez-vous d’appliquer les mêmes filtres à toutes les feuilles de calcul du fichier.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="b7ee0-141">Évitez de charger de très grandes quantités de données dans le fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="b7ee0-142">Sinon, les performances pourraient être affectées, entraînant un ralentissement d’Excel et de votre système.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="b7ee0-143">Nous vous recommandons de toujours utiliser les filtres « Société » ainsi que « Numéro de relevé » ou « Numéro de transaction » pour votre fichier.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="b7ee0-144">Une fois les filtres configurés, sélectionnez **Rafraîchir** pour charger les données.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="b7ee0-145">Modifiez les données requises, puis publiez-les.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="b7ee0-146">Si le bouton **Publier** n’est pas disponible, certains champs clés n’ont probablement pas été ajoutés au classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="b7ee0-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b7ee0-147">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b7ee0-147">Additional resources</span></span>

[<span data-ttu-id="b7ee0-148">Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison</span><span class="sxs-lookup"><span data-stu-id="b7ee0-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="b7ee0-149">Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones</span><span class="sxs-lookup"><span data-stu-id="b7ee0-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="b7ee0-150">Modifier les dimensions financières des transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="b7ee0-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="b7ee0-151">Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="b7ee0-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]