---
title: Importer des utilisateurs depuis Azure Active Directory
description: Cette procédure peut être utilisée par les administrateurs système pour importer manuellement des utilisateurs sélectionnés ou un grand nombre d’utilisateurs depuis Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c2600ad8f441e6b73b143c27afa08ad0a5c2748
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571003"
---
# <a name="import-users-from-azure-active-directory"></a>Importer des utilisateurs depuis Azure Active Directory

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Importer les utilisateurs sélectionnés

Cette procédure peut être utilisée par les administrateurs système pour importer des utilisateurs sélectionnés depuis Azure Active Directory (Azure AD).

1. L’utilisateur sera importé avec la société de session actuelle comme société par défaut. Changez la société actuelle le cas échéant avant d’importer des utilisateurs.
2. Accédez à **Administration système > Utilisateurs > Utilisateur** s.
3. Cliquez sur **Importer des utilisateurs**.
4. Sélectionnez les utilisateurs à importer et sélectionnez **Importer des utilisateurs**.

Une fois l’importation terminée, il sera nécessaire d’attribuer des rôles aux utilisateurs.

## <a name="import-users-in-bulk"></a>Importer des utilisateurs en bloc

Cette procédure peut être utilisée par les administrateurs système pour importer un grand nombre d’utilisateurs depuis Azure Active Directory.
Notez qu’il n’est pas possible de sélectionner des utilisateurs lors de l’utilisation de l’option d’importation par lots.

## <a name="run-the-import-as-a-batch-job"></a>Exécutez l’importation comme un traitement par lots
1. L’utilisateur sera importé avec la société de session actuelle comme société par défaut. Changez la société actuelle le cas échéant avant d’importer des utilisateurs.
2. Accédez à **Administration système > Utilisateurs > Utilisateurs**.
3. Cliquez sur **Importation par lots**.
4. Développez la section **Exécuter à l’arrière-plan**.
4. Sélectionnez **Oui** dans le champ **Traitement par lots**.
6. Dans le champ **Groupe de traitement par lots**, entrez ou sélectionnez une valeur. Cette étape est facultative.  
7. Sélectionnez **Oui** dans le champ **Privé**. Cette étape est facultative.  
8. Sélectionnez **Oui** dans le champ **Tâche critique**. Cette étape est facultative.  
9. Dans le champ **Catégorie de surveillance**, sélectionnez une option.
10. Cliquez sur **OK**.

Une fois l’importation terminée, il sera nécessaire d’attribuer des rôles aux utilisateurs.

## <a name="run-in-a-sandbox-environment"></a>Exécuter dans un environnement de bac à sable
1. Sélectionner **Importation par lots**.
2. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]