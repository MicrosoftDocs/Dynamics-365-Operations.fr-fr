--- 
title: "Configuration du système pour envoyer un e-mail associé au workflow aux utilisateurs"
description: "Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 04d90c9ded1ba7fb1ceac4ff1d54f54f6c43f9e9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a><span data-ttu-id="d50dc-103">Configuration du système pour envoyer un e-mail associé au workflow aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d50dc-103">Configure the system to send workflow-related email to users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d50dc-104">Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.</span><span class="sxs-lookup"><span data-stu-id="d50dc-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="d50dc-105">Par exemple, des messages e-mail peuvent être envoyés aux utilisateurs lorsque des documents leur sont affectés pour approbation.</span><span class="sxs-lookup"><span data-stu-id="d50dc-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="d50dc-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d50dc-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="d50dc-107">Accédez à Administration système > Utilisateurs > Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d50dc-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="d50dc-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d50dc-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d50dc-109">Cliquez sur Options utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d50dc-109">Click User options.</span></span>
4. <span data-ttu-id="d50dc-110">Cliquez sur l'onglet Workflow.</span><span class="sxs-lookup"><span data-stu-id="d50dc-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="d50dc-111">Assurez-vous que la section Notifications est développée.</span><span class="sxs-lookup"><span data-stu-id="d50dc-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="d50dc-112">Dans la section Notifications, vous pouvez préciser la manière dont vous souhaitez que l'utilisateur soit prévenu des événements liés au workflow.</span><span class="sxs-lookup"><span data-stu-id="d50dc-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="d50dc-113">Dans le champ Type de notification de workflow pour ligne, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d50dc-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="d50dc-114">Groupé – Les notifications pour les lignes sont regroupées dans un seul e-mail.</span><span class="sxs-lookup"><span data-stu-id="d50dc-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="d50dc-115">Individuel – Un e-mail est envoyé pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="d50dc-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="d50dc-116">Si vous voulez que l'utilisateur reçoive les notifications dans le client, activez la case à cocher Envoyer des notifications sous la forme d'e-mails.</span><span class="sxs-lookup"><span data-stu-id="d50dc-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="d50dc-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d50dc-117">Click Save.</span></span>
7. <span data-ttu-id="d50dc-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d50dc-118">Close the page.</span></span>


