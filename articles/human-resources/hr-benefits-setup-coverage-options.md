---
title: Créer des options de couverture
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
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008960"
---
# <a name="create-coverage-options"></a>Créer des options de couverture

[!include [banner](includes/preview-feature.md)]

Les options de couverture dans Microsoft Dynamics 365 Human Resources sont les niveaux de couverture selon le choix d'un participant dans un régime ou un programme d'avantages sociaux, comme Employé seulement pour un régime médical ou 2x Salaire pour un régime d'assurance-vie. Une fois définies, les options de couverture des prestations sont réutilisables et vous pouvez associer une option à un ou plusieurs plans.

Une fois les options de couverture définies, associez les options de couverture à un type de régime d'avantages sociaux. Le type de plan est ensuite associé à un plan ou programme d'avantages. Les options de couverture associées à un type de plan seront disponibles pour tous les plans créés avec ce type de plan. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Options de couverture**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Option de couverture** | Un nom d'option de couverture unique. |
   | **Description** | La description de l'option de couverture. |
   | **Code couverture** | Les codes de couverture attribuent des montants minimum et maximum pour chaque type de personne couverte éligible. Un code de couverture indique qui est couvert ou le montant de couverture autorisé pour un type de plan. Vous pouvez exprimer le montant de la couverture sous forme de montant ou de pourcentage. Par exemple :</br></br>- **Emp + 1** - pour être qualifié, le salarié doit avoir sélectionné une personne à charge (si plus d'une personne est sélectionnée, il ne sera plus qualifié).</br></br>- **Emp + famille** - pour être qualifié, le salarié doit avoir sélectionné au moins deux personnes à charge. |
   | **Nombre maximal** | Nombre maximal de personnes à charge |
   | **État** | Statut de l'option de couverture. Si l'état de l'option de couverture est défini sur Inactif, l'option de couverture ne peut pas être sélectionnée sur les types de plan. |
   | **Pourcentage** | Montant du pourcentage. Ce champ n'est actif que si % x Salaire a été sélectionné dans le champ Code de couverture. |
   | **Diviseur** | Diviseur à utiliser dans le calcul lorsque vous sélectionnez le code de couverture % x salaire. |
   | **Pourcentage minimum** | Le pourcentage minimum lorsque vous sélectionnez le code de couverture en pourcentage. |
   | **Pourcentage maximal** | Le pourcentage maximum lorsque vous sélectionnez le code de couverture en pourcentage. |

4. Sous **Options d'éligibilité des contacts personnels**, associez l'option d'éligibilité des contacts personnels appropriée à chaque option de couverture.

5. Sous **Libre-service**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Autoriser le montant de la contribution de l'employé** | Indique s'il faut autoriser les employés à modifier le montant de la contribution sur le libre-service des avantages lorsqu'ils sélectionnent des avantages. Si vous cochez cette case, le système calculera les paramètres du régime d'avantages en fonction du montant de cotisation que l'employé saisit dans le libre-service des avantages. |
   | **Autoriser le montant de la couverture de l'employé** | Indique s'il faut autoriser les employés à modifier le montant de la couverture sur le libre-service des avantages lorsqu'ils sélectionnent des avantages. Si vous cochez cette case, le système calculera les paramètres du régime d'avantages en fonction du montant de couverture que l'employé saisit dans le Libre-service employé. |

6. Sélectionnez **Enregistrer**. 
