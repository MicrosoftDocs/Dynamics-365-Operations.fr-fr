---
title: Créer et associer des caisses enregistreuses
description: Cette procédure montre comment créer un registre de point de vente.
author: rubencdelgado
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba978a3d895394760687386197dbb3512c62ef98
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798559"
---
# <a name="create-and-associate-registers"></a>Créer et associer des caisses enregistreuses

[!include [banner](../includes/banner.md)]

Cette procédure montre comment créer un registre de point de vente. La société fictive USRT sert d’exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Paramétrage du canal > Paramétrage du PD > Caisses enregistreuses.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro de registre, tapez un identifiant pour le nouveau registre.
    * L’ID de registre inclut généralement des codes qui aident à associer le registre au magasin auquel il appartient, et à l’emplacement dans le magasin.  
4. Dans le champ Nom, entrez un nom descriptif pour le registre.
5. Entrez ou sélectionnez une valeur dans le champ Numéro de magasin.
6. Saisissez ou sélectionnez une valeur dans le champ Profil matériel.
    * Les profils matériels permettent de spécifier les périphériques qui seront associés à la caisse enregistreuse, comme le tiroir-caisse ou l’imprimante de tickets.  
7. Saisissez ou sélectionnez une valeur dans le champ Profil visuel.
    * Des profils visuels sont utilisés pour spécifier les images utilisées dans l’arrière-plan de l’ouverture de session et l’arrière-plan du PDV, ainsi que les thèmes pour le PDV.  
8. Tapez une valeur dans le champ Numéro de caisse enregistreuse TEF du TPV.
    * Le numéro TEF du TPV est utilisé pour informer le processeur de paiement du terminal de paiement qui envoie des demandes d’autorisation. Cette valeur s’appelle souvent « ID terminal » ou « TID ». On trouve généralement le terme TID sur un autocollant sur le dispositif de paiement.  
9. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]