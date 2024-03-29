---
title: Annuler le travail d’entrepôt pour le traitement des exceptions
description: Cet article décrit la fonctionnalité Annuler le travail qui permet aux superviseurs d’entrepôt de gérer le travail bloqué.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b1e2036e4e7a8a47d6df029f285df7aca0fa74e6
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403679"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Annuler le travail d’entrepôt pour le traitement des exceptions

[!include [banner](../includes/banner.md)]

La fonctionnalité Annuler le travail dans Microsoft Dynamics 365 Supply Chain Management permet à l’utilisateur administrateur d’annuler un travail d’entrepôt spécifique en cours, mais qui est bloqué par le système ou ne peut pas être exécuté en raison de les circonstances exceptionnelles. Cette fonctionnalité est une offre attractive et sécurisée autre que les scripts correctifs SQL qui résolvent des données incohérentes. Toutefois, alors que ces scripts sont généralement demandés par des professionnels de l’informatique, la fonctionnalité Annuler le travail peut être utilisée par les utilisateurs de la société disposant de droits d’administrateur.

Vous pouvez accéder à la fonctionnalité Annuler le travail dans **Gestion des entrepôts** \> **Tâches périodiques** \> **Nettoyer \> Annuler le travail**. Dans la boîte de dialogue **Annuler le travail**, spécifiez l’ID travail du travail à annuler, puis sélectionnez **OK**.

## <a name="warehouse-work-that-can-be-canceled"></a>Travail d’entrepôt pouvant être annulé

Au cours des opérations de prélèvement d’entrepôt, un collaborateur peut rencontrer des situations où ils ont enregistré des quantités comme prélevées à un emplacement de stockage et rangé dans leur emplacement utilisateur, mais ils ne peuvent pas enregistrer l’opération de rangement. Les données d’entrepôt incohérentes sont souvent, mais pas toujours, la raison pour laquelle le travail est bloqué.

Contrairement à une fonctionnalité Annuler standard à laquelle on accède via le bouton **Annuler** dans l’en-tête du travail, la fonctionnalité Annuler le travail ne nécessite pas que la dernière ligne de travail terminé soit une ligne de travail du type **rangement**. En d’autres termes, pour la fonctionnalité Annuler le travail, la logique d’annulation peut être exécutée même si la quantité d’article sur une ligne de travail est à un emplacement utilisateur.

> [!NOTE]
> Pour le travail qui doit être annulé pour des raisons opérationnelles, les utilisateurs d’entrepôts doivent continuer à utiliser la fonctionnalité Annuler standard sur la page de travail.

Seul le travail de type **Ventes**, **Sortie de transfert**, **Prélèvement de matières premières** ou **Réapprovisionnement** peut être annulé à l’aide de la fonctionnalité Annuler le travail. La logique d’annulation n’est pas exécutée sur le travail de prélèvement de matières premières surgelées ou le travail qui peut être annulé en utilisant la fonctionnalité Annuler standard (voir la note précédente).

Pour débloquer le travail, le système annule toutes les lignes de travail restantes et corrige les données d’entrepôt associées à l’ID travail que l’utilisateur a spécifié. Toutes les opérations de gestion en entrepôt standard qui impliquent la quantité d’article affectée peuvent alors continuer.

Pour ranger l’article affecté à un emplacement spécifique une fois le travail annulé, l’utilisateur doit utiliser une opération de mouvement de stock ou d’ajustement de quantité sur un appareil mobile.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]