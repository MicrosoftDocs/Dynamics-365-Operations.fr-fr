---
title: Déboguer les sources de données d'un format ER exécuté pour analyser le flux de données et la transformation
description: Cette rubrique explique comment vous pouvez déboguer les sources de données d'un format ER exécuté pour mieux comprendre le flux de données et la transformation configurés.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 5b51c4beac0ddf1e2b53fe300e10c0f608e5d1e1
ms.sourcegitcommit: 153bb33722c02501bf7bcfd56ac887602d5dfbd3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2020
ms.locfileid: "3318664"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="1764b-103">Déboguer les sources de données d'un format ER exécuté pour analyser le flux de données et la transformation</span><span class="sxs-lookup"><span data-stu-id="1764b-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="1764b-104">Lorsque vous [configurez](tasks/er-format-configuration-2016-11.md) une solution de gestion des états électroniques (ER) pour générer des documents sortants, vous définissez les méthodes qui sont utilisées pour obtenir des données issues de l'application et pour les entrer dans la sortie qui est générée.</span><span class="sxs-lookup"><span data-stu-id="1764b-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="1764b-105">Pour rendre le support de cycle de vie de la solution ER plus efficace, votre solution doit consister en un [modèle de données](general-electronic-reporting.md#DataModelComponent) ER et ses composants de [mise en correspondance](general-electronic-reporting.md#ModelMappingComponent), et aussi un [format](general-electronic-reporting.md#FormatComponentOutbound) ER et ses composants de mise en correspondance, de sorte que la mise en correspondance des modèles est spécifique à l'application, tandis que d'autres composants restent indépendants de l'application.</span><span class="sxs-lookup"><span data-stu-id="1764b-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="1764b-106">Par conséquent, plusieurs composants ER peuvent [affecter](general-electronic-reporting.md#FormatComponentOutbound) le processus de saisie des données dans la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="1764b-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="1764b-107">Parfois, les données de la sortie générée sont différentes des mêmes données dans la base de données d'application.</span><span class="sxs-lookup"><span data-stu-id="1764b-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="1764b-108">Dans ces cas, vous souhaiterez déterminer quel composant ER est responsable de la transformation des données.</span><span class="sxs-lookup"><span data-stu-id="1764b-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="1764b-109">La fonction de débogage de source de données ER réduit considérablement le temps et les coûts impliqués dans cette enquête.</span><span class="sxs-lookup"><span data-stu-id="1764b-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="1764b-110">Vous pouvez interrompre l'exécution d'un format ER et ouvrir l'interface du débogueur de source de données.</span><span class="sxs-lookup"><span data-stu-id="1764b-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="1764b-111">Là, vous pouvez parcourir les sources de données disponibles et sélectionner une source de données individuelle pour l'exécution.</span><span class="sxs-lookup"><span data-stu-id="1764b-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="1764b-112">Cette exécution manuelle simule l'exécution de la source de données pendant l'exécution réelle d'un format ER.</span><span class="sxs-lookup"><span data-stu-id="1764b-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="1764b-113">Le résultat est présenté sur une page où vous pouvez analyser les données reçues.</span><span class="sxs-lookup"><span data-stu-id="1764b-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="1764b-114">Pour activer la fonction de débogage de la source de données, définissez l'option **Activer le débogage des données lors de l'exécution du format** sur **Oui** dans les paramètres utilisateur ER.</span><span class="sxs-lookup"><span data-stu-id="1764b-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="1764b-115">Vous pouvez ensuite démarrer le débogage de la source de données pendant que vous exécutez un format ER pour générer des documents sortants.</span><span class="sxs-lookup"><span data-stu-id="1764b-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="1764b-116">Vous pouvez également utiliser l'option **Démarrer le débogage** pour lancer le débogage de la source de données pour un format ER configuré dans le [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="1764b-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="1764b-117">Cette rubrique fournit des instructions pour lancer le débogage de la source de données pour les formats ER exécutés.</span><span class="sxs-lookup"><span data-stu-id="1764b-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="1764b-118">Il explique comment les informations peuvent vous aider à comprendre le flux de données et les transformations de données.</span><span class="sxs-lookup"><span data-stu-id="1764b-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="1764b-119">Les exemples de cette rubrique utilisent le processus technique pour le traitement des paiements fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1764b-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="1764b-120">Limitations</span><span class="sxs-lookup"><span data-stu-id="1764b-120">Limitations</span></span>

<span data-ttu-id="1764b-121">Le débogueur de source de données peut être utilisé pour accéder aux données des sources de données utilisées dans les formats ER qui sont exécutés pour générer des documents sortants.</span><span class="sxs-lookup"><span data-stu-id="1764b-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="1764b-122">Il ne peut pas être utilisé pour déboguer des sources de données de formats ER conçus pour analyser des documents entrants.</span><span class="sxs-lookup"><span data-stu-id="1764b-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="1764b-123">Les paramètres suivants des formats ER ne sont actuellement pas accessibles pour le débogage de la source de données :</span><span class="sxs-lookup"><span data-stu-id="1764b-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="1764b-124">Transformations de format</span><span class="sxs-lookup"><span data-stu-id="1764b-124">Format transformations</span></span>
- <span data-ttu-id="1764b-125">Format et mise en correspondance des règles de validation</span><span class="sxs-lookup"><span data-stu-id="1764b-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="1764b-126">Activation des expressions</span><span class="sxs-lookup"><span data-stu-id="1764b-126">Enabling expressions</span></span>
- <span data-ttu-id="1764b-127">Détails de la collecte de données en mémoire</span><span class="sxs-lookup"><span data-stu-id="1764b-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1764b-128">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1764b-128">Prerequisites</span></span>

- <span data-ttu-id="1764b-129">Pour terminer les exemples de cette rubrique, vous devez avoir accès aux [rôles](../sysadmin/tasks/assign-users-security-roles.md) suivants :</span><span class="sxs-lookup"><span data-stu-id="1764b-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="1764b-130">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="1764b-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="1764b-131">Consultant fonctionnel de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="1764b-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="1764b-132">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="1764b-132">System administrator</span></span>

- <span data-ttu-id="1764b-133">La société doit être paramétrée sur **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="1764b-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="1764b-134">Suivez les étapes de l'[Annexe 1](#appendix1) de cette rubrique pour télécharger les composants de la solution Microsoft ER requis pour traiter les paiements des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="1764b-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="1764b-135">Suivez les étapes de l'[Annexe 2](#appendix2) de cette rubrique pour préparer la comptabilité fournisseur pour le traitement des paiements des fournisseurs à l'aide de la solution ER que vous téléchargerez.</span><span class="sxs-lookup"><span data-stu-id="1764b-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="1764b-136">Traiter un paiement fournisseur pour obtenir un fichier de paiement</span><span class="sxs-lookup"><span data-stu-id="1764b-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="1764b-137">Suivez les étapes de l'[Annexe 3](#appendix3) de cette rubrique pour traiter les paiements des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="1764b-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Traitement des paiements fournisseur en cours](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="1764b-139">Téléchargez et enregistrez le fichier zip sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="1764b-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="1764b-140">Extrayez le fichier de paiement **Transfert de crédit ISO20022.xml** à partir du fichier zip.</span><span class="sxs-lookup"><span data-stu-id="1764b-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="1764b-141">Ouvrez le fichier de paiement extrait à l'aide de la visionneuse de fichiers XML.</span><span class="sxs-lookup"><span data-stu-id="1764b-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="1764b-142">Dans le fichier de paiement, le code IBAN (International Bank Account Number) du compte bancaire du fournisseur ne contient aucun espace.</span><span class="sxs-lookup"><span data-stu-id="1764b-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="1764b-143">Par conséquent, il diffère de la valeur qui était [entrée](#enteredIBANcode) sur la page **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="1764b-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![Code IBAN sans espaces](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="1764b-145">Vous pouvez utiliser le débogueur de sources de données ER pour savoir quel composant de la solution ER est utilisé pour tronquer les espaces dans le code IBAN.</span><span class="sxs-lookup"><span data-stu-id="1764b-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="1764b-146">Activer le débogage des sources de données</span><span class="sxs-lookup"><span data-stu-id="1764b-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="1764b-147">Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="1764b-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1764b-148">Dans la page **Configurations**, dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="1764b-149">Paramétrez l'option **Activer le débogage des données lors de l'exécution du format** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1764b-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1764b-150">Ce paramètre est spécifique à l'utilisateur et à l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="1764b-150">This parameter is user-specific and company-specific.</span></span>

    ![Boîte de dialogue Paramètres utilisateur](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="1764b-152">Traiter un paiement fournisseur pour le débogage</span><span class="sxs-lookup"><span data-stu-id="1764b-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="1764b-153">Suivez les étapes de l'[Annexe 3](#appendix3) de cette rubrique pour traiter les paiements des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="1764b-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="1764b-154">Dans la boîte de message, sélectionnez **Oui** pour confirmer que vous souhaitez interrompre le traitement des paiements fournisseur et démarrer le débogage de la source de données à la place sur la page **Déboguer les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="1764b-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Boîte de message de confirmation](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="1764b-156">Déboguer les sources de données utilisées dans le traitement des paiements</span><span class="sxs-lookup"><span data-stu-id="1764b-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="1764b-157">Déboguer la mise en correspondance des modèles</span><span class="sxs-lookup"><span data-stu-id="1764b-157">Debug the model mapping</span></span>

1. <span data-ttu-id="1764b-158">Sur la page **Déboguer les sources de données**, dans le volet Actions, sélectionnez **Mise en correspondance de modèles** pour commencer à déboguer à partir de ce composant ER.</span><span class="sxs-lookup"><span data-stu-id="1764b-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="1764b-159">Dans le volet de la source de données sur la gauche, sélectionnez la source de données **\$notSentTransactions**, puis sélectionnez **Lire tous les enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="1764b-160">Vous pouvez sélectionner **Lire 1 enregistrement**, **Lire 10 enregistrements**, **Lire 100 enregistrements** ou **Lire tous les enregistrements** pour forcer le nombre approprié d'enregistrements à lire à partir de la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1764b-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="1764b-161">De cette façon, vous pouvez simuler l'accès à la source de données à partir du format ER en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1764b-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="1764b-162">Dans le volet des données de droite, sélectionnez **Développer tout**.</span><span class="sxs-lookup"><span data-stu-id="1764b-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="1764b-163">Vous pouvez voir que la source de données sélectionnée du type **Liste des enregistrements** contient un seul enregistrement.</span><span class="sxs-lookup"><span data-stu-id="1764b-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="1764b-164">Développez la source de données **\$notSentTransactions** et sélectionnez la méthode **vendBankAccountInTransactionCompany ()** imbriquée.</span><span class="sxs-lookup"><span data-stu-id="1764b-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="1764b-165">Développez la méthode **vendBankAccountInTransactionCompany()**, puis sélectionnez le champ **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="1764b-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="1764b-166">Sélectionnez **Obtenir la valeur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-166">Select **Get value**.</span></span>

    <span data-ttu-id="1764b-167">Vous pouvez sélectionner **Obtenir la valeur** pour forcer la lecture d'un champ sélectionné de la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1764b-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="1764b-168">De cette façon, vous pouvez simuler l'accès à ce champ à partir du format ER en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1764b-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="1764b-169">Sélectionnez **Développer tout**.</span><span class="sxs-lookup"><span data-stu-id="1764b-169">Select **Expand all**.</span></span>

    ![Valeur du champ IBAN dans la mise en correspondance des modèles](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="1764b-171">Comme vous pouvez le voir, la mise en correspondance des modèles n'est pas responsable des espaces tronqués, car le code IBAN qu'il renvoie pour le compte bancaire du fournisseur comprend des espaces.</span><span class="sxs-lookup"><span data-stu-id="1764b-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="1764b-172">Par conséquent, vous devez continuer le débogage de la source de données.</span><span class="sxs-lookup"><span data-stu-id="1764b-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="1764b-173">Déboguer la mise en correspondance des formats</span><span class="sxs-lookup"><span data-stu-id="1764b-173">Debug the format mapping</span></span>

1. <span data-ttu-id="1764b-174">Sur la page **Déboguer les sources de données**, dans le volet Actions, sélectionnez **Mise en correspondance des formats** pour continuer à déboguer à partir de ce composant ER.</span><span class="sxs-lookup"><span data-stu-id="1764b-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="1764b-175">Sélectionnez la source de données **\$PaymentByDebtor**, puis sélectionnez **Lire tous les enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="1764b-176">Développez **\$PaymentByDebtor**.</span><span class="sxs-lookup"><span data-stu-id="1764b-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="1764b-177">Développez **\$PaymentByDebtor.Lines**, puis sélectionnez **Lire tous les enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="1764b-178">Développez **\$PaymentByDebtor.Lines.CreditorAccount**.</span><span class="sxs-lookup"><span data-stu-id="1764b-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="1764b-179">Développez **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, puis sélectionnez **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span><span class="sxs-lookup"><span data-stu-id="1764b-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="1764b-180">Sélectionnez **Obtenir la valeur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-180">Select **Get value**.</span></span>
8. <span data-ttu-id="1764b-181">Sélectionnez **Développer tout**.</span><span class="sxs-lookup"><span data-stu-id="1764b-181">Select **Expand all**.</span></span>

    ![Valeur du champ IBAN dans la mise en correspondance des formats](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="1764b-183">Comme vous pouvez le voir, les sources de données de la mise en correspondance des formats ne sont pas responsables des espaces tronqués, car le code IBAN qu'elles renvoient pour le compte bancaire du fournisseur comprend des espaces.</span><span class="sxs-lookup"><span data-stu-id="1764b-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="1764b-184">Par conséquent, vous devez continuer le débogage de la source de données.</span><span class="sxs-lookup"><span data-stu-id="1764b-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="1764b-185">Déboguer le format</span><span class="sxs-lookup"><span data-stu-id="1764b-185">Debug the format</span></span>

1. <span data-ttu-id="1764b-186">Sur la page **Déboguer les sources de données**, dans le volet Actions, sélectionnez **Format** pour continuer à déboguer à partir de ce composant ER.</span><span class="sxs-lookup"><span data-stu-id="1764b-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="1764b-187">Développez les éléments de format pour sélectionner **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, puis sélectionnez **Lire tous les enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="1764b-188">Développez les éléments de format pour sélectionner **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, puis sélectionnez **Lire tous les enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="1764b-189">Développez les éléments de format pour sélectionner **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, puis sélectionnez **Obtenir la valeur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="1764b-190">Sélectionnez **Développer tout**.</span><span class="sxs-lookup"><span data-stu-id="1764b-190">Select **Expand all**.</span></span>

    ![Valeur du champ IBAN dans le format](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="1764b-192">Comme vous pouvez le voir, la liaison de format n'est pas responsable des espaces tronqués, car le code IBAN qu'elle renvoie pour le compte bancaire du fournisseur comprend des espaces.</span><span class="sxs-lookup"><span data-stu-id="1764b-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="1764b-193">Par conséquent, l'élément **BankIBAN** est configuré pour utiliser une transformation de format qui tronque les espaces.</span><span class="sxs-lookup"><span data-stu-id="1764b-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="1764b-194">Fermez le débogueur de source de données.</span><span class="sxs-lookup"><span data-stu-id="1764b-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="1764b-195">Examiner les transformations de format</span><span class="sxs-lookup"><span data-stu-id="1764b-195">Review the format transformations</span></span>

1. <span data-ttu-id="1764b-196">Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="1764b-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1764b-197">Sur la page **Configurations**, sélectionnez **Modèle de paiement** \> **ISO20022 Credit transfer**.</span><span class="sxs-lookup"><span data-stu-id="1764b-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="1764b-198">Sélectionnez **Concepteur**, puis développez les éléments pour sélectionner **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span><span class="sxs-lookup"><span data-stu-id="1764b-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![Élément BankIBAN sur la page Concepteur de format](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="1764b-200">Comme vous pouvez le voir, l'élément **BankIBAN** est configuré pour utiliser la transformation **supprimer non alphanumérique**.</span><span class="sxs-lookup"><span data-stu-id="1764b-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="1764b-201">Sélectionnez l'onglet **Transformations**.</span><span class="sxs-lookup"><span data-stu-id="1764b-201">Select the **Transformations** tab.</span></span>

    ![Onglet Transformations de l'élément BankIBAN](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="1764b-203">Comme vous pouvez le voir, la transformation **supprimer non alphanumérique** est configurée pour utiliser une expression qui tronque les espaces de la chaîne de texte fournie.</span><span class="sxs-lookup"><span data-stu-id="1764b-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="1764b-204">Commencer à déboguer dans le Concepteur d'opérations</span><span class="sxs-lookup"><span data-stu-id="1764b-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="1764b-205">Lorsque vous configurez une version provisoire du format ER pouvant être exécutée directement à partir du concepteur d'opérations, vous pouvez accéder au débogueur de source de données en sélectionnant **Démarrer le débogage** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="1764b-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Bouton Démarrer le débogage sur la page Concepteur de format](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="1764b-207">La mise en correspondance des formats et des composants de format du format ER en cours de modification sont disponibles pour le débogage.</span><span class="sxs-lookup"><span data-stu-id="1764b-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="1764b-208">Commencer à déboguer dans le Concepteur de mise en correspondance des modèles</span><span class="sxs-lookup"><span data-stu-id="1764b-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="1764b-209">Lorsque vous configurez une mise en correspondance des modèles ER pouvant être exécutée à partir de la page **Mise en correspondance des modèles**, vous pouvez accéder au débogueur de source de données en sélectionnant **Démarrer le débogage** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="1764b-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Bouton Démarrer le débogage sur la page Concepteur de mise en correspondances de modèles](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="1764b-211">Le composant de mise en correspondance des modèles de la mise en correspondance ER en cours de modification est disponible pour le débogage.</span><span class="sxs-lookup"><span data-stu-id="1764b-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="1764b-212">Annexe 1 : Obtenir une solution ER</span><span class="sxs-lookup"><span data-stu-id="1764b-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="1764b-213">Télécharger une solution ER</span><span class="sxs-lookup"><span data-stu-id="1764b-213">Download an ER solution</span></span>

<span data-ttu-id="1764b-214">Si vous souhaitez utiliser une solution ER pour générer un fichier de paiement électronique pour un paiement fournisseur qui est traité, vous pouvez [télécharger](download-electronic-reporting-configuration-lcs.md) le format de paiement ER **Transfert de crédit ISO20022** disponible dans la bibliothèque de ressources partagées dans Microsoft Dynamics Lifecycle Services (LCS) ou à partir du référentiel global.</span><span class="sxs-lookup"><span data-stu-id="1764b-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Importation du format de paiement ER sur la page Référentiel de configuration](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="1764b-216">En plus du format ER sélectionné, les [configurations](general-electronic-reporting.md#Configuration) suivantes doivent être automatiquement importées dans votre instance de Microsoft Dynamics 365 Finance dans le cadre de la solution ER **Transfert de crédit ISO20022** :</span><span class="sxs-lookup"><span data-stu-id="1764b-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="1764b-217">**Modèle de paiement** [Configuration du modèle de données ER](general-electronic-reporting.md#DataModelComponent)</span><span class="sxs-lookup"><span data-stu-id="1764b-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="1764b-218">**Transfert de crédit ISO20022** [Configuration de format ER](general-electronic-reporting.md#FormatComponentOutbound)</span><span class="sxs-lookup"><span data-stu-id="1764b-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="1764b-219">**Mise en correspondance du modèle de paiement 1611** - [Configuration de la mise en correspondance du modèle ER](general-electronic-reporting.md#ModelMappingComponent)</span><span class="sxs-lookup"><span data-stu-id="1764b-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="1764b-220">Configuration de la mise en correspondance du modèle ER **Mise en correspondance du modèle de paiement avec le transfert ISO20022 de destination**</span><span class="sxs-lookup"><span data-stu-id="1764b-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="1764b-221">Vous pouvez trouver ces configurations sur la page **Configurations** de la structure ER (**Administration de l'organisation** \> **Rapports électroniques** \> **Configurations**).</span><span class="sxs-lookup"><span data-stu-id="1764b-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![Configurations importées sur la page Configurations](./media/er-data-debugger-configurations.png)

<span data-ttu-id="1764b-223">Si l'une des configurations répertoriées précédemment manque dans l'arborescence de configuration, vous devez les télécharger manuellement à partir de la bibliothèque de ressources partagées LCS de la même manière que vous avez téléchargé le format de paiement ER **Transfert de crédit ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1764b-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="1764b-224">Analyser la solution ER téléchargée</span><span class="sxs-lookup"><span data-stu-id="1764b-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="1764b-225">Examiner la mise en correspondance des modèles</span><span class="sxs-lookup"><span data-stu-id="1764b-225">Review the model mapping</span></span>

1. <span data-ttu-id="1764b-226">Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="1764b-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1764b-227">Sélectionnez **Modèle de paiement** \> **Mise en correspondance du modèle de paiement 1611**.</span><span class="sxs-lookup"><span data-stu-id="1764b-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="1764b-228">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-228">Select **Designer**.</span></span>
4. <span data-ttu-id="1764b-229">Sélectionnez l'enregistrement de mise en correspondance **Mise en correspondance du modèle de paiement ISO20022 CT**.</span><span class="sxs-lookup"><span data-stu-id="1764b-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="1764b-230">Sélectionnez **Concepteur**, puis passez en revue le mappage de modèle ouvert.</span><span class="sxs-lookup"><span data-stu-id="1764b-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="1764b-231">Notez que le champ **Paiements** du modèle de données est lié à la source de données **\$notSentTransactions** qui renvoie la liste des lignes de paiement fournisseur en cours de traitement.</span><span class="sxs-lookup"><span data-stu-id="1764b-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Champ Paiements sur la page Concepteur de mise en correspondance des modèles](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="1764b-233">Examiner la mise en correspondance des formats</span><span class="sxs-lookup"><span data-stu-id="1764b-233">Review the format mapping</span></span>

1. <span data-ttu-id="1764b-234">Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="1764b-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1764b-235">Sélectionnez **Modèle de paiement** \> **Transfert de crédit ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1764b-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="1764b-236">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-236">Select **Designer**.</span></span>
4. <span data-ttu-id="1764b-237">Sur l'onglet **Mise en correspondance**, passez en revue la mise en correspondance de formats qui est ouverte.</span><span class="sxs-lookup"><span data-stu-id="1764b-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="1764b-238">Notez que l'élément **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** du fichier **ISO20022CTReports** \> **XMLHeader** est lié à la source de données **\$PaymentByDebtor** configurée pour regrouper les enregistrements du champ Modèles de données **Paiements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![Élément PmtInf sur la page Concepteur de format](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="1764b-240">Examiner le format</span><span class="sxs-lookup"><span data-stu-id="1764b-240">Review the format</span></span>

1. <span data-ttu-id="1764b-241">Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="1764b-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1764b-242">Sélectionnez **Modèle de paiement** \> **Transfert de crédit ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1764b-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="1764b-243">Sélectionnez **Concepteur**, puis passez en revue le format qui est ouvert.</span><span class="sxs-lookup"><span data-stu-id="1764b-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="1764b-244">Notez que l'élément de format sous **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** est configuré pour saisir le code IBAN du compte fournisseur dans le fichier de paiement.</span><span class="sxs-lookup"><span data-stu-id="1764b-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![Élément BankIBAN sur la page Concepteur de format](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="1764b-246">Annexe 2 : Configurer le module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1764b-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="1764b-247">Modifier une propriété de fournisseur</span><span class="sxs-lookup"><span data-stu-id="1764b-247">Modify a vendor property</span></span>

1. <span data-ttu-id="1764b-248">Accédez à **Comptabilité fournisseur** \> **Fournisseurs** \> **Tous les fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="1764b-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="1764b-249">Sélectionnez un fournisseur **DE-01002**, puis dans le volet Actions, sous l'onglet **Fournisseur**, dans le groupe **Paramétrer**, sélectionnez **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="1764b-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="1764b-250">Dans le raccourci **Identification**, dans le champ **IBAN**, <a name="enteredIBANcode"></a>saisissez **GB33 BUKB 2020 1555 5555 55**.</span><span class="sxs-lookup"><span data-stu-id="1764b-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="1764b-251">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1764b-251">Select **Save**.</span></span>

![Champ IBAN paramétré sur la page Comptes bancaires fournisseur](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="1764b-253">Paramétrer un mode de paiement</span><span class="sxs-lookup"><span data-stu-id="1764b-253">Set up a method of payment</span></span>

1. <span data-ttu-id="1764b-254">Accédez à **Comptabilité fournisseur** \> **Paramétrage des paiements** \> **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="1764b-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="1764b-255">Sélectionnez le mode de paiement **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="1764b-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="1764b-256">Dans le raccourci **Formats de fichier**, dans la section **Formats de fichier**, définissez l'option **Format d'exportation électronique générique** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1764b-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="1764b-257">Dans le champ **Exporter la configuration du format**, sélectionnez le champ ER **Transfert de crédit ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1764b-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="1764b-258">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1764b-258">Select **Save**.</span></span>

![Paramètres des formats de fichier sur la page Modes de paiement](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="1764b-260">Ajouter un paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="1764b-260">Add a vendor payment</span></span>

1. <span data-ttu-id="1764b-261">Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="1764b-262">Ajouter un journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="1764b-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="1764b-263">Sélectionnez **Lignes** et ajoutez une nouvelle ligne de paiement.</span><span class="sxs-lookup"><span data-stu-id="1764b-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="1764b-264">Dans le champ **Compte**, sélectionnez le fournisseur **DE-01002**.</span><span class="sxs-lookup"><span data-stu-id="1764b-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="1764b-265">Dans le champ **Débit**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1764b-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="1764b-266">Dans le champ **Mode de paiement**, sélectionnez **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="1764b-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="1764b-267">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1764b-267">Select **Save**.</span></span>

![Paiement fournisseur ajouté sur la page Paiements fournisseur](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="1764b-269">Annexe 3 : Traiter un paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="1764b-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="1764b-270">Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="1764b-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="1764b-271">Sur la page **Journal de paiement fournisseur**, sélectionnez le journal des paiements que vous avez créé précédemment, puis sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="1764b-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="1764b-272">Sélectionnez la ligne de paiement, puis sélectionnez **Statut de paiement** \> **Aucun(e)**.</span><span class="sxs-lookup"><span data-stu-id="1764b-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="1764b-273">Sélectionnez **Générer des paiements**.</span><span class="sxs-lookup"><span data-stu-id="1764b-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="1764b-274">Dans le champ **Mode de paiement**, sélectionnez **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="1764b-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="1764b-275">Dans le champ **Compte bancaire**, sélectionnez **DEMF OPER**.</span><span class="sxs-lookup"><span data-stu-id="1764b-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="1764b-276">Dans la boîte de dialogue **Générer des paiements**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1764b-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="1764b-277">Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1764b-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
