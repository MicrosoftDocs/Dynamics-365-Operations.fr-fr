---
title: Permettre aux utilisateurs de recevoir des e-mails liés au workflow
description: Vous pouvez configurer le système pour envoyer des messages e-mail aux utilisateurs lorsque des événements liés au workflow se produisent.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 40ad380c7bfb2b3fc518b0278286ae03532668ed
ms.sourcegitcommit: 4db8c30c2f26af1896938dd3ece3756577374ecb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3416551"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permettre aux utilisateurs de recevoir des e-mails liés au workflow

[!include [banner](../../includes/banner.md)]

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

> [!NOTE]
> Les modèles d'e-mail de workflow proviendront des modèles d'e-mail système ou des modèles d'e-mail de l'organisation, selon que le workflow est un workflow de niveau système (non spécifique à la société) ou de niveau organisation (spécifique à la société).
