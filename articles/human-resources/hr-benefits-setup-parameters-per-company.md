---
title: Configurer les paramètres de gestion des avantages par entreprise
description: Configurez les paramètres de gestion des avantages par entreprise dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2c564f0dfd1cbe44566269c97218450fedf2173
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057620"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurer les paramètres de gestion des avantages par entreprise

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Pour chaque organisation qui offre des avantages, vous devez configurer les paramètres des e-mails de confirmation des avantages.

## <a name="configure-confirmation-email-settings"></a>Configurer la confirmation des paramètres d’e-mail

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres Human Resources**.

2. Dans l’onglet **Gestion des avantages**, spécifiez les valeurs pour les champs suivants : 

   | Champ | Description |
   | --- | --- |
   | **Envoyer un e-mail de confirmation** | Lorsque cette fonction est activée, un e-mail de confirmation est envoyé aux employés lorsqu’ils quittent l’expérience d’inscription aux avantages dans le libre-service des employés. |
   | **Modèle d’e-mail de confirmation** | Sélectionnez le modèle d’e-mail de l’organisation à utiliser lors de l’envoi de la confirmation d’inscription. Si vous ne sélectionnez pas de modèle, l’e-mail générique suivant sera envoyé :<br><br>%EmployeeFirstName%,<br><br>Félicitations ! Vous avez terminé votre inscription aux avantages.<br><br>Merci,<br><Nom de l’entreprise/organisation> Avantages. |
   | **Adresse e-mail de l’expéditeur par défaut** | L’adresse e-mail à utiliser lors de l’envoi de l’e-mail de confirmation. |

3. Sélectionnez **Enregistrer**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]