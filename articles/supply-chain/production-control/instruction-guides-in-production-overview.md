---
title: Fournir des guides de réalité mixte aux collaborateurs de la production
description: Cette rubrique explique comment intégrer le module de gestion de production dans Microsoft Dynamics 365 Supply Chain Management avec Dynamics 365 Guides.
author: cabeln
manager: tfehr
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: d8c2da17d4e3df37c55844f0aad00f883725f741
ms.sourcegitcommit: c55fecae96b4bb27bc313ba10a97eddb9c91350a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "3989272"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Fournir des guides de réalité mixte aux collaborateurs de la production

Les collaborateurs des processus de production bénéficieront d'instructions pertinentes fournies au bon moment dans le cadre de leur travail. Les *Instructions* s'appliquent dans plusieurs domaines de travail, notamment : l'assembly, le service, les opérations, la certification et la sécurité. Dans toutes ces fonctions commerciales de base, des instructions de formation continue peuvent aider les collaborateurs à accomplir plus et à mieux travailler.

## <a name="introduction"></a>Introduction

Vous pouvez fournir des instructions de différentes manières. Un système efficace et prêt à l'emploi qui utilise [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).

Dynamics 365 Guides peut aider à responsabiliser vos employés grâce à un apprentissage pratique. Vous pouvez définir des processus standardisés avec des instructions détaillées qui guident vos employés vers les outils et les pièces dont ils ont besoin et leur montrent comment utiliser ces outils dans des situations de travail réelles.

Vous pouvez joindre des guides à divers aspects du contrôle de production, notamment :

