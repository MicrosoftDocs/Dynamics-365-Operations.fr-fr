---
title: " Créer et associer des caisses enregistreuses"
description: Cette procédure montre comment créer un registre de point de vente.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ac5135d0606ffc9816c841637aa032826f87e28
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022523"
---
# <a name="create-and-associate-registers"></a> Créer et associer des caisses enregistreuses

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure montre comment créer un registre de point de vente. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Paramétrage du canal > Paramétrage POS > Caisses enregistreuses.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro de registre, tapez un identifiant pour le nouveau registre.
    * L'ID de registre inclut généralement des codes qui aident à associer le registre au magasin auquel il appartient, et à l'emplacement dans le magasin.  
4. Dans le champ Nom, entrez un nom descriptif pour le registre.
5. Entrez ou sélectionnez une valeur dans le champ Numéro de magasin.
6. Saisissez ou sélectionnez une valeur dans le champ Profil matériel.
    * Les profils de matériel sont utilisés pour spécifier les périphériques de vente au détail qui seront associés au registre, comme l'imprimante de tickets et la caisse enregistreuse.  
7. Saisissez ou sélectionnez une valeur dans le champ Profil visuel.
    * Des profils visuels sont utilisés pour spécifier les images utilisées dans l’arrière-plan de l’ouverture de session et l’arrière-plan du PDV, ainsi que les thèmes pour le PDV.  
8. Tapez une valeur dans le champ Numéro de caisse enregistreuse TEF du TPV.
    * Le numéro TEF du TPV est utilisé pour informer le processeur de paiement du terminal de paiement qui envoie des demandes d'autorisation. Cette valeur s'appelle souvent « ID terminal » ou « TID ». On trouve généralement le terme TID sur un autocollant sur le dispositif de paiement.  
9. Cliquez sur Enregistrer.

