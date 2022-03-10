---
title: Achat et vente de congés
description: Cette rubrique décrit comment soumettre des requêtes d’achat et de vente de congés dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ddc50540ba0686f18b6e8875e40f11c378c448f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067477"
---
# <a name="buy-and-sell-leave"></a>Achat et vente de congés


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dans Dynamics 365 Human Resources, vous pouvez soumettre des demandes d’achat et de vente de congés en fonction des stratégies d’achat et de vente de congés mises en place par votre entreprise.  

## <a name="request-to-buy-leave"></a>Demande d’achat de congé

1. Dans l’espace de travail **Libre service employé**, sélectionnez **Demande d’achat de congés** dans la vignette **Soldes des congés**. 

2. Ajoutez un **Type de congé** et entrez une **Quantité** pour la quantité de congés que vous souhaitez acheter. 

3. Sélectionner **Soumettre** lorsque vous êtes prêt à soumettre votre demande. 

Vos soldes seront automatiquement mis à jour ou passer par un processus d’approbation avant la mise à jour. Cela dépend de la façon dont la stratégie d’achat a été configurée.

## <a name="request-to-sell-leave"></a>Demande de vente de congé

1. Dans l’espace de travail **Libre service employé**, sélectionnez **Demande de vente de congés** dans la vignette **Soldes des congés**. 

2. Ajoutez un **Type de congé** et entrez une **Quantité** pour la quantité de congés que vous souhaitez vendre. 

3. Sélectionner **Soumettre** lorsque vous êtes prêt à soumettre votre demande.

Vos soldes seront automatiquement mis à jour ou passer par un processus d’approbation avant la mise à jour. Cela dépend de la façon dont la stratégie d’achat a été configurée.


## <a name="troubleshooting"></a>Résolution des problèmes 

Si un workflow de demande d’achat ou de vente de congé échoue, les utilisateurs ayant le privilège **EssLeaveBuySellRequestApprover** peuvent consulter le journal des messages pour toutes les demandes d’achat et de vente de congé. Pour ce faire, accédez à **Congés et absences > Liens > Demandes d’achat et de vente de congés > Journal des messages** (en haut à gauche). Le **Journal des messages** montre aux utilisateurs comment les transactions ont été traitées ainsi que l’historique du workflow associé.


## <a name="see-also"></a>Voir également :

[Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)</br>
[Gérer les stratégies d’achat et de vente de congés](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
