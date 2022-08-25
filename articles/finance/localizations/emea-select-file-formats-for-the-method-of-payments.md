---
title: Formats de fichier des modes de paiement
description: Cet article décrit les deux méthodes d’obtention des formats de fichier que vous pouvez utiliser pour les modes de paiement.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 262514
ms.search.form: CustPaymMode, VendPaymMode
ms.openlocfilehash: eae21fba2499d819a146953e56f48a8f9d748582
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292216"
---
# <a name="file-formats-for-methods-of-payment"></a>Formats de fichier des modes de paiement

[!include [banner](../includes/banner.md)]

Cet article décrit les deux méthodes d’obtention des formats de fichier que vous pouvez utiliser pour les modes de paiement.

Deux méthodes peuvent être utilisées pour obtenir les formats de fichier à utiliser avec les modes de paiement, les formats de fichier de génération d’états électroniques ou les formats de fichier X++. Lorsque vous paramétrez un mode de paiement pour un client ou un fournisseur, vous indiquez les formats de fichier et les normes qui doivent être utilisés pour les paiements et le mode de traitement des paiements. Vous pouvez choisir parmi les types de format suivants :

-   Exportation
-   Importation
-   Retourner
-   Remise

### <a name="method-1-electronic-reporting-file-formats"></a>Méthode 1 : formats de fichier de génération d’états électroniques

Pour les formats de fichier basés sur les configurations ER, vous devez importer les configurations à partir de Lifecycle Services (LCS). Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md) Après avoir importé les configurations de génération d’états pour ces formats de fichier, les formats importés sont disponibles dans la page **Modes de paiement**. Le processus d’importation et de sélection des formats de fichier pour l’Europe est similaire à la procédure pour le Japon. Pour plus d’informations, voir [Activer le format de fichier de paiement JBA](tasks/jba-payment-file-format.md)

### <a name="method-2-x-file-formats"></a>Méthode 2 : formats de fichier X++

Pour sélectionner les formats de fichier basés sur le code X++, procédez comme suit.

1.  Accédez à la page **Modes de paiement**.
2.  Dans l’organisateur **Formats de fichier**, cliquez sur **Paramétrage**.
3.  Sélectionnez l’onglet correspondant au type de format de fichier.
4.  Sélectionnez un format de fichier dans la liste **Disponible** et déplacez-le vers la liste **Sélectionné** avec le contrôle de flèche.
5.  Fermez la page **Formats de fichier des modes de paiement**.
6.  Dans l’organisateur **Formats de fichier**, sélectionnez le format de fichier à utiliser pour le mode de paiement dans le champ de format de fichier approprié. Les options de génération d’états électroniques génériques doivent être définies sur **Non** pour les formats de fichier X++.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
