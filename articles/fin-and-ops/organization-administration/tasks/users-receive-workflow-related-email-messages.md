---
title: Permettre aux utilisateurs de recevoir des e-mails liés au workflow
description: Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916390"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permettre aux utilisateurs de recevoir des e-mails liés au workflow

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent. Par exemple, des messages e-mail peuvent être envoyés aux utilisateurs lorsque des documents leur sont affectés pour approbation. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à **Volet de navigation > Modules > Administration système > Utilisateurs > Utilisateurs**.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans le **volet Actions**, cliquez sur **Options de l'utilisateur**.
4. Cliquez sur l'onglet **Workflow** et vérifiez que la section **Notifications** est développée. Dans la section **Notifications**, vous pouvez préciser la manière dont vous souhaitez que l'utilisateur soit prévenu des événements liés au workflow.  
5. Dans le champ **Type de notification de workflow pour ligne**, sélectionnez une option.
    - Groupé – Les notifications pour les lignes sont regroupées dans un seul e-mail.
    - Individuel – Un e-mail est envoyé pour chaque ligne.  
    - Si vous voulez que l'utilisateur reçoive les notifications dans le client, activez la case à cocher **Envoyer des notifications sous la forme d'e-mails**.  
6. Cliquez sur **Enregistrer**.
7. Fermez la page.

