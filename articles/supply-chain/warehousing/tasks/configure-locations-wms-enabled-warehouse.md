--- 
title: "Configurer les emplacements dans un entrepôt compatible WMS"
description: "Ce guide vous indique comment configurer le paramétrage d'emplacement pour un nouvel entrepôt compatible WMS (un entrepôt qui utilise des processus avancés de gestion des entrepôts)."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1082c86361180db84bb2b5c0b8158816f76a219e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Configurer les emplacements dans un entrepôt compatible WMS

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide vous indique comment configurer le paramétrage d'emplacement pour un nouvel entrepôt compatible WMS (un entrepôt qui utilise des processus avancés de gestion des entrepôts). Le processus est généralement effectué par un gestionnaire d'entrepôt. Vous pouvez exécuter ce guide dans la société fictive de démonstration USMF ou utiliser vos propres données. Une condition préalable est qu'au moins un site soit configuré.


## <a name="create-a-new-warehouse"></a>Créer un nouvel entrepôt
1. Accédez à Entrepôts.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Entrepôts.
4. Tapez une valeur dans le champ Nom.
5. Tapez une valeur dans le champ Site.
6. Développez ou réduisez la section Entrepôt.
7. Définissez l'option Utiliser les processus de gestion des entrepôts sur Oui.
    * Ce paramètre permet d'exécuter des processus avancés de stockage à l'aide du travail d'entrepôt et de périphériques mobiles.  
8. Fermez la page.

## <a name="define-a-location-format"></a>Définir un format d'emplacement
1. Accédez à Formats d'emplacements.
    * Les formats d'emplacements constituent un système d'affectation de noms pour créer des noms uniques et cohérents pour des lieux de casiers dans un entrepôt. Il peut être utile d'utiliser des séparateurs dans le cadre du format d'emplacement pour faciliter l'identification des composants de l'emplacement, tels que le numéro d'allée. Dans cet exemple, nous créerons un nom à quatre composants. Par exemple, ceux-ci peuvent être allée, rayon, étagère et casier.  
2. Cliquez sur Nouveau.
3. Dans le champ Format d'emplacement, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Description du segment, tapez une valeur.
    * Ceci décrit ce que représente le premier composant du nom de l'emplacement. Par exemple, il peut s'agir d'Allée.  
6. Dans le champ Longueur, entrez un nombre.
    * Cela détermine le nombre de caractères que doit compter cette partie du nom d'emplacement. Notez que le total de tous les composants présents dans le nom, y compris les séparateurs, ne peut pas dépasser 10 caractères.  
7. Dans le champ Séparateur, tapez une valeur.
    * Cela détermine le caractère ou symbole qui est utilisé entre le premier et deuxième composant du nom.  
8. Cliquez sur Nouveau.
9. Dans le champ Description du segment, tapez une valeur.
10. Dans le champ Longueur, entrez un nombre.
11. Dans le champ Séparateur, tapez une valeur.
12. Cliquez sur Nouveau.
13. Dans le champ Description du segment, tapez une valeur.
14. Dans le champ Longueur, entrez un nombre.
15. Dans le champ Séparateur, tapez une valeur.
16. Cliquez sur Nouveau.
17. Dans le champ Description du segment, tapez une valeur.
18. Dans le champ Longueur, entrez un nombre.
19. Cliquez sur Enregistrer.
20. Fermez la page.

## <a name="define-location-types"></a>Définir les types d'emplacements
1. Accédez à Types d'emplacements.
    * Les types d'emplacements peuvent être utilisés comme options de filtrage pour contrôler les différents processus de gestion des entrepôts. Vous devez au minimum créer les types d'échelonnement et d'emplacement final d'expédition afin de définir le processus sortant de gestion des entrepôts.  
2. Cliquez sur Nouveau.
3. Dans le champ Emplacement, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Fermez la page.

## <a name="define-location-profile"></a>Définir un profil d'emplacement
1. Accédez à Profils d'emplacements.
    * La définition des profils d'emplacement est très importante. La capacité d'emplacements groupés peut être contrôlée ici, tout comme les stratégies associées au stock (ce qui est stocké et comment). Les profils d'emplacements peuvent être utilisés comme options de filtrage pour contrôler les différents processus de gestion des entrepôts. Vous devez au minimum créer un profil d'emplacement d'utilisateur afin d'activer les processus de gestion des entrepôts.  
2. Cliquez sur Nouveau.
3. Dans le champ ID du profil d'emplacement, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Format d'emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Type d'emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Activez ou désactivez la case à cocher Autoriser les statuts de stock mixtes.
    * Activez cette option si vous souhaitez autoriser des valeurs mixtes de statut de stock dans les emplacements qui vont être regroupés par ce profil d'emplacement.  
12. Activez ou désactivez la case à cocher Règles de remplacement pour les jours de traitement par lots.
    * Activez cette option pour remplacer la règle concernant le nombre de jours pendant lequel il est possible de différer les dates d'expiration du lot de stock, pour autoriser le mélange des lots de stock qui ne se conforment pas à cette règle.  
13. Activez ou désactivez la case à cocher Autoriser l'inventaire tournant.
    * Activez cette option si vous souhaitez autoriser le traitement de l'inventaire tournant dans tous les emplacements qui vont être regroupés par ce profil d'emplacement.  
14. Développez ou réduisez la section Dimensions.
    * L'onglet Dimensions permet de définir les paramètres et méthodes pour activer les calculs exacts de la capacité de travail dans chacun des emplacements.  
