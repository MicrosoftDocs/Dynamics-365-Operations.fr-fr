---
title: Le justificatif n’est pas généré
description: Cette rubrique fournit des informations de dépannage qui peuvent vous aider lorsqu’un justificatif doit être généré mais ne l’est pas.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1fbd5b5bb4a1d2a0c498b2abac82bd6f5ff3f1d2ed9960885eb8f44cbb17884d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759870"
---
# <a name="voucher-isnt-generated"></a>Le justificatif n’est pas généré

[!include [banner](../includes/banner.md)]

Si un justificatif doit être généré, mais que la page **Justificatif de transaction** n’affiche rien, suivez les étapes des sections suivantes pour résoudre ce problème.

[![Page Justificatif de transaction sans justificatif.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Vérifier l’applicabilité de la taxe

1. Accédez à **Taxe** \> **Tâches périodiques** \> **Écritures de journal de comptabilité auxiliaire non encore transférées**.
2. S’il existe un enregistrement de journal, sélectionnez-le, puis sélectionnez **Transférer maintenant**.

    [![Bouton Transférer maintenant sur la page Écritures de journal de comptabilité auxiliaire non encore transférées.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Ouvrez la page **Justificatif de transaction** à nouveau pour voir si le justificatif a été généré.

## <a name="determine-whether-customization-exists"></a>Déterminer si la personnalisation existe

Si vous avez terminé les étapes de la section précédente mais que vous n’avez trouvé aucun problème, déterminez s’il existe une personnalisation. Si aucune personnalisation n’existe, créez une demande de service Microsoft pour une assistance supplémentaire.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
