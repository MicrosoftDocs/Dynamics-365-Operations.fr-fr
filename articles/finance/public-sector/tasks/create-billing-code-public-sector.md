---
title: Créer un code de facturation pour le secteur public
description: Les champs personnalisés du code facturation permettent de rassembler les valeurs des champs de code facturation lors de la création de factures financières.
author: twheeloc
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustCustomField
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 849f5342273c4440e60ebf6d19c77829eb483d9e
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119573"
---
# <a name="create-a-billing-code-for-the-public-sector"></a>Créer un code de facturation pour le secteur public

[!include [banner](../../includes/banner.md)]

Les champs personnalisés du code facturation permettent de rassembler les valeurs des champs de code facturation lors de la création de factures financières. Une fois que vous avez affecté le champ personnalisé aux codes facturation,les utilisateurs peuvent accéder au champ lorsque le code facturation est sélectionné au niveau d’une ligne de facture financière. Cette procédure a été créée à l’aide des données de la société fictive PSUS dans la partition du secteur public.

1. Accédez à **Comptabilité client > Configuration > Champs personnalisés du code facturation**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Nom**.
4. Sélectionnez une option dans le champ **Type**.
    * Lorsque vous sélectionnez une option, les champs de la section **Description** changent pour refléter les paramètres disponibles pour cette option.  
    * Dans la section **Détails**, entrez la valeur par défaut pour ce champ personnalisé et toutes autres valeurs nécessaires.  
5. Ouvrez la section **Description**.
6. Facultatif : dans le champ **Description de l’utilisation**, décrivez comment le champ personnalisé doit être utilisé. Ces informations sont à usage interne uniquement. Elle ne sont pas visibles pour l’utilisateur.
7. Ouvrez la section **Références du code facturation**. Lorsque vous affectez ce champ personnalisé à un code facturation, le code facturation est indiqué ici.
8. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
