---
title: Synchroniser la date et l’heure dans les tâches d’importation
description: Utilisez les fuseaux horaires UTC dans les tâches d’importation pour éviter les problèmes de conversion de fuseau horaire.
author: Sunil-Garg
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748667"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Synchroniser la date et l’heure dans les tâches d’importation

[!include [banner](../includes/banner.md)]

Il est important de définir le fuseau horaire de votre tâche d’importation sur le temps universel coordonné (UTC). Vous pouvez voir des dates et des heures inattendues dans vos données importées si vous utilisez un paramètre différent. Sans le paramètre correct, le processus d’importation convertit la date UTC au format local, puis les paramètres système la convertit à nouveau.

Cette double conversion fait changer les dates entre les applications. Par exemple, la double conversion pourrait faire en sorte que la date de début d’un employé soit différente entre Dynamics 365 Human Resources et Dynamics 365 Finance en raison de différences dans les fuseaux horaires locaux. La définition de la tâche d’importation sur UTC résout ce problème.

1. Dans Dynamics 365 Finance and Operations, sélectionnez **Gestion de données**.

2. Sélectionnez **Importer des projets**, puis sélectionnez le projet.

3. Sous **Format de date source**, sélectionnez **CSV-Unicode**.

   [![Changer le format de date source en UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Changez le champ **Fuseau horaire** sur **Fuseau horaire universel coordonné** et changez le champ **Langue** sur **Fr-FR**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]