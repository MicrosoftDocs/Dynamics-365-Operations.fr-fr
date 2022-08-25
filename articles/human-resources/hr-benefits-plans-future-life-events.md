---
title: Configurer les événements de vie futurs
description: Cet article décrit comment planifier des événements de vie futurs dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2cb3ca03e0d9d7e5423a405f1eb0372e1c19588d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227983"
---
# <a name="configure-future-life-events"></a>Configurer les événements de vie futurs

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

Vous pouvez planifier des événements de vie futurs dans Dynamics 365 Human Resources.

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Événement de vie futurs**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | Date de l’événement de vie | Le système traite tous les événements de la période d’inscription qui se produisent jusqu’à cette date. |
   | Événement de vie enregistré | Date et heure de consignation de l’événement de vie. |
   | Type de journal | Indique si l’action est l’une des suivantes :</br></br>- **Mettre à jour** – modification à un enregistrement existant qui effectue le suivi des événements de vie</br></br>- **Insérer** – création d’un nouvel enregistrement d’événement de vie |
   | ID du type d’événement de vie | Identificateur unique pour le type d’événement de vie. |
   | Type d’événement de vie | Catalyseur pour mettre à jour l’inscription aux avantages d’un employé. Pour plus d'informations, voir la section Déclencheurs d’événement de vie. |
   | Statut | Indique si l’événement de vie a été traité ou non. |
   | Ligne | Numéro de ligne du futur événement de vie. |

4. Cliquez sur **Enregistrer**. 

Vous pouvez supprimer des événements de vie futurs. Si un événement de vie futur traité est supprimé, l’enregistrement futur est également supprimé. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
