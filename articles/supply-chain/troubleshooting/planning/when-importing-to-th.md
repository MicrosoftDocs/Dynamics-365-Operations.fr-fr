---
title: Vous êtes invité à enregistrer les paramètres de couverture des articles même si vous n’avez effectué aucune modification
description: Vous êtes invité à enregistrer les paramètres de couverture des articles même si vous n’avez effectué aucune modification.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 29ee23164430f219ff3d0c94216a8be43f480ce309f6cdac3dac6ed5b6d030af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730080"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>Vous êtes invité à enregistrer les paramètres de couverture des articles même si vous n’avez effectué aucune modification

Numéro de la base de connaissances : 4615588

## <a name="symptoms"></a>Symptômes

Dans certains scénarios, vous pouvez recevoir le message suivant lorsque vous ouvrez la page **Couverture d’article** après avoir importé des articles via l’entité *Couverture d’article V2* :

> Voulez-vous enregistrer les modifications avant de clôturer ?

Vous recevez ce message même si vous n’avez effectué aucune modification.

## <a name="resolution"></a>Résolution

La page **Couverture d’article** inclut une logique par défaut complexe qui peut entraîner l’affichage du message une fois que des changements directs ont été récemment effectués dans la base de données, par exemple via l’importation d’entités. Par exemple, le champ d’entité `AREGENERALSETTINGSOVERRIDDEN` est défini sur *Non*, mais vous importez un fichier qui fournit des valeurs nouvelles ou modifiées pour des champs tels que `PRODUCTCOVERAGEGROUPID` et/ou `VENDORACCOUNTNUMBER`. Dans ce cas, comme le champ `AREGENERALSETTINGSOVERRIDDEN` est défini sur *Non*, les valeurs sont automatiquement effacées des champs lorsque vous ouvrez la page **Couverture d’article** pour la première fois après l’importation. Si vous enregistrez les modifications à l’invite de la zone de message, elles sont stockées dans la base de données. Sinon, vous recevrez le même message la prochaine fois que vous ouvrirez la page.

Pour éviter ce comportement mais aussi inclure des valeurs pour des champs tels que `PRODUCTCOVERAGEGROUPID` via l’importation d’entités, définissez `AREGENERALSETTINGSOVERRIDDEN` sur *Oui* lors de l’importation.
