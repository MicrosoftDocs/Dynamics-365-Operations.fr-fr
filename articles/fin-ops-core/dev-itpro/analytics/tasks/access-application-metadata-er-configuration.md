---
title: Accéder aux métadonnées d'application à l'aide de la configuration de la gestion des états électroniques
description: Les étapes de cette rubrique expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) peut créer une mise en correspondance de modèle de génération d'états électroniques (ER) à l'aide des métadonnées de Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa8444b081650e3d375e6f28f47866c8d4853721
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772461"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Accéder aux métadonnées d'application à l'aide de la configuration de la gestion des états électroniques

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une mise en correspondance de modèle de génération d'états électronique (ER) en utilisant les métadonnées de l'application. Les métadonnées d'application sont accessibles à l'aide d'une configuration de métadonnées ER contenant un échantillon de métadonnées pour accéder aux transactions de commerce extérieur. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette rubrique dans RCS, [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md). Ensuite, suivez les étapes de la rubrique [Préparer les métadonnées d'application à utiliser dans RCS](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Conditions préalables
1. Accédez à **Tous les espaces de travail** > **États électroniques**. 
2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="import-metadata-configuration"></a>Importer la configuration des métadonnées 
1. Cliquez sur **Configuration des métadonnées**. 
2. Importez la configuration de métadonnées ER contenant des métadonnées configurées pour générer des documents électroniques pour le commerce extérieur. Cette configuration de métadonnées ER a été exportées en tant que fichier XML lors des étapes de la procédure [Préparer les métadonnées d'application à utiliser dans RCS](prepare-application-metadata-rcs.md). 
3. Cliquez sur **Exchange**. 
4. Cliquez sur **Charger depuis le fichier XML**. 
5. Cliquez sur **Parcourir** et sélectionnez le fichier Foreign trade metadata.xml. 
6. Cliquez sur **OK**. 
7. Fermez la page. 

## <a name="create-data-model-configuration"></a>Créer une configuration de modèle de données
1. Cliquez sur **Configurations des états**. 
2. Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue. 
3. Dans le champ **Nom**, tapez « Modèle commerce extérieur ». 
4. Cliquez sur **Créer une configuration**. 
5. Cliquez sur **Concepteur**. 
6. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue. 
7. Dans le champ **Nom**, tapez « Racine ». 
8. Cliquez sur **Ajouter**. 
9. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue. 
10. Dans le champ **Nom**, tapez « Transaction ». 
11. Dans le champ **Type d'article**, sélectionnez **Liste d'enregistrements**. 
12. Cliquez sur **Ajouter**. 
13. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue. 
14. Dans le champ **Nom**, tapez « Code marchandise ». 
15. Dans le champ **Type d'article**, sélectionnez **Chaîne**. 
16. Cliquez sur **Ajouter**. 
17. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue. 
18. Dans le champ **Nom**, tapez « Montant facture » 
19. Dans le champ **Type d'article**, sélectionnez **Réel**. 
20. Cliquez sur **Ajouter**. 
21. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue. 
22. Dans le champ **Nom**, tapez « Date ». 
23. Dans le champ **Type d'article**, sélectionnez **Date**. 
24. Cliquez sur **Ajouter**. 
25. Cliquez sur **Référence racine**. 
26. Cliquez sur **OK**. 
27. Cliquez sur **Enregistrer**. 
28. Fermez la page. 
29. Cliquez sur **Modifier le statut**. 
30. Cliquez sur **Terminé.** 
31. Cliquez sur **OK**. 

## <a name="create-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèle 
1. Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue. 
2. Dans le champ **Nouveau**, entrez « Mise en correspondance de modèle basée sur le modèle de commerce extérieur ». 
3. Dans le champ **Nom**, tapez « Mise en correspondance de commerce extérieur ». 
4. Cliquez sur **Créer une configuration**. 
5. Développez la section **Conditions préalables**. 
6. Cliquez sur **Modifier**. 
7. Cliquez sur **Nouveau**. 
8. Dans la liste, marquer la ligne sélectionnée. 
9. Dans le champ **Type nécessaire de composant**, sélectionnez **Configuration**. 
10. Sélectionnez la configuration **Métadonnées de commerce extérieur**. 
11. Cliquez sur **Enregistrer**. 
12. Nous avons ajouté la référence à la version 1 de la configuration « Métadonnées de commerce extérieur ». Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue. 
13. Fermez la page. 
14. Cliquez sur **Concepteur**. 
15. Cliquez sur **Concepteur**. 
16. Dans l'arborescence, sélectionnez **Dynamics 365 for Operations\Enregistrements de table**. 
17. Cliquez sur **Ajouter racine**. 
18. Dans le champ **Nom**, tapez « Déclaration d'échanges de biens ». 
19. Sélectionnez les enregistrements de table **Déclaration d'échanges de biens**. 
20. Cliquez sur **OK**. 

> [!NOTE]
> Seules 2 tables sont proposées car ces seules 2 tables ont été ajoutées à l'ensemble de métadonnées en cours de utilisation. 

21. Cliquez sur **Lier**. 
22. Dans l'arborescence, développez **Déclaration d'échanges de biens**. 
23. Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens\AmountMST**. 
24. Dans l'arborescence, développez **Transaction = Déclaration d'échanges de biens**. 
25. Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens\Montant facturé**. 
26. Cliquez sur **Lier**. 
27. Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens\TransDate**. 
28. Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens\Date**. 
29. Cliquez sur **Lier**. 
30. Dans l'arborescence, développez **Déclaration d'échanges de biens\>Relations**. 
31. Dans l'arborescence, développez **Déclaration d'échanges de biens\>Relations\IntrastatCommodity**. 
32. Dans l'arborescence, développez **Déclaration d'échanges de biens\>Relations\IntrastatCommodity\Code**. 
33. Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens\Code marchandise**. 
34. Cliquez sur **Lier**. 
35. Cliquez sur **Valider**. 

> [!NOTE]
> Nous avons lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l'aide des informations des métadonnées de l'application issues de la configuration de métadonnées ER associée. 
36. Cliquez sur **Enregistrer**. 
37. Fermez la page. 
38. Fermez la page. 
39. Le cas échéant, vous pouvez étendre l'ensemble existant de métadonnées, puis exporter la nouvelle version terminée de la configuration de métadonnées ER. Vous pouvez ensuite l'importer dans RCS et mettre à jour les conditions préalables et la configuration de mise en correspondance du modèle configuré se référant à une nouvelle version de la configuration des métadonnées importée. 

> [!NOTE]
> Cette manière d'obtenir des informations sur les métadonnées d'application est la seule disponible pour les applications déployées localement (lorsqu'un modèle de déploiement de données métier local (LBD) ou sur site est utilisé).
        
