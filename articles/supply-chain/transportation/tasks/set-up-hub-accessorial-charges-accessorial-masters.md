---
title: Paramétrer des frais annexes de terminal et des données principales annexes
description: Cette procédure décrit la création de données principales annexes pour un terminal et l’utilisation de ces données principales pour créer des frais annexes de terminal.
author: Weijiesa
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ae7580e0c2a2f776512a7cf4c378266f1a878e9
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672624"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Paramétrer des frais annexes de terminal et des données principales annexes

[!include [banner](../../includes/banner.md)]

Cette procédure décrit la création de données principales annexes pour un terminal et l’utilisation de ces données principales pour créer des frais annexes de terminal. La procédure utilise le dataset USMF. Cette configuration est généralement réalisée par un coordinateur transport.


## <a name="set-up-a-hub-master"></a>Paramétrer une table maître de transbordement
1. Accédez à Gestion du transport > Configurer > Taux > Données principales de l’élément accessoire.
2. Cliquez sur Nouveau.
3. Dans le champ Données principales annexes, saisissez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Type d’annexe, sélectionnez « Terminal ».
6. Cliquez sur Enregistrer.
7. Fermez la page.

## <a name="set-up-a-hub-accessorial-charge"></a>Paramétrer des frais annexes de terminal
1. Accédez à Gestion du transport > Configurer > Classement > Frais annexes du terminal.
2. Cliquez sur Nouveau.
3. Dans le champ ID annexe du terminal, saisissez une valeur.
4. Dans le champ Point de transbordement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
6. Dans le champ Position du terminal, sélectionnez une option.
    * Vous pouvez créer les frais pour le lieu d’enlèvement ou le lieu de livraison. En fonction de votre choix, les frais seront appliqués au segment de transport correspondant sur votre route.  
7. Dans le champ Données principales annexes, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez les données principales que vous venez de créer.  
9. Cliquez sur Enregistrer.
10. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]