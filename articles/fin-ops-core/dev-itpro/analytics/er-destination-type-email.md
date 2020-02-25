---
title: Type de destination pour l'envoi d'états électroniques par e-mail
description: Cette rubrique fournit des informations sur la configuration d'une destination de messagerie pour chaque composant DOSSIER ou FICHIER d'un format d'état électronique (ER) configuré pour générer des documents sortants.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019766"
---
# <span data-ttu-id="6d5b7-103"><a name="EmailDestinationType">Destination du courrier électronique</a></span><span class="sxs-lookup"><span data-stu-id="6d5b7-103"><a name="EmailDestinationType">Email destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d5b7-104">Vous pouvez configurer une destination de messagerie pour chaque composant DOSSIER ou FICHIER d'un format d'état électronique (ER) configuré pour générer des documents sortants.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="6d5b7-105">En fonction du paramètre de destination, un document généré est remis en tant que pièce jointe d'un courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="6d5b7-106">Définissez **Activé** sur **Oui** pour envoyer un fichier de sortie par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="6d5b7-107">Une fois cette option activée, vous pouvez spécifier les destinataires du message et modifier l'objet et le corps du courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="6d5b7-108">Vous pouvez paramétrer des textes constants pour l'objet et le corps du courrier électronique, ou vous pouvez utiliser des [formules](er-formula-language.md) de génération d'états électroniques pour créer dynamiquement les textes de courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="6d5b7-109">Vous pouvez configurer les adresses électroniques pour les états électroniques de deux manières.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="6d5b7-110">La configuration peut être effectuée de la même manière que pour la fonction de gestion de l'impression, ou vous pouvez résoudre une adresse e-mail en utilisant une référence directe à la configuration ER via une formule.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="6d5b7-111">[![Activer la destination de l'e-mail](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="6d5b7-112">Types d'adresses électroniques</span><span class="sxs-lookup"><span data-stu-id="6d5b7-112">Email address types</span></span>

<span data-ttu-id="6d5b7-113">Lorsque vous sélectionnez **Modifier** dans les champs **À** ou **Cc**, la boîte de dialogue **E-mail à** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="6d5b7-114">Vous pouvez ensuite sélectionner le type d'adresse électronique à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="6d5b7-115">Les types d'e-mail **E-mail de configuration** et **Gestion de l'impression** sont actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="6d5b7-116">[![Sélectionner un type d'e-mail](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="6d5b7-117">Gestion de l'impression</span><span class="sxs-lookup"><span data-stu-id="6d5b7-117">Print management</span></span>

<span data-ttu-id="6d5b7-118">Si vous sélectionnez le type d'e-mail **Gestion de l'impression**, vous pouvez entrer des adresses électroniques fixes dans le champ **À**.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="6d5b7-119">[![Configurer des adresses e-mail fixes](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="6d5b7-120">Pour utiliser des adresses électroniques non fixes, vous devez sélectionner le type de source du courrier électronique pour une destination de fichier.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="6d5b7-121">Les valeurs suivantes sont prises en charge : **Client**, **Fournisseur**, **Prospect**, **Contact**, **Concurrent**, **Collaborateur**, **Candidat**, **Fournisseur potentiel** et **Fournisseur non autorisé**.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="6d5b7-122">Après avoir sélectionné un type de source de courrier électronique, utilisez le bouton en regard **Compte source de l'e-mail** pour ouvrir l'écran **Concepteur de formule**.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="6d5b7-123">Vous pouvez utiliser cet écran pour joindre une formule qui renvoie au moment de l'exécution le **compte de partie** du type de source sélectionné du document traité à la destination de l'e-mail.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="6d5b7-124">[![Configurer le compte source de messagerie](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="6d5b7-125">Les formules sont spécifiques à la configuration de l'état électronique.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="6d5b7-126">Dans le champ **Formule**, entrez une référence spécifique au document pour un type de partie Client ou Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="6d5b7-127">Au lieu de taper, vous pouvez rechercher un nœud de source de données qui représente le compte client ou fournisseur, puis sélectionner **Ajouter une source de données** pour mettre la formule à jour.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="6d5b7-128">Par exemple, si vous utilisez la configuration **Virement bancaire ISO 20022**, le nœud représentant un compte fournisseur est : `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="6d5b7-129">Si vous entrez une valeur de chaîne, telle que `"DE-001"`, et enregistrez une formule, un e-mail sera envoyé à la personne de contact du vendeur, **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="6d5b7-130">[![Page Concepteur de formule ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="6d5b7-131">[![Configurer le compte source de messagerie](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-131">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="6d5b7-132">E-mail de configuration</span><span class="sxs-lookup"><span data-stu-id="6d5b7-132">Configuration email</span></span>

<span data-ttu-id="6d5b7-133">Utilisez ce type de courrier électronique si la configuration que vous utilisez a un nœud dans les sources de données qui retourne une **adresse électronique**.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="6d5b7-134">Vous pouvez utiliser les sources et fonctions de données du concepteur de formule pour obtenir une adresse électronique correctement mise en forme.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="6d5b7-135">Par exemple, si vous utilisez la configuration **Virement bancaire ISO 20022**, le nœud représentant l'adresse e-mail du contact du fournisseur est : `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="6d5b7-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="6d5b7-136">[![Configurer la source d'adresse de messagerie](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d5b7-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6d5b7-137">Additional resources</span></span>

- [<span data-ttu-id="6d5b7-138">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="6d5b7-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="6d5b7-139">Destinations pour la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="6d5b7-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="6d5b7-140">Concepteur de formule dans les états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="6d5b7-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
