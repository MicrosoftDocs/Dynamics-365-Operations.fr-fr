--- 
title: "Mettre à niveau votre format en adoptant la nouvelle version de base de ce format pour la génération d'états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut conserver une configuration de format pour la génération d'états électronique (ER)."
author: NickSelin
manager: AnnBe
ms.date: 02/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: cfc68c1d0810cbc296b35c09176dde2c948a50d0
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---
# <a name="upgrade-your-format-by-adopting-of-new-base-version-of-that-format-for-electronic-reporting-er"></a>Mettre à niveau votre format en adoptant la nouvelle version de base de ce format pour la génération d'états électroniques (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut conserver une configuration de format pour la génération d'états électronique (ER). Cette procédure explique comment une version personnalisée d'un format peut être créée en fonction du format reçu d'un fournisseur de configuration. Elle décrit également comment adopter une nouvelle version de base de ce format.



Pour effectuer ces étapes, vous devez tout d'abord appliquer les procédures « Créer un fournisseur de configuration et le marquer comme actif » et « Utiliser le format créé pour générer des documents électroniques ». Ces étapes peuvent être effectuées dans la société GBSI.


## <a name="select-format-configuration-for-customization"></a>Sélectionner la configuration du format pour la personnalisation
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Dans cet exemple, la société fictive Litware, Inc. (`http://www.litware.com`) fait office de fournisseur de configuration qui prend en charge les configurations de format pour les paiements électroniques pour un pays particulier.  La société fictive Proseware, Inc. (`http://www.proseware.com`) fait office de consommateur de la configuration du format fourni par Litware, Inc. Proseware, Inc. utilise des formats dans certaines régions de ce pays.  
2. Cliquez sur Configurations des états.
3. Cliquez sur Afficher les filtres.
4. Appliquez les filtres suivants : entrez la valeur de filtre « BACS (nom fictif britannique) » dans le champ « Nom » à l'aide de l'opérateur de filtre « commence par ».
    * LE SYSTÈME BACS (R-U factice)  
    * La configuration du format sélectionné BACS (nom fictif britannique) appartient au fournisseur Litware, Inc.  
5. Cliquez sur Afficher les filtres.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * La version du format dont le statut est Terminé est utilisée par Proseware, Inc. pour la personnalisation.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Créer une configuration pour le format personnalisé du document électronique
Proseware, Inc. a reçu la version 1.1 de la configuration BACS (nom fictif britannique) qui contient le format initial pour générer des documents de paiement électronique à partir de Litware, Inc. conformément à leur abonnement au service. Proseware, Inc. souhaite commencer à l'aide de cette norme pour son pays, mais certaines personnalisations sont nécessaires pour prendre en charge des besoins spécifiques à la région. Proseware, Inc. souhaite également conserver la capacité de mettre à niveau un format personnalisé dès qu'une nouvelle version de celui-ci (avec des modifications pour prendre en charge de nouveaux besoins spécifiques au pays) est disponible à partir de Litware, Inc. et il souhaite effectuer cette mise à niveau à moindre coût.  Pour ce faire, Proseware, Inc. doit créer une configuration à l'aide de la configuration du format sélectionné BACS (nom fictif britannique) de Litware, Inc. comme base.  
1. Fermez la page.
2. Sélectionnez Proseware, Inc. pour en faire un fournisseur actif.
3. Cliquez sur Activer.
4. Cliquez sur Configurations des états.
5. Dans l'arborescence, développez « Paiements (modèle simplifié) ».
6. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».
    * Sélectionnez la configuration du format sélectionné BACS (nom fictif britannique) de Litware, Inc.     Proseware, Inc. utilise la version 1,1 comme base pour la version personnalisée.  
7. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
    * Cela vous permet de créer une configuration pour un format de paiement personnalisé.  
