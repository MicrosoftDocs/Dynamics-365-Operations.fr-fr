---
title: Configurer les options d’éligibilité des contacts personnels
description: Cet article explique comment configurer les options d’éligibilité pour les contacts personnels dans Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: 82bb7c037b4e0ab9950ce4c314c03a0f2d713bbd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895929"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurer les options d’éligibilité des contacts personnels


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article explique comment configurer les types de contacts personnels pouvant être utilisés pour les avantages dans Microsoft Dynamics 365 Human Resources. Les contacts personnels sont les personnes qui seront couvertes par vos régimes (personnes à charge) ou qui bénéficieront de vos régimes (bénéficiaires). Les personnes à charge sont généralement les conjoints ou les enfants. Les bénéficiaires peuvent être des conjoints, des enfants, des fiducies ou des parents.

1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Options d’éligibilité des contacts personnels**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Option d’éligibilité** | Nom ou code d’option d’éligibilité unique pour identifier l’option d’éligibilité. |
   | **Description** | Brève description de l’option d’éligibilité. |
   | **Code d’éligibilité du contact** | Code système qui décrit le mieux l’option d’éligibilité personnelle. Vous pouvez sélectionner l’une des valeurs suivantes : <ul><li>Relation</li><li>Étudiant</li><li>Couverture des personnes à charge</li><li>Personne à charge présentant un handicap et dépassant l’âge requis</li></ul> |
   | **État** | Statut de l’option d’éligibilité. Si le statut d’une option d’éligibilité est défini sur inactif, vous ne pouvez pas sélectionner cette option d’éligibilité pour les contacts personnels. |
   | **Relation** | Spécifie la relation entre le contact personnel et l’employé. Ce champ n’est actif que si le code d’éligibilité du contact est défini sur Relation. |
   | **Âge** | Âge maximum d’un contact personnel éligible pour le plan d’avantages. Ce champ n’est actif que si vous sélectionnez une relation. Cet âge est comparé à l’âge calculé du contact personnel. L’âge calculé est le suivant : (date de couverture – date de naissance du contact personnel / 365). Ce nombre est toujours un entier. |

4. Sélectionnez **Enregistrer**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
