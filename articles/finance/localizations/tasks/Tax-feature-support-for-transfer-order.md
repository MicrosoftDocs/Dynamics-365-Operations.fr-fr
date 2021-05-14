---
title: Prise en charge de la fonction de taxe pour les ordres de transfert
description: Cette rubrique explique la prise en charge de la nouvelle fonctionnalité de taxe pour les ordres de transfert à l’aide du service de calcul des taxes.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920953"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="eb96e-103">Prise en charge de la fonction de taxe pour les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="eb96e-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eb96e-104">Cette rubrique fournit des informations sur le calcul des taxes et l’intégration de la validation dans les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="eb96e-105">Cette fonctionnalité vous permet de configurer le calcul et la validation des taxes dans les ordres de transfert pour les transferts de stock.</span><span class="sxs-lookup"><span data-stu-id="eb96e-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="eb96e-106">En vertu de la réglementation de l’Union européenne (UE) sur la taxe sur la valeur ajoutée (TVA), les transferts de stock sont considérés comme des livraisons intracommunautaires et des acquisitions intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="eb96e-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="eb96e-107">Pour configurer et utiliser cette fonctionnalité, vous devez effectuer trois étapes principales :</span><span class="sxs-lookup"><span data-stu-id="eb96e-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="eb96e-108">**Configuration RCS :** dans Regulatory Configuration Service, configurez la fonctionnalité de taxe, les codes taxe et l’applicabilité des codes taxe pour la détermination du code taxe dans les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="eb96e-109">**Configuration Finance :** dans Microsoft Dynamics 365 Finance, activez la fonctionnalité **Taxe dans l’ordre de transfert**, configurez les paramètres du service de taxe pour le stock et configurez les paramètres fiscaux de base.</span><span class="sxs-lookup"><span data-stu-id="eb96e-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="eb96e-110">**Configuration du stock :** paramétrez la configuration du stock pour les transactions d’ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="eb96e-111">Configurer RCS pour les taxes et les transactions d’ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="eb96e-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="eb96e-112">Suivez ces étapes pour configurer la taxe impliquée dans un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="eb96e-113">Dans l’exemple présenté ici, l’ordre de transfert va des Pays-Bas vers la Belgique.</span><span class="sxs-lookup"><span data-stu-id="eb96e-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="eb96e-114">Sur la page **Fonctionnalité de taxe**, sur l’onglet **Versions**, sélectionnez la version provisoire de la fonctionnalité, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Sélection de Modifier](../media/image1.png)

2. <span data-ttu-id="eb96e-116">Sur la page **Configuration des fonctionnalités de taxe**, sur l’onglet **Codes taxe**, sélectionnez **Ajouter** pour créer de nouveaux codes taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="eb96e-117">Pour cet exemple, trois codes taxe sont créés : **NL-Exempt**, **BE-RC-21** et **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="eb96e-118">Lorsqu’un ordre de transfert est expédié depuis un entrepôt aux Pays-Bas, le code d’exonération de TVA néerlandais (**NL-Exempt**) est appliqué.</span><span class="sxs-lookup"><span data-stu-id="eb96e-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="eb96e-119">Créez le code taxe **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="eb96e-120">Sélectionnez **Ajouter**, entrez **NL-Exempt** dans le champ **Code taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="eb96e-121">Sélectionnez **Par montant net** dans le champ **Composant de taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="eb96e-122">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-122">Select **Save**.</span></span>
        4. <span data-ttu-id="eb96e-123">Sélectionnez **Ajouter** dans la table **Taux**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="eb96e-124">Faites basculer l’option **Est exonéré** sur **Oui** dans la section **Général**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![Code taxe NL-Exempt](../media/image2.png)

    - <span data-ttu-id="eb96e-126">Lorsqu’un ordre de transfert est reçu dans un entrepôt de Belgique, le mécanisme de taxe au preneur est appliqué en utilisant les codes taxe **BE-RC-21** et **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="eb96e-127">Créez le code taxe **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="eb96e-128">Sélectionnez **Ajouter**, entrez **BE-RC-21** dans le champ **Code taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="eb96e-129">Sélectionnez **Par montant net** dans le champ **Composant de taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="eb96e-130">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-130">Select **Save**.</span></span>
        4. <span data-ttu-id="eb96e-131">Sélectionnez **Ajouter** dans la table **Taux**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="eb96e-132">Entrez **-21** dans le champ **Taux de taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="eb96e-133">Faites basculer l’option **Est une taxe au preneur** sur **Oui** dans la section **Général**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="eb96e-134">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-134">Select **Save**.</span></span>

        ![Code taxe BE-RC-21 pour les taxes au preneur](../media/image3.png)
        
        <span data-ttu-id="eb96e-136">Créez le code taxe **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="eb96e-137">Sélectionnez **Ajouter**, entrez **BE-RC-21** dans le champ **Code taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="eb96e-138">Sélectionnez **Par montant net** dans le champ **Composant de taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="eb96e-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-139">Select **Save**.</span></span>
        4. <span data-ttu-id="eb96e-140">Sélectionnez **Ajouter** dans la table **Taux**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="eb96e-141">Entrez **21** dans le champ **Taux de taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="eb96e-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-142">Select **Save**.</span></span>

        ![Code taxe BE-RC+21 pour les taxes au preneur](../media/image4.png)