8. Dans le champ Nouveau, entrez « Provenant du nom : BACS (nom fictif britannique), Litware, Inc. ».
    * Sélectionnez l'option Déduire pour confirmer l'utilisation de BACS (nom fictif britannique) comme base pour créer la version personnalisée.  
9. Dans le champ Nom, tapez « BACS (nom personnalisé fictif britannique) ».
    * BACS (nom personnalisé fictif britannique)  
10. Dans le champ Description, entrez « Paiement fournisseur BACS (nom personnalisé fictif britannique) ».
    * Paiement fournisseur BACS (nom personnalisé fictif britannique)  
    * Le fournisseur de configuration actif (Proseware, Inc.) est automatiquement entré ici. Ce fournisseur pourra mettre à jour cette configuration. D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.  
11. Cliquez sur Créer une configuration.

## <a name="customize-your-format-for-the-electronic-document"></a>Personnaliser le format du document électronique
1. Cliquez sur Concepteur.
2. Cliquez sur Développer/réduire.
3. Cliquez sur Développer/réduire.
4. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».
5. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
6. Dans l'arborescence , sélectionnez « XML\Élément ».
7. Tapez « IBAN » dans le champ Nom.
    * IBAN  
8. Cliquez sur OK.
9. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\IBAN ».
10. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
11. Dans l'arborescence, sélectionnez « Texte\Chaîne ».
12. Cliquez sur OK.
13. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom\Chaîne ».
14. Dans le champ Longueur maximale, entrez 60.
15. Cliquez sur l'onglet Mise en relation.
16. Dans l'arborescence , développez « model ».
17. Dans l'arborescence, développez model\Payments.
18. Dans l'arborescence , développez « modèle\Paiements\Créditeur ».
19. Dans l'arborescence , développez « modèle\Paiements\Créditeur\Compte ».
20. Dans l'arborescence, sélectionnez « Modèle\Paiements\Créditeur\Compte\IBAN ».
21. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article = model.Payments\Fournisseur\Banque\IBAN\Chaîne ».
22. Cliquez sur Lier.
23. Cliquez sur Enregistrer.

## <a name="validate-the-customized-format"></a>Valider le format personnalisé
1. Cliquez sur Valider.
    * Validez la structure de format personnalisée et les modifications de mise en correspondance des données pour vous assurer que toutes les liaisons sont correctes.  
2. Fermez la page.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Modifier le statut de la version actuelle de la configuration de format personnalisé
    * Modifiez le statut de la configuration du format conçu : remplacez Brouillon par Terminé pour le rendre disponible pour la génération de document de paiement.  
1. Cliquez sur Modifier le statut.
    * Notez que la version actuelle de la configuration sélectionnée est en mode Brouillon.  
2. Cliquez sur Terminé.
3. Dans le champ Description, entrez une valeur.
4. Cliquez sur OK.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Notez que la configuration créée est enregistrée comme version 1.1.1 terminée. Cela signifie que c'est la version 1 du format BACS (nom personnalisé fictif britannique) personnalisé, qui est basé sur la version 1 du format BACS (nom fictif britannique), basé sur la version 1 du modèle de données Paiements (modèle simplifié).  

## <a name="test-the-customized-format-to-generate-payment-files"></a>Tester le format personnalisé pour générer des fichiers de paiement
Suivez les étapes de la procédure « Utiliser le format créé pour générer des documents électroniques de paiement » dans une session parallèle de Dynamics 365 for Finance and Operations. Sélectionnez le format BACS (nom personnalisé fictif britannique) dans les paramètres de mode de paiement électronique. Vérifiez que le fichier de paiement créé contient le nœud XML introduit récemment présentant le code IBAN conformément aux besoins spécifiques.  

## <a name="update-the-existing-country-specific-configuration"></a>Mettre à jour la configuration spécifique au pays existant
Litware, Inc. doit mettre à jour la configuration BACS (nom personnalisé fictif britannique) et adopter de nouvelles exigences spécifiques au pays pour gérer le format du document électronique. Cela sera ensuite associé à une nouvelle version de cette configuration qui sera proposée aux abonnés du service, notamment Proseware, Inc.  

