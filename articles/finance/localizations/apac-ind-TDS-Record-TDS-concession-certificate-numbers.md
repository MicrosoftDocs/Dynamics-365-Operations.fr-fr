---
title: Enregistrez les numéros de certificat de concession TDS
description: Cette rubrique explique comment enregistrer les numéros de certificat de concession de taxe déduite à la source (TDS) qui sont délivrés aux fournisseurs.
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023226"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="50811-103">Enregistrez les numéros de certificat de concession TDS</span><span class="sxs-lookup"><span data-stu-id="50811-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50811-104">Cette rubrique explique comment enregistrer les numéros de certificat de concession de taxe déduite à la source (TDS) qui sont délivrés aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="50811-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="50811-105">Accédez à **Taxe \> > Taxes indirectes \> Retenue à la source \> Concessions de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="50811-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="50811-106">Dans le champ **Type de taxe**, sélectionnez **TDS** pour enregistrer les certificats de concession pour le type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="50811-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="50811-107">Dans l'onglet **Aperçu**, sélectionnez **Alt + N** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="50811-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="50811-108">[![En-tête de la nouvelle ligne](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="50811-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="50811-109">Dans le champ **Code de retenue à la source**, sélectionnez le code de taxe TDS pour lequel les certificats de concession fournisseur sont émis.</span><span class="sxs-lookup"><span data-stu-id="50811-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="50811-110">Le champ **Nom de code de retenue à la source** affiche le nom du code taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="50811-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="50811-111">Dans les champs **Date de début** et **Date de fin**, définissez la période de validité du certificat de concession qui utilise le code de taxe TDS pour calculer TDS pour le fournisseur sur une base concessionnelle.</span><span class="sxs-lookup"><span data-stu-id="50811-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="50811-112">Dans le champ **Remarques**, entrez vos remarques.</span><span class="sxs-lookup"><span data-stu-id="50811-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="50811-113">Dans le champ **Section**, entrez le code de section légale sous lequel le certificat de concession TDS est utilisé.</span><span class="sxs-lookup"><span data-stu-id="50811-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="50811-114">Si le code de section est 197, la valeur "A" apparaît à la fois dans la colonne "Raison de la non-déduction/déduction inférieure" du formulaire 26Q et dans la colonne "Raison de la non-déduction/de la déduction inférieure/de la majoration (le cas échéant)» dans Formulaire 27Q.</span><span class="sxs-lookup"><span data-stu-id="50811-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="50811-115">Si le code de section est 197A, la valeur "B" apparaît à ces deux endroits.</span><span class="sxs-lookup"><span data-stu-id="50811-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="50811-116">Sélectionnez le raccourci **Certificat** pour enregistrer les numéros de certificat de concession TDS pour les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="50811-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="50811-117">Dans le champ **Compte fournisseur**, sélectionnez le compte fournisseur pour lequel le certificat de concession TDS est émis.</span><span class="sxs-lookup"><span data-stu-id="50811-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="50811-118">Dans les champs **Date de début** et **Date de fin**, définissez la période de validité du certificat de concession TDS.</span><span class="sxs-lookup"><span data-stu-id="50811-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="50811-119">Le calcul de TDS sur une base concessionnelle est basé sur la période pendant laquelle le certificat est créé pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="50811-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="50811-120">Dans le champ **Numéro de certificat**, entrez le numéro de certificat de concession.</span><span class="sxs-lookup"><span data-stu-id="50811-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="50811-121">[![Raccourci Certificat](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="50811-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="50811-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50811-122">Close the page.</span></span>