15. Fermez la page.

## <a name="enable-warehouse-management-parameters"></a>Activer les paramètres de gestion des entrepôts
1. Accédez à Paramètres de gestion des entrepôts.
    * Pour pouvoir traiter le travail d'entrepôt, vous devez définir les paramètres du profil d'emplacement de l'utilisateur, le type d'emplacement d'échelonnement et le type d'emplacement d'expédition finale  Dès que le processus sortant se termine au type d'emplacement d'expédition finale que vous avez défini, les transactions sortantes associées seront mises à jour sur « Prélevée ».  
2. Développez ou réduisez la section Profils d'emplacements.
3. Dans le champ Emplacement utilisateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Développez ou réduisez la section Types d'emplacements.
6. Dans le champ Emplacement intermédiaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Type d'emplacement d'expédition final, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Fermez la page.

## <a name="define-warehouse-zone-groups"></a>Définir des groupes de zones d'entrepôt
1. Accédez à Groupes de zones d'entrepôts.
    * Les zones d'entrepôts peuvent être utilisées comme options de filtrage pour contrôler les différents processus de gestion des entrepôts. Vous devez créer un groupe de zones avant de définir une zone.  
2. Cliquez sur Nouveau.
3. Dans le champ ID du groupe de zones, tapez une valeur.
4. Dans le champ Nom du groupe de zones, tapez une valeur.
5. Fermez la page.

## <a name="define-warehouse-zones"></a>Définir des zones d'entrepôt
1. Aller à Zones.
2. Cliquez sur Nouveau.
3. Dans le champ ID de zone, tapez une valeur.
4. Dans le champ Nom de zone, tapez une valeur.
5. Dans le champ ID du groupe de zones, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Fermez la page.

## <a name="create-locations-using-the-location-setup-wizard"></a>Créer des emplacements à l'aide de l'assistant de configuration des emplacements
1. Accédez à Assistant Paramétrage d'emplacement.
2. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ ID de zone, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ ID de profil d'emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Dans la liste, marquez la ligne sélectionnée.
12. Dans le champ Numéro de départ, entrez un nombre.
    * Les champs Numéro de départ et Numéro d'arrivée définissent le nombre d'emplacements qui seront créés. Par exemple, si vous définissez Numéro de départ sur 1 et Numéro d'arrivée sur 3 pour chacune des quatre lignes du format d'emplacement, 81 emplacements seront créés (3x3x3x3).  
13. Dans le champ Numéro d'arrivée, entrez un numéro.
14. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
15. Dans le champ Numéro de départ, entrez un nombre.
16. Dans le champ Numéro d'arrivée, entrez un numéro.
17. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
18. Dans le champ Numéro de départ, entrez un nombre.
19. Dans le champ Numéro d'arrivée, entrez un numéro.
20. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
21. Dans le champ Numéro de départ, entrez un nombre.
22. Dans le champ Numéro d'arrivée, entrez un numéro.
23. Cliquez sur Créer.

## <a name="create-locations-manually"></a>Créer manuellement des emplacements
1. Accédez à Emplacements.
    * Il est facilement possible de créer manuellement des emplacements dans un entrepôt. Le nom de l'emplacement et l'ID du profil d'emplacement sont des valeurs obligatoires.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Entrepôts.
4. Dans le champ Emplacement, tapez une valeur.
    * Notez que puisque vous créez un nouvel emplacement ici, vous devez entrer un nouveau nom unique, plutôt que d'en sélectionner un existant.  
5. Dans le champ ID du profil d'emplacement, tapez une valeur.
6. Fermez la page.

## <a name="define-pack-size-categories"></a>Définir des catégories de tailles de colis
1. Accédez à Catégories de taille de colis.
    * Les catégories de taille de paquet peuvent être utilisées pour regrouper des articles présentant des tailles physiques similaires d'emballage. Dans cet exemple, la catégorie de taille de paquet sera utilisée pour contrôler la capacité aux emplacements de prélèvement dans une zone spécifique de l'entrepôt. Notez que l'ID de catégorie de taille de paquet doit être affecté à l'entité de produit lancé afin de pouvoir l'utiliser dans le cadre du traitement des limites de stockage.  
2. Cliquez sur Nouveau.
3. Dans le champ ID de catégorie de taille de colis, tapez une valeur.
4. Dans le champ Nom de catégorie de taille de colis, tapez une valeur.
5. Fermez la page.

## <a name="define-location-stocking-limits"></a>Définir des limites de stockage d'emplacement
1. Accédez à Limites de stockage de l'emplacement.
    * Les limites de stockage de l'emplacement permettent de s'assurer que le travail n'est pas créé pour demander le déplacement du stock vers un emplacement qui n'a pas de capacité physique de le conserver.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Entrepôts.
4. Dans le champ ID du profil d'emplacement, tapez une valeur.
5. Dans le champ ID de catégorie de taille de colis, tapez une valeur.
6. Dans le champ Quantité, entrer un numéro.
7. Cliquez sur Enregistrer.
8. Fermez la page.

## <a name="define-fixed-picking-locations"></a>Définir des emplacements de prélèvement fixes
1. Accédez à Emplacements fixes.
    * Vous pouvez définir les emplacements à utiliser par produit ou par variante de produit. Il est possible de créer plusieurs emplacements fixes pour un même produit dans un même entrepôt.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Numéro d'article.
4. Tapez une valeur dans le champ Entrepôts.
5. Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Fermez la page.


