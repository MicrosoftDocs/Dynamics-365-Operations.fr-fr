---
title: Créer des options de couverture
description: Cette rubrique décrit les options de couverture dans Microsoft Dynamics 365 Human Resources pour le choix d’un participant dans un régime de prestations sociales.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b6d35967e731f3618d932694b49c1952af9f93cf
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693918"
---
# <a name="create-coverage-options"></a>Créer des options de couverture


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les options de couverture déterminent qui doit être couvert, ou l’étendue de la couverture disponible dans un régime d’assurance. Par exemple, pour un régime médical, vous pouvez avoir une option **Employé seulement**, une option **Employé + 1** et une option **Famille**. Pour l’assurance-vie, vous pouvez offrir une couverture pour **1 x salaire** ou pour **2 x salaire**.

Une fois les options de couverture des avantages définie, vous pouvez les réutiliser. Vous pouvez associer une option avec un ou plusieurs plans.

> [!IMPORTANT]
> Après avoir défini les options de couverture, associez-les à un type de régime d’avantages. Le type de plan est ensuite associé à un régime de prestations sociales. Les options de couverture associées à un type de régime sont disponibles pour tous les régimes créés avec ce type de régime.

## <a name="create-coverage-options"></a>Créer des options de couverture
1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Options de couverture**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Option de couverture** | Un nom d’option de couverture unique. |
   | **Description** | La description de l’option de couverture. |
   | **Code couverture** | Les codes de couverture attribuent des montants minimum et maximum pour chaque type de personne couverte éligible. Un code de couverture indique qui est couvert ou le montant de couverture autorisé pour un type de plan. Vous pouvez exprimer le montant de la couverture sous forme de montant ou de pourcentage. Par exemple :<ul><li>**Emp+1** : pour être qualifié, l’employé doit avoir sélectionné une personne à charge (si plus d’une personne est sélectionnée, il ne sera plus qualifié).</li><li>**Emp+famille** : pour être qualifié, le salarié doit avoir sélectionné au moins deux personnes à charge.</li></ul> |
   | **Nombre maximal** | Nombre maximal de personnes à charge |
   | **État** | Statut de l’option de couverture. Si l’état de l’option de couverture est défini sur **Inactif**, l’option de couverture ne peut pas être sélectionnée sur les types de régime. |
   | **Pourcentage** | Montant du pourcentage. Ce champ n’est actif que si % x Salaire a été sélectionné dans le champ Code de couverture. |
   | **Diviseur** | Diviseur à utiliser dans le calcul lorsque vous sélectionnez le code de couverture % x salaire. |
   | **Pourcentage minimum** | Le pourcentage minimum lorsque vous sélectionnez le code de couverture en pourcentage. |
   | **Pourcentage maximal** | Le pourcentage maximum lorsque vous sélectionnez le code de couverture en pourcentage. |

4. Sous **Options d’éligibilité des contacts personnels**, associez l’option d’éligibilité des contacts personnels appropriée à chaque option de couverture.

5. Sous **Libre service**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Autoriser le montant de la contribution de l’employé** | Indique s’il faut autoriser les employés à modifier le montant de la contribution dans le libre service des avantages lorsqu’ils sélectionnent des avantages. Si vous cochez cette case, le système calculera les paramètres du régime de prestations en fonction du montant de cotisation que l’employé saisit dans le libre service des avantages. |
   | **Autoriser le montant de la couverture de l’employé** | Indique s’il faut autoriser les employés à modifier le montant de la couverture dans le libre service des avantages lorsqu’ils sélectionnent des avantages. Si vous cochez cette case, le système calculera les paramètres du régime de prestations en fonction du montant de couverture que l’employé saisit dans le Libre service employé. |

6. Sélectionnez **Enregistrer**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
