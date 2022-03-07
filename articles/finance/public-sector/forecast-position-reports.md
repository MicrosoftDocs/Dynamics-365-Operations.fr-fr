---
title: États de poste de prévision pour le secteur public
description: Vous pouvez utiliser les états de synthèse de poste de prévision et de détail de poste de prévision pour générer des informations sur les postes de prévision lors d’un plan budgétaire et d’un scénario que vous spécifiez.
author: velofog
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2019-8-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 012f5db5e524cd43ab1971d0eb72fddd13512104
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258149"
---
# <a name="forecast-position-reports-for-the-public-sector"></a>États de poste de prévision pour le secteur public

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser les états de **synthèse de poste de prévision** et de **détail de poste de prévision** pour générer des informations sur les postes de prévision lors d’un plan budgétaire et d’un scénario que vous spécifiez.  

L’état **Synthèse de poste de prévision** montre les coûts de poste de prévision par distributions de compte. Les coûts de poste de prévision sont affichés, regroupés par leurs distributions de compte affectées. Les montants des coûts sont factorisés selon le pourcentage attribué à la distribution de compte. 

L’état **Détails du poste de prévision** contient la plupart des informations affichées sur le formulaire de poste de prévision. Les distributions de compte affectées au poste de prévision via les dimensions financières et les modèles de dimension financière sont affichées, ainsi que les coûts associés à chaque combinaison de répartition pour le poste de prévision. 

Pour afficher des informations supplémentaires sur un poste de prévision, sélectionnez le numéro de poste pour ouvrir la page du poste de prévision.

## <a name="filter-the-data-on-this-report"></a>Filtrage des données dans cet état

Lorsque vous générez l’état, les paramètres par défaut suivants sont affichés.  Ces paramètres permettent de filtrer les données qui apparaîtront sur l’état.  

| Champ | Description |
| --------- | ------- |
| Scénario de plan budgétaire | Sélectionnez le scénario de plan budgétaire qui doit figurer dans l’état. <p> Les scénarios de plan budgétaire définissent les catégories de données pour les plans budgétaires. Vous définissez des scénarios de plan budgétaire pour prendre en charge des classes monétaires et d’autres classes d’unités de mesure, telles que la quantité. L’année précédente du département et les demandes du département sont des exemples de scénarios de plan budgétaire monétaires. Les appels passés au support de l’année précédente et le comptage équivalent temps plein (ETP) sont des exemples de scénarios de plan budgétaire qui utilisent des quantités. </p>  |
| Processus de planification budgétaire | Sélectionnez le processus de planification budgétaire qui doit figurer dans l’état.<p> Les processus de planification budgétaire déterminent la manière dont les plans budgétaires peuvent être mis à jour, acheminés, révisés, puis approuvés dans la hiérarchie d’organisation de budgétisation. Un processus de planification budgétaire est lié à un cycle budgétaire et à une organisation via une entité juridique. </p> |
| Structure de compte par défaut | Sélectionnez la structure de compte par défaut pour afficher les dimensions comptables aux postes de prévision dans l’ordre que vous souhaitez.|
| Département | Sélectionnez un département qui doit figurer dans l’état. Laissez le champ vide pour exécuter l’état pour tous les comptes. |
| Non exécuté uniquement | Définissez cette option sur Oui pour exclure des postes actuellement remplis. |
| Supprimer le total | Définissez cette option sur Oui pour exclure les totaux de l’état. |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]