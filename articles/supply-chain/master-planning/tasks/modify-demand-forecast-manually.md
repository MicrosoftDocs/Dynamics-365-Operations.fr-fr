---
title: 'Guide : Modifier une prévision de la demande manuellement'
description: Cette rubrique décrit comment modifier la prévision pour un article
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f48e1689d21fd0085ec38aab8f5171997fbf432
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567197"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>Guide : Modifier une prévision de la demande manuellement

[!include [banner](../../includes/banner.md)]

Cette procédure permet d’indiquer comment modifier la prévision pour un article. Cette procédure est destinée au gestionnaire de production.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modifier la prévision pour un article sélectionné

Pour modifier la prévision pour un article sélectionné :

1. Accédez à **Modules \> Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Sélectionnez l’article dont vous souhaitez modifier la prévision.
1. Dans le volet Actions, ouvrez l’onglet **Planifier** et sélectionnez **Prévision de la demande**.
1. Dans la liste, sélectionnez une ligne. S’il n’existe aucune ligne de prévision, créez une ligne en sélectionnant **Nouveau** dans le volet Actions.  
1. Entrez un nombre positif dans le champ **Quantité vendue**. Ce chiffre représente la quantité prévue pour l’article. Une erreur s’affichera si vous entrez un nombre négatif.
1. Renseignez les autres champs selon vos besoins.
1. Sélectionnez **Enregistrer** dans le volet Actions.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Modifier la prévision pour un ou plusieurs articles avec Microsoft Excel

Pour modifier la prévision pour un ou plusieurs articles avec Microsoft Excel :

1. Effectuez l’une des opérations suivantes :
    - Ouvrez la page **Prévision de la demande** pour n’importe quel article (peu importe lequel), comme décrit dans la section précédente.
    - Accédez à **Planification \> Prévision \> Entrée manuelle de la prévision \> Lignes de prévision de la demande**.
1. Dans le volet Actions, sélectionnez **Ouvrir dans Microsoft Office \> Entrées de prévision de la demande**.
1. Sélectionnez un emplacement de téléchargement, enregistrez, puis ouvrez le fichier téléchargé dans Excel.
1. Si vous voyez un avertissement, sélectionnez **Activer la modification**.
1. Dans Excel, connectez-vous à Supply Chain Management à l’aide du volet des tâches Microsoft Dynamics. Vous devez vous connecter avec l’option **Maintenir la connexion** activée et vous devez faire confiance à l’application de connexion aux données.
1. La feuille de calcul Excel affiche désormais toutes les lignes de prévision de la demande actuelle pour votre entreprise.  Ajoutez, supprimez et modifiez les lignes de prévision de la demande selon vos besoins.
1. Sélectionnez **Publier** dans le volet des tâches de Microsoft Dynamics pour charger vos modifications dans Supply Chain Management.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