Dans les véritables processus associés à l'approvisionnement de service, chaque nouvelle version de BACS (nom fictif britannique) peut être importée par Proseware, Inc. à partir du référentiel LCS de configurations Litware, Inc. Dans cette procédure nous simulerons cela en mettant à jour BACS (nom fictif britannique) au nom d'un fournisseur de services.

1. Fermez la page.
2. Sélectionnez Litware, Inc. .
3. Cliquez sur Activer.
4. Cliquez sur Configurations des états.
5. Dans l'arborescence, développez « Paiements (modèle simplifié) ».
6. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».
    * La version temporaire BACS (nom fictif britannique) appartenant au fournisseur Litware, Inc. est sélectionnée pour apporter des modifications pour prendre en charge de nouvelles exigences spécifiques au pays.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Localiser le format de base du document électronique
Supposons qu'il existe de nouvelles exigences spécifiques au pays à prendre en charge par Litware :  
- Une valeur pour le code SWIFT de la banque créancière dans chaque transaction de paiement.  
- La longueur du nom du fournisseur est limitée à 100 caractères dans la génération de fichiers.  
 
Sélectionnez la version temporaire de la configuration souhaitée pour afficher les modifications requises.  

1. Cliquez sur Concepteur.
2. Cliquez sur Développer/réduire.
3. Cliquez sur Développer/réduire.
4. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».
5. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
6. Dans l'arborescence , sélectionnez « XML\Élément ».
7. Tapez SWIFT dans le champ Nom.
    * SWIFT  
8. Cliquez sur OK.
9. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\SWIFT ».
10. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
11. Dans l'arborescence, sélectionnez « Texte\Chaîne ».
12. Cliquez sur OK.
13. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom\Chaîne ».
14. Dans le champ Longueur maximale, entrez 100.
15. Cliquez sur l'onglet Mise en relation.
16. Dans l'arborescence , développez « model ».
17. Dans l'arborescence, développez model\Payments.
18. Dans l'arborescence , développez « modèle\Paiements\Créditeur ».
19. Dans l'arborescence , développez « modèle\Paiements\Créditeur\Agent ».
20. Dans l'arborescence, sélectionnez « Modèle\Paiements\Créditeur\Agent\SWIFT ».
21. Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article = model.Payments\Fournisseur\Banque\SWIFT\Chaîne ».
22. Cliquez sur Lier.
23. Cliquez sur Enregistrer.

## <a name="validate-the-localized-format"></a>Valider le format localisé
1. Cliquez sur Valider.
2. Fermez la page.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Modifier le statut de la version actuelle de la configuration du format de base
Modifiez le statut de la configuration du format de base mis à jour de Brouillon à Terminé pour le rendre disponible pour la génération de documents de paiement et de mises à jour des configurations de format dérivées de celui-ci.  
1. Cliquez sur Modifier le statut.
    * Notez que la version actuelle de la configuration sélectionnée est en mode Brouillon.  
2. Cliquez sur Terminé.
3. Dans le champ Description, entrez une valeur.
4. Cliquez sur OK.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Modifier la version de base pour la configuration du format personnalisé
Proseware, Inc. est informé qu'une nouvelle version 1.2 de la configuration de BACS (nom fictif britannique) est disponible pour générer des documents de paiement électronique conformément aux nouvelles exigences spécifiques au pays annoncées. Proseware, Inc. souhaite commencer à l'utiliser en tant que standard pour le pays.  Pour cela, Proseware, Inc. doit modifier la version de configuration de base pour la configuration personnalisée BACS (nom personnalisé fictif britannique). Utilisez la nouvelle version 1.2 au lieu de la version 1.1 de BACS (nom fictif britannique).  

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Sélectionnez le fournisseur Proseware, Inc. pour le marquer comme actif.
3. Cliquez sur Activer.
4. Cliquez sur Configurations des états.
5. Dans l'arborescence, développez « Paiements (modèle simplifié) ».
6. Dans l'arborescence, développez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».
7. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique)\BACS (nom personnalisé fictif britannique) ».
    * Sélectionnez BACS (nom personnalisé fictif britannique), qui appartient à Proseware, Inc.  
    * Utilisez la version temporaire de la configuration sélectionnée pour afficher les modifications requises.  
