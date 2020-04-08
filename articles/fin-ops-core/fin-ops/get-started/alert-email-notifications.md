---
title: Notifications d'alerte de client par e-mail
description: Cette rubrique offre des informations sur la manière de configurer des règles qui envoient des notifications par e-mail lorsque des événements prédéfinis se produisent.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a0cf8037ba151bb4e68da1cf4609fb2e4806303a
ms.sourcegitcommit: b952b9f9066a5317259b8344db4c5d99eab4bf3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2020
ms.locfileid: "3165773"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="a0787-103">Notifications d'alerte du client par e-mail</span><span class="sxs-lookup"><span data-stu-id="a0787-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0787-104">Vous pouvez définir des règles d'alerte personnalisées qui surveillent les vues filtrées des données et qui envoient automatiquement les notifications par e-mail lorsque des événements prédéfinis surviennent.</span><span class="sxs-lookup"><span data-stu-id="a0787-104">You can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="a0787-105">L'option d'envoi de notifications par e-mail est disponible pour tous les types d'alerte pris en charge et peut être également activée pour les règles d'alerte existantes.</span><span class="sxs-lookup"><span data-stu-id="a0787-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="a0787-106">Vous pouvez utiliser les contrôles intégrés pour créer des règles d'alerte qui supervisent les vues filtrées des traitements par lots du système.</span><span class="sxs-lookup"><span data-stu-id="a0787-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="a0787-107">En surveillant la valeur du champ **Statut**, vous pouvez également configurer les règles d'alerte qui envoient un e-mail en cas d'échec d'un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="a0787-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="a0787-108">Une fois ces règles d'alerte créées, vous n'avez plus à vérifier les états relatifs aux modifications apportées aux données commerciales.</span><span class="sxs-lookup"><span data-stu-id="a0787-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="a0787-109">Au lieu de cela, vous pouvez laisser le service de détection intelligente des modifications faire le contrôle pour vous.</span><span class="sxs-lookup"><span data-stu-id="a0787-109">Instead, you can let the intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="a0787-110">Les alertes de client dépendent du sous-système d'e-mail fourni via l'intégration avec Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a0787-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="a0787-111">Nous vous recommandons d'utiliser le fournisseur SMTP afin que la distribution d'e-mail n'ait pas à se reposer sur un client de courrier local.</span><span class="sxs-lookup"><span data-stu-id="a0787-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="a0787-112">Pour envoyer des notifications par e-mail, les clients doivent configurer des services d'e-mail intégrés.</span><span class="sxs-lookup"><span data-stu-id="a0787-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="a0787-113">Les notifications par e-mail sont envoyées aux destinataires pour le compte de propriétaires d'alerte.</span><span class="sxs-lookup"><span data-stu-id="a0787-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="a0787-114">Pour plus d'informations sur la configuration de l'e-mail, consultez la rubrique [Configurer et envoyer un e-mail](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="a0787-114">For more information about how to configure email, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="a0787-115">L'image suivante présente la boîte de dialogue **Créer une règle d'alerte**, qui comprend désormais une option **Envoyer un e-mail**.</span><span class="sxs-lookup"><span data-stu-id="a0787-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="a0787-116">[![Créer la boîte de dialogue de règle d'alerte, où l'option Envoyer un e-mail est définie sur Oui](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="a0787-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="a0787-117">Lorsque l'option **Envoyer un e-mail** est définie sur **Oui**, les notifications d'alerte continuent d'être fournies depuis le centre d'action.</span><span class="sxs-lookup"><span data-stu-id="a0787-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="a0787-118">Modèles d'e-mail de notification d'alerte</span><span class="sxs-lookup"><span data-stu-id="a0787-118">Alert notification email templates</span></span>

<span data-ttu-id="a0787-119">Le service envoie des notifications par e-mail à l'aide de modèles d'e-mail prédéfinis qui offrent les détails de base de la notification d'alerte.</span><span class="sxs-lookup"><span data-stu-id="a0787-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="a0787-120">L'image suivante présente la structure des notifications d'alerte lorsqu'elles sont reçues par e-mail.</span><span class="sxs-lookup"><span data-stu-id="a0787-120">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="a0787-121">[![Notifications d'alerte basées sur un modèle pour la création des enregistrements, les modifications de champ et la suppression du modèle](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="a0787-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>
