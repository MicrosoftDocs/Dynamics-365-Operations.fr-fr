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
ms.openlocfilehash: 001bdd61f9266798dadae2ac7c96a4f4c19dbb94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412327"
---
# <a name="create-and-associate-registers"></a> Créer et associer des caisses enregistreuses

[!include [banner](../includes/banner.md)]

Cette procédure montre comment créer un registre de point de vente. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Paramétrage du canal > Paramétrage du PD > Caisses enregistreuses.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro de registre, tapez un identifiant pour le nouveau registre.
    * L'ID de registre inclut généralement des codes qui aident à associer le registre au magasin auquel il appartient, et à l'emplacement dans le magasin.  
4. Dans le champ Nom, entrez un nom descriptif pour le registre.
5. Entrez ou sélectionnez une valeur dans le champ Numéro de magasin.
6. Saisissez ou sélectionnez une valeur dans le champ Profil matériel.
    * Les profils matériels permettent de spécifier les périphériques qui seront associés à la caisse enregistreuse, comme le tiroir-caisse ou l'imprimante de tickets.  
7. Saisissez ou sélectionnez une valeur dans le champ Profil visuel.
    * Des profils visuels sont utilisés pour spécifier les images utilisées dans l’arrière-plan de l’ouverture de session et l’arrière-plan du PDV, ainsi que les thèmes pour le PDV.  
8. Tapez une valeur dans le champ Numéro de caisse enregistreuse TEF du TPV.
    * Le numéro TEF du TPV est utilisé pour informer le processeur de paiement du terminal de paiement qui envoie des demandes d'autorisation. Cette valeur s'appelle souvent « ID terminal » ou « TID ». On trouve généralement le terme TID sur un autocollant sur le dispositif de paiement.  
9. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]