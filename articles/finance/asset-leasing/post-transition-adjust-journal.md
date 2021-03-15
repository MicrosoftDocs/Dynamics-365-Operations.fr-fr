---
title: Valider les écritures de journal d’ajustement de transition dans la location d’actifs
description: Cette rubrique décrit la fonctionnalité qui vous permet de faire la transition d’un portefeuille de locations vers les nouvelles normes comptables de location, l’article 842 sur la codification des normes comptables (ASC 842) et la norme internationale en matière de génération des états financiers 16 (IFRS 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51ae41e22507d77f32b8b0f4685cce797fd19cff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969551"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Valider les écritures de journal d’ajustement de transition dans la location d’actifs

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité qui vous permet de faire la transition d’un portefeuille de location vers les nouvelles normes de comptabilité de location : l’article 842 sur la codification des normes comptables (ASC 842), qui est la norme dans les principes comptables généralement reconnus aux États-Unis (US GAAP), et la norme internationale en matière de génération des états financiers 16 (IFRS 16).

Pour plus d’informations sur la configuration d’un registre pour la transition vers les nouvelles normes, voir [Créer des registres de location](set-up-lease-books.md).

Lorsque vous créez une écriture de journal d’ajustement de transition, une écriture de journal est générée. Cette écriture reflète l’impact sur le bilan de l’enregistrement de location selon les nouvelles normes à cette date. Le compte d’actif approprié est débité de la valeur comptable à cette date et le compte de passif est crédité. La différence est soit débitée, soit créditée aux bénéfices non répartis.

Pour enregistrer un ajustement de transition conformément aux nouvelles normes comptables, procédez comme suit.

1. Sur la page **Résumé du bail**, sélectionnez le bail, puis sélectionnez **Registres**.
2. Dans le registre, sélectionnez **Calendrier de paiement**.
3. Dans la boite de dialogue **Échéancier de paiement**, sélectionnez **Confirmer**. Ensuite fermez la boîte de dialogue.
4. Sélectionnez **Ajustement de transition**.

    > [!NOTE]
    > Un ajustement de transition ne peut être créé que pour les registres de location affectés à un registre où le champ **Registre de transition** est disponible. Si la valeur dans le champ **Début du bail** est postérieure à la date de transition, la valeur dans le champ **Ajustement de transition** ne sera pas mis à jour.

5. Pour afficher l’entrée de journal, sélectionnez **Journaux de location d’actifs**.
6. Sélectionnez le nouveau journal, puis sélectionnez **Valider**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]