---
title: Soumettre une demande d'absence au workflow
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 008ee231ca9f0459e332b17cea9f2a3f3e3cc2a5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009062"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="955ad-102">Soumettre une demande d'absence au workflow</span><span class="sxs-lookup"><span data-stu-id="955ad-102">Submit a leave request to workflow</span></span>

<span data-ttu-id="955ad-103">Dans Microsoft Dynamics 365 Human Resources, vous pouvez utiliser l'interface de programmation d'application (API) MyLeaveRequests submit() pour soumettre une demande de congé au workflow.</span><span class="sxs-lookup"><span data-stu-id="955ad-103">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="955ad-104">Cette API est présentée comme une action sur l'entité OData MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="955ad-104">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="955ad-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="955ad-105">Prerequisites</span></span>

<span data-ttu-id="955ad-106">La demande de congé doit être enregistrée dans la base de données et doit pouvoir être récupérée via l'entité MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="955ad-106">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="955ad-107">Autorisations</span><span class="sxs-lookup"><span data-stu-id="955ad-107">Permissions</span></span>

<span data-ttu-id="955ad-108">L'une des autorisations suivantes est requise pour appeler cette API.</span><span class="sxs-lookup"><span data-stu-id="955ad-108">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="955ad-109">Pour plus d'informations sur le paramétrage des autorisations et la manière de sélectionner, voir [Authentification](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="955ad-109">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="955ad-110">Type d'autorisation</span><span class="sxs-lookup"><span data-stu-id="955ad-110">Permission type</span></span>                    | <span data-ttu-id="955ad-111">Autorisations (des moins privilégiées au plus privilégiées)</span><span class="sxs-lookup"><span data-stu-id="955ad-111">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="955ad-112">Délégué (compte professionnel ou éducatif)</span><span class="sxs-lookup"><span data-stu-id="955ad-112">Delegated (work or school account)</span></span> | <span data-ttu-id="955ad-113">utilisateur\_substitution d'identité</span><span class="sxs-lookup"><span data-stu-id="955ad-113">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="955ad-114">Demande HTTPS</span><span class="sxs-lookup"><span data-stu-id="955ad-114">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="955ad-115">La demande est conforme aux normes OData.</span><span class="sxs-lookup"><span data-stu-id="955ad-115">The request conforms to OData standards.</span></span> <span data-ttu-id="955ad-116">Les paramètres {requestId}, {leaveType}, {leaveDate} et {dataArea} se rapportent aux champs qui constituent la clé naturelle composite de l'entité MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="955ad-116">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="955ad-117">Alors que les champs de l'entité MyLeaveRequests font référence à une ligne individuelle dans la demande de congé, l'appel de l'API de soumission soumettra toute la demande de congé (toutes les lignes) au workflow.</span><span class="sxs-lookup"><span data-stu-id="955ad-117">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="955ad-118">En-tête de la demande</span><span class="sxs-lookup"><span data-stu-id="955ad-118">Request headers</span></span>

| <span data-ttu-id="955ad-119">En-tête</span><span class="sxs-lookup"><span data-stu-id="955ad-119">Header</span></span>         | <span data-ttu-id="955ad-120">Value</span><span class="sxs-lookup"><span data-stu-id="955ad-120">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="955ad-121">Autorisation</span><span class="sxs-lookup"><span data-stu-id="955ad-121">Authorization</span></span>  | <span data-ttu-id="955ad-122">Détenteur {token} (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="955ad-122">Bearer {token} (required)</span></span> |
| <span data-ttu-id="955ad-123">Type de contenu</span><span class="sxs-lookup"><span data-stu-id="955ad-123">Content-Type</span></span>   | <span data-ttu-id="955ad-124">application/json</span><span class="sxs-lookup"><span data-stu-id="955ad-124">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="955ad-125">Corps de demande</span><span class="sxs-lookup"><span data-stu-id="955ad-125">Request body</span></span>

<span data-ttu-id="955ad-126">Ne fournissez pas de corps de demande pour cette méthode.</span><span class="sxs-lookup"><span data-stu-id="955ad-126">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="955ad-127">Réponse</span><span class="sxs-lookup"><span data-stu-id="955ad-127">Response</span></span>

<span data-ttu-id="955ad-128">Une réponse de réussite est toujours une réponse **204 Aucun contenu**.</span><span class="sxs-lookup"><span data-stu-id="955ad-128">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="955ad-129">Les appelants non autorisés recevront une réponse **401 Non autorisé**ou **403 Interdit**.</span><span class="sxs-lookup"><span data-stu-id="955ad-129">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="955ad-130">Si la soumission échoue (en raison de la validation, par exemple), la réponse sera **500 Erreur du serveur** et le corps de la réponse comprendra un objet JSON avec plus de détails.</span><span class="sxs-lookup"><span data-stu-id="955ad-130">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="955ad-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="955ad-131">Example</span></span>

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a><span data-ttu-id="955ad-132">Validation et messages et d'erreur</span><span class="sxs-lookup"><span data-stu-id="955ad-132">Validation and error messages</span></span>

<span data-ttu-id="955ad-133">Dans le cadre de l'appel à l'API de soumission, Human Resources effectue la validation de la logique métier avant la soumission, ce qui garantit que la demande de congé est dans un état valide pour la soumission.</span><span class="sxs-lookup"><span data-stu-id="955ad-133">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="955ad-134">Les messages d'erreur possibles que vous pouvez recevoir dans la réponse si les validations échouent sont :</span><span class="sxs-lookup"><span data-stu-id="955ad-134">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="955ad-135">La demande doit définir le solde « {LeaveTypeId} » en-dessous du solde minimal autorisé au {date}.</span><span class="sxs-lookup"><span data-stu-id="955ad-135">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="955ad-136">La demande de congé en état Terminé ne peut pas être soumise.</span><span class="sxs-lookup"><span data-stu-id="955ad-136">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="955ad-137">Impossible de soumettre ou d'enregistrer la demande car aucune modification n'a été apportée.</span><span class="sxs-lookup"><span data-stu-id="955ad-137">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="955ad-138">Ajoutez ou mettez à jour le montant ou le type de congé et réessayez.</span><span class="sxs-lookup"><span data-stu-id="955ad-138">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="955ad-139">La demande de congé saisie contient un ou plusieurs jours avec la même date et le même type de congé qu'une demande en attente existante.</span><span class="sxs-lookup"><span data-stu-id="955ad-139">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="955ad-140">Veuillez rappeler la demande actuelle pour apporter des modification.</span><span class="sxs-lookup"><span data-stu-id="955ad-140">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="955ad-141">Le code motif « {ReasonCodeId} » ne s'applique pas aux types de congé de la demande.</span><span class="sxs-lookup"><span data-stu-id="955ad-141">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="955ad-142">Le type de congé ' {LeaveTypeId} 'nécessite un code motif.</span><span class="sxs-lookup"><span data-stu-id="955ad-142">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="955ad-143">Sélectionnez le type et le code motif appropriés.</span><span class="sxs-lookup"><span data-stu-id="955ad-143">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="955ad-144">Le congé n'a pas été soumis avec succès.</span><span class="sxs-lookup"><span data-stu-id="955ad-144">The time off was not submitted successfully.</span></span> <span data-ttu-id="955ad-145">Le congé a été enregistré en tant que brouillon de demande.</span><span class="sxs-lookup"><span data-stu-id="955ad-145">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="955ad-146">Voir également :</span><span class="sxs-lookup"><span data-stu-id="955ad-146">See also</span></span>

- [<span data-ttu-id="955ad-147">Vue d'ensemble de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="955ad-147">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="955ad-148">Authentification</span><span class="sxs-lookup"><span data-stu-id="955ad-148">Authentication</span></span>](hr-developer-api-authentication.md)