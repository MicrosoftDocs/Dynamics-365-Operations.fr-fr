---
title: Paramétrer un profil de vue d’ensemble des arrivées
description: Cette rubrique se concentre sur le paramétrage d’un profil de vue d’ensemble des arrivées.
author: ShylaThompson
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3de1316844451d2bbfd4c8a4d4f72d75bfd27b9a13d72ed8237e0e8066147add
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755297"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>Paramétrer un profil de vue d’ensemble des arrivées

[!include [banner](../../includes/banner.md)]]

Cette rubrique se concentre sur le paramétrage d’un profil de vue d’ensemble des arrivées. Le profil de vue d’ensemble des arrivées est une collection de règles qui sont appliquées lorsque la page de vue d’ensemble des arrivées est ouverte par un utilisateur. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. Cette procédure est généralement effectuée par la personne qui s’occuper de la réception.

1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Distribution > Profils de vue d’ensemble des arrivées**.
2. Sélectionnez **Nouveau**. Étant donné que vous travaillerez presque toujours dans le même entrepôt lors du déchargement de camions pleins, vous devez créer un profil de vue d’ensemble des arrivées pour simplifier le processus d’enregistrer les articles reçus.  
3. Dans le champ **Nom du profil de vue d’ensemble des arrivées**, tapez une valeur.
4. Dans le champ **Afficher les lignes**, sélectionnez une option. Permet de sélectionner les lignes à afficher pour les réceptions :  

    - **Tout** - Permet d’afficher toutes les lignes, quel que soit leur statut.   
    - **En cours** - Affiche les lignes des réceptions dans lesquelles la progression est Complète ou Partielle. Ceci signifie que, pour chaque ligne, la totalité ou une partie de la quantité a été enregistrée dans un journal des arrivées.   
    - **Incomplète** - Affiche les lignes des réceptions dans lesquelles la progression est Aucune ou Partielle. Ceci signifie que, pour chaque ligne, soit la quantité n’a pas été enregistrée ou seule une partie l’a été dans un journal des arrivées.  

5. Développez ou réduisez la section **Options des arrivées**.
6. Dans le champ **Jours après**, tapez une valeur. Ceci définit un filtre pour afficher les lignes de réception devant être reçues dans les prochains jours (selon le nombre que vous définissez).  
7. Dans le champ **Jours avant**, tapez une valeur. Ceci définit un filtre pour afficher les lignes de réception devant être reçu il y a un certain nombre de jours.  
8. Dans le champ **Entrepôts**, tapez une valeur. Filtrez sur un ou plusieurs entrepôts.  
9. Sélectionnez une valeur dans le champ **Mode de livraison**. Ceci définit un filtre pour afficher uniquement les lignes de réception avec ce mode de livraison.  
10. Sélectionnez WHS dans le champ **Nom**.
11. Dans le champ **Entrepôt**, sélectionnez l’entrepôt 24. Il s’agit de l’entrepôt par défaut utilisé pour les lignes de réception enregistrées qui utilisent ce profil.  
12. Dans le champ **Emplacement**, sélectionnez **Baydoor**. Il s’agit de l’emplacement par défaut utilisé pour les lignes de réception enregistrées qui utilisent ce profil.  
13. Développez ou réduisez la section **Détails des requêtes des arrivées**.
14. Sélectionnez site 2 dans le champ **Limiter au site**. Ceci définit un filtre pour afficher uniquement les lignes de réception avec ce site.  
15. Définissez l’option **Commandes fournisseur** sur **Oui**. Sélectionnez des lignes de réception à partir de commandes fournisseur.  
16. Définissez l’option Ordres de **transfert** sur **Oui**. Sélectionnez des lignes de réception à partir d’ordres de transfert.  
17. Sélectionnez **Enregistrer**.
18. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]