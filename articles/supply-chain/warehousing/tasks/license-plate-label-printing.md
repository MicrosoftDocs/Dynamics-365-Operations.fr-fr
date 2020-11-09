---
title: Activer l'impression d'étiquette de contenant
description: Cette rubrique présente comment activer l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e548e5e5528733412d47478dd740b87217cdac2
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016100"
---
# <a name="enable-license-plate-label-printing"></a>Activer l'impression d'étiquette de contenant

[!include [banner](../../includes/banner.md)]

Cette rubrique présente comment activer l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes. Vous pouvez exécuter cette procédure dans les données de démonstration de la société fictive USMF. Si vous l'exécutez à l'aide de vos propres données, vous devez avoir une souche de numéros pour les plaques d'immatriculation. Vous devez paramétrer une imprimante d'étiquettes avant de commencer cette tâche. Accédez à Administration d'organisation > Configuration > Imprimantes réseau. Dans le volet Actions, cliquez sur Options, puis sur le bouton Télécharger le fichier d'installation d'un agent d'acheminement de document. Exécutez le programme d'installation et assurez-vous d'avoir une imprimante réseau définie sur Actif avant de poursuivre la procédure.


## <a name="set-up-the-gs1-company-prefix"></a>Paramétrer le préfixe de la société GS1
1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts**.
2. Dans le champ **Préfixe société GS1** , entrez les 7 chiffres de numéro de l'entreprise GS1.
3. Sélectionnez **Enregistrer**.
4. Fermez la page.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Définir la séquence pour le numéro de contenant SSCC
1. Allez dans **Volet de navigation > Modules > Administration d'organisation > Souches de numéros > Souches de numéros**.
2. Dans le champ **Zone** , sélectionnez une option.
3. Dans le champ **Référence** , sélectionnez une option.
4. Dans le champ **Société** , sélectionnez une valeur.
5. Développez la section **Segments**.
6. Sélectionnez **Modifier**.
7. Dans la table **Segments** , sélectionnez la première ligne.
8. Sélectionnez **Supprimer**.
9. Sélectionnez **Supprimer**.
10. Sélectionnez **Enregistrer**.
11. Fermez la page.

## <a name="create-the-document-route-layout"></a>Créer la mise en page de l'acheminement du document
1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Acheminement de document > Mises en page de l'acheminement de document**. Activez la structure de SSCC.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **ID mise en page** , saisissez une valeur.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez **Insérer à la fin du texte**.
6. Sélectionnez **Enregistrer**.
7. Fermez la page.

## <a name="set-up-the-document-routing"></a>Définir l'acheminement de document
1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Acheminement de document > Acheminement de document**.
2. Dans le champ **Type d'ordre d'exécution** , sélectionnez une option.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Entrepôts** , saisissez une valeur.
5. Tapez une valeur dans le champ **Nom**.
6. Sélectionnez **Nouveau**.
7. Dans le champ **ID mise en page** , saisissez ou sélectionnez une valeur.
8. Dans le champ **Nom** , entrez le nom de l'imprimante à utiliser.
9. Sélectionnez **Enregistrer**.
10. Fermez la page.

## <a name="create-mobile-device-menu"></a>Créer un menu d'appareil mobile
1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom de l'option de menu** , saisissez une valeur.
4. Dans le champ **Titre** , saisissez une valeur.
5. Dans le champ **Mode** , sélectionnez une option.
6. Sélectionnez **Oui** dans le champ **Utiliser un travail existant**.
7. Sélectionnez **Oui** dans le champ **Générer un contenant**.
8. Développez la section **Classes de travail**.
9. Sélectionnez **Nouveau**.
10. Dans le champ **ID classe de travail** , saisissez une valeur.
11. Sélectionnez **Enregistrer**.
12. Fermez la page.
13. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile**.
14. Dans l'arborescence, sélectionnez l'article de menu que vous avez créé précédemment.
15. Sélectionnez **Modifier**.
16. Sélectionnez la flèche pour ajouter l'option de menu au menu.
17. Sélectionnez **Enregistrer**.
18. Fermez la page.

## <a name="update-a-work-template"></a>Mettre à jour un modèle de travail
1. Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Travail > Modèles de travail**.
2. Sélectionnez **Modifier**.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Type de travail** , sélectionnez **Imprimer**.
5. Dans le champ **ID classe de travail** , saisissez ou sélectionnez une valeur.
6. Sélectionnez **Déplacer vers le haut**.
7. Sélectionnez **Enregistrer**.
8. Fermez la page.

