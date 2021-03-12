---
title: Reclasser la partie à court terme d’un passif locatif
description: Cette rubrique explique comment créer une entrée de journal mensuelle pour reclasser une partie du passif locatif comme à court terme.
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
ms.openlocfilehash: 08ca824bb4c4a02a80f2187fb5f8fe4e8b7327c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992912"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Reclasser la partie à court terme du passif locatif

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer une entrée de journal mensuelle pour reclasser une partie du passif locatif comme à court terme. Lorsque la planification sélectionnée dans le traitement par lots est **Reclassement du passif locatif à court terme**, une entrée de journal est créée. Cette entrée est utilisée pour enregistrer la partie courante du passif locatif le dernier jour du mois. Dans le même temps, une écriture de contrepassation est validée à partir du premier jour du mois suivant.

La partie à court terme du passif locatif est présentée dans le tableau d’amortissement du passif. Lorsque l’entrée de journal est validée, la colonne **Journal de reclassement du passif créé** devient disponible et l’ID du journal est également renseignée dans le programme.

Pour créer et valider l’entrée de journal de reclassement de passif à court terme, procédez comme suit.

1. Aller à **Location d’actifs \> Périodique \> Création de journal par lot**.
2. Dans la boîte de dialogue **Création de journaux par lots**, dans le champ **Sélectionner un échéancier**, sélectionnez **Reclassement du passif locatif à court terme**.
3. Dans le champ **Groupe de location**, sélectionnez un groupe de locations. Alternativement, dans le champ **ID du registre**, sélectionnez l’ID du registre.
4. Activez le paramètre **valider**. Sinon, si l’écriture doit être créée mais pas publiée, laissez ce paramètre désactivé.
5. Activez le paramètre **Aperçu avant de valider** pour afficher l’écriture avant sa validation.
6. Cliquez sur **OK**.
