--- 
title: "Importer des configurations pour générer des documents contenant des données d'application"
description: "Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Créer un fournisseur de configuration et le marquer comme actif »."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 87352293a78d6a356db49deffb930016a1bf836c
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="import-configurations-to-generate-documents-with-application-data"></a>Importer des configurations pour générer des documents contenant des données d'application

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Créer un fournisseur de configuration et le marquer comme actif ».

Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique. Dans cette procédure, vous importerez les configurations ER requises qui ont été créées pour la société fictive, Litware, Inc., puis les utiliserez pour générer des documents électroniques. Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. Ces étapes peuvent être effectuées à l'aide de l'ensemble de données DEMF. Avant de commencer, téléchargez et enregistrez les fichiers répertoriés dans la rubrique d'aide, « Générer des documents électroniques et mettre à jour les données d'application à l'aide de l'outil de gestion des états électroniques » (generate-electronic-documents-update-application-data/). Les fichiers sont Déclaration d'échanges de biens (modèle).xml, Déclaration d'échanges de biens (mise en correspondance).xml et Déclaration d'échanges de biens (format).xml.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, Créer un fournisseur de configuration et le marquer comme actif.  
    * Les étapes de cette procédure indiquent comment utiliser les fonctionnalités ER pour effectuer une mise à jour des données d'application et comment générer un état de déclaration d'échanges de biens. Les détails du processus de génération d'états sont archivés dans les tables d'application. Pour le moment, lorsque le processus de génération d'états de déclaration d'échanges de biens est activé depuis l'écran Déclaration d'échanges de biens, l'archivage est effectué en fonction de la logique programmée dans le code source existant. Dans cette procédure, vous configurerez une logique similaire mais simplifiée des données d'application en utilisant uniquement l'infrastructure ER. Aucune modification ne sera apportée au code source.   

## <a name="import-er-configurations"></a>Importer les configurations ER
1. Cliquez sur Configurations des états.
2. Cliquez sur Échanger.
3. Cliquez sur Charger depuis le fichier XML.
    * Importez la configuration du modèle ER qui contient le modèle de données conçu pour être utilisé comme source de données pour générer l'état de déclaration d'échange de biens. Ensuite, vous étendrez cette définition de modèle de données pour l'utiliser pour une mise à jour des données d'application pour archiver les détails du processus de génération d'états de déclaration d'échanges de biens.   
    * Cliquez sur Parcourir et sélectionnez le fichier Déclaration d'échanges de biens (modèle).xml.  
4. Cliquez sur OK.
5. Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens (modèle) ».
6. Cliquez sur Concepteur.
7. Dans l'arborescence, développez « Pour le document sortant ».
8. Dans l'arborescence, développez « Pour le document sortant\Transactions ».
    * Examinez la structure du modèle de données importé. Notez que l'élément racine « Pour le document sortant » est défini pour spécifier le flux de données permettant d'obtenir des données de l'application et de les utiliser comme source de données pour générer l'état de déclaration d'échanges de biens. L'élément « Transactions (liste d'enregistrements) » est utilisé pour représenter la liste des transactions de déclaration d'échanges de biens qui doivent être établies. Comme vous archiverez les codes marchandise déclarés, l'identificateur unique d'un seul code marchandise « ID enregistrement de marchandise (Int64) » est nécessaire dans ce flux de données.   
9. Fermez la page.
10. Cliquez sur Échanger.
11. Cliquez sur Charger depuis le fichier XML.
    * Importez la configuration de mise en correspondance ER qui spécifie le flux de données permettant d'obtenir des données de l'application et de les utiliser pour générer l'état de déclaration d'échanges de biens. Par la suite, vous étendrez cette définition de mise en correspondance de modèle pour obtenir des données de l'état de déclaration d'échanges de biens et les utiliser pour la mise à jour des données d'application pour archiver les détails du processus de génération d'états de déclaration d'échanges de biens.   
    * Cliquez sur Parcourir et sélectionnez le fichier Déclaration d'échanges de biens (mise en correspondance).xml.  
12. Cliquez sur OK.
13. Dans l'arborescence, développez « Déclaration d'échanges de biens (modèle) ».
14. Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens (modèle)\Déclaration d'échanges de biens (mise en correspondance) ».
15. Cliquez sur Concepteur.
    * Notez que la mise en correspondance de modèle actuelle contient la valeur « Vers le modèle » dans le champ Direction. Cela signifie que cette mise en correspondance de modèle a été conçue pour obtenir des données de l'application et les enregistrer dans le modèle de données.  
16. Cliquez sur Concepteur.
17. Dans l'arborescence, développez « Liste ».
18. Dans l'arborescence , développez « Transactions = Liste ».
    * Examinez la structure de la mise en correspondance de modèle qui utilise le modèle de données filtré selon l'élément racine, « Pour le document sortant ». Notez que la source de données ajoutée, « Liste » permet d'accéder aux données d'application requises, c'est-à-dire la liste des enregistrements de la table de déclaration d'échanges de biens.  
19. Fermez la page.
20. Fermez la page.
21. Cliquez sur Échanger.
22. Cliquez sur Charger depuis le fichier XML.
    * Importez la configuration du format ER qui spécifie la mise en page de l'état de déclaration d'échanges de biens et le processus de remplissage des données dans l'état. Par la suite, vous étendrez cette définition de format pour importer les données de l'état de déclaration d'échanges de biens dans le modèle de données et les utiliser pour mettre à jour les données de l'application pour archiver les détails du processus de génération d'états de déclaration d'échanges de biens.   
    * Cliquez sur Parcourir et sélectionnez le fichier Déclaration d'échanges de biens (format).xml.  
23. Cliquez sur OK.
24. Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens (modèle)\Déclaration d'échanges de biens (format) ».
25. Cliquez sur Concepteur.
26. Cliquez sur Développer/réduire.
27. Dans l'arborescence, sélectionnez « Fichier\Déclaration ».
28. Cliquez sur l'onglet Mise en relation.
29. Dans l'arborescence, sélectionnez « Fichier ».
    * Examinez la structure du format utilisé pour générer l'état de déclaration d'échanges de biens. Notez qu'elle est conçue pour générer un fichier XML en remplissant les données du modèle de données, qui est basé sur l'élément racine « Pour le document sortant ». Vérifiez que le nom du fichier généré est défini sur l'écran Boîte de dialogue utilisateur (la source de données « fn » est utilisée à cet effet).   
30. Fermez la page.


