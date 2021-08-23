---
title: Soumettre une demande d’absence au workflow
description: Dans Microsoft Dynamics 365 Human Resources, vous pouvez utiliser l’interface de programmation d’application (API) MyLeaveRequests submit() pour soumettre une demande de congé au workflow.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d9a4c472868002c6cae061507bfe2f75d7f3eb86935d69acaac8cb7f2d970bfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732055"
---
# <a name="submit-a-leave-request-to-workflow"></a>Soumettre une demande d’absence au workflow

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dans Microsoft Dynamics 365 Human Resources, vous pouvez utiliser l’interface de programmation d’application (API) MyLeaveRequests submit() pour soumettre une demande de congé au workflow. Cette API est présentée comme une action sur l’entité OData MyLeaveRequests.

## <a name="prerequisites"></a>Conditions préalables

La demande de congé doit être enregistrée dans la base de données et doit pouvoir être récupérée via l’entité MyLeaveRequests.

## <a name="permissions"></a>Autorisations

L’une des autorisations suivantes est requise pour appeler cette API. Pour plus d’informations sur le paramétrage des autorisations et la manière de sélectionner, voir [Authentification](hr-developer-api-authentication.md).

| Type d’autorisation                    | Autorisations (des moins privilégiées au plus privilégiées) |
|------------------------------------|--------------------------------------------------------|
| Délégué (compte professionnel ou éducatif) | utilisateur\_substitution d’identité                                    |

## <a name="https-request"></a>Demande HTTPS

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

La demande est conforme aux normes OData. Les paramètres {requestId}, {leaveType}, {leaveDate} et {dataArea} se rapportent aux champs qui constituent la clé naturelle composite de l’entité MyLeaveRequests.

> [!NOTE]
> Alors que les champs de l’entité MyLeaveRequests font référence à une ligne individuelle dans la demande de congé, l’appel de l’API de soumission soumettra toute la demande de congé (toutes les lignes) au workflow.

### <a name="request-headers"></a>En-tête de la demande

| En-tête         | Value                     |
|----------------|---------------------------|
| Autorisation  | Détenteur {token} (obligatoire) |
| Type de contenu   | application/json          |

### <a name="request-body"></a>Corps de demande

Ne fournissez pas de corps de demande pour cette méthode.

### <a name="response"></a>Réponse

Une réponse de réussite est toujours une réponse **204 Aucun contenu**.

Les appelants non autorisés recevront une réponse **401 Non autorisé** ou **403 Interdit**.

Si la soumission échoue (en raison de la validation, par exemple), la réponse sera **500 Erreur du serveur** et le corps de la réponse comprendra un objet JSON avec plus de détails.

## <a name="example"></a>Exemple

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

## <a name="validation-and-error-messages"></a>Validation et messages et d’erreur

Dans le cadre de l’appel à l’API de soumission, Human Resources effectue la validation de la logique métier avant la soumission, ce qui garantit que la demande de congé est dans un état valide pour la soumission. Les messages d’erreur possibles que vous pouvez recevoir dans la réponse si les validations échouent sont :

 - La demande doit définir le solde « {LeaveTypeId} » en-dessous du solde minimal autorisé au {date}.
 - La demande de congé en état Terminé ne peut pas être soumise.
 - Impossible de soumettre ou d’enregistrer la demande car aucune modification n’a été apportée. Ajoutez ou mettez à jour le montant ou le type de congé et réessayez.
 - La demande de congé saisie contient un ou plusieurs jours avec la même date et le même type de congé qu’une demande en attente existante. Veuillez rappeler la demande actuelle pour apporter des modification.
 - Le code motif « {ReasonCodeId} » ne s’applique pas aux types de congé de la demande.
 - Le type de congé ’ {LeaveTypeId} ’nécessite un code motif. Sélectionnez le type et le code motif appropriés.
 - Le congé n’a pas été soumis avec succès. Le congé a été enregistré en tant que brouillon de demande.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble de MyLeaveRequests](hr-developer-api-myleaverequests-overview.md)
- [Authentification](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]