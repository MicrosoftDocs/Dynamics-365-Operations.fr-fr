---
title: Préparer les métadonnées spécifiques à l'application pour RCS et ER
description: Cette rubrique explique comment préparer des métadonnées spécifiques à l'application pour le service RCS (Regulatory Configuration Service) et la génération d'états électroniques (ER)
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 289f901501a68319c9d85e993d8dfbfc3838a8eb
ms.sourcegitcommit: d940c7892b6caa6141b3bda8abf1c56e9df4687a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2019
ms.locfileid: "1726430"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a>Préparer les métadonnées spécifiques à l'application pour RCS

[!include[banner](../includes/banner.md)]

Cette rubrique que vous guide via les exemples de tâches suivantes :

- [Préparer les métadonnées d'application à utiliser dans RCS](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Accéder aux métadonnées d'application à l'aide d'une configuration de gestion des états électroniques](#access-application-metadata-by-using-an-er-configuration)
- [Accéder aux métadonnées d'application à l'aide des applications connectées](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>Préparer les métadonnées d'application à utiliser dans RCS

La procédure suivante montre comment un utilisateur de Finance and Operations ayant le rôle **Administrateur système** ou **Développeur d'états électroniques** peut créer une configuration de génération d'états électroniques (ER) contenant des métadonnées pour l'application Microsoft Dynamics 365 for Finance and Operations, et qui est utilisée pour concevoir les configurations de mise en correspondance de modèles ER dans le service RCS (Regulatory Configuration Service). L'exemple de configuration de mise en correspondance de modèle ER créée dans cette procédure sera utilisé pour accéder à des transactions de commerce extérieur.

Pour cet exemple, vous souhaitez utiliser RCS pour créer une solution ER pour Finance and Operations qui sera utilisée pour générer les documents électroniques contenant les informations du commerce extérieur. Pour spécifier la mise en correspondance entre le modèle de données ER et les sources de données nécessaires, vous devez avoir accès aux métadonnées d'application pour Finance and Operations dans RCS. Par conséquent, dans le cadre de la conception de la solution ER, vous devez paramétrer une nouvelle configuration de métadonnées ER contenant toutes les métadonnées actuellement requises pour générer des les états électroniques pour le domaine d'activité sélectionné.

> [!NOTE]
> Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société.

1. Allez dans **Administration d'organisation \> Espaces de travail \> États électroniques**.
2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Sélectionnez **Configuration des métadonnées**.
4. Sélectionnez **Créer une configuration**.
5. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez un nom. Pour cet exemple, entrez **Métadonnées de commerce extérieur**.
6. Sélectionnez **Créer une configuration**.
7. Sélectionnez **Concepteur**.
8. Sélectionnez **Ajouter**.

    > [!NOTE]
    > Vous pouvez sélectionner toutes les métadonnées pour l'application entière, ou pour des modèles ou des modules sélectionnés. Dans les deux cas, notez que les métadonnées suivantes sont automatiquement ajoutées : tables des enregistrements, énumérations, et types de données étendus (EDT, Extended Data Types). Lorsque d'autres types de métadonnées sont requis, ils doivent être ajoutés manuellement.

Vous devez ajouter des métadonnées relatives aux transactions de commerce extérieur et sélectionner manuellement les éléments de métadonnées.

9. Sélectionnez **Ajouter une source de données \> Enregistrements de table**.
10. Filtrez sur une valeur de **Déclaration d'échanges de biens** dans le champ **Nom**.
11. Sélectionnez l'enregistrement de table **Déclaration d'échanges de biens**.
12. Cliquez sur **OK**.

Vous devez ajouter des informations de métadonnées sur la table d'enregistrements de la déclaration d'échanges de biens.

13. Dans l'arborescence, sélectionnez **Enregistrements de table Déclaration d'échanges de biens \> \>Relations \> IntrastatCommodity (Enregistrements de table EcoResCategory)**.
14. Sélectionnez **Ajouter des métadonnées**.

    > [!NOTE]
    > Les métadonnées sur les relations requises pour la table d'enregistrements sélectionnée doivent être ajoutées manuellement.

15. Sélectionnez **Ajouter une source de données**.
16. Sélectionnez **Énumération**.
17. Filtrez sur une valeur de **IntrastatDirection** dans le champ **Nom**.
18. Sélectionnez l'enregistrement d'énumération **IntrastatDirection**.
19. Cliquez sur **OK**.
20. Sélectionnez **Enregistrer**.
21. Fermez la page.
22. Complétez la version temporaire de la configuration de métadonnées :

    1. Sélectionnez **Modifier le statut \> Terminé**.
    2. Cliquez sur **OK**.
    3. Sélectionnez la version 1 terminée.

23. Exportez la version achevée de la configuration des métadonnées à partir de l'application dans un fichier XML :

    1. Sélectionnez **Exchange \> Exporter en tant que fichier XML**.
    2. Cliquez sur **OK**.

La configuration de métadonnées ER que vous avez créée est enregistrée comme fichier **Foreign trade metadata.xml**. Vous pouvez désormais l'importer dans RCS pour qu'elle soit utilisée comme la source des métadonnées pour le domaine du commerce extérieur dans Finance and Operations. Sur la base de ces informations, vous pouvez spécifier la mise en correspondance entre les métadonnées d'application et le modèle de données ER.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Accéder aux métadonnées d'application à l'aide d'une configuration de gestion des états électroniques

La procédure suivante ontre comment un utilisateur de RCS ayant le rôle **Administrateur système** ou **Développeur d'états électroniques** peut créer une mise en correspondance de modèle ER à l'aide des métadonnées de l'application Finance and Operations. Les métadonnées d'application sont accessibles à l'aide d'une configuration de métadonnées ER contenant un échantillon de métadonnées pour accéder aux transactions de commerce extérieur.

Avant d'exécuter cette procédure, vous devez d'abord réaliser celles qui suivent :

- [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [Préparer les métadonnées d'application à utiliser dans RCS](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Accédez à **Tous les espaces de travail \> États électroniques**.
2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Importez la configuration de métadonnées ER contenant les métadonnées pour l'application Finance and Operations, configurée pour générer des documents électroniques pour le commerce extérieur. Vous avez créé cette configuration de métadonnées ER et l'avez exportée dans un fichier XML dans la procédure [Préparer les métadonnées d'application à utiliser dans RCS](#prepare-application-metadata-that-can-be-used-in-rcs) décrite plus haut dans cette rubrique.

    1. Sélectionnez **Configuration des métadonnées**.
    2. Sélectionnez **Exchange**.
    3. Sélectionnez **Charger depuis le fichier XML**.
    4. Recherchez et sélectionnez le fichier **Foreign trade metadata.xml**.
    5. Cliquez sur **OK**.
    6. Fermez la page.

4. Créez une configuration de modèle de données :

    1. Sélectionnez **Configurations des états**.
    2. Sélectionnez **Créer une configuration**.
    3. Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Modèle de commerce extérieur**.
    4. Sélectionnez **Créer une configuration**.
    5. Sélectionnez **Concepteur**.
    6. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.

        1. Dans le champ **Nom**, tapez **Racine**.
        2. Sélectionnez **Ajouter**.
    
    7. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.

        1. Dans le champ **Nom**, tapez **Transaction**.
        2. Dans le champ **Type d'article**, sélectionnez **Liste d'enregistrements**.
        3. Sélectionnez **Ajouter**.
 
    8. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.

        1. Dans le champ **Nom**, tapez **Code marchandise**.
        2. Dans le champ **Type d'article**, sélectionnez **Chaîne**.
        3. Sélectionnez **Ajouter**.

    9. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.

        1. Dans le champ Nom, tapez **Montant facture**.
        2. Dans le champ **Type d'article**, sélectionnez **Réel**.
        3. Sélectionnez **Ajouter**.

    10. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.

        1. Dans le champ **Nom**, tapez **Date**.
        2. Dans le champ **Type d'article**, sélectionnez **Date**.
        3. Sélectionnez **Ajouter**.
 
    11. Sélectionnez **Ajouter \> Référence racine**.
    12. Cliquez sur **OK**.
    13. Sélectionnez **Enregistrer**.
    14. Fermez la page.
    15. Sélectionnez **Modifier le statut \> Terminé**.
    16. Cliquez sur **OK**.

5. Créez une configuration de mise en correspondance de modèle :

    1. Sélectionnez **Créer une configuration**.
    2. Dans la boîte de dialogue déroulante, dans le champ **Nouveau**, entrez **Mise en correspondance de modèle basée sur le modèle de commerce extérieur**.
    3. Dans le champ **Nom**, tapez **Mise en correspondance de commerce extérieur**.
    4. Sélectionnez **Créer une configuration**.
    5. Dans l'organisateur **Conditions préalables**, sélectionnez **Éditer**.
    6. Sélectionnez **Nouveau**.
    7. Dans le champ **Type nécessaire de composant**, sélectionnez **Configuration**.
    8. Sélectionnez la configuration **Métadonnées de commerce extérieur**.
    9. Sélectionnez **Enregistrer**. Notez que nous avons ajouté la référence à la version 1 de la configuration **Métadonnées de commerce extérieur**. Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.
    10. Fermez la page.
    11. Sélectionnez **Concepteur**.
    12. Sélectionnez **Concepteur**.
    13. Dans l'arborescence, sélectionnez **Dynamics 365 for Operations \> Enregistrements de table**.
    14. Sélectionnez **Ajoutez racine**.
    15. Dans le champ **Nom**, entrez **Déclaration d'échanges de biens**.
    16. Sélectionnez les enregistrements de table **Déclaration d'échanges de biens**.
    17. Cliquez sur **OK**.

        > [!NOTE]
        > Seules 2 tables sont proposées, car ces seules 2 tables ont été ajoutées à l'ensemble de métadonnées en cours de utilisation.

    18. Sélectionnez **Lier**.
    19. Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens \> AmountMST**.
    20. Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens \> Montant facturé**.
    21. Sélectionnez **Lier**.
    22. Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens \> TransDate**.
    23. Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens \> Date**.
    24. Sélectionnez **Lier**.
    25. Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens \> \>Relations \> IntrastatCommodity \> Code**.
    26. Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens \> Code marchandise**.
    27. Sélectionnez **Lier**.
    28. Sélectionnez **Valider**.

        > [!NOTE]
        > Une fois la validation effectuée, nous avons lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l'aide des informations des métadonnées de l'application issues de la configuration de métadonnées ER associée.

    29. Sélectionnez **Enregistrer**.

Selon vos besoins, vous pouvez étendre l'ensemble de métadonnées existant dans Finance and Operations. Vous pouvez ensuite exporter la nouvelle version achevée de la configuration des métadonnées ER à partir de Finance and Operations, l'importer dans RCS et mettre à jour les conditions préalables et la configuration de mise en correspondance du modèle configurée se référant à une nouvelle version de la configuration des métadonnées importée.

> [!NOTE]
> Cette manière d'obtenir des informations sur les métadonnées d'application est la seule disponible pour les applications déployées localement (c'est-à-dire lorsqu'un modèle de déploiement de données métier local \[LBD\], ou sur site, est utilisé pour Finance and Operations).

## <a name="access-application-metadata-by-using-connected-applications"></a>Accéder aux métadonnées d'application à l'aide des applications connectées

La procédure suivante ontre comment un utilisateur de RCS ayant le rôle **Administrateur système** ou **Développeur d'états électroniques** peut créer une mise en correspondance de modèle ER à l'aide des métadonnées de l'application Finance and Operations. Les métadonnées d'application ne sons accessibles en ligne qu'à l'aide de l'application RCS connectée. Un exemple de mise en correspondance de modèle ER est configuré pour accéder à des transactions de commerce extérieur.

Pour réaliser cette procédure, vous devez commencer par effectuer la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md) dans RCS. Si vous n'avez pas encore réalisé les la procédure [Accéder aux métadonnées d'application à l'aide de la configuration de la gestion des états électroniques](#access-application-metadata-by-using-an-er-configuration) plus haut dans cette rubrique, accédez à la page [Guides de tâches de la génération d'états électroniques pour Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) pour télécharger par avance les fichiers de configuration ER suivants et les enregistrer localement : **Foreign trade metadata.xml**, **Foreign trade model.xml** et **Foreign trade mapping.xml**.


### <a name="get-required-er-configurations"></a>Obtenir les configurations ER requises

Si vous avez déjà réalisé les étapes de la procédure [Accéder aux métadonnées d'application à l'aide d'une configuration de la gestion des états électroniques](#access-application-metadata-by-using-an-er-configuration) plus haut dans cette rubrique, vous disposez déjà de toutes les configurations ER nécessaires (métadonnées de commerce extérieur, configurations de modèle et de mise en correspondance) dans l'instance RCS actuelle. Dans ce cas, vous pouvez ignorer cette procédure.

1. Accédez à **Tous les espaces de travail \> États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Chargez les fichiers de configuration **Foreign trade metadata.xml**, **Foreign trade model.xml**, et **CForeign trade mapping.xml** répétant la chaîne d'étapes suivantes pour chacun d'eux :

    1. Sélectionnez **Exchange**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir** et sélectionnez un fichier.
    4. Cliquez sur **OK**.

### <a name="register-the-connection-with-finance-and-operations"></a>Inscrivez la connexion à Finance and Operations.

1. Accédez à **Tous les espaces de travail \> États électroniques**.
2. Sélectionnez **Applications connectées**.
3. Assurez-vous que l'application configurée est basée sur Microsoft Azure, et qu'elle est accessible en général aux utilisateurs de RCS. L'utilisateur RCS actuel doit avoir accès à l'application configurée en étant inscrit comme utilisateur de cette application avec un rôle lui accordant les privilèges d'accès aux métadonnées de l'application.
4. Sélectionnez **Nouveau**.
5. Dans le champ **Nom**, entrez **MyConnectedApp** comme nom de l'application connectée.
6. Dans le champ **Application**, spécifiez l'URL de l'application.
7. Dans le champ **Locataire**, spécifiez le fournisseur de l'application.
8. Sélectionnez **Enregistrer**. 
9. Lorsque vous vérifiez la connexion à l'application configurée, dans la page **Se connecter à l'application distante** sélectionnez le lien **Cliquer ici pour vous connecter à l'application distante sélectionnée**. 
10. Sélectionnez **Vérifier la connexion** pour valider l'accès à l'application configurée.
11. Sélectionnez **Fermer**.

Une fois la procédure exécutée et la validation de la connexion réussie, les détails de la version et du client sont mis à jour pour l'application configurée dans la grille actuelle.

### <a name="review-the-existing-model-mapping-configuration"></a>Examiner la configuration de mise en correspondance de modèle existante

1. Accédez à **Tous les espaces de travail \> États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Dans l'arborescence, sélectionnez **Modèle de commerce extérieur \> Mise en correspondance de commerce extérieur**.
4. Sélectionnez l'organisateur **Conditions préalables**.

    > [!NOTE]
    > Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées. Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.

4. Sélectionnez **Concepteur**.
5. Sélectionnez **Concepteur**.
6. Dans l'arborescence, sélectionnez **Dynamics 365 for Operations \> Enregistrements de table**.
7. Sélectionnez **Ajoutez racine**.
8. Dans le champ **Table**, saisissez ou sélectionnez une valeur.

    > [!NOTE]
    > Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées. Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.

9. Sélectionnez **Annuler**.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Affecter l'application connectée à une mise en correspondance de modèle

1. Sélectionnez **Modifier**.
2. Dans le champ **Application connectée**, sélectionnez l'application **MyConnectedApp**.

    > [!NOTE]
    > Cette mise en correspondance fait référence aux métadonnées de l'application connectée sélectionnée. Si une mise en correspondance fait référence à la configuration des métadonnées et à l'application connectée en même temps, les métadonnées de l'application connectée sont utilisées.

3. Sélectionnez **Concepteur**.
4. Sélectionnez **Concepteur**.
5. Dans l'arborescence, sélectionnez **Dynamics 365 for Operations \> Enregistrements de table**.
6. Sélectionnez **Ajoutez racine**.
7. Dans le champ **Table**, saisissez ou sélectionnez une valeur.

    > [!NOTE]
    > À ce stade, plus de deux tables d'application sont présentées, car cette mise en correspondance utilise toutes les métadonnées de l'application connectée qui lui a été affectée.

8. Sélectionnez **Annuler**.
9. Sélectionnez **Valider**.

Vous avez lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l'aide des informations des métadonnées de l'application connectée qui a été affectée à cette mise en correspondance.

Lorsque vous devez évaluer cette mise en correspondance de modèle à l'aide de métadonnées d'une version différente de l'application, enregistrez une autre application connectée, affectez-la à cette mise en correspondance de modèle et validez-la par rapport aux nouvelles métadonnées.

## <a name="additional-resources"></a>Ressources supplémentaires

Sinon, vous pouvez lire le guide de tâche **Préparer les métadonnées d'application à utiliser dans RCS** dans Finance and Operations, ainsi que les guides de tâche **Accéder aux métadonnées d'application à l'aide d'une configuration de gestion des états électroniques** et **Accéder aux métadonnées d'application à l'aide des applications connectées** dans RCS. Ces guides de tâche peuvent être téléchargés à partir de la page [Guides de tâches de la génération d'états électroniques pour Dynamics 365 for Finance and Operations 8,1](https://go.microsoft.com/fwlink/?linkid=2082739).
