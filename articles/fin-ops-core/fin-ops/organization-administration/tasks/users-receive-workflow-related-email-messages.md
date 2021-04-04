---
title: Permettre aux utilisateurs de recevoir des e-mails liés au workflow
description: Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a81e01c36081ce7131ee65344f583755fa3bfd3
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564188"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="a9f3e-103">Permettre aux utilisateurs de recevoir des e-mails liés au workflow</span><span class="sxs-lookup"><span data-stu-id="a9f3e-103">Enable users to receive workflow-related email messages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a9f3e-104">Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="a9f3e-105">Par exemple, des messages e-mail peuvent être envoyés aux utilisateurs lorsque des documents leur sont affectés pour approbation.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="a9f3e-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="a9f3e-107">Accédez à **Volet de navigation > Modules > Administration système > Utilisateurs > Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="a9f3e-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a9f3e-109">Dans le **volet Actions**, cliquez sur **Options de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="a9f3e-110">Cliquez sur l’onglet **Workflow** et vérifiez que la section **Notifications** est développée.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="a9f3e-111">Dans la section **Notifications**, vous pouvez préciser la manière dont vous souhaitez que l’utilisateur soit prévenu des événements liés au workflow.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="a9f3e-112">Dans le champ **Type de notification de workflow pour ligne**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="a9f3e-113">Groupé – Les notifications pour les lignes sont regroupées dans un seul e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="a9f3e-114">Individuel – Un e-mail est envoyé pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="a9f3e-115">Si vous voulez que l’utilisateur reçoive les notifications dans le client, activez la case à cocher **Envoyer des notifications sous la forme d’e-mails**.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="a9f3e-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-116">Click **Save**.</span></span>
7. <span data-ttu-id="a9f3e-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a9f3e-117">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="a9f3e-118">Les modèles d’e-mail de workflow proviendront des modèles d’e-mail système ou des modèles d’e-mail de l’organisation, selon que le workflow est un workflow de niveau système (non spécifique à la société) ou de niveau organisation (spécifique à la société).</span><span class="sxs-lookup"><span data-stu-id="a9f3e-118">The workflow email templates will be sourced from either system email templates or organization email templates depending on whether the workflow is a system-level (not company specific) or organization-level (company specific) workflow.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]