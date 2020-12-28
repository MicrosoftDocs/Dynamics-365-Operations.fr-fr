---
title: Nouveautés ou modifications dans Dynamics 365 Talent (7 janvier 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461169"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Nouveautés ou modifications dans Dynamics 365 Talent (7 janvier 2020)

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2697. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>Impossible de supprimer les collaborateurs sans dossier d'emploi - (386157)

Cette modification ajoute une option de suppression dans le formulaire **Collaborateurs sans emploi**. Les collaborateurs apparaissent dans ce formulaire lorsqu'ils ne sont associés à aucun emploi futur, actif ou historique. Dans cette version, la suppression n'est activée que pour les administrateurs système. Cependant, dans la version de la semaine prochaine, la sécurité sera mise à jour pour permettre à tous les utilisateurs avec le rôle d'assistant RH de supprimer des employés sans emploi. Vous pouvez également effectuer ces modifications manuellement en suivant les étapes suivantes.

1. Accédez à **Configuration de sécurité**.
2. Dans l'onglet **Privilèges**, filtrez la liste **Privilèges** sur **Tenir à jour les collaborateurs**.
3. Dans la colonne **Références**, sélectionnez **Options du menu d'affichage**.
4. Dans **Options du menu d'affichage**, sélectionnez **HcmWOrkersWithoutEmployment**.
5. Définissez l'autorisation **Supprimer** sur Accorder.
6. Sélectionnez l'onglet **Objets non publiés**.
7. Sélectionnez **Publier tous**.
