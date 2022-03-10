---
title: Configurer les paramètres de bail (version préliminaire)
description: Cette rubrique décrit les paramètres de configuration de la location d’actifs, tels que les informations de sécurité et les paramètres de comptabilité.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a644b3c9d9ed4fc86a816af1ab338b96b1aa7ad
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968075"
---
# <a name="configure-lease-parameters"></a>Configurer les paramètres de bail

[!include [banner](../includes/banner.md)]

Plusieurs paramètres de configuration affectent le comportement de la location d’actifs. Ces paramètres incluent les noms de journaux, les paramètres généraux et les paramètres de profil de publication.

1. Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.
2. Sous l’onglet **Baux**, sélectionnez le raccourci **Général**.

    Le paramètre **Autoriser le remplacement manuel de la classification** détermine si la classification du bail peut être remplacée avant la confirmation de l’échéancier de paiement.

    Le paramètre **Lot inter-entités** détermine si vous pouvez publier dans d’autres entités juridiques à partir de l’entité juridique actuelle. Si ce paramètre est activé, vous pouvez créer des entrées de journal pour les entités juridiques auxquelles vous avez accès.

3. Mettez l’option **Autoriser la suppression des baux confirmés** sur **Oui** pour permettre la suppression des baux dont les échéanciers de paiement ont été confirmés. Les baux ne peuvent pas être supprimés si des transactions validées ou non comptabilisées leur sont associées, quel que soit le paramètre de cette option. Vous ne pouvez pas restaurer un enregistrement de bail après sa suppression. Si vous téléchargez des enregistrements pour un bail supprimé, manuellement ou via des entités de données, les informations téléchargées sont traitées comme nouvelles et non comme une mise à jour d’un bail existant.

    Si vous définissez cette option sur **Oui**, et si le type de transition du registre est **Option de rattrapage cumulatif A ou B**, le système définit le champ **Taux d’emprunt progressif** sur la valeur du champ **Taux d’emprunt progressif à la transition** sur la page **Paramétrage du registre**. Si cette option est définie sur **Non**, le taux du bail principal est fixé sur la valeur du champ **Taux d’emprunt progressif** sur la page **Détails du registre**, quel que soit le type de transition du registre.

4. Définissez l’option **Autoriser les contrepassations d’amortissement sur le registre clôturé** sur **Oui** pour permettre la contrepassation des transactions de dotation aux amortissements. Les transactions de dépenses peuvent être annulées même lorsque la version comptable est fermée.

    > [!NOTE]
    > Nous vous recommandons de conserver cette option définie sur **Non**. Le paramétrage de cette option est utilisé comme une validation et un contrôle pour éviter qu’une version de registre clôturé ne soit accidentellement dépréciée. En gardant l’option définie sur **Non**, vous contribuez à maintenir la précision de la valeur nette et des calculs d’amortissement à venir.

5. Définissez l’option **Autoriser la ventilation du montant du paiement** sur **Oui** pour autoriser la ventilation des montants des paiements sur le raccourci **Lignes d’échéancier de paiement** de la page **Bail**. Les types de répartition des paiements sont définis sous **Paramétrage** sur la page **Types de montant de paiement**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
