---
title: Configurer les options d’éligibilité des contacts personnels
description: Cette rubrique explique comment configurer les options d’éligibilité pour les contacts personnels dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bd0ba4b609aaf05d37b120eaea71095a589bcc0a
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423291"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurer les options d’éligibilité des contacts personnels

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique explique comment configurer les types de contacts personnels pouvant être utilisés pour les avantages dans Microsoft Dynamics 365 Human Resources. Les contacts personnels sont les personnes qui seront couvertes par vos régimes (personnes à charge) ou qui bénéficieront de vos régimes (bénéficiaires). Les personnes à charge sont généralement les conjoints ou les enfants. Les bénéficiaires peuvent être des conjoints, des enfants, des fiducies ou des parents.

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
