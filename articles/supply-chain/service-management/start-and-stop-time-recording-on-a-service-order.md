---
title: Démarrage et arrêt de l’enregistrement de l’heure dans une commande de service
description: Démarrage et arrêt de l’enregistrement de l’heure dans une commande de service.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cc205daa35c898147559427b071d1d2c2720de3a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817459"
---
# <a name="start-and-stop-time-recording-on-a-service-order"></a>Démarrage et arrêt de l’enregistrement de l’heure dans une commande de service 

[!include [banner](../includes/banner.md)]


Cette procédure permet de démarrer et d’arrêter l’enregistrement d’heure pour une commande de service pour laquelle un contrat SLA est défini.

## <a name="start-time-recording"></a>Démarrage de l’enregistrement de l’heure

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Cliquez sur l’onglet **Commande de service**. Dans le volet **Actions**, dans le groupe **Contrat de niveau de service**, cliquez sur **Démarrer**.

3.  Entrez les date et heure auxquelles l’enregistrement de l’heure doit commencer.

## <a name="stop-time-recording"></a>Arrêter l’enregistrement de l’heure

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Cliquez sur l’onglet **Commande de service**. Dans le volet **Actions**, dans le groupe **Contrat de niveau de service**, cliquez sur **Arrêter**.

3.  Entrez les date et heure auxquelles l’enregistrement de l’heure doit être arrêté.

4.  Sélectionnez **Ajouter un motif de révocation** et sélectionnez un code motif dans la liste **Code motif du stade** si vous souhaitez indiquer la raison de l’arrêt de l’enregistrement de l’heure.


> [!NOTE]
> <P>Si <STRONG>Code motif du dépassement de l’heure</STRONG> est sélectionné dans l’écran <STRONG>Paramètres de gestion des services</STRONG>, vous devez fournir un code motif avant de pouvoir arrêter l’enregistrement de l’heure.</P>



## <a name="see-also"></a>Voir également :

[Démarrer l’enregistrement de l’heure du contrat SLA (écran)](https://technet.microsoft.com/library/hh242297\(v=ax.60\))

[Arrêter l’enregistrement de l’heure du contrat SLA (écran)](https://technet.microsoft.com/library/hh242241\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]