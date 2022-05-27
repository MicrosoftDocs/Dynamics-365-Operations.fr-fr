---
title: Configurer le libre-service employé
description: Dans Microsoft Dynamics 365 Human Resources, vous pouvez configurer des vignettes pour une navigation de niveau supérieur dans le libre-service employé.
author: twheeloc
ms.date: 12/06/2021
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
ms.openlocfilehash: d7ddb1f1ea74a16265dac701151b2c25a4f9d4dc
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687161"
---
# <a name="configure-employee-self-service"></a>Configurer le libre-service employé


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dans Microsoft Dynamics 365 Human Resources, vous pouvez configurer des vignettes pour une navigation de niveau supérieur dans le **libre-service employé**. Les vignettes de régime de prestations dirigent les utilisateurs vers les plans d’avantages auxquels ils sont éligibles.

## <a name="set-up-a-benefit-plans-tile"></a>Paramétrage d’une vignette de régime d’avantage

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres du libre-service employé**.

2. Sélectionnez l’onglet **Paramétrage d’une vignette de plans d’avantage**, puis sélectionnez **Nouveau**.

3. Spécifiez des valeurs pour les champs suivants.

   | Champ | Description |
   | --- | --- |
   | **Code de type de plan** | Type de régime qui s’affiche lorsque cette vignette est sélectionnée dans **Libre-service des avantages**. |
   | **ID vignette** | Identificateur unique de la vignette. |
   | **Texte d’étiquette de vignette** | Texte qui sera affiché pour la vignette dans le **Libre-service des avantages**. |
   | **Description** | Description de la vignette. |
   | **Image d’arrière-plan de la vignette** | URL de l’image à utiliser pour la vignette (facultatif). |
   | **Suivre la progression des affiliations** | Sélectionnez cette option pour suivre la progression de l’affiliation pour ce type de régime. Par exemple, vous pouvez avoir des régimes créés où **Type de régime = Autre**. Ces régimes peuvent être des régimes facultatifs pour lesquels vous ne souhaitez pas suivre la progression de l’affiliation. Si vous ne sélectionnez pas ce type de régime, il sera ignoré lors du suivi de la progression ou de l’achèvement de l’affiliation dans l’onglet **Affiliation**. Ce paramètre s’applique au type de régime sélectionné pour toutes les périodes et entités juridiques. |

4. Cliquez sur **Enregistrer**.

## <a name="set-up-a-flex-credit-plan-tile"></a>Configuration d’une vignette de plan de crédit flexible

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres du libre-service employé**.

2. Sélectionnez l’onglet **Paramétrage d’une vignette de plan de crédit flexible**, puis sélectionnez **Nouveau**.

3. Spécifiez des valeurs pour les champs suivants.

   | Champ | Description |
   | --- | --- |
   | **ID de crédit d’avantage** | Régimes du programme de crédit flexible qui s’affichent lorsque cette vignette est sélectionnée dans **Libre-service des avantages**. |
   | **ID vignette** | Identificateur unique de la vignette. |
   | **Texte d’étiquette de vignette** | Texte qui sera affiché pour la vignette dans le **Libre-service des avantages**. |
   | **Description** | Description de la vignette. |
   | **Image d’arrière-plan de la vignette** | URL de l’image à utiliser pour la vignette (facultatif). |
   | **Suivre la progression des affiliations** | Sélectionnez cette option pour suivre la progression de l’affiliation pour ce type de régime. Par exemple, vous pouvez avoir des régimes créés où **Type de régime = Autre**. Ces régimes peuvent être des régimes facultatifs pour lesquels vous ne souhaitez pas suivre la progression de l’affiliation. Si vous ne sélectionnez pas ce type de régime, il sera ignoré lors du suivi de la progression ou de l’achèvement de l’affiliation dans l’onglet **Affiliation**. Ce paramètre s’applique au type de régime sélectionné pour toutes les périodes et entités juridiques. |

4. Cliquez sur **Enregistrer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
