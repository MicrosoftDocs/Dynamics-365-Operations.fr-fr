---
title: Demander un congé
description: Soumettre une demande de congé.
author: twheeloc
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveofAbsenceRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6c98246e94670dd5f882fcbbd1f269e57f66faf
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805285"
---
# <a name="request-a-leave-of-absence"></a>Demander un congé

>[!Important]
>La fonctionnalité indiquée dans cet article est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez soumettre une demande de congé et voir l’état de vos demandes de congé dans Dynamics 365 Human Resources.

## <a name="request-a-leave-of-absence"></a>Demander un congé

1. Dans l’espace de travail **Libre service employé**, sélectionnez **Plus** (...) dans la vignette **Soldes des congés**.

2. Pour soumettre une demande de congé, sélectionnez **Demander un congé**.

3. Entrez des informations pour **Type de congé**, **Date de début** et **Date de fin**.

4. Si vous devez soumettre des pièces justificatives, sélectionnez **Charger** sous **Pièces jointes**.

5. Entrez les informations dans **Commentaire**, si besoin.

6. Sélectionner **Soumettre** lorsque vous êtes prêt à soumettre votre demande. Sinon, sélectionnez **Enregistrer en tant que brouillon**.


## <a name="view-leave-of-absence-request-status"></a>Afficher le statut des demandes de congé

1. Dans l’espace de travail **Libre service employé**, sélectionnez **Plus** (...) dans la vignette **Soldes des congés**.

2. Pour visualiser vos demandes de congé, sélectionnez **Afficher les congés**.

## <a name="update-a-leave-of-absence-request"></a>Mettre à jour une demande de congé

1. Dans l’espace de travail **Libre-service employé**, sélectionnez **Plus** (...) dans la vignette **Congé**.
2. Sélectionnez la demande de congé à mettre à jour, puis sélectionnez **Mettre à jour le congé**.
3. Dans le champ **Date de fin**, mettez à jour la valeur appropriée pour prolonger ou raccourcir le congé.
4. Si la date de fin est confirmée, définissez l’option **Confirmer la date de fin** sur **Oui**.
5. Une fois que l’option **Confirmer la date de fin** est définie sur **Oui**, vous pouvez télécharger un avis de retour au travail. Cochez ensuite la case pour confirmer qu’un avis de retour au travail a été téléchargé.
6. Sélectionnez **Soumettre** pour mettre à jour la demande de congé.

## <a name="cancel-a-leave-of-absence-request"></a>Annuler une demande de congé

1. Dans l’espace de travail **Libre-service employé**, sélectionnez **Plus** (...) dans la vignette **Congé**.
2. Sélectionnez la demande de congé à annuler, puis sélectionnez **Mettre à jour le congé**.
3. Définissez l’option **Annuler le congé** sur **Oui**.
4. Sélectionnez **Soumettre** pour annuler la demande de congé.

## <a name="importing-leave-requests-from-other-systems-or-older-systems"></a>Importation de demandes de congé depuis d’autres systèmes ou des systèmes plus anciens

Pour importer des demandes de congé à partir d’un autre système, vous devez passer par le workflow normal pour créer les transactions de congé appropriées. Autrement, vous pouvez importer les transactions bancaires de congé et les demandes de congé dans un état Terminé. Notez que les transactions bancaires de congés ne sont pas créées automatiquement si vous importez uniquement les demandes de congés.

## <a name="see-also"></a>Voir également :

[Suspendre les congés](hr-leave-and-absence-suspend-leave.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