- [Ressources](#resources)
- [Groupes de ressources](#resource-groups)
- [Produits lancés](#released-products)
- [Formules](#formulas)
- [Versions de formule](#formula-versions)
- [Nomenclatures](#bom)
- [Versions de nomenclature](#bom-versions)
- [Gammes](#routes)
- [Versions de gamme](#route-versions)
- [Relations de l'opération de gamme](#route-operation-relations)

> [!NOTE]
> Vous pouvez également joindre des guides à la Gestion des actifs. Pour plus d’informations sur cette option, voir [Intégrer Dynamics 365 Supply Chain Management (Gestion des actifs) avec Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).

Lorsqu'un travailleur de première ligne choisit un travail dans l'atelier via Supply Chain Management, le travailleur peut voir [les guides pertinents](#logic) sur le bon de travail. Lorsque le travailleur choisit un guide spécifique, un code QR pour ce guide s'affiche à l'écran. Le travailleur utilise alors son HoloLens pour scanner le code QR, qui lance les guides et affiche les instructions requises.

Les sous-sections suivantes décrivent quelques scénarios sélectionnés dans lesquels les entreprises de tous les secteurs peuvent voir la plus grande valeur lors de l'utilisation des guides pour présenter des instructions de fabrication.

### <a name="assembly"></a>Assembly

![Utiliser les guides dans les tâches d'assemblage](media/instruction-guides-hero-assembly.png "Utiliser les guides dans les tâches de service")

Les instructions relatives aux opérations d'assemblage montrent aux travailleurs les outils et les pièces dont ils ont besoin et comment les utiliser dans des situations de travail réelles.

Les responsables de production peuvent créer et attribuer des guides, par exemple pour [itinéraires de production](routes-operations.md),[relations opérationnelles](routes-operations.md#operation-relations) ou [nomenclatures](bill-of-material-bom.md). Les travailleurs trouveront les instructions pertinentes sur l'expérience d'exploitation respective dans l'atelier.

### <a name="service"></a>Service

![Utiliser les guides dans les tâches de service](media/instruction-guides-hero-service.png "Utiliser les guides dans les tâches de service")

Dotez les techniciens d'instructions guidées sur le chantier, éliminant ainsi le besoin de planifier des visites supplémentaires.

Les gestionnaires de services peuvent attribuer des guides, par exemple, à des [produits](../../commerce/product.md) spécifiques qui parcourent les routines d’évaluation de la qualité.

### <a name="quality"></a>Qualité

![Utiliser les guides dans les tâches d'assurance qualité](media/instruction-guides-hero-quality.png "Utiliser les guides dans les tâches d'assurance qualité")

Déployez de nouveaux processus et assurez une cohérence accrue en transformant les connaissances des employés en un outil reproductible.

Les gestionnaires de l'assurance qualité peuvent attribuer des guides, par exemple, à des [produits](../../commerce/product.md) spécifiques qui parcourent les routines d’évaluation de la qualité.

### <a name="certifications"></a>Certifications

![Utiliser les guides pour les tâches liées à la certification](media/instruction-guides-hero-certification.png "Utiliser les guides pour les tâches liées à la certification")

Assurez-vous que chaque employé respecte des normes élevées en identifiant rapidement qui a besoin d'aide et où.

### <a name="safety"></a>Sécurité

![Utiliser les guides dans les consignes de sécurité au travail](media/instruction-guides-hero-safety.png "Utiliser les guides dans les consignes de sécurité au travail")

Fournissez des instructions qui parcourent les procédures dangereuses virtuellement avant toute tentative dans l'environnement physique. Avec une approche de réalité mixte, les travailleurs peuvent expérimenter virtuellement des procédures dangereuses.

Les responsables de production peuvent fournir des instructions de manutention dédiées pour la manipulation de matières dangereuses ou les procédures de manutention délicates en attribuant des instructions aux [articles de produit](../../commerce/product.md),[itinéraires](routes-operations.md) et aux [opérations ](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Démarrer avec les instructions et les guides

Pour activer les instructions dans les processus de production, Supply Chain Management fournit une intégration prête à l'emploi avec Dynamics 365 Guides. Une instance d'application sous licence et installée des Guides est requise pour créer, maintenir et attribuer des instructions de réalité mixte aux ressources de production et au travail.

### <a name="prerequisites"></a>Conditions préalables

Pour utiliser cette fonction, votre système doit inclure les éléments suivants :

- Dynamics 365 Supply Chain Management version 10.0.15 ou version ultérieure
- [Double écriture](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) pour les applications Supply Chain Management.
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 ou version ultérieure

### <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Pour rendre la fonction disponible sur votre système, vous devez activer ses clés de configuration. Vous ne devez le faire qu'une seule fois. Pour ce faire, un administrateur doit effectuer les opérations suivantes :

1. Mettrez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Développer la section **Réalité mixte** puis sélectionner la case à cocher **Guide de réalité mixte**.
1. Développer la section **Gestion de la production** puis sélectionner la case à cocher **Instructions de production**.
1. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Configurer la façon dont les guides apparaissent dans l'atelier

Pour configurer l'affichage des guides dans l'atelier, accédez à **Réalité mixte \> Dynamics 365 Guides \> Configurer l'intégration des guides**.

![Configurer l'intégration des guides pour la fabrication](media/instruction-guides-configure-integration.png "Configurer l'intégration des guides pour la fabrication")

Définisse les champs suivants :

- **Sous-domaine d'environnement CDS** - Ce champ doit déjà afficher une valeur. Ce champ contient le sous-domaine pour l'environnement Common Data Service dans lequel vous créez vos guides. Le sous-domaine est la première partie de l'URL et porte généralement le nom de votre organisation. Par exemple, si votre URL Common Data Service est « contoso.crm4.dynamics.com », vous devez entrer *contoso* ici. Cette valeur est utilisée pour composer les adresses de vos guides et sera encodée dans les codes QR.
- **Taille du code QR** - Définissez la taille du code QR rendu. Nous vous recommandons de choisir une taille qui remplira la majeure partie de votre écran, mais pas plus. *15* est généralement une valeur adaptée.
- **Niveau de correction d'erreur de code QR** - Définissez la granularité du code QR. Une granularité plus élevée peut aider à augmenter la fiabilité du code, mais votre **Taille de code QR** doit être suffisamment élévée pour prendre en charge le niveau de détail requis par le niveau de correction sélectionné.


> [!TIP]
> - Les tailles de codes QR qui sont trop élevées pour votre écran prendront un peu plus de temps à s'afficher, puis seront réduites pour s'adapter à votre écran. Cela ne présente aucun avantage.
> - Des tailles de code QR trop faibles peuvent réduire la capacité de HoloLens pour la lecture correcte du code dans certains environnements.
> - Nous vous recommandons de tester les paramètres de chaque appareil qui affichera les codes QR pour les utilisateurs HoloLens. Choisissez des paramètres offrant une lisibilité suffisante dans votre environnement d'atelier.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Obtenir un aperçu de toutes les affectations de guide

Utilisez la page **Tous les guides** pour voir la liste de tous les guides disponibles dans votre organisation et toutes les affectations à vos processus et ressources de production. Pour l'ouvrir, accédez à **Réalité mixte \> Guides \> Tous les guides**. La liste dans la partie supérieure montre tous les guides disponibles et vous pouvez utiliser le champ ici pour filtrer la liste. La liste dans la partie inférieure montre toutes les affectations de guide et fournit une barre d'outils pour les gérer.

![Gérer les guides](media/instruction-guides-allguides.png "Gérer les guides")

Les sections suivantes décrivent les types d'objets auxquels vous pouvez attribuer des guides. Chaque guide attribué fournit des instructions qui sont automatiquement liées aux travaux de production respectifs et qui seront disponibles dans l'atelier.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Associer un guide à une ressource

Ajouter un guide à une [ressource](operations-resources.md) pour proposer le guide dans le cadre de travaux de production pertinents.

### <a name="typical-scenario-using-resources"></a>Scénario typique utilisant des ressources

Par exemple, vous pouvez joindre un guide contenant des instructions générales de sécurité ou de gestion de la machine à une ressource de type machine. Ensuite, le Guide sera disponible pour chaque tâche réalisée sur la machine.

### <a name="add-a-guide-to-a-resource"></a>Ajouter un guide à une ressource

Pour ajouter un guide à une ressource :

1. Accédez à **Contrôle de la production \> Configuration \> Ressources \> Ressources**.
1. Depuis le volet de liste, sélectionnez la ressource à laquelle vous souhaitez attribuer un guide.
1. Développez le raccourci **Guides associés**.
1. Sélectionnez **Ajouter** dans la barre d'outils **Guides associés**. Une nouvelle ligne est ajoutée à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer. Si vous avez un grand nombre de guides, vous pouvez filtrer la liste pour trouver celui que vous recherchez.
    ![Gérer les guides](media/instruction-guides-allguides.png "Gérer les guides")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Associer un guide à un groupe de ressources

Vous pouvez ajouter un guide à des [groupes de ressources](tasks/define-discrete-manufacturing-resource-group.md) si vous les utilisez pour gérer des groupes de machines, des lignes de production ou des cellules de travail.

### <a name="typical-scenarios-using-resource-groups"></a>Scénarios typiques utilisant des groupes de ressources

**Exemple 1 :** Vous avez défini un groupe de ressources pour plusieurs machines du même modèle. Au lieu d'affecter le guide d'instructions de manipulation approprié pour le modèle de machine à chaque ressource appropriée, vous pouvez à la place affecter le guide au groupe de ressources qui reflète ce modèle de machine.

**Exemple 2 :** Vous avez défini un groupe de ressources pour une cellule de travail qui contient différentes machines et vous disposez d'un guide qui fournit des instructions générales sur la façon de gérer la cellule de travail. Le Guide s'applique à toute activité de production dans cette cellule de travail.

### <a name="add-a-guide-to-a-resource-group"></a>Ajouter un guide à un groupe de ressources

Pour ajouter un guide à un groupe de ressources :

1. Accédez à **Contrôle de la production \> Configuration \> Ressources \> Groupe de ressources**.
1. Depuis le volet de liste, sélectionnez le groupe de ressources auquel vous souhaitez attribuer un guide.
1. Développez le raccourci **Guides associés**.
1. Sélectionnez **Ajouter** dans la barre d'outils **Guides associés**. Une nouvelle ligne est ajoutée à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer. Si vous avez un grand nombre de guides, vous pouvez filtrer la liste pour trouver celui que vous recherchez.
    ![Ajouter un guide à un groupe de ressources](media/instruction-guides-resourcegroup.png "Ajouter un guide à un groupe de ressources")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Associer un guide à un produit lancé

Vous pouvez ajouter un guide à un [produit lancé](../pim/tasks/create-released-product-single-company.md).

### <a name="typical-scenario-using-released-products"></a>Scénario typique utilisant des produits lancés

Les guides au niveau du produit aident les travailleurs de l'atelier avec des instructions relatives à l'utilisation ou à la manipulation d'un produit ou d'un article lancé.

### <a name="add-a-guide-to-a-released-product"></a>Ajouter un guide à un produit lancé

Pour ajouter un guide à un produit lancé :

1. Allez à **Gestion des informations de production \> Produits \> Produits lancés**.
1. Ouvrez le produit auquel vous souhaitez attribuer un guide.
1. Dans le volet Action, ouvrez l'onglet **Ingénieur** et, dans le groupe **Vue**, sélectionnez **Guides associés**.
1. La page **Guides associés** s'ouvre pour votre produit sélectionné.
1. Sélectionnez **Ajouter** dans le volet Action pour ajouter une nouvelle ligne à la grille. 
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à un produit lancé](media/instruction-guides-ReleasedProduct-AddGuides.png "Ajouter un guide à un produit lancé")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Associer un guide à une formule

Vous pouvez ajouter un guide à une [formule](bill-of-material-bom.md#formulas-co-products-and-by-products).

### <a name="typical-scenario-using-formulas"></a>Scénario typique utilisant des formules
  
Les guides au niveau des formules fournissent aux travailleurs de l'atelier des instructions de manipulation guidées dans le contexte d'une formule ou d'une recette. Les guides peuvent également être affectés à des versions d'une formule.

> [!NOTE]
> Vous pouvez affecter des conseils pertinents pour les processus de production basés sur une formule à une gamme, une version de gamme ou des relations d'opération de gamme.  

> Les guides ne peuvent actuellement pas être associés à des lignes de formule individuelles.

### <a name="add-a-guide-to-a-formula"></a>Ajouter un guide à une formule

Pour ajouter un guide à une formule :

1. Accédez à **Gestion d'informations de production \> Nomenclatures et formules \> Formules**.
1. Ouvrez la formule à laquelle vous souhaitez attribuer un guide.
1. Ouvrez l'onglet **En-tête** au-dessus du raccourci supérieur.
1. Développez le raccourci **Guides associés**.
1. Sélectionnez **Ajouter** dans la barre d'outils **Guides associés**. Une nouvelle ligne est ajoutée à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à une formule](media/instruction-guides-Formula.png "Ajouter un guide à une formule")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Associer un guide à une version de formule

Vous pouvez ajouter un guide à une [version de formule](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-formula-versions"></a>Scénario typique utilisant des versions de formule

Les guides liés à une version individuelle de formule fournissent aux travailleurs de l'atelier des instructions qui expliquent la production de cette version de la recette de formule.

> [!TIP]
> Vous pouvez affecter des conseils pertinents pour les processus de production basés sur cette versions de formule à une gamme, une version de gamme ou des relations d'opération de gamme.  

> [!NOTE]
> Les guides ne peuvent actuellement pas être associés à des lignes de formule individuelles.

### <a name="add-a-guide-to-a-formula-version"></a>Ajouter un guide à une version de formule

Pour ajouter un guide à une version de formule :

1. Accédez à **Gestion d'informations de production \> Nomenclatures et formules \> Formules**.
1. Ouvrez la formule qui inclut une version à laquelle vous souhaitez affecter un guide.
1. Ouvrez l'onglet **En-tête** au-dessus du raccourci supérieur.
1. Sur le raccourci **Versions de formule**, sélectionnez la version à laquelle vous souhaitez affecter un guide.
1. Dans la barre d'outils **Versions de formule**, sélectionnez **Guides associés**.
    ![Ouvrez les guides associés à une version de formule sélectionnée](media/instruction-guides-FormulaVersion.png "Ouvrez les guides associés à une version de formule sélectionnée")
1. La page **Guides associés** s'ouvre pour votre version de formule.
1. Sélectionnez **Ajouter** dans le volet Action pour ajouter une nouvelle ligne à la grille. 
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à une version de formule](media/instruction-guides-FormulaVersionAddGuide.png "Ajouter un guide à une version de formule")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Associer un guide à une nomenclature

Vous pouvez ajouter un guide à une [nomenclature](bill-of-material-bom.md).

### <a name="typical-scenario-using-bills-of-materials"></a>Scénario typique utilisant des nomenclatures

Les guides liés à une nomenclature fournissent aux travailleurs de l'atelier des instructions qui expliquent comment préparer et manipuler le matériel à partir d'une nomenclature. Les guides peuvent également être affectés à des versions d'une nomenclature.

> [!NOTE]
> Les guides ne peuvent actuellement pas être associés à des lignes de nomenclature.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Ajouter un guide à une nomenclature

Pour ajouter un guide à une nomenclature :

1. Accédez à **Gestion des informations de production \> Nomenclatures et formules \> Nomenclatures**.
1. Ouvrez la nomenclature à laquelle vous souhaitez affecter un guide.
1. Ouvrez l'onglet **En-tête** au-dessus du raccourci supérieur.
1. Développez le raccourci **Guides associés**.
1. Sélectionnez **Ajouter** dans la barre d'outils **Guides associés**. Une nouvelle ligne est ajoutée à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à une nomenclature](media/instruction-guides-BOM.png "Ajouter un guide à une nomenclature")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Associer un guide à une version de nomenclature

Vous pouvez ajouter un guide à une [version de nomenclature](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Scénario typique utilisant des versions de nomenclatures

Les guides liés à une version de nomenclature individuelle fournissent aux travailleurs de l'atelier des instructions qui expliquent comment préparer et gérer le matériel pour une version d'une nomenclature différente de la nomenclature générique ou d'autres versions de celle-ci.

> [!NOTE]
> Les guides ne peuvent actuellement pas être associés à des lignes de nomenclature.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Ajouter un guide à une version de nomenclature

Pour ajouter un guide à une version de nomenclature :

1. Accédez à **Gestion des informations de production \> Nomenclatures et formules \> Nomenclatures**.
1. Ouvrez la nomenclature qui inclut une version à laquelle vous souhaitez affecter un guide.
1. Ouvrez l'onglet **En-tête** au-dessus du raccourci supérieur.
1. Sur le raccourci **Versions de nomenclature**, sélectionnez la version à laquelle vous souhaitez affecter un guide.
1. Dans la barre d'outils **Versions de nomenclature**, sélectionnez **Guides associés**.
    ![Ouvrez les guides associés à une version de nomenclature sélectionnée](media/instruction-guides-BOMVersion.png "Ouvrez les guides associés à une version de nomenclature sélectionnée")
1. La page **Guides associés** s'ouvre pour votre version de nomenclature.
1. Sélectionnez **Ajouter** dans le volet Action pour ajouter une nouvelle ligne à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à une version de nomenclature](media/instruction-guides-BOMVersionAddGuide.png "Ajouter un guide à une version de nomenclature")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Associer un guide à une gamme

Vous pouvez ajouter un guide à une [gamme](routes-operations.md).

### <a name="typical-scenario-using-routes"></a>Scénario typique utilisant des gammes

Les gammes sont généralement utilisées pour spécifier comment un certain produit lancé doit être produit sur la base d'une nomenclature ou d'une version de nomenclature et avec un ensemble de ressources ou de groupes de ressources.

Affectez un guide à une gamme pour fournir des instructions étape par étape pour le processus de production respectif.

### <a name="add-a-guide-to-a-route"></a>Ajouter un guide à une gamme

Pour ajouter un guide à une gamme :

1. Accédez à **Contrôle de production \> Toutes les gammes**.
1. Ouvrez la gamme à laquelle vous souhaitez affecter un guide.
1. Développez le raccourci **Guides associés**.
1. Sélectionnez **Ajouter** dans la barre d'outils **Guides associés**. Une nouvelle ligne est ajoutée à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à une gamme](media/instruction-guides-Route.png "Ajouter un guide à une gamme")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Associer un guide à une version de gamme

Vous pouvez ajouter un guide à une [version de gamme](routes-operations.md#route-versions).

### <a name="typical-scenario-using-route-versions"></a>Scénario typique utilisant des versions de gamme

Les versions de gamme sont généralement utilisées pour spécifier des variantes de processus de production basées sur une gamme existante. Vous pouvez affecter différents guides à chaque version de gamme.

### <a name="add-a-guide-to-a-route-version"></a>Ajouter un guide à une version de gamme

Pour ajouter un guide à une version de gamme :

1. Accédez à **Contrôle de production \> Toutes les gammes**.
1. Ouvrez la gamme à laquelle vous souhaitez affecter un guide.
1. Sur le raccourci **Versions**, sélectionnez la version à laquelle vous souhaitez affecter un guide.
1. Dans la barre d'outils **Versions**, sélectionnez **Guides associés**.
    ![Ouvrez les guides associés à une version de gamme sélectionnée](media/instruction-guides-RouteVersion.png "Ouvrez les guides associés à une version de gamme sélectionnée")
1. La page **Guides associés** s'ouvre pour votre version de nomenclature.
1. Sélectionnez **Ajouter** dans le volet Action pour ajouter une nouvelle ligne à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer.
    ![Ajouter un guide à une version de gamme](media/instruction-guides-RouteVersionAddGuide.png "Ajouter un guide à une version de gamme")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Associer un guide à une relation d'opération de gamme

Vous pouvez ajouter un guide à une [relation d'opération de gamme](routes-operations.md#operation-relations).

### <a name="typical-scenario-using-route-operation-relations"></a>Scénario typique utilisant des relations d'opération de gamme

Les relations d'opération sont le moyen le plus spécifique d'ajouter des conseils à un processus produit et à ses opérations associées. Vous pouvez spécifier des conseils guidage pour chaque opération d'une gamme et spécifier des conseils différents pour tout type de contexte de relation spécifié pour une gamme, par exemple pour des éléments spécifiques, des configurations, etc. Vous pouvez également spécifier à quelles étapes de l'opération les conseils s'appliquent (telles que la configuration, la mise en file d'attente, le processus ou le transport).

> [!NOTE]
> Si vous spécifiez des conseils pour plusieurs relations d'opération d'une gamme, parmi ces guides, seul le guide de la relation la plus spécifique sera affiché dans l'atelier pour le travail généré.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Ajouter un guide à une relation d'opération de gamme

Pour ajouter un guide à une relation d'opération de gamme :

1. Accédez à **Contrôle de production \> Toutes les gammes**.
1. Ouvrez la gamme à laquelle vous souhaitez affecter un guide.
1. Dans le volet Action, ouvrez l'onglet **Gamme** et, dans le groupe **Gérer**, sélectionnez **Détails de gamme**.
1. La page **Détails de gamme** s'ouvre pour votre gamme sélectionnée.
1. Dans la grille supérieure, sélectionnez l'opération pour laquelle vous souhaitez fournir des conseils.
1. Dans la grille du bas, sélectionnez une relation spécifique (ou la relation générique **Tout**).
    ![Sélectionner une opération puis une relation](media/instruction-guides-RouteOperationRelation.png "Sélectionner une opération puis une relation")
1. Au-dessus de la grille inférieure, ouvrez l'onglet **Guides associés**.  ![L'onglet Guides associés](media/instruction-guides-RouteOperationRelation-AddGuide.png "L'onglet Guides associés")
1. Sélectionnez **Ajouter** à partir de la barre d'outils en haut de la grille inférieure pour ajouter une nouvelle ligne à la grille.
1. Pour la nouvelle ligne, utilisez la liste déroulante dans la colonne **Nom** pour choisir le guide que vous souhaitez attribuer. Dans le reste de la ligne, cochez la case de chaque contexte dans lequel le Guide sélectionné doit être disponible.

> [!NOTE]
> Vous pouvez ajouter un ou plusieurs guides pour chaque étape de chaque opération.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Sélectionnez des guides dans l'interface d'exécution de l'atelier

Lorsqu'un collaborateur ouvre une liste de travaux sur l'interface d'exécution de l'atelier, Supply Chain Management trouve les guides appropriés pour les travaux affichés. Utilisez le bouton **Guides** pour afficher les guides pertinents.

![Bouton Guides dans l'interface d'exécution de l'atelier](media/instruction-guides-Shopfloor1.png "Bouton Guides dans l'interface d'exécution de l'atelier")

Ensuite, placez un HoloLens et accédez au guide respectif en jetant un coup d'œil au code QR et en activant le guide respectif.

![Code QR pour accéder aux guides à l'aide d'un HoloLens](media/instruction-guides-Shopfloor2.png "Code QR pour accéder aux guides à l'aide d'un HoloLens")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Résoudre la logique de sélection des guides

Vous pouvez ajouter des guides aux données de production suivantes :

- [Ressources](#resources)
- [Groupes de ressources](#resource-groups)
- [Produits lancés](#released-products)
- [Formules](#formulas)
- [Versions de formule](#formula-versions)
- [Nomenclatures](#bom)
- [Versions de nomenclature](#bom-versions)
- [Gammes](#routes)
- [Versions de gamme](#route-versions)
- [Relations de l'opération de gamme](#route-operation-relations)

Lorsque Supply Chain Management génère les tâches pour l'atelier de production, il collecte les guides pertinents à partir de ces sources. Prenez note des règles importantes suivantes.

- Si vous associez une version de nomenclature ou une version de formule à une gamme ou à un ordre de fabrication, tous les guides associés à cette version, ainsi que les guides associés à la nomenclature parent ou à la formule de cette version, seront affichés sur la tâche.
- Si vous associez une version de gamme à un ordre de fabrication, tous les guides associés à cette version, ainsi que les guides associés à la gamme parente de cette version, seront affichés sur la tâche.
- Si vous définissez plusieurs relations d'opération de gamme qui incluent la relation *Tout* et attribuez des guides à celles-ci, seuls les guides de la relation la plus spécifique seront affichés pour le travail.  

![Diagramme sur la résolution des guides pertinents](media/instruction-guides-Resolve.png "Diagramme sur la résolution des guides pertinents")
