---
title: Permettre aux utilisateurs de recevoir des e-mails liés au workflow
description: Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6800d02878123388611d35760123d0215e9d539f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560496"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permettre aux utilisateurs de recevoir des e-mails liés au workflow

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent. Par exemple, des messages e-mail peuvent être envoyés aux utilisateurs lorsque des documents leur sont affectés pour approbation. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à Administration système > Utilisateurs > Utilisateurs.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Cliquez sur Options utilisateur.
4. Cliquez sur l'onglet Workflow.
    * Assurez-vous que la section Notifications est développée.     Dans la section Notifications, vous pouvez préciser la manière dont vous souhaitez que l'utilisateur soit prévenu des événements liés au workflow.  
5. Dans le champ Type de notification de workflow pour ligne, sélectionnez une option.
    * Groupé – Les notifications pour les lignes sont regroupées dans un seul e-mail.    Individuel – Un e-mail est envoyé pour chaque ligne.  
    * Si vous voulez que l'utilisateur reçoive les notifications dans le client, activez la case à cocher Envoyer des notifications sous la forme d'e-mails.  
6. Cliquez sur Enregistrer.
7. Fermez la page.