3. <span data-ttu-id="eb96e-144">Définissez l’applicabilité des codes taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="eb96e-145">Sélectionnez **Gérer les colonnes**, puis sélectionnez les colonnes à utiliser pour créer le tableau d’applicabilité.</span><span class="sxs-lookup"><span data-stu-id="eb96e-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="eb96e-146">Assurez-vous d’ajouter les colonnes **Processus d’entreprise** et **Directions de taxe** à la table.</span><span class="sxs-lookup"><span data-stu-id="eb96e-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="eb96e-147">Les deux colonnes sont essentielles à la fonctionnalité de taxe dans les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="eb96e-148">Ajoutez des règles d’applicabilité.</span><span class="sxs-lookup"><span data-stu-id="eb96e-148">Add applicability rules.</span></span> <span data-ttu-id="eb96e-149">Ne laissez pas vides les champs **Codes taxe**, **Groupe de taxes** et **Groupe de taxes d’article**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="eb96e-150">Ajoutez une nouvelle règle pour l’expédition des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="eb96e-151">Sélectionnez **Ajouter** dans la table **Règles d’applicabilité**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="eb96e-152">Dans le champ **Processus d’entreprise**, sélectionnez **Stock** pour rendre la règle applicable à un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="eb96e-153">Dans le champ **Expédier depuis le pays/ la région**, entrez **NLD**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="eb96e-154">Dans le champ **Expédier vers le pays/ la région**, entrez **BEL**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="eb96e-155">Dans le champ **Direction de taxe**, sélectionnez **Sortie** pour rendre la règle applicable à l’expédition des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="eb96e-156">Dans le champ **Codes taxe**, sélectionnez **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="eb96e-157">Dans les champs **Groupe de taxes** et **Groupe de taxes d’article**, saisissez le groupe de taxes de vente et le groupe de taxes de vente d’article associés qui sont définis dans votre système Finance.</span><span class="sxs-lookup"><span data-stu-id="eb96e-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="eb96e-158">Ajoutez une autre règle pour la réception des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="eb96e-159">Sélectionnez **Ajouter** dans la table **Règles d’applicabilité**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="eb96e-160">Dans le champ **Processus d’entreprise**, sélectionnez **Stock** pour rendre la règle applicable à un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="eb96e-161">Dans le champ **Expédier depuis le pays/ la région**, entrez **NLD**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="eb96e-162">Dans le champ **Expédier vers le pays/ la région**, entrez **BEL**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="eb96e-163">Dans le champ **Direction de taxe**, sélectionnez **Entrée** pour rendre la règle applicable à la réception des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="eb96e-164">Dans le champ **Codes taxe**, sélectionnez **BE-RC+21** et **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="eb96e-165">Dans les champs **Groupe de taxes** et **Groupe de taxes d’article**, saisissez le groupe de taxes de vente et le groupe de taxes de vente d’article associés qui sont définis dans votre système Finance.</span><span class="sxs-lookup"><span data-stu-id="eb96e-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Règles d’applicabilité](../media/image5.png)

4. <span data-ttu-id="eb96e-167">Complétez et publiez la nouvelle version de la fonctionnalité de taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="eb96e-168">[![Changer le statut de la nouvelle version](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="eb96e-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="eb96e-169">Configurer Finance pour les transactions d’ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="eb96e-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="eb96e-170">Procédez comme suit pour activer et paramétrer les taxes pour les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="eb96e-171">Dans Finance, accédez à **Espaces de travail** \> **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="eb96e-172">Dans la liste, recherchez et sélectionnez la fonctionnalité **Taxe dans l’ordre de transfert**, puis sélectionnez **Activer maintenant** pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="eb96e-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eb96e-173">La fonctionnalité **Taxe dans l’ordre de transfert** dépend entièrement du service de taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="eb96e-174">Par conséquent, elle ne peut être activée qu’après avoir installé le service de taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Fonctionnalités Taxe dans l’ordre de transfert](../media/image7.png)

3. <span data-ttu-id="eb96e-176">Activez le service de taxe et sélectionnez le processus d’entreprise **Inventaire**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eb96e-177">Vous devez effectuer cette étape pour chaque entité juridique dans Finance pour laquelle vous souhaitez rendre disponibles le service de taxe et la fonctionnalité de taxe dans les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="eb96e-178">Accédez à **Taxe** \> **Paramétrage** \> **Configuration de taxe** \> **Configuration du service de taxe**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="eb96e-179">Dans le champ **Processus d’entreprise**, sélectionnez **Inventaire**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Définition du champ Processus d’entreprise](../media/image8.png)

4. <span data-ttu-id="eb96e-181">Vérifiez que le mécanisme de taxe au preneur est configuré.</span><span class="sxs-lookup"><span data-stu-id="eb96e-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="eb96e-182">Accédez à **Comptabilité** \> **Paramétrage** \> **Paramètres** puis, sur l’onglet **Taxe au preneur**, vérifiez que l’option **Activer la taxe au preneur** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Activer l’option de taxe au preneur](../media/image9.png)

5. <span data-ttu-id="eb96e-184">Vérifiez que les codes taxe, les groupes de taxe, les groupes de taxes d’article et les numéros d’immatriculation de TVA associés ont été configurés dans Finance conformément aux instructions du service de taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="eb96e-185">Créez un compte de transit provisoire.</span><span class="sxs-lookup"><span data-stu-id="eb96e-185">Set up an interim transit account.</span></span> <span data-ttu-id="eb96e-186">Cette étape n’est requise que lorsque la taxe appliquée à un ordre de transfert n’est pas applicable à un mécanisme d’exonération de taxe ou de taxe au preneur.</span><span class="sxs-lookup"><span data-stu-id="eb96e-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="eb96e-187">Accédez à **Taxe** \> **Paramétrage** \> **Taxe de vente** \> **Groupes de validations dans la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="eb96e-188">Dans le champ **Transit provisoire**, sélectionnez un compte général.</span><span class="sxs-lookup"><span data-stu-id="eb96e-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Sélection d’un compte de transit provisoire](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="eb96e-190">Configurer l’inventaire de base pour les transactions d’ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="eb96e-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="eb96e-191">Suivez ces étapes pour configurer l’inventaire de base afin d’activer les transactions d’ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="eb96e-192">Créez des sites d’expédition et de livraison pour vos entrepôts dans différents pays ou régions, et ajoutez l’adresse principale de chaque site.</span><span class="sxs-lookup"><span data-stu-id="eb96e-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="eb96e-193">Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Sites**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="eb96e-194">Sélectionnez **Nouveau** pour créer le site que vous attribuerez ultérieurement à un entrepôt.</span><span class="sxs-lookup"><span data-stu-id="eb96e-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="eb96e-195">Répétez l’étape 2 pour tous les autres sites que vous devez créer.</span><span class="sxs-lookup"><span data-stu-id="eb96e-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb96e-196">L’un des sites que vous créez doit être nommé **Transit**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="eb96e-197">Dans les étapes ultérieures de cette procédure, vous affecterez ce site à l’entrepôt de transit, de sorte que les justificatifs d’inventaire liés à la taxe puissent être validés dans les transactions « expédition » et « réception » pour les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="eb96e-198">L’adresse du site de transit n’a pas d’importance pour le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="eb96e-199">Par conséquent, vous ne pouvez pas le laisser vide.</span><span class="sxs-lookup"><span data-stu-id="eb96e-199">Therefore, you can leave it blank.</span></span>

    ![Paramétrage des sites](../media/image11.png)

2. <span data-ttu-id="eb96e-201">Créez des entrepôts d’expédition, de transit et de livraison.</span><span class="sxs-lookup"><span data-stu-id="eb96e-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="eb96e-202">Les informations d’adresse conservées dans un entrepôt remplaceront l’adresse du site lors du calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="eb96e-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="eb96e-203">Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="eb96e-204">Sélectionnez **Nouveau** pour créer un entrepôt et affectez-le au site correspondant.</span><span class="sxs-lookup"><span data-stu-id="eb96e-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="eb96e-205">Répétez l’étape 2 pour créer un entrepôt pour chaque site, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="eb96e-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Paramétrage d’entrepôts](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="eb96e-207">Pour un entrepôt d’expédition, un entrepôt de transit doit être sélectionné dans le champ **Entrepôt de transit** pour les transactions d’ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Sélection d’un entrepôt de transit](../media/image13.png)

3. <span data-ttu-id="eb96e-209">Vérifiez que la configuration de la validation du stock est paramétrée pour les transactions d’ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="eb96e-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="eb96e-210">Accédez à **Gestion des stocks** \> **Paramétrage** \> **Validation** \> **Validation**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="eb96e-211">Sur l’onglet **Inventaire**, vérifiez qu’un compte général est configuré pour les deux validations **Sortie de stock** et **Réception de stock**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Configuration des validations Sortie de stock et Réception de stock](../media/image14.png)

    3. <span data-ttu-id="eb96e-213">Vérifiez qu’un compte général est configuré pour la validation **Somme à payer entre unités**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Configuration de la validation Somme à payer entre unités](../media/image15.png)

    4. <span data-ttu-id="eb96e-215">Vérifiez qu’un compte général est configuré pour la validation **Somme à recevoir entre unités**.</span><span class="sxs-lookup"><span data-stu-id="eb96e-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Configuration de la validation Somme à recevoir entre unités](../media/image16.png)
