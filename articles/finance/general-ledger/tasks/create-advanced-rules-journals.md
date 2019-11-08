---
title: Créer des règles avancées pour les journaux
description: Cette procédure consiste à créer des règles avancées pour les journaux.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3eb34ac419aeab3663a8931d022abf7bcbfddd37
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186231"
---
# <a name="create-advanced-rules-for-journals"></a>Créer des règles avancées pour les journaux

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure consiste à créer des règles avancées pour les journaux. Cela inclut de définir un contrôle des journaux et des restrictions de validation utilisateur. La société fictive USMF sert d'exemple dans cette procédure.


## <a name="set-up-journal-control"></a>Paramétrer le contrôle des journaux
1. Dans le **Volet de navigation**, allez dans **Modules > Comptabilité > Paramétrage du journal > Noms de journal**.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans le **Volet Actions**, cliquez sur **Contrôle des journaux**.
4. Dans l'organisateur **Quels types de compte peuvent être validés ?**, cliquez sur **Ajouter**.
5. Dans le champ **Comptes société**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans l'organisateur **Quelles valeurs de segment sont valides pour ce journal ?**, cliquez sur **Ajouter**.
9. Dans le champ **Structure de compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
12. Dans le champ **Segment**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Dans le champ **Valeur de début**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Dans le champ **Valeur de fin**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
18. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
19. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="set-up-posting-restrictions"></a>Paramétrage des restrictions de validation
1. Fermez la page.
2. Cliquez sur **Restrictions de validation**.
3. Dans le champ **Comment voulez-vous paramétrer des restrictions de validation ?**, sélectionnez par Groupe d'utilisateurs.
4. Dans l'arborescence, activez « Le groupe pour lequel vous souhaitez autoriser la validation pour ce nom de journal. ».
5. Cliquez sur **OK**.