8. Cliquez sur Redéfinir.
    * Sélectionnez la nouvelle version 1.2 de la configuration de base à appliquer nouvelle comme base pour mettre la configuration à jour.  
9. Cliquez sur OK.
    * Notez que certains conflits ont été découverts entre la fusion de la version personnalisée et une nouvelle version de base représentant certaines modifications de format qui ne peuvent pas être fusionnées automatiquement.  

## <a name="resolve-rebase-conflicts"></a>Résoudre des conflits redéfinis
1. Cliquez sur Concepteur.
    * Notez que les modifications apportées à la limite de longueur de texte du nom du fournisseur ne peuvent pas être résolues automatiquement. Elles sont par conséquent présentées dans une liste des conflits. Pour chaque conflit de mise à jour du type, les options suivantes sont disponibles : Appliquer la valeur de base précédente (bouton en haut de la grille) pour afficher la valeur de version de base précédente (0 dans ce cas).  - Appliquez une valeur de base (bouton en haut de la grille) pour afficher la nouvelle valeur de version de base (100 dans ce cas).  - Conservez vos propres valeurs (personnalisées) (60 dans notre cas).  Cliquez sur Appliquer la valeur de base pour appliquer une limite spécifique au pays de 100 caractères pour la longueur du nom du fournisseur.  
    * Notez que Proseware, Inc. et Litware, Inc. ont des versions personnalisées et locales de ce format à l'aide de codes IBAN et SWIFT avec les composants associés qui sont automatiquement fusionnés dans le format de gestion.  
2. Cliquez sur Appliquer la valeur de base.
    * Cliquez sur Appliquer la valeur de base pour appliquer la limite spécifique à la région de 100 caractères aux noms de fournisseur.  
3. Cliquez sur Enregistrer.
    * Si vous enregistrez le format, cela supprimera des conflits résolus de la liste des conflits.  
4. Fermez la page.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Modifier le statut de la nouvelle version de la configuration du format personnalisé
1. Cliquez sur Modifier le statut.
    * Modifiez le statut de la configuration du format personnalisé, mis à jour de Brouillon à Terminé. Cela rendra la configuration du format disponible pour générer des documents de paiement. Notez que la version actuelle de la configuration sélectionnée est en mode Brouillon.  
2. Cliquez sur Terminé.
3. Dans le champ Description, entrez une valeur.
4. Cliquez sur OK.
    * Notez que la configuration créée est enregistrée comme version 1.2.2 terminée : la version 2 du format BACS (nom personnalisé fictif britannique) de base, basé sur la version 2 du format du BACS (nom fictif britannique) de base, basé sur la version 1 du modèle de données Paiements (modèle simplifié).  

## <a name="test-the-customized-format-for-payment-files-generation"></a>Tester le format personnalisé pour la génération des fichiers de paiement
Suivez les étapes de la procédure « Utiliser le format créé pour générer des documents électroniques de paiement » dans une session parallèle de Dynamics 365 for Finance and Operations. Sélectionnez le format BACS (nom personnalisé fictif britannique) créé dans les paramètres de mode de paiement électronique. Vérifiez que le fichier de paiement créé contient le nœud XML introduit récemment par Proseware, Inc. présentant le code de compte IBAN conformément aux besoins spécifiques. Le fichier doit également contenir le nœud de XML récemment introduit par Litware, Inc. présentant le code de banque SWIFT dans l'accord aux besoins de pays.  


