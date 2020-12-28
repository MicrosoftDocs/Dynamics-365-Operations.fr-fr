---
title: Paramétrer l'emballage manuel (février 2016 et mai 2016)
description: Le processus d'emballage vous permet de valider et conditionner les produits dans des conteneurs.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67e1e99b479752a027c60a878c57bd35d4219981
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428272"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a>Paramétrer l'emballage manuel (février 2016 et mai 2016)

[!include [banner](../../includes/banner.md)]

Le processus d'emballage vous permet de valider et conditionner les produits dans des conteneurs. Dans ce processus, les magasiniers prélèvent les produits dans les emplacements de stockage et les déplacent dans un centre d'emballage dans lequel ils vérifient les quantités et les types d'article, puis ils les affectent aux conteneurs appropriés. Lorsqu'un conteneur est entièrement emballé, ils peuvent le fermer et le déplacer vers les quais d’expédition, et les produits sont alors prêts à expédier. La société fictive USMF sert d'exemple dans cette procédure. Cette procédure s'applique aux versions de février 2016 et mai 2016 de Dynamics 365 for Operations uniquement.


## <a name="set-up-location-profiles"></a>Définir des profils d'emplacement
1. Accédez à Gestion des entrepôts > Paramétrage > Entrepôt > Profils d'emplacement.
2. Cliquez sur Nouveau.
    * Le profil d'emplacement est utilisé pour les centres d'emballage et contient des informations et des règles pour un emplacement.  
3. Dans le champ ID du profil d'emplacement, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Saisissez ou sélectionnez une valeur dans le champ Format de l'emplacement.
6. Saisissez ou sélectionnez une valeur dans le champ Type d'emplacement.
7. Sélectionnez Oui dans le champ Autoriser les articles mixtes.
8. Sélectionnez Oui dans le champ Autoriser les statuts de stock mixtes.
9. Sélectionnez Oui dans le champ Règles de remplacement pour les jours de traitement par lots.
10. Fermez la page.

## <a name="set-up-warehouse-management-parameters"></a>Définir les paramètres de gestion des entrepôts 
1. Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.
2. Cliquez sur l'onglet Emballage.
3. Saisissez ou sélectionnez une valeur dans le champ ID profil pour l'emplacement d'emballage.
    * Sélectionnez le profil d'emplacement que vous voulez utiliser pour l'emballage.  
4. Fermez la page.

## <a name="set-up-container-types"></a>Paramétrer les types de conteneur
1. Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Types de conteneurs.
2. Cliquez sur Nouveau.
    * Vous pouvez définir les types de conteneurs à utiliser. Vous pouvez spécifier les dimensions physiques du conteneur, notamment le poids de la tare, le poids maximum, le volume maximum, la longueur, la largeur et le poids.  Les attributs sont des champs personnalisés qui permettent d'ajouter des dimensions supplémentaires sur le type de conteneur.     
3. Tapez une valeur dans le champ Type de conteneur.
4. Dans le champ Description, entrez une valeur.
5. Entrez un nombre dans le champ Tare.
6. Entrez un nombre dans le champ Poids maximal.
7. Dans le champ Volume, entrez un nombre.
8. Dans le champ Longueur, entrez un nombre.
9. Entrez un nombre dans le champ Largeur.
10. Entrez un nombre dans le champ Hauteur.
11. Cliquez sur Enregistrer.
12. Fermez la page.

## <a name="set-up-packing-profiles"></a>Paramétrer les profils de conditionnement
1. Accédez à Gestion des entrepôts > Paramétrage > Emballage > Profils d'emballage.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ ID profil d'emballage.
4. Dans le champ Description, entrez une valeur.
5. Saisissez ou sélectionnez une valeur dans le champ ID profil de clôture de conteneur.
    * Un ID profil de clôture de conteneur est facultatif, il s'agit du profil de fermeture de conteneur par défaut pour ce profil d'emballage.  
6. Sélectionnez une option dans le champ Mode ID conteneur.
    * Cette option détermine si un ID conteneur est automatiquement généré lorsqu'un conteneur est créé ou si un ID conteneur sera créé manuellement.  
7. Saisissez ou sélectionnez une valeur dans le champ Type de conteneur.
    * Le type de conteneur sera utilisé par défaut lorsqu'un nouveau conteneur est créé.  
8. Activez la case à cocher Créer automatiquement un conteneur à la clôture du conteneur.
9. Cliquez sur Enregistrer.
10. Fermez la page.

## <a name="set-up-container-closing-profiles"></a>Paramétrer les profils de clôture de conteneur
1. Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Profils de clôture de conteneur.
    * Les profils de clôture de conteneur définissent ce qui se produit lorsqu'un conteneur est clôturé. Vous pouvez paramétrer plusieurs profils de fermeture de conteneur.       
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ ID profil de clôture de conteneur.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez une option dans le champ Date manifeste.
    * Spécifiez si la manifestation a lieu lors de la fermeture des conteneurs ou lors de la confirmation de l'expédition. Notez que la gestion du transport est nécessaire pour la manifestation. Pour pouvoir fonctionner, la manifestation doit être implémentée dans les moteurs de transport.  
6. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
7. Saisissez ou sélectionnez une valeur dans le champ Emplacement par défaut pour l'expédition finale.
    * Il s'agit de l'emplacement où les produits seront déplacés une fois les conteneurs clôturés. Cet emplacement doit avoir un profil d'emplacement défini dans les paramètres d'entrepôt.  
8. Saisissez ou sélectionnez une valeur dans le champ Unité de poids.
9. Cliquez sur Enregistrer.

