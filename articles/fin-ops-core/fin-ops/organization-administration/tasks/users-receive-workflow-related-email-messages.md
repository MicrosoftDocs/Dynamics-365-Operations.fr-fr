---
title: Permettre aux utilisateurs de recevoir des e-mails liés au workflow
description: Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189842"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="ad717-103">Permettre aux utilisateurs de recevoir des e-mails liés au workflow</span><span class="sxs-lookup"><span data-stu-id="ad717-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ad717-104">Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.</span><span class="sxs-lookup"><span data-stu-id="ad717-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="ad717-105">Par exemple, des messages e-mail peuvent être envoyés aux utilisateurs lorsque des documents leur sont affectés pour approbation.</span><span class="sxs-lookup"><span data-stu-id="ad717-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="ad717-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="ad717-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="ad717-107">Accédez à **Volet de navigation > Modules > Administration système > Utilisateurs > Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ad717-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="ad717-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ad717-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ad717-109">Dans le **volet Actions**, cliquez sur **Options de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ad717-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="ad717-110">Cliquez sur l'onglet **Workflow** et vérifiez que la section **Notifications** est développée.</span><span class="sxs-lookup"><span data-stu-id="ad717-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="ad717-111">Dans la section **Notifications**, vous pouvez préciser la manière dont vous souhaitez que l'utilisateur soit prévenu des événements liés au workflow.</span><span class="sxs-lookup"><span data-stu-id="ad717-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="ad717-112">Dans le champ **Type de notification de workflow pour ligne**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="ad717-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="ad717-113">Groupé – Les notifications pour les lignes sont regroupées dans un seul e-mail.</span><span class="sxs-lookup"><span data-stu-id="ad717-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="ad717-114">Individuel – Un e-mail est envoyé pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="ad717-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="ad717-115">Si vous voulez que l'utilisateur reçoive les notifications dans le client, activez la case à cocher **Envoyer des notifications sous la forme d'e-mails**.</span><span class="sxs-lookup"><span data-stu-id="ad717-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="ad717-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ad717-116">Click **Save**.</span></span>
7. <span data-ttu-id="ad717-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad717-117">Close the page.</span></span>

