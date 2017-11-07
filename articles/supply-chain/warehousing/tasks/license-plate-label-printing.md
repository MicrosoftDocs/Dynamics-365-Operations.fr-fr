--- 
title: "Activer l'impression d'étiquette de contenant"
description: "Cette procédure active l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes."
author: perlynne
manager: AnnBe
ms.date: 11/03/2016
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
ms.openlocfilehash: 6d186bf7e4aee8cfa97adbd90b9090085e842f9b
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="enable-license-plate-label-printing"></a>Activer l'impression d'étiquette de contenant

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure active l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes. Vous pouvez exécuter cette procédure dans les données de démonstration de la société fictive USMF. Si vous l'exécutez à l'aide de vos propres données, vous devez avoir une souche de numéros pour les plaques d'immatriculation. Vous devez paramétrer une imprimante d'étiquettes avant de commencer cette tâche. Accédez à Administration d'organisation > Configuration > Imprimantes réseau. Dans le volet Actions, cliquez sur Options, puis cliquez sur le bouton Télécharger le fichier d'installation d'un agent d'acheminement de document. Exécutez le programme d'installation et assurez-vous d'avoir une imprimante réseau définie sur Actif avant de poursuivre la procédure.


## <a name="set-up-the-gs1-company-prefix"></a>Paramétrer le préfixe de la société GS1
1. Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.
2. Dans le champ Préfixe société GS1, entrez les 7 chiffres de numéro de l'entreprise GS1.
3. Cliquez sur Enregistrer.
4. Fermez la page.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Définir la séquence pour le numéro de contenant SSCC
1. Accédez à Administration d'organisation > Séquences de nombres > Séquences de nombres.
2. Sélectionnez une option dans le champ Zone.
3. Sélectionnez une option dans le champ Référence.
4. Tapez une valeur dans le champ Société.
5. Dans la liste, marquer la ligne sélectionnée.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Développez la section Segments.
8. Cliquez sur Modifier.
9. Sélectionnez la première ligne du tableau Segment.
10. Cliquez sur Supprimer.
11. Cliquez sur Supprimer.
12. Cliquez sur Enregistrer.
13. Fermez la page.

## <a name="create-the-document-route-layout"></a>Créer la mise en page de l'acheminement du document
1. Accédez à Gestion des entrepôts > Paramétrage > Acheminement de document > Mises en page de l'acheminement de document.
    * Activez la structure de SSCC.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ ID mise en page.
4. Dans le champ Description, entrez une valeur.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
6. Cliquez sur Insérer à la fin du texte.
7. Cliquez sur Enregistrer.
8. Fermez la page.

## <a name="set-up-the-document-routing"></a>Définir l'acheminement de document
1. Accédez à Gestion des entrepôts > Configuration > Acheminement de document > Acheminement de document.
2. Sélectionnez une option dans le champ Type d'ordre d'exécution.
3. Cliquez sur Nouveau.
4. Tapez une valeur dans le champ Entrepôts.
5. Tapez une valeur dans le champ Nom.
6. Cliquez sur Nouveau.
7. Saisissez ou sélectionnez une valeur dans le champ ID mise en page.
8. Dans le champ Nom, entrez le nom de l'imprimante à utiliser.
9. Cliquez sur Enregistrer.
10. Fermez la page.

## <a name="create-mobile-device-menu"></a>Créer un menu d'appareil mobile
1. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.
2. Cliquez sur Nouveau.
3. Saisissez une valeur dans le champ Nom de l'option de menu.
4. Tapez une valeur dans le champ Titre.
5. Sélectionnez une option dans le champ Mode.
6. Sélectionnez Oui dans le champ Utiliser un travail existant.
7. Sélectionnez Oui dans le champ Générer un contenant.
8. Développez la section Classes de travail.
9. Cliquez sur Nouveau.
10. Tapez une valeur dans le champ ID classe de travail.
11. Cliquez sur Enregistrer.
12. Fermez la page.
13. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile.
14. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
15. Dans l'arborescence, sélectionnez « Dans l'arborescence, sélectionner l'option de menu que vous avez créée avant. ».
16. Cliquez sur Modifier.
17. Cliquez sur la flèche pour ajouter l'option de menu dans le menu.
18. Cliquez sur Enregistrer.
19. Fermez la page.

## <a name="update-a-work-template"></a>Mettre à jour un modèle de travail
1. Accédez à Gestion des entrepôts > Configuration > Travail > Modèles de travail.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Cliquez sur Modifier.
4. Cliquez sur Nouveau.
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ Type de travail, sélectionnez Imprimer.
7. Saisissez ou sélectionnez une valeur dans le champ ID classe de travail.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur Déplacer vers le haut.
10. Cliquez sur Enregistrer.
11. Fermez la page.


