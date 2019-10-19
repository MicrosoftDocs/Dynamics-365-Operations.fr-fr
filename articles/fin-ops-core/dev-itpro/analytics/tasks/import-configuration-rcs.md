---
title: (Gestion des états électroniques) Importer les configurations depuis RCS
description: Cette rubrique fournit des informations sur la manière dont un utilisateur peut importer une nouvelle version d'une configuration ER à partir de RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32c9c17d8b63e4c0806559c2dcc2e11ae9825a53
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184621"
---
# <a name="er-import-configurations-from-rcs"></a>(Gestion des états électroniques) Importer les configurations depuis RCS

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Regulatory Configuration Services (RCS). Dans cet exemple, vous sélectionnerez la version de la configuration ER qui a été configurée dans une instance RCS et l'importerez dans l'instance actuelle pour la société fictive Litware, Inc. Ces étapes peuvent être réalisées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette rubrique, [Créer un fournisseur de configuration et le marquer comme actif](er-configuration-provider-mark-it-active-2016-11.md). Pour effectuer ces étapes, vous devez également avoir accès à une instance RCS contenant au moins une configuration ER ayant le statut **Terminé** ou **Partagé**.

1. Accédez à **Administration d'organisation** > **Espaces de travail** > **États électroniques**. 
2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](er-configuration-provider-mark-it-active-2016-11.md). 
3. Si vous n'avez pas d'environnement RCS configuré dans votre société, cliquez sur le lien externe **Regulatory services – Configuration** et suivez les instructions pour mettre en service un environnement RCS. 
4. Cliquez sur **Paramètres de la gestion des états électroniques**. 
5. Cliquez sur l'onglet **RCS**. 
6. Si l'environnement de RCS a déjà été mis en service dans votre société, utilisez les URL affichées sur la page pour y accéder. 
7. Fermez la page. 

## <a name="register-a-new-er-repository"></a>Enregistrez un nouveau référentiel ER. 
1. Dans la liste, marquer la ligne sélectionnée. 
2. Sélectionnez le fournisseur Litware, Inc. 
3. Cliquez sur Référentiels. 
4. Cliquez sur Ajouter pour ouvrir la boîte de dialogue. 
5. Dans le champ Type du référentiel de configuration, entrez « RCS ». 
6. Cliquez sur Créer un référentiel. 
7. Dans le champ Nom complet de l'environnement RCS, saisissez ou sélectionnez une valeur. 
8. Sélectionnez l'instance RCS souhaitée. Notez que vous pouvez en définir plusieurs. 
9. Cliquez sur OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importer des configurations de gestion des états électroniques depuis un référentiel basé sur RCS
1. Cliquez sur **Afficher les filtres**. 
2. Entrez la valeur de filtre « RCS » dans le champ **Nom** à l'aide de l'opérateur de filtre **commence par**. 
3. Lorsque vous ouvrez le référentiel sélectionné, dans la page **Connexion à Regulatory Configuration Services**, cliquez sur le lien **Cliquer ici pour se connecter à Regulatory Configuration Services**. 
4. Cliquez sur **Ouvrir.** 
5. Cliquez sur **Fermer**. 
6. Sélectionnez la version souhaitée de la configuration ER et cliquez sur **Importer** pour l'importer dans l'instance actuelle.

