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
ms.openlocfilehash: 80b7125df93d9bdfb866b37abebbdc412d7e5b95
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509386"
---
# <a name="buy-and-sell-leave"></a>Achat et vente de congés


>[!Important]
>La fonctionnalité indiquée dans cette rubrique est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.

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
