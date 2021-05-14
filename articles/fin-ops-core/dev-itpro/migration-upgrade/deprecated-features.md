---
title: Fonctions supprimées ou obsolètes dans les versions précédentes
description: Cette rubrique décrit les fonctionnalités qui ont été supprimées ou dont la suppression de Dynamics 365 for Finance and Operations était planifiée et les versions précédentes.
author: sericks007
ms.date: 02/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce49835f167881417000b066fd4a351d26ca0909
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921421"
---
# <a name="removed-or-deprecated-features-in-previous-releases"></a>Fonctionnalités supprimées ou obsolètes dans les versions précédentes

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!IMPORTANT]
> Cette rubrique n’est plus mise à jour. Pour afficher une liste actuelle des fonctionnalités qui ont été supprimées des applications Finance and Operations ou qui sont obsolètes, recherchez le contenu **« Fonctionnalités supprimées ou obsolètes »** qui est lié à l’application que vous utilisez.

Cette rubrique décrit les fonctionnalités qui ont été supprimées de Dynamics 365 for Finance and Operations ou qui sont obsolètes ainsi que les versions précédentes de ce produit.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](/dynamics/s-e/global/axtechrefrep_61). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="finance-1007-with-platform-update-31"></a>Finance 10.0.7 avec Platform update 31

### <a name="chinese-voucher-types-without-account-groups-selection"></a>Types de documents chinois sans sélection de groupes de comptes
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par la fonctionnalité avec sélection de groupes de comptes. |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Application |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : À partir du 1er décembre 2020, nous prévoyons de ne plus prendre en charge les types de documents chinois paramétrés sans sélection de groupes de comptes. Pour plus d’informations sur la nouvelle conception de fonctionnalité dans Nouveautés de la version 10.0.7 |

## <a name="finance-and-operations-1006-with-platform-update-30"></a>Finance and Operations 10.0.6 avec Platform update 30


### <a name="dimensionhashgethashstr-_message"></a>DimensionHash.getHash(str _message)

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Windows rend obsolète l’utilisation de SHA1, comme documenté dans [Application Windows des certificats SHA1](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Application |
| **Option de déploiement**              | Tous |
| **État**                         | Déconseillé : d’ici le 1er avril 2020, les développeurs doivent utiliser les API de plateforme disponibles dans la classe **HasFunction**. |

### <a name="hashcomputesha1hashstring-message"></a>Hash.ComputeSHA1Hash(string message)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Windows rend obsolète l’utilisation de SHA1, comme documenté dans [Application Windows des certificats SHA1](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Plateforme |
| **Option de déploiement**              | Tous |
| **État**                         | Déconseillé : d’ici le 1er avril 2020, les développeurs doivent utiliser les API de plateforme disponibles dans la classe **HasFunction**. |


### <a name="formdatetimecontrolsetutcstring"></a>FormDateTimeControl.setUtcString()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous supprimons la méthode **setUtcString()**, car une meilleure méthode de remplacement est disponible. |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Plateforme |
| **Option de déploiement**              | Tous |
| **État**                         | Abandon : Avant le 1er octobre 2020, nous prévoyons de ne plus prendre en charge la méthode  **setUtcString ()**. Les développeurs doivent utiliser la méthode **setUtcDateTime ()** à la place. |

### <a name="blacklist-report-it--feature-reference-it-00001"></a>État de la liste rouge (IT) – Référence de la fonctionnalité IT-00001

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pas autorisé légalement. |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Localisation italienne |
| **Option de déploiement**              | Tous |
| **État**                         | Abandon : d’ici au 1er octobre 2020, nous prévoyons de ne plus prendre en charge la fonction **État de la liste rouge (IT) – Référence de la fonctionnalité IT-00001**. |

### <a name="domestic-tax-report--feature-reference-it-00003"></a>Déclarations de taxe domestique – Référence de la fonctionnalité IT-00003

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pas autorisé légalement. |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Localisation italienne |
| **Option de déploiement**              | Tous |
| **État**                         | Abandon : d’ici au 1er octobre 2020, nous prévoyons de ne plus prendre en charge la fonction **État de taxe domestique – Référence de la fonctionnalité IT-00003**. |


## <a name="finance-and-operations-1005-with-platform-update-29"></a>Finance and Operations 10.0.5 avec Platform update 29

### <a name="us-payroll-tax-updates"></a>Mises à jour de l’impôt sur les salaires aux États-Unis

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous retirons les mises à jour fiscales pour la fonctionnalité de paie des États-Unis en raison d’une faible utilisation et des fonctionnalités améliorées qui sont désormais offertes via des intégrations stratégiques.  |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Paie |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à compter du 31 juillet 2024, nous prévoyons de ne plus fournir de mises à jour fiscales aux clients concernés par les salaires aux États-Unis. La fonctionnalité restera dans le produit, mais les améliorations ne la maintiendront plus à jour et les défauts du produit seront évalués au cas par cas. |

>[!NOTE]
> Cela représente un changement par rapport à la date d’arrêt initiale du 1er octobre 2021. Pour plus d’informations, voir [Retrait des mises à jour fiscales pour la fonctionnalité Paie États-Unis dans Microsoft Dynamics 365 for Finance and Operations](https://aka.ms/financepayrollfaq).


### <a name="data-management-staging-clean-up"></a>Nettoyage de la gestion des données
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Ne répond pas aux exigences de base requises pour la planification du nettoyage périodique. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, la fonctionnalité de nettoyage de l’historique des tâches est en cours d’ajout pour répondre aux scénarios de manière globale. |
| **Zones de produit affectées**         | Gestion des données |
| **Option de déploiement**              | Tous  |
| **État**                         | Obsolète : le délai cible pour la suppression de la fonctionnalité est Décembre 2020. |

## <a name="finance-and-operations-1004-with-platform-update-28"></a>Finance and Operations 10.0.4 avec Platform update 28

### <a name="france-fec-accounting-data-export-in-xml"></a>France : Exportation des données comptables FEC au format XML

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par le format TXT, **Fichier d’audit FEC français** est disponible via **Comptabilité générale** \> **Tâches périodiques** \> **Exportation de données**.
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Comptabilité |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète. Le délai cible pour la suppression de la fonctionnalité est juillet 2020. |


### <a name="legacy-navigation-bar"></a>Barre de navigation héritée

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Alignement d’en-tête avec d’autres produits Dynamics et Office. Pour plus de détails, voir [Barre de navigation mise à jour qui s’aligne à présent avec l’en-tête Bureau](/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar).
| **Remplacé par une autre fonctionnalité ?**   | Depuis Platform update 24, une barre de navigation remodelée avec une recherche des fonctionnalités a été introduite. |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : À compter d’avril 2020, la barre de navigation héritée ne sera plus disponible. Jusque là, les clients peuvent rétablir la barre de navigation héritée via la page **Options de performances du client**. |


## <a name="finance-and-operations-1002-with-platform-update-26"></a>Finance and Operations 10.0.2 avec Platform update 26


### <a name="legacy-default-action-behavior"></a>Comportement hérité des actions par défaut

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le comportement hérité pour les actions par défaut dans les grilles a pour effet qu’une colonne inattendue comporte le lien d’action par défaut après la réorganisation des colonnes de grille suite à la personnalisation. La nouvelle fonctionnalité d’action par défaut rémanente corrige ce problème. Pour plus de détails, voir [Actions par défaut rémanentes dans les grilles](/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **Remplacé par une autre fonctionnalité ?**   | À compter de Platform update 21, la fonctionnalité des « actions par défaut rémanentes » a été introduite. Cette fonction peut être activée dans la page **Options de performances du client**. |
| **Zones de produit affectées**         | Grilles dans le client Web |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à compter d’avril 2020, les actions par défaut rémanentes sont le comportement par défaut, sans mécanisme de rétablissement au comportement antérieur. |

### <a name="legacy-is-one-of-filtering-experience"></a>L’ancien comportement est l’expérience de filtrage « est l’un de »

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’expérience de filtrage « Est l’un de » a subi une refonte dans la Platform update 22. Le projet est qu’elle soit finalement la seule expérience de filtrage « Est l’un de ». |
| **Remplacé par une autre fonctionnalité ?**   | Depuis la Platform update 22, une expérience améliorée Platform update 22 est disponible dans la page **Options de performances du client**. Pour plus d’informations, voir [Optimisation de l’expérience de filtrage « Est l’un de »](/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à compter d’avril 2020, l’expérience de filtrage « Est l’un de » améliorée est le comportement par défaut, sans mécanisme de rétablissement au comportement antérieur. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Paramètre pour activer les commandes client avec plusieurs sources de financement de contrat de projet
La prise en charge de la création de commandes client basées sur le projet où le projet inclut plusieurs sources de financement est activée à l’aide du paramètre **Paramètres de gestion de projets** défini sur **Autoriser les commandes client pour les projets avec plusieurs sources de financement**. Par défaut, ce paramètre n’est pas activé. 

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonctionnalité demeure activée après la suppression du paramètre. |
| **Remplacé par une autre fonctionnalité ?**   | N° La fonctionnalité de prise en charge des commandes client basée sur un projet avec plusieurs sources de financement sera toujours activée.   |
| **Zones de produit affectées**         |Le paramètre **Autoriser les commandes client pour les projets avec plusieurs sources de financement** sera supprimé. Les méthodes suivantes seront modifiées lorsque le paramètre sera supprimé : méthode **ctrlSalesOrderTable** dans la classe **ProjStatusType**, méthode **validate** pour le champ **ProjId**, et méthode **run** dans l’écran **SalescreateOrder**. Les méthodes suivantes seront abandonnées lorsque le paramètre sera supprimé : **IsSalesOrderAllowedForMultipleFundingSources** dans le fichier de table **ProjTable**, méthode **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** dans le fichier de table **ProjTable**, champ de données **AllowSalesOrdersForMultipleFundingSources** dans l’écran **ProjParameters** et les fichiers **ProjParameterEntity**, méthode privée **IsAssociatedToMultipleFundingSourcesContract** dans le fichier de table **ProjTable**. |
| **Option de déploiement**              | Tous  |
| **État**                         | L’abandon est prévu pour la vague de publication d’avril 2020. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>États de workflow hérités pour le statut du suivi et des instances

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les états de workflow hérités pour le statut du suivi et des instances sont obsolètes car ils ne sont plus référencés dans la navigation. Les noms d’état sont WorkflowWorkflowInstanceByStatusReport et WorkflowWorkflowTrackingReport. |
| **Remplacé par une autre fonctionnalité ?**   | L’écran Historique du workflow peut être utilisé à la place. |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : le délai cible pour la suppression de la fonctionnalité est avril 2020. |

## <a name="finance-and-operations-1001-with-platform-update-25"></a>Finance and Operations 10.0.1 avec Platform update 25

### <a name="deprecated-apis-and-potential-breaking-changes"></a>API obsolètes et dernières modifications potentielles


#### <a name="deriving-from-internal-classes-is-deprecated"></a>Abandon de la dérivation depuis les classes internes

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Dans les versions antérieures à Platform Update 25, il était possible de créer une classe ou une table à partir d’une classe/d’une table interne définie dans un autre package/module. Cela n’est pas une pratique de codage sûre. À partir de Platform update 25, le compilateur affiche un avertissement. |
| **Remplacé par une autre fonctionnalité ?**   | L’avertissement du compilateur sera remplacé par une erreur dans Platform update 26. Cette modification est rétrocompatible lors de l’exécution. Autrement dit, Platform Update 25 ou une version ultérieure peut être déployée dans n’importe quel environnement de bac à sable (sandbox) ou de production sans avoir besoin de modifier le code personnalisé. Cette modification ne concerne que le développement et le temps de compilation.|
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : l’avertissement devient une erreur de compilation dans Platform update 26. |

#### <a name="overriding-internal-methods-is-deprecated"></a>Abandon des modes internes de remplacement

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Dans les versions antérieures à Platform Update 25, il était possible de remplacer une méthode interne dans une classe dérivée définie dans un autre package/module. Cela n’est pas une pratique de codage sûre. À partir de Platform update 25, le compilateur affiche un avertissement. |
| **Remplacé par une autre fonctionnalité ?**   | Cet avertissement sera remplacé par une erreur de compilation dans Platform Update 26. Cette modification est rétrocompatible lors de l’exécution. Autrement dit, Platform Update 25 ou une version ultérieure peut être déployée dans n’importe quel environnement de bac à sable (sandbox) ou de production sans avoir besoin de modifier le code personnalisé. Cette modification ne concerne que le développement et le temps de compilation. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : l’avertissement devient une erreur de compilation dans Platform update 26. |

## <a name="finance-and-operations-1000-with-platform-update-24"></a>Finance and Operations 10.0.0 avec Platform update 24

### <a name="renaming-released-products"></a>Renommer les produits lancés 
| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Lorsque vous utilisez la fonction **Renommer la clé principale** pour modifier l’ItemId d’un produit lancé, seules les références directes de clé étrangère sont mises à jour. Toutes les autres références au produit lancé, comme des ordres de fabrication, conserveront l’ancien ItemId. Par conséquent, il peut y avoir des données incohérentes qui risquent de bloquer les processus d’entreprise. |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Gestion des informations sur les produits |
| **Option de déploiement**              | Tout  |
| **État**                         | Supprimé à partir de Finance and Operations 10.0.0 avec platform update 24.|


## <a name="finance-and-operations-813-with-platform-update-23"></a>Finance and Operations 8.1.3 avec Platform update 23

### <a name="sql-server-reporting-services-reportviewer-control"></a>Contrôle ReportViewer des états SQL Server Reporting Services
Les clients peuvent utiliser l’action **Exporter** proposée par le contrôle intégré ReportViewer des états SQL Server Reporting Services (SSRS) pour télécharger les documents produits par les applications Finance and Operations. Cette présentation basée sur HTML de l’état offre aux utilisateurs un aperçu non paginé du document.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La nature non paginée de l’expérience d’aperçu HTML n’offre **pas** une fidélité par rapport aux documents physiques finalement produits par Finance and Operations. Comme le format PDF est entièrement pris en charge comme format standard des documents commerciaux, les utilisateurs peuvent bénéficier d’une expérience de visualisation moderne avec de meilleurs performances lors de la générations d’états d’application. |
| **Remplacé par une autre fonctionnalité ?**   | De même, le format PDF des documents est le format par défaut pour les états rendus par Finance and Operations.   |
| **Zones de produit affectées**         | Cette modification n’a **pas** d’impact sur les scénarios clients où les états sont distribués de manière électronique ou envoyés directement vers les imprimantes.    |
| **Option de déploiement**              | Tous  |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. La fonctionnalité de prévisualisation automatique des états d’application à l’aide d’une visionneuse PDF intégrée est prévue pour Platform Update de mai 2019. |

### <a name="client-kpi-controls"></a>Contrôles KPI client
Les indicateurs de performance clé intégrés (KPI) peuvent être modélisés dans Visual Studio par un développeur et personnalisés davantage par l’utilisateur final.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les contrôles client natifs utilisés pour définir les KPI sont peu utilisés par les clients et reposent sur un développeur afin de bénéficier d’ajout de mesures de suivi. |
| **Remplacé par une autre fonctionnalité ?**   | Le service PowerBI.com fournit des outils de première classe pour définir et gérer les KPI selon les données depuis des sources externes.  Dans un prochaine version, nous prévoyons de vous permettre d’intégrer des solutions hébergées sur PowerBI.com dans les espaces de travail de l’application.   |
| **Zones de produit affectées**         | Cette mise à jour empêche les développeurs d’introduire de nouveaux contrôles de KPI dans le concepteur Visual Studio.    |
| **Option de déploiement**              | Tous  |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>API obsolètes et dernières modifications à venir

#### <a name="field-groups-containing-invalid-field-references"></a>Groupes de champ contenant des références de champs non valides

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Il est possible pour les définitions de métadonnées de table d’avoir des groupes de champs contenant des références de champs non valides. En cas de déploiement, cela peut provoquer des erreurs d’exécution dans Financial Reporting et SQL Server Reporting Services (SSRS). Ce problème est actuellement catégorisé comme *avertissement du compilateur* plutôt que comme *erreur*, ce qui signifie que la création et le déploiement d’un pack déployable peuvent survenir sans corriger ce problème. Pour résoudre ce problème :<br><br>1. Supprimez la référence de champ non valide de la définition du groupe de champs de table.<br><br>2. Recompilez.<br><br>3. Veillez à ce que tous les avertissements ou toutes les erreurs soient traitées. |
| **Remplacé par une autre fonctionnalité ?**   | Cet avertissement du compilateur sera remplacé par une erreur de compilation dans une prochaine version. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : L’avertissement est une erreur de compilation avec les mises à jour de la plateforme pour la version 10.0.11 des applications Finance and Operations. |

#### <a name="complete-list"></a>Liste complète
Pour accéder à la liste complète des API en cours d’abandon, voir [Abandon des méthodes et des éléments de métadonnées](deprecation-deletion-apis.md).

## <a name="finance-and-operations-81-with-platform-update-20"></a>Finance and Operations 8.1 avec Platform update 20

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Règles de transfert par lots des écritures de compte de journal de comptabilité auxiliaire
Le mode de transfert synchrone n’est plus utilisé dans les paramètres de comptabilité.  Ce mode est remplacé par le mode asynchrone et le traitement par lots planifié uniquement, qui existent déjà comme options de transfert. Pour plus de détails, voir le blog [Paramètres de comptabilité – Règles de transfert des traitements par lots](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous supprimons l’option synchrone en raison de l’impact sur les performances du système. |
| **Remplacé par une autre fonctionnalité ?**   | Le mode asynchrone et le traitement par lots planifié sont les options à utiliser à la place du mode synchrone.   |
| **Zones de produit affectées**         | Comptabilité, Comptabilité fournisseur, Comptabilité client, Approvisionnement, Dépenses    |
| **Option de déploiement**              | Tous  |
| **État**                         | Abandon – Le délai cible pour la suppression de la fonctionnalité est la version 10.0.|

### <a name="electronic-reporting-for-russia"></a>Gestion des états électroniques pour la Russie
Fonction de configuration des formats de fichier .txt et .xml des déclarations. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par l’outil de gestion des états électroniques. |
| **Remplacé par une autre fonctionnalité ?**   | Oui. |
| **Zones de produit affectées**         | Comptabilité générale |
| **Option de déploiement**              | Tout |
| **État**                         | Supprimé à partir de Finance and Operations 8.1 avec platform update 20. |

### <a name="financial-reports-generator-for-russia"></a>Générateur d’états financiers pour la Russie
Outil pour paramétrer la collecte des données pour la comptabilité et les états fiscaux et pour exporter les données vers les modèles d’état XLS et DOC. Parties fonctionnelles : la fonction d’exportation des données vers les modèles d’état XLS et DOC, les requêtes, les conditions requises fixes sont supprimées. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les parties supprimées sont remplacées par l’outil de gestion des états électroniques. |
| **Remplacé par une autre fonctionnalité ?**   | Oui. L’interface utilisateur de paramétrage des états financiers doit être utilisée pour paramétrer les règles de collecte de données par les comptes généraux ou les registres de taxe. La fonction d’exportation des données vers divers types de fichiers, les conditions requises fixes et les règles de collecte des données de type requête doivent être configurées dans l’outil de gestion des états électroniques. |
| **Zones de produit affectées**         | Comptabilité générale. |
| **Option de déploiement**              | Tout |
| **État**                         | Supprimé à partir de Finance and Operations 8.1 avec platform update 20. |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Intégration avec les fournisseurs externes pour l’envoi des états électroniques via les canaux de communication pour la Russie
Fonction d’exportation des fichiers électroniques générés des déclarations vers un dossier pour l’envoi ultérieur aux fournisseurs officiels d’états électroniques, ainsi que pour la réimportation de l’état.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par la fonction configurable des messages électroniques. |
| **Remplacé par une autre fonctionnalité ?**   | Oui.  |
| **Zones de produit affectées**         | Comptabilité générale, Taxe |
| **Option de déploiement**              | Tout |
| **État**                         | Supprimé à partir de Finance and Operations 8.1 avec platform update 20. |


### <a name="profit-tax-register-wizard"></a>Assistant de registre de l’impôt sur les bénéfices
Fonctionnalité pour créer des modèles de nouveaux registres de l’impôt sur les bénéfices. Cette fonctionnalité permet de créer des objets X++ pour les nouveaux livres, qui sont ensuite créés en tant que modèles avec la logique de calcul appropriée.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonctionnalité n’est pas compatible avec le modèle d’extensibilité Finance and Operations. |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Taxes |
| **Option de déploiement**              | Tout |
| **État**                         | Supprimé à partir de Finance and Operations 8.1 avec platform update 20. |


## <a name="finance-and-operations-80-with-platform-update-15"></a>Finance and Operations 8.0 avec Platform update 15
Aucune fonctionnalité n’a été supprimée ou rendue obsolète avec cette version. Platform update 15 est cumulative et contient les fonctionnalités, nouvelles ou modifiées, depuis Platform update 13, Platform update 14, et Platform update 15.

## <a name="finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Finance and Operations, Enterprise Edition 7.3 avec platform update 12

### <a name="personalized-product-recommendations"></a>Recommandations de produit personnalisées 
À compter du 15 février 2018, les détaillants ne pourront plus afficher des recommandations de produits personnalisées sur un appareil de point de vente (PDV). Pour plus d’informations, voir [Vue d’ensemble des recommandations de produit](../../../commerce/product-recommendations.md).  

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous supprimons la version actuelle du service de recommandation de produit car nous remodelons cette fonction avec un meilleur algorithme et de nouvelles fonctionnalités orientées détail.  |
| **Remplacé par une autre fonctionnalité ?**   | N° Cependant, après le printemps 2018, nous prévoyons de rétablir cette fonctionnalité pour tirer parti d’un nouveau service de recommandation.   |
| **Zones de produit affectées**         | Recommandations de produit personnalisées dans le PDV.                                                    |
| **Option de déploiement**              | Tout                                                                                      |
| **Statut**                         |Supprimé à partir de 15 février 2018. Cela concerne les clients exécutant Dynamics 365 for Operations 1611 et versions ultérieures.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Extension de la liste des fonctions de génération d’états électroniques (ER)
La possibilité d’introduire des fonctions personnalisées à utiliser dans le générateur d’expression ER (pour plus d’informations, voir [Extension de la liste des fonctions de génération d’états électroniques (ER)](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) n’est plus prise en charge. En raison des modifications des API de génération d’états électroniques, l’API pour appeler les fonctions intégrées à partir du générateur d’expression ER est devenue interne et ne peut plus être étendue.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Initiative de scellage du code  |
| **Remplacé par une autre fonctionnalité ?**   | Aucun(e). Lorsqu’une nouvelle fonction intégrée est requise, une nouvelle demande d’extension doit être adressée à l’équipe de la structure ER.<br><br>En tant que travail temporaire pendant que la fonction demandée est en cours de développement par l’équipe ER, la logique requise peut être programmée en tant que méthode d’une classe d’application personnalisée. Cette méthode est accessible dans une expression ER en tant que propriété de la source de données ER ajoutée du type **Application\Classe** qui fait référence à cette classe d’application personnalisée.  |
| **Zones de produit affectées**         | Structure de gestion des états électroniques                                                      |
| **Option de déploiement**              | Tous                                                                                      |
| **Statut**                         | Supprimé à partir de Finance and Operations, Enterprise Edition 7.3.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>États Stock par groupe d’articles et Stock par balance âgée des dimensions de stock

Ces deux rapports ne sont plus pris en charge dans Finance and Operations. À la place, l’état **Stock – Balance âgée** peut être utilisé pour améliorer l’expérience de l’utilisateur.

| &nbsp;  | &nbsp; |
|--------------|-----------------------|
| **Motif de la suppression**       | Fonctionnalité en double  |
| **Remplacé par une autre fonctionnalité ?** | Oui. Les deux états ont été remplacés par l’état **Stock – Balance âgée**.     |
| **Zones de produit affectées**       | Gestion des stocks, Gestion des coûts        |
| **Option de déploiement**        | Tout|
| **Statut**                       | Déconseillé : les options de menu des deux états ont été supprimées dans la version 7.3. Toutefois, le code des états est conservé dans le produit. L’objectif est de supprimer le code dans une prochaine version. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Packs de contenu Power BI disponibles sur AppSource
Les packs de contenu **Gestion des coûts**, **Performances financières** et **Retail Channel Performance**, disponibles sur le site [Microsoft AppSource](https://appsource.microsoft.com), sont déconseillés suite aux mises à jour de produit dans Microsoft Power BI. Les écrans d’administration du système utilisés pour déployer ces packs de contenu sur PowerBI.com sont également déconseillés dans Finance and Operations.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Mises à jour de produit dans Microsoft Power BI. |
| **Remplacé par une autre fonctionnalité ?**   | Les packs de contenu **Gestion des coûts**, **Performances financières** et **Retail Channel Performance**, disponibles sur le site [AppSource](https://appsource.microsoft.com), sont remplacés par des applications analytiques qui permettent l’intégration de solutions au niveau de la base de données. Pour plus d’informations sur les applications analytiques, voir [Power BI intégré dans les espaces de travail](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Zones de produit affectées**         | Gestion des coûts, Finance et Vente au détail                                                                                               |
| **Option de déploiement**              | Cloud uniquement (l’intégration à PowerBI.com n’est pas prise en charge dans les déploiements sur site.)                                                                                                            |
| **Statut**                         | Déconseillé : le délai cible pour la suppression de la fonctionnalité est le deuxième trimestre 2018.    |

### <a name="standard-ui-in-data-management-workspace"></a>Interface utilisateur standard de l’espace de travail de gestion des données

L’interface utilisateur standard de gestion des données est l’interface utilisateur hérité, qui est l’interface utilisateur par défaut que les utilisateurs voient lorsqu’ils se rendent dans l’espace de travail de gestion des données.

| &nbsp;  | &nbsp; |
|------------------|-------------------------|
| **Motif de l’abandon/de la suppression** | Nous faisons tout notre possible pour fournir de nouvelles expériences utilisateur dans la nouvelle interface utilisateur.             |
| **Remplacé par une autre fonctionnalité ?**   | La nouvelle interface utilisateur appelée *Vues améliorées* remplace l’ancienne interface utilisateur.            |
| **Zones de produit affectées**         | Espace de travail de gestion des données                                                     |
| **Option de déploiement**              | Tout                                                                           |
| **Statut**                         | Obsolète : le délai cible pour la suppression de la fonctionnalité est le deuxième trimestre 2018. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Contributions indirectes, taxe, taxe sur les services pour l’Inde

Ces taxes ont été englobées dans le GST indien.

|  &nbsp;                                           |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motif de la suppression ou de l’abandon**       | Ces taxes ont été englobées dans le GST indien.                          |
| **Remplacé par une autre fonctionnalité ?**            | GST indien                                                              |
| **Zones de produit affectées**                  | Taxes                                                                     |
| **Option de déploiement**                       | Tous les modules                                                   |
| **Statut**                                  | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |    

### <a name="file-validation-utility-fvu-for-india"></a>Utilitaire de validation de fichier (FVU) pour l’Inde

|              &nbsp;                               |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motif de la suppression ou de l’abandon**       | Peu utilisé par les clients                                                  |
| **Remplacé par une autre fonctionnalité ?**            | N°                                                                      |
| **Zones de produit affectées**                  | Retenue à la source indienne                                                  |
| **Option de déploiement**                       | Tous les modules                                                                    |
| **Statut**                                  | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.   |        

### <a name="tdstcs-certificate-for-india"></a>Certificat TDS/TCS pour l’Inde

Les utilisateurs peuvent le télécharger à partir du portail gouvernemental.

|             &nbsp;                                |    &nbsp;                                                                     |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motif de la suppression ou de l’abandon**       | Peu utilisé par les clients                                                  |
| **Remplacé par une autre fonctionnalité ?**            | N°                                                                      |
| **Zones de produit affectées**                  | Retenue à la source indienne                                                  |
| **Option de déploiement**                       | Tous les modules                                                                   |
| **Statut**                                  | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Modèle d’incitant d’exportation/importation pour l’Inde


|              &nbsp;                               |        &nbsp;                                                                 |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motif de la suppression ou de l’abandon**       | Peu utilisé par les clients                                                  |
| **Remplacé par une autre fonctionnalité ?**            | N°                                                                      |
| **Zones de produit affectées**                  | Importer et exporter                                                       |
| **Option de déploiement**                       | Tous les modules                                                                    |
| **Statut**                                  | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Recommandations de produit personnalisées 
À compter du 15 février 2018, les détaillants ne pourront plus afficher des recommandations de produits personnalisées sur un appareil de point de vente (PDV). Pour plus d’informations, voir [Vue d’ensemble des recommandations de produit](../../../commerce/product-recommendations.md).  

|  &nbsp; |  &nbsp;|
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous supprimons la version actuelle du service de recommandation de produit car nous remodelons cette fonction avec un meilleur algorithme et de nouvelles fonctionnalités orientées détail.  |
| **Remplacé par une autre fonctionnalité ?**   | N° Cependant, après le printemps 2018, nous prévoyons de rétablir cette fonctionnalité pour tirer parti d’un nouveau service de recommandation.   |
| **Zones de produit affectées**         | Recommandations de produit personnalisées dans le PDV.                                                    |
| **Option de déploiement**              | Tout                                                                                      |
| **Statut**                         |Supprimé à partir de 15 février 2018. Cela concerne les clients exécutant Dynamics 365 for Retail 7.2 et versions ultérieures. |


## <a name="finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Finance and Operations, Enterprise Edition juillet 2017 avec platform update 8

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Conversion de devise pour les devises comptables et de déclaration

La conversion de devise pour les devises comptables et de déclaration a été introduite avec l’introduction de l’euro.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Utilisation limitée et ajout de la fonctionnalité Copier l’entité juridique en remplacement.      |
| **Remplacé par une autre fonctionnalité ?**   | Non, mais les fonctionnalités Copier l’entité juridique et Configurations ont été ajoutées pour pouvoir passer facilement à une société dont les besoins de base évoluent. |
| **Zones de produit affectées**         | Gestion financière     |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.   |


### <a name="warehouse-mobile-devices-portal"></a>Portail des appareils mobiles d’entrepôt

Le Portail des appareils mobiles d’entrepôt (WMDP) est un composant autonome qui a été prévu pour l’auto-déploiement local. Ce composant n’est plus pris en charge dans Finance and Operations. Une application native qui améliore l’expérience utilisateur a remplacé la fonctionnalité de WMDP.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Fonction doublon.       |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Cette fonctionnalité a été remplacée par Finance and Operations – Entreposage. Pour plus d’informations sur le paramétrage et les conditions préalables, voir [Vue d’ensemble Installer et configurer l’application Entreposage](../../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Zones de produit affectées**         | Gestion des entrepôts, Gestion du transport     |
| **Option de déploiement**              | Le Portail des appareils mobiles d’entrepôt (WMDP) est un composant autonome qui a été prévu pour l’auto-déploiement local.               |
| **Statut**                         | Obsolète : le délai cible pour la suppression de la fonctionnalité est le quatrième trimestre 2019.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Rapprochement bancaire avancé correspondant à la règle de correspondance manuelle

Règle de correspondance utilisée pour sélectionner et marquer un document bancaire lorsque des documents ont fait l’objet d’une correspondance manuelle dans la feuille de calcul de rapprochement

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Utilisation limitée.                                                                         |
| **Remplacé par une autre fonctionnalité ?**   | N° Les fonctions de filtrage de colonnes doivent permettre de rechercher des documents pour le rapprochement. |
| **Zones de produit affectées**         | Gestion de la trésorerie et de la banque                                                               |
| **Option de déploiement**              | Tous                                                                                    |
| **État**                         | Supprimé à partir de juillet 2017.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 avec Platform update 3

### <a name="aeb-payment-formats-for-spain"></a>Formats de paiement AEB pour l’Espagne

Les formats de paiement Consejo Superior Bancario étaient utilisés pour envoyer des fichiers de remise à la banque pour les paiements client et les paiements fournisseur. Le contenu de ces formats était déterminé par Asociación Española de Banca. Cela concerne Cuaderno 19, 32, 58, 34.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                                  |
| **Remplacé par une autre fonctionnalité ?**   | Oui, les formats de transfert du crédit ISO20022 et de paiement de débit direct pour l’Espagne |
| **Zones de produit affectées**         | Comptabilité fournisseur, Comptabilité client                                    |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Les transferts de paiements bancaires pour la Lithuanie

Les transferts de paiements bancaires étaient générés et imprimés au moyen du format d’exportation de transfert de paiement (LT) pour la Lituanie. Le marché lithuanien a commencé à utiliser le LITAS, le système bancaire électronique unifié, en 2005.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de virement bancaire ISO20022 pour la Lituanie     |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                               |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Les formats de paiement BBS Direkte Remittering pour la Norvège

Les formats de paiement BBS Direkte Remittering incluent l’exportation de collecte des paiements client (débit) et l’importation de message de retour.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.  |
| **Remplacé par une autre fonctionnalité ?**   | Le format de paiement client AvtaleGiro pour la Norvège peut être utilisé pour générer des messages de débit direct. L’importation de message de retour sera implémentée dans les versions futures. |
| **Zones de produit affectées**         | Comptabilité fournisseur, Comptabilité client   |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Outil de plan de comptes pour l’Espagne

Cet outil est utilisé lorsqu’un plan de comptes en Espagne nécessite des modifications importantes. Les utilisateurs peuvent importer un nouveau plan de comptes dans Microsoft Excel ou au format de texte, et peuvent également importer des tableaux d’analyse.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Utilisation limitée                                                  |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                             |
| **Zones de produit affectées**         | Comptabilité                                                 |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="dom80-payment-format-for-belgium"></a>Format de paiement Dom80 pour la Belgique

Le format de paiement belge hérité pour la collecte de paiement (débit direct).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format de paiement n’est plus utilisé.                          |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de paiement de débit direct ISO 20022 pour la Belgique         |
| **Zones de produit affectées**         | Module Comptabilité client                                            |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formats de paiement DTA/EZAG pour la Suisse

Les formats DTA/EZAG sont intégrés dans le système ESR car ils peuvent conserver le numéro de référence. Du fait que les numéros de référence ne sont pas obligatoires, ces formats peuvent être utilisés pour traiter tous les paiements fournisseur. Ces formats sont utilisés par les sociétés qui ont un compte bancaire à un emplacement autre que « Postfinance ».

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de virement bancaire ISO20022 pour la Suisse   |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                               |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Format de paiement EDIFACT-DIRDEB pour l’Autriche

Le format de paiement EDIFACT-DIRDEB pour la collecte de paiement (débit direct).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format de paiement n’est plus utilisé.                          |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de paiement de débit direct ISO 20022 pour l’Autriche         |
| **Zones de produit affectées**         | Module Comptabilité client                                            |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="edivat-for-belgium"></a>EDIVAT pour la Belgique

EDIVAT est une norme belge obsolète pour la déclaration électronique via courrier sécurisé. Dynamics AX 2012 conserve la solution en lecture seule pour permettre l’accès aux données historiques.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonctionnalité n’est plus utilisée.                           |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                             |
| **Zones de produit affectées**         | Comptabilité                                                 |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Format d’importation de paiements eGiro EDIFACT CREMUL pour la Norvège

eGiro s’appuie sur la norme internationale EDIFACT CREMUL (Avis de crédit multiple) standard, utilisée pour la validation automatique des paiements client. Dans Dynamics AX, eGiro est implémenté comme format d’importation de paiements client.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format de paiement n’est plus utilisé.                                                     |
| **Remplacé par une autre fonctionnalité ?**   | Oui, l’importation de la notification ISO20022 Camt.054. |
| **Zones de produit affectées**         | Module Comptabilité client                                                                       |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                            |

### <a name="external-inventory-for-poland"></a>Stock externe pour la Pologne

Preuve des marchandises prises d’un fournisseur pour les ventes sans achat. Marchandises gérées dans le stock externe, n’affectant pas le stock standard, qui peuvent être vendues puis achetées automatiquement. Ce processus crée de vrais mouvements de stock.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une autre fonction                                    |
| **Remplacé par une autre fonctionnalité ?**   | Oui, la fonctionnalité de consignation entrante de base                |
| **Zones de produit affectées**         | Comptabilité fournisseur, Gestion des stocks                         |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Générateur d’états financiers pour l’Europe de l’Est

Un outil est utilisé pour paramétrer la collecte des informations pour la comptabilité et les états fiscaux et pour exporter le données vers les modèles d’état XLS et DOC.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Utilisation limitée                                                                            |
| **Remplacé par une autre fonctionnalité ?**   | N° L’outil sera remplacé par des configurations de génération d’états électroniques dans les versions futures. |
| **Zones de produit affectées**         | Comptabilité générale                                                                           |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importation des transactions de paiement client pour la Finlande

Vous pouvez sélectionner un format d’importation pour les paiements finlandais pour importer des transactions de paiement client à partir d’un fichier externe fourni par la banque.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format de paiement n’est plus utilisé.                                                     |
| **Remplacé par une autre fonctionnalité ?**   | Oui, l’importation de la notification ISO20022 Camt.054. |
| **Zones de produit affectées**         | Module Comptabilité client                                                                       |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importation des transactions de paiement dans un journal de comptabilité pour la Finlande

Un format qui est spécifique à la Finlande est utilisé pour importer les transactions comptables dans la comptabilité.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format de paiement n’est plus utilisé.                                                     |
| **Remplacé par une autre fonctionnalité ?**   | Oui, l’importation du relevé bancaire ISO20022 Camt.053 à l’aide du rapprochement bancaire avancé. |
| **Zones de produit affectées**         | Module Comptabilité client                                                                       |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>L’intégration à Isabel synchronized (CIS) pour la Belgique

Isabel est le cadre des opérations bancaires électroniques en Europe et une norme de facto en Belgique.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’intégration avec le client Isabel est devenue obsolète.   |
| **Remplacé par une autre fonctionnalité ?**   | Non. Les formats de paiement qui ne sont plus utilisés sont remplacés par le format de paiement de transfert de crédit ISO20022 pour la Belgique. |
| **Zones de produit affectées**         | Module Comptabilité fournisseur     |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Modifications dans le plan de comptes et les règles comptables pour l’Espagne

Cette fonctionnalité est utilisée pour les modifications apportées au plan de comptes et aux règles comptables en Espagne. Elle mappe les comptes pour aider à transformer l’ancien plan de comptes en nouveau plan de comptes, et compare l’exercice précédent au nouvel exercice, même s’ils ont été validés à des numéros de compte distincts.

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Utilisation limitée                                                  |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                             |
| **Zones de produit affectées**         | Comptabilité                                                 |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Format de paiement fournisseur Pagamento Fornittori

Format de paiement italien hérité pour les transferts de crédit.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format de paiement n’est plus utilisé.                          |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de virement bancaire ISO20022 pour l’Italie         |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                               |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="payment-export-formats-for-estonia"></a>Formats d’exportation de paiement pour l’Estonie

Les formats Telehansa et Teleservice sont utilisés pour l’exportation de paiements bancaires.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de virement bancaire ISO20022 pour l’Estonie       |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                               |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="payment-file-archive-for-norway"></a>Archive de fichier de paiement pour la Norvège

Lorsque des fichiers de paiement sont générés, l’archive du fichier archive automatiquement tous les fichiers créés, même les fichiers enregistrés ou lus précédemment.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une autre fonction                                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, les tâches de gestion des états électroniques archivées                            |
| **Zones de produit affectées**         | Comptabilité fournisseur, Comptabilité client, Administration d’organisation |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.     |

### <a name="payment-import-formats-for-estonia"></a>Formats d’importation de paiement pour l’Estonie

Les formats Telehansa et TeleTeenus sont utilisés pour l’importation de paiements bancaires.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                                                    |
| **Remplacé par une autre fonctionnalité ?**   | Oui, l’importation de la notification bancaire ISO20022 Camt.054. |
| **Zones de produit affectées**         | Module Comptabilité client                                                                        |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                             |

### <a name="payroll-information-in-human-resources"></a>Informations sur les salaires dans le module Ressources humaines

Informations sur les salaires dans Ressources humaines

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Cette fonctionnalité a été remplacée par les pages Paie et Ressources humaines principales.  |
| **Remplacé par une autre fonctionnalité ?**   | Les pages **Avantages**, **Rémunérations**, et les autres pages associées qui étaient précédemment dans Paie États-Unis ont été reconfigurées et font désormais partie de la configuration du module Ressources humaines principal pour aider à prendre en charge le traitement externe de la paie. Cette fonctionnalité est accessible à l’aide de la clé de configuration **Ressources humaines 1** \> **Paie**. |
| **Zones de produit affectées**         | Ressources humaines, Paie   |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations version 1611.    |

### <a name="performance-management-goal-workflow"></a>Workflow de l’objectif de gestion des performances

La gestion des performances inclut la gestion et l’intégration d’objectifs incluant des entretiens d’évaluation des performances.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La gestion des performances a été remodelée, et le nombre de pages d’objectifs a été réduit pour simplifier le processus.                 |
| **Remplacé par une autre fonctionnalité ?**   | Non. Les objectifs sont visibles des responsables via le portail en libre-service pour responsables, qui peuvent être changés et affichés par le responsable. |
| **Zones de produit affectées**         | Gestion du capital humain       |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations version 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formats de paiement Postgirot et Postgirot Utland pour la Suède

Formats de paiement Postgirot et Postgirot Utland pour la Suède.

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de virement bancaire ISO20022 pour la Suède        |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                               |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="radio-frequency-identifier"></a>Identification par radiofréquence

L’identification par radio-fréquence (RFID) est une technologie de collecte de données utilisant des balises électroniques pour stocker des données d’identification et un lecteur sans exigence de visibilité directe pour les capturer.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation de la part des clients et ensemble de fonctionnalités limité.   |
| **Remplacé par une autre fonctionnalité ?**   | N°                                              |
| **Zones de produit affectées**         | Gestion des stocks                            |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>État sur la numérotation des factures d’état pour la Lettonie

La législation lettone impose des règles spécifiques sur la numérotation des factures. La fonctionnalité permet d’affecter des numéros spécifiques aux factures client, selon l’utilisateur ou le groupe d’utilisateurs. Vous pouvez ensuite générer un état ou un fichier XML. Vous pouvez également imprimer un état sur les numéros de facture qui sont utilisés.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La numérotation de facture d’état ne doit plus être mise à jour. L’état sur les numéros de facture utilisés n’est plus nécessaire. |
| **Remplacé par une autre fonctionnalité ?**   | N°       |
| **Zones de produit affectées**         | Module Comptabilité client    |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Paramétrez le nom du responsable et du comptable général d’une société pour la Lithuanie

Les noms du responsable et du comptable général d’une société peuvent être spécifiés dans les informations sur la société et utilisés dans différentes impressions locales d’état.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une autre fonction                                     |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le paramétrage des officiels peut être utilisé pour le même objectif.   |
| **Zones de produit affectées**         | Comptabilité fournisseur, Comptabilité client, Gestion de la trésorerie et de la banque |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.  |

### <a name="shipping-carrier-interface"></a>Interface du transporteur

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Fonctionnalité en double   |
| **Remplacé par une autre fonctionnalité ?**   | Partiellement remplacé par la gestion du transport |
| **Zones de produit affectées**         | Gestion des stocks, Ventes et marketing  |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations version 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Formats de paiement Telepay pour la Norvège

Les formats de paiement Telepay incluent l’exportation de paiement fournisseur (transfert de crédit) et la collecte de paiement client (débit direct).

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                                                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de paiement par virement ISO20022 et le format de paiement client AvtaleGiro pour la Norvège, ainsi que l’importation des fichiers de retour de notification bancaire pain.002 et camt.054. |
| **Zones de produit affectées**         | Comptabilité fournisseur, Comptabilité client                                                          |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Formats d’exportation de paiement fournisseur pour la Finlande

Deux formats pour exporter les paiements sont disponibles pour la Finlande. LM02 (FI) est utilisé pour les paiements locaux, et LUM2 (FI) est utilisé pour les paiements étrangers.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les formats de paiement ne sont plus utilisés.                        |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le format de virement bancaire ISO20022 pour la Finlande       |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                               |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="warehouse-management-ii"></a>Gestion des entrepôts II

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La solution Gestion des entrepôts II (WMS II) qui était disponible dans le module **Gestion des stocks** duplique la fonctionnalité située dans le module **Gestion des entrepôts** qui a été lancée dans Dynamics AX 2012 R3.                                                                         |
| **Remplacé par une autre fonctionnalité ?**   | Le module **Gestion des entrepôts** qui a été lancé dans AX 2012 R3, Dynamics AX 2012 R3 CU8 et Dynamics AX 2012 R3 CU9 remplace les fonctionnalités de Gestion des entrepôts II. Le nouveau module a des fonctionnalités plus avancées et des processus de gestion des entrepôts plus flexibles que dans le module Gestion des entrepôts II. |
| **Zones de produit affectées**         | Gestion des stocks, Ventes et marketing, Approvisionnements   |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations version 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Rappels pour les travailleurs dans le module Ressources humaines

Informations sur les salaires dans Ressources humaines

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation                                                           |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                                  |
| **Zones de produit affectées**         | Ressources humaines                                                     |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations version 1611 |

### <a name="workflow-for-creating-goals"></a>Workflow pour créer des objectifs

Un workflow pour la gestion de la création des objectifs de l’employé est l’un des workflows disponibles pour faciliter la coordination du processus de gestion des performances.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le module Gestion des performances a été entièrement revisité dans Finance and Operations.     |
| **Remplacé par une autre fonctionnalité ?**   | La fonction de gestion des performances remodelée donne plus de contrôle sur le contenu des objectifs, les mesures utilisées pour suivre la progression, et l’association des documents associés. Les objectifs peuvent être stockés comme des modèles pour être réutilisés. Cette fonction peut vous aider à paramétrer des objectifs supplémentaires pour vos employés plus rapidement. |
| **Zones de produit affectées**         | Gestion du capital humain                 |
| **Statut**                         | Supprimé à partir de Dynamics 365 for Operations version 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Possibilité d’annuler les modifications apportées à une facture fournisseur

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Améliorations des performances        |
| **Remplacé par une autre fonctionnalité ?**   | N°                             |
| **Zones de produit affectées**         | Module Comptabilité fournisseur               |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>Intégration d’AIF, AxD et AxBC

Dans l’environnement d’intégration applicative (AIF), les données peuvent être échangées avec les systèmes externes via une logique métier exposée en tant que service. Dynamics AX inclut des services basés sur des documents et sur .NET Business Connector (AxBC). Un document est créé à l’aide de XML. XML inclut des informations d’en-tête qui sont ajoutées pour créer un *message* qui peut être transféré ou extrait de Dynamics AX. Parmi les exemples de documents on trouve les commandes client et les commandes fournisseur. Toutefois, pratiquement n’importe quelle entité (un client par exemple), peut être représentée par un document. Les services basés sur des documents utilisent les classes **Axd \<Document\>**.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’architecture d’AIF et d’AxDs ne pouvait pas être mise à l’échelle vers un service cloud. Il y avait des problèmes de performances avec l’importation en bloc.                                        |
| **Remplacé par une autre fonctionnalité ?**   | Cette fonctionnalité est remplacée par l’environnement d’importation/exportation des données, qui prend en charge l’importation/exportation en bloc récurrente. Pour AxBC, il est recommandé d’utiliser les tables réelles. |
| **Zones de produit affectées**         | AxDs, AxBCs et AIF   |
| **État**                         | Supprimé à partir de Dynamics AX 7.0.   |

### <a name="billing-code-rate-scripts"></a>Scripts de taux des codes de facturation

Les scripts de facturation étaient utilisés pour calculer les taux de facturation pour les codes de facturation. Ces scripts nécessitaient un développement personnalisé dans le langage de programmation C# ou Visual Basic. Dans la version actuelle de Dynamics AX, les **scripts de taux des code de facturation** ne sont pas pris en charge.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La prise en charge des scripts C# ou Visual Basic n’a pas été ajoutée dans Dynamics AX 7.0. |
| **Remplacé par une autre fonctionnalité ?**   | Non                                                                                      |
| **Zones de produit affectées**         | Secteur public, Comptabilité client                                    |
| **État**                         | Supprimé à partir de Dynamics AX 7.0.                                                          |

### <a name="boms-without-bom-versions"></a>Nomenclatures sans versions de nomenclature

Si la clé de configuration des **versions de nomenclature** a été désactivée, les versions de nomenclature (BOM) ont été masquées dans tous les écrans, et le système a forcé une relation 1 à 1 entre les produits et les nomenclatures. Dans la version actuelle de Dynamics AX, la clé de configuration des **versions de nomenclature** ne peut pas être désactivée.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’utilisation d’une clé de configuration pour contrôler les versions de nomenclature n’effectue pas de mise à l’échelle dans un environnement cloud. |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                                                      |
| **Zones de produit affectées**         | Gestion des informations sur les produits, Gestion des stocks                                    |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Bordero brésilien

Mode de paiement spécifique aux sociétés brésiliennes

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La prise en charge du mode de paiement du Bordero brésilien est devenue obsolète dans la localisation brésilienne |
| **Remplacé par une autre fonctionnalité ?**   | N°   |
| **Zones de produit affectées**         | Module Comptabilité fournisseur   |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="brazilian-sintegra-statement"></a>Relevé Sintegra brésilien

Déclaration de taxe fédérale pour la taxe ICMS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Ce relevé ne s’applique plus dans certains états brésiliens. |
| **Remplacé par une autre fonctionnalité ?**   | Non. Les utilisateurs peuvent utiliser l’outil de génération d’états électroniques génériques pour configurer le relevé si nécessaire dans des situations spécifiques. |
| **Zones de produit affectées**         | Registres fiscaux    |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Mode de secours NF-e SCAN brésilien

L’environnement de secours (SCAN) permet de générer, d’exporter, et d’importer le statut d’un Nota Fiscal eletrônica (NF-e) lorsque l’environnement du Secretaria da Fazenda (SEFAZ) n’est pas disponible.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Cette méthode de secours ne s’applique plus dans tous les états brésiliens |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                                          |
| **Zones de produit affectées**         | Module Comptabilité client                                                         |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.              |

### <a name="business-analyzer"></a>Business Analyzer

Cette application mobile permet aux utilisateurs d’examiner les indicateurs clés de l’entreprise.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Cette fonctionnalité a été remplacée par une autre.   |
| **Remplacé par une autre fonctionnalité ?**   | Le pack de contenu Surveiller les performances financières pour Microsoft Power BI va inclure des mesures financières clés qui étaient précédemment disponibles dans le Business Analyzer. |
| **Zones de produit affectées**         | Comptabilité      |
| **Statut**                         | Déconseillé : l’utilisation de Business Analyzer a été déconseillée.    |

### <a name="business-statistics"></a>Statistiques commerciales

Paramétrage des requêtes de statistiques commerciales qui peut aider à analyser les performances de l’organisation

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Approche héritée de la BI (Business Intelligence), faible utilisation de la part des clients et ensemble de fonctionnalités limité |
| **Remplacé par une autre fonctionnalité ?**   | Nouvelles solutions de BI pour la version actuelle de Dynamics AX                                      |
| **Zones de produit affectées**         | Approvisionnements, Comptabilité fournisseur, Ventes et marketing, Comptabilité client         |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Modifier la fonction de date de document de modification dans le journal des approbations de facture

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation                                                               |
| **Remplacé par une autre fonctionnalité ?**   | Oui. La date de document de la transaction fournisseur validée peut être modifiée. |
| **Zones de produit affectées**         | Module Comptabilité fournisseur                                                        |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Format de paiement ClieOp03 pour les Pays-Bas

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format ne s’applique plus aux Pays-Bas, car il a été remplacé par la fonctionnalité SEPA. |
| **Remplacé par une autre fonctionnalité ?**   | Exportation des paiements SEPA  |
| **Zones de produit affectées**         | Tous les modules     |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.   |

### <a name="compliance-center"></a>Centre de conformité

Le Centre de conformité est un site Enterprise Portal pour gérer les besoins en matière de documentation pour des initiatives de conformité liées à la législation de Sarbanes-Oxley.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Peu utilisé par les clients. Microsoft SharePoint inclut la même capacité que celle qui était disponible dans le Centre de conformité. |
| **Remplacé par une autre fonctionnalité ?**   | N°   |
| **Zones de produit affectées**         | Conformité et contrôles internes  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Connecteur pour Microsoft Dynamics

Cet outil était utilisé pour faire passer des données clés de Microsoft Dynamics CRM vers les candidatures Dynamics ERP.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Cette fonctionnalité a été remplacée par une autre. |
| **Remplacé par une autre fonctionnalité ?**   | Dataverse                                      |
| **Zones de produit affectées**         | Connecteur pour Dynamics                         |
| **État**                         | Supprimé à partir de Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unité de conteneur et stock disponible multidimensions

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Fonctionnalité en double |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Depuis AX 2012, cette fonctionnalité a été remplacée par les fonctionnalités des lots de production consolidés. Ces fonctionnalités incluent l’affichage disponible consolidé. |
| **Zones de produit affectées**         | Gestion des informations sur les produits, Contrôle de la production, Gestion des stocks, Ventes et marketing  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Métadonnées de groupe de files d’attente

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les groupes de files d’attente étaient utilisés pour afficher une ou plusieurs files d’attente dans la zone de récapitulatif. L’utilisation était limitée et il y avait également des soucis de performances, car une modification d’enregistrement dans un écran parent entrainait une requête par file d’attente dans le groupe des files d’attente. |
| **Remplacé par une autre fonctionnalité ?**   | N°      |
| **Zones de produit affectées**         | Tous les modules    |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Métadonnées de files d’attente

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les métadonnées de files d’attente étaient limitées aux informations de comptage ou de somme.    |
| **Remplacé par une autre fonctionnalité ?**   | Les métadonnées de mosaïque ont été introduites pour fournir plus de flexibilité pour la modélisation. Par exemple, vous pouvez modéliser les comptes actuels, la navigation, et les indicateurs de performance clés (KPI). Les métadonnées de mosaïque de compte remplacent directement les métadonnées de files d’attente. |
| **Zones de produit affectées**         | Tous les modules           |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0      |

### <a name="danish-check-format"></a>Format de chèque danois

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La prise en charge du format de chèque danois a été abandonnée, et l’état a été supprimé de la localisation DK. |
| **Remplacé par une autre fonctionnalité ?**   | N°    |
| **Zones de produit affectées**         | Tous les modules    |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.  |

### <a name="data-partitions"></a>Partitions de données

Les partitions de données fournissent une séparation logique des données dans la base de données Dynamics AX.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les partitions de données ont été introduites dans Dynamics AX 2012 R2 pour permettre l’isolement des données. Dans un scénario courant, une société possède des filiales, et les données d’une filiale ne doivent pas être visibles d’une autre filiale, même si les deux filiales sont gérés par le même service informatique. Toutefois, des scripts supplémentaires et du temps système de gestion tout au long du programme ont été requis afin de créer des partitions et de les remplir avec des données et pour sauvegarder les données de la partition. Dans le cloud, sur lequel nous avons accès aux services de base de données PaaS (Platform as a Service) (base de données Microsoft Azure SQL), il est beaucoup plus efficace d’utiliser une base de données en tant que conteneur d’isolation que de faire de l’isolation dans le programme. Même si le partitionnement des données est requis pour les filiales, pour plusieurs locataires ou juste pour une mise à l’échelle, nous pensons que les scénarios peuvent être mieux gérés par l’intermédiaire de plusieurs instances de Finance and Operations. |
| **Remplacé par une autre fonctionnalité ?**   | Les clients qui utilisent les partitions de données doivent utiliser plusieurs instances de Finance and Operations si la séparation au niveau de la base de données est un problème critique.    |
| **Zones de produit affectées**         | Tous les modules  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Stockage de base de données et de partage de fichiers pour les pièces jointes

Dynamics AX 2012 autorisait le stockage de pièces jointes dans la base de données et dans le partage de fichier. Ces deux options ne sont plus prises en charge.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le stockage de partage de fichiers n’est plus pris en charge car les environnements hébergés dans le cloud ne peuvent pas communiquer avec les partages de fichier locaux. Le stockage de base de données a été abandonné en faveur du stockage Azure Blob. Le stockage Azure Blob est l’équivalent du stockage dans la base de données, car les documents peuvent uniquement être accessibles via les écrans client Finance and Operations. Ceci offre l’avantage supplémentaire de fournir un stockage qui n’affecte pas négativement les performances de la base de données. Le stockage d’objet Blob est le mécanisme par défaut de stockage pour la gestion des documents et fonctionne immédiatement. |
| **Remplacé par une autre fonctionnalité ?**   | Le stockage de base de données a été abandonné en faveur du stockage Azure Blob.   |
| **Zones de produit affectées**         | Tous les modules  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.   |

### <a name="delimitation"></a>Délimitation

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Aucune utilisation de la fonctionnalité n’a été trouvée. |
| **Remplacé par une autre fonctionnalité ?**   | N°                                     |
| **Zones de produit affectées**         | Pointage                    |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Client du Bureau

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’expérience du client Dynamics AX a été remodelée pour améliorer la facilité d’utilisation sur plusieurs plateformes et périphériques.                      |
| **Remplacé par une autre fonctionnalité ?**   | Le nouveau client Web est basé sur les métadonnées de l’écran du bureau et le modèle de programmation qui a été modifié pour fournir une plateforme Web riche. |
| **Zones de produit affectées**         | Tous les modules  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Connexion directe à la base de données

Dans Dynamics AX 2012 R3, le terminal Retail Modern POS pouvait se connecter directement à la base de données des canaux de façon similaire au PDV de l’entreprise. Cela a été ajouté à la méthode standard de communication du terminal Retail Modern POS via le serveur de vente au détail.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La connexion directe à la base de données nécessitait un niveau de sécurité moindre au niveau des protocoles et a été utilisée principalement pour atteindre des niveaux de performances supérieurs. En raison des améliorations au niveau des performances et de la sécurité dans Finance and Operations, cette fonctionnalité entraîne désormais plus de problèmes qu’elle n’en résout. |
| **Remplacé par une autre fonctionnalité ?**   | N° Seule la communication standard via le serveur de vente au détail est désormais prise en charge.  |
| **Zones de produit affectées**         | Base de données des canaux/Retail Modern POS   |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>SWIFT MT940 néerlandais

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonctionnalité générique est désormais utilisée à la place de la fonctionnalité localisée.                    |
| **Remplacé par une autre fonctionnalité ?**   | Oui, cette fonctionnalité a été remplacée par la fonctionnalité Rapprochement bancaire avancé. |
| **Zones de produit affectées**         | Tous les modules                                                                              |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL pour l’Allemagne)

Cette fonctionnalité fournit la sortie XBLR (eXtensible Business Reporting Language) prévue spécifiquement pour la taxonomie eBilanz allemande.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Peu utilisé par les clients  |
| **Remplacé par une autre fonctionnalité ?**   | Cette fonctionnalité n’a pas été remplacée par une autre fonctionnalité, mais plusieurs packages XBRL spécialisés qui fournissent la fonctionnalité XBRL étendue sont disponibles pour le marché allemand. |
| **Zones de produit affectées**         | Management Reporter      |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.  |

### <a name="enterprise-portal-client"></a>Client Enterprise Portal

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Une plateforme cliente unique a été fournie.  |
| **Remplacé par une autre fonctionnalité ?**   | Le nouveau client Web est basé sur les métadonnées de l’écran du bureau et le modèle de programmation qui a été modifié pour fournir une plateforme Web riche. |
| **Zones de produit affectées**         | Tous les modules  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Durabilité environnementale

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation de la part des clients et ensemble de fonctionnalités limité  |
| **Remplacé par une autre fonctionnalité ?**   | N°              |
| **Zones de produit affectées**         | Module Conformité et contrôles internes, Comptabilité fournisseur  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>Écran Contrôles hôtes gérés et ActiveX

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les contrôles hôtes gérés et ActiveX sont basés sur le client de bureau obsolète. |
| **Remplacé par une autre fonctionnalité ?**   | L’infrastructure de contrôle extensible prend en charge les nouveaux contrôles basés sur HTML, CSS, et JavaScript, il s’agit d’un contrôle de première classe dans l’environnement Microsoft Visual Studio Tooling. |
| **Zones de produit affectées**         | Tous les modules     |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Génération de notes préliminaires à l’aide d’un traitement par lots

La génération de notes préliminaires ne peut pas être effectuée à l’aide d’un traitement par lots mais peut toujours être effectuée par un utilisateur.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Il n’existe aucun écran pour maintenir et afficher le fichier de notes préliminaires lorsqu’il est généré à l’aide d’un traitement par lots. |
| **Remplacé par une autre fonctionnalité ?**   | Les notes préliminaires peuvent toujours être générées, et l’utilisateur peut contrôler où le fichier est stocké.   |
| **Zones de produit affectées**         | Comptabilité fournisseur, Comptabilité client, Gestion de la trésorerie et de la banque  |
| **Statut**                         | Supprimé à partir de AX 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Exportation de paiement DTAUS et importation de relevé de compte allemands (totaux et transactions)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format ne s’applique plus en Allemagne, car il a été remplacé par la fonctionnalité Espace unique de paiement en euros (SEPA).                    |
| **Remplacé par une autre fonctionnalité ?**   | Oui, cette fonctionnalité a été remplacée par la fonctionnalité de rapprochement bancaire avancée et d’exportation de paiement SEPA pour importer les relevés de compte. |
| **Zones de produit affectées**         | Tous les modules  |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="german-dtazv-payment-format-in-domestic-currency"></a>Format de paiement DTAZV allemand en devise nationale

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format ne s’applique plus en Allemagne, car il a été remplacé par la fonctionnalité SEPA. |
| **Remplacé par une autre fonctionnalité ?**   | Exportation des paiements SEPA    |
| **Zones de produit affectées**         | Module Comptabilité fournisseur   |
| **État**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.    |

### <a name="german-mt940-import"></a>Importation du MT940 allemand

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonctionnalité générique est désormais utilisée à la place de la fonctionnalité localisée.                    |
| **Remplacé par une autre fonctionnalité ?**   | Oui, cette fonctionnalité a été remplacée par la fonctionnalité Rapprochement bancaire avancé. |
| **Zones de produit affectées**         | Tous les modules                                                                              |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.                           |

### <a name="german-xml-eu-sales-list"></a>Liste des ventes intracommunautaires pour l’Allemagne (format XML)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le format XML pour la génération d’états pour la Liste des ventes intracommunautaires pour l’Allemagne n’est plus pris en charge. Seul le format de fichier texte ELMA5 peut être utilisé pour envoyer la liste des ventes intracommunautaires à l’administration fiscale allemande. |
| **Remplacé par une autre fonctionnalité ?**   | N°         |
| **Zones de produit affectées**         | Taxes        |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.   |

### <a name="gl-ssrs-reports"></a>États GL SSRS

Les états qui comprennent les options de menu suivantes ont été supprimés : **Synthèse de balance comptable**, **Balance comptable détaillée**, **Plan de comptes**, **Piste d’audit**, **Soldes** et **Liste des soldes**.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les états financiers de Microsoft SQL Server Reporting Services (SSRS) ont été remplacés par des capacités et des états par défaut Management Reporter. |
| **Remplacé par une autre fonctionnalité ?**   | Management Reporter (appelé **États financiers** dans la version actuelle de Dynamics AX)    |
| **Zones de produit affectées**         | Comptabilité   |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>Métadonnées InfoPart et FormPart

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les métadonnées InfoPart et FormPart ont permis la création de récapitulatifs pour deux clients différents. |
| **Remplacé par une autre fonctionnalité ?**   | Les métadonnées InfoPart (une définition d’écran simplifiée) sont converties en écran par l’outillage de mise à niveau. Les métadonnées FormPart, qui référençaient un écran, sont remplacées par une référence plus directe créée par l’outillage de mise à niveau. |
| **Zones de produit affectées**         | Tous les modules    |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Page de liste Compte principal

Liste des comptes pour l’entité juridique et les informations sur le solde associées

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les informations sur le solde sont disponibles dans la page **Balance comptable** par compte et dimension.  |
| **Remplacé par une autre fonctionnalité ?**   | La page **Comptes principaux** contient la même liste de comptes que la page de liste **Compte principal**. La vue grille dans **Comptes principaux** affiche également une vue plus petite, semblable à une grille. |
| **Zones de produit affectées**         | Comptabilité      |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>État sur les flux de trésorerie des banques de Malaisie et de Singapour

Cette fonctionnalité permet à un utilisateur d’imprimer un état sur les flux de trésorerie qui indique les transactions et les détails des encaissements et décaissements pour un intervalle de dates spécifique pour des comptes bancaires sélectionnés.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les mêmes informations peuvent être obtenues à partir de la transaction bancaire Recherche. |
| **Remplacé par une autre fonctionnalité ?**   | La transaction bancaire Recherche.                                            |
| **Zones de produit affectées**         | Gestion de la trésorerie et de la banque                                                |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction.          |

### <a name="mexican-cfd-electronic-invoice"></a>Facture électronique CFD mexicaine

Cette fonctionnalité a permis la génération de factures électroniques mexicaines à l’aide de la méthode Comprobante Fiscal Digital (CFD), dans laquelle la société signe la facture en demandant l’autorisation associée d’une administration. Cette fonctionnalité fournit également un état mensuel qui inclut toutes les factures électroniques qui ont été émises dans la période.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La méthode ne s’applique plus. La génération de factures électroniques à l’aide de la méthode CFD a été abandonnée par les administrations fiscales et remplacée par la méthode Comprobante Fiscal Digital a través de Internet (CFDI), dans laquelle la signature est déléguée au fournisseur tiers (PAC). L’état mensuel a été supprimé, et une option de recherche permet aux utilisateurs d’en savoir plus sur les transactions historiques. |
| **Remplacé par une autre fonctionnalité ?**   | N°    |
| **Zones de produit affectées**         | Comptabilité client, Projet   |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="mexico-realized-and-unrealized-vat"></a>TVA réalisées et non réalisées au Mexique

Dynamics AX 2012 gérait la taxe sur la valeur ajoutée non réalisée (VAT) à l’aide de la fonctionnalité spécifique au Mexique pour la taxe non réalisée.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Fonctionnalité en double  |
| **Remplacé par une autre fonctionnalité ?**   | Oui, cette fonctionnalité a été remplacée par la fonctionnalité de taxe sur les encaissements standard fournie par Core. |
| **Zones de produit affectées**         | Taxes   |
| **Statut**                         | Déconseillé : une date de suppression n’a pas été définie pour cette fonction. |

### <a name="microsoft-outlook-integration"></a>Intégration à Microsoft Outlook


| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Cette fonctionnalité a été remplacée par l’intégration Microsoft Exchange Server. |
| **Remplacé par une autre fonctionnalité ?**   | Oui                                                                            |
| **Zones de produit affectées**         | Sales and Marketing                                                            |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Blocage privé des journaux de gestion de stock et d’entrepôt.

Les journaux de gestion de stock et d’entrepôt ne prennent plus en charge la possibilité de marquer un journal comme privé pour un utilisateur sélectionné. Seul les processus de blocage des journaux comme privé pour des groupes d’utilisateurs et de blocage lors de la modification sont pris en charge.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Aucune utilisation de la fonctionnalité n’a été trouvée. |
| **Remplacé par une autre fonctionnalité ?**   | N°                                     |
| **Zones de produit affectées**         | Gestion des stocks                   |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.         |

### <a name="product-builder"></a>Configurateur

Le configurateur était utilisé pour la configuration dynamique d’articles à partir d’une commande client, d’une commande fournisseur, d’un ordre de fabrication, d’un devis de vente, d’un devis de projet ou d’une demande d’articles. En fonction d’un modèle de produit ayant des variables de modélisation, l’utilisateur pouvait sélectionner des valeurs pour répondre aux exigences des clients et pour obtenir une unique variante de produit qui avait une nomenclature et une gamme.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le configurateur exposait du code X++ aux utilisateurs finaux et il n’est pas pris en charge dans la version actuelle de Dynamics AX. Il a été supprimé pour éviter les efforts de maintenance en double en matière de chevauchement et de codebases importants.  |
| **Remplacé par une autre fonctionnalité ?**   | Oui. La configuration basée sur les contraintes a été introduite dans Dynamics AX 2012 où l’abandon du configurateur dans les prochaines versions était déjà annoncé. La technologie de configuration basée sur les contraintes est sélectionnée sur les produits génériques pour activer la configuration. Pour en savoir plus, voir [Vue d’ensemble de configuration de produit](../../../supply-chain/pim/build-product-configuration-model.md). |
| **Zones de produit affectées**         | Gestion d’informations sur les produits, Ventes et marketing  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.      |

### <a name="production-floor-app"></a>Application Atelier de production
Il s’agit de l’application pour les tablettes s’exécutant sous Windows 8.1 et Windows 8.1 Pro.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La modification apportée à un client basé sur le Web, il est possible de fournir des fonctionnalités similaires via le client natif Dynamics AX 7.0. Le périphérique des bons de travail fournit une interface utilisateur d’atelier de production optimisée pour les facteurs d’écrans tactiles et de tablettes. |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Le périphérique des bons de travail, qui fait une partie native de Dynamics AX 7.0.                                                                           |
| **Zones de produit affectées**         | Contrôle de la production                                                |
| **Statut**                         | Obsolète : Une date de suppression de Microsoft Store n’a pas encore été définie pour cette fonctionnalité.                                                |


### <a name="rename-product-dimension"></a>Renommer la dimension de produit

Cette fonctionnalité permet de remplacer le nom de l’une des trois dimensions de produit standard (taille, couleur ou style) par un nom convenant mieux aux exigences métier. Le fonctionnalité de changement de nom comprenait tous les libellés où le nom de la dimension de produit était utilisé.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La version actuelle de Dynamics AX ne prend pas en charge le changement de nom au moment de l’exécution. |
| **Remplacé par une autre fonctionnalité ?**   | N°                                                                            |
| **Zones de produit affectées**         | Gestion des informations sur les produits                                                |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Connectivité du serveur de vente au détail avec HTTP

Dans Dynamics AX 2012 R3, le serveur de vente au détail pouvait fonctionner via une communication HTTP (non sécurisée). Cela a été ajouté à la communication standard via HTTPS.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | En raison de nouvelles exigences de sécurité, seule la communication sécurisée via TLS 1.2 (ou version ultérieure, si disponible) est maintenant prise en charge. Le programme d’installation en libre-service configurera automatiquement l’ordinateur pour la communication. |
| **Remplacé par une autre fonctionnalité ?**   | N° Seule la communication standard HTTPS est désormais prise en charge. |
| **Zones de produit affectées**         | Serveur de vente au détail  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Pages d’Aperçu interactif

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les pages d’aperçu interactif ont été établies sur la plateforme Enterprise Portal obsolète, qui a été remplacée par la nouvelle plateforme client Web dans la version actuelle de Dynamics AX. |
| **Remplacé par une autre fonctionnalité ?**   | Le nouveau modèle d’écran de l’espace de travail offre aux utilisateurs un design orienté processus qui fournit un accès simple aux tâches utilisées couramment dans ce processus.                       |
| **Zones de produit affectées**         | Tous les modules    |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0   |

### <a name="sales-tax-jurisdictions"></a>Juridictions fiscales

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation de la part des clients et ensemble de fonctionnalités limité |
| **Remplacé par une autre fonctionnalité ?**   | N°                                           |
| **Zones de produit affectées**         | taxe U.S.                                 |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.               |

### <a name="sites-services"></a>Services Sites

Sites Services vous permet de créer des sites Web qui étendent vos processus d’entreprise à Internet sans support informatique.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’infrastructure Microsoft Azure utilisée par Dynamics AX dispose des nouvelles capacités qui peuvent être utilisées à la place (par exemple, les sites Azure). |
| **Remplacé par une autre fonctionnalité ?**   | N°   |
| **Zones de produit affectées**         | Recrutement RH, gestion des incidents, demande de devis, enregistrement des fournisseurs, espaces de travail de collaboration pour les opportunités et les campagnes  |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>Stratégie de prévision de la demande SSAS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La conception de la fonctionnalité ne peut pas être prise en charge dans la nouvelle architecture de cloud. |
| **Remplacé par une autre fonctionnalité ?**   | Stratégie de prévision de la demande Azure Machine Learning                           |
| **Zones de produit affectées**         | Planification                                                              |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Registre de factures fournisseur excluant les détails de validation

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation. Cette fonctionnalité a été remplacée par le journal des factures avec une fonctionnalité de workflow. |
| **Remplacé par une autre fonctionnalité ?**   | Fonctionnalités de workflow du journal des factures.     |
| **Zones de produit affectées**         | Module Comptabilité fournisseur |
| **Statut**                         | Supprimé à partir de Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Comptes société virtuels

La fonctionnalité des sociétés virtuelles n’est plus prise en charge dans Dynamics AX. La fonctionnalité des sociétés virtuelles permet aux utilisateurs de paramétrer des tables à partager entre un ensemble de sociétés. Pour obtenir une description de la fonctionnalité, consultez [Comptes société et comptes société virtuels](../../fin-ops/get-started/ax4-content-retired.md). La fonctionnalité fonctionne en regroupant les tables en recouvrements affectés aux sociétés virtuelles, qui sont des groupes de « véritables » sociétés existantes. Les requêtes sont créées afin que toutes les sociétés de la société virtuelle puissent accéder aux données des tables des recouvrements de table associés.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | - Les sociétés virtuelles doivent être définies avant que les données soient enregistrées dans les tables. Il est très difficile d’adapter des sociétés virtuelles dans une implémentation existante.<br><br>- Comme il y a eu tellement de standardisation de données dans la version actuelle de Dynamics AX, il est devenu très difficile de savoir quoi ajouter aux ensembles de tables. Par exemple, il est difficile de savoir quelle table partager. Toutes les tables référencées à partir des tables qui sont dans une société virtuelle doivent également être ajoutées. Du fait de la standardisation des tables, même une diffusion de données principales entre une multitude de tables doit faire partie de la société virtuelle. Toute erreur faite ici provoquera des problèmes fonctionnels.<br><br>- Lorsqu’une table fait partie d’une société virtuelle, elle perd les informations sur l’origine des données, et seule la société virtuelle est enregistrée.   |
| **Remplacé par une autre fonctionnalité ?** | Les tables générales peuvent être utilisées pour rendre des tables accessibles à partir de toutes les sociétés. Actuellement, il n’existe aucune fonction de remplacement. |   
| **Zones de produit affectées**       | Tous les modules |   
| **Statut**                       | Supprimé à partir de Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>Application pour tablettes Windows 8

L’application pour tablettes Windows 8 a fourni la fonctionnalité pour la saisie et l’approbation des dépenses.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Finance and Operations est compatible avec les tablettes. L’application pour tablettes n’est plus nécessaire.    |
| **Remplacé par une autre fonctionnalité ?**   | N°          |
| **Zones de produit affectées**         | Gestion des dépenses   |
| **Statut**                         | Supprimé : cette fonctionnalité n’est disponible que pour Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Planificateur de travail

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Faible utilisation |
| **Remplacé par une autre fonctionnalité ?**   | Non, mais la page **Relation de profil**, qui est ouverte sur la page **Groupes de profils**, prend en charge le même scénario que la page **Workplanner** abandonnée. |
| **Zones de produit affectées**         | Pointage     |
| **Statut**                         | Le code n’a pas été supprimé. Toutefois, l’écran, JmgWorkPlanner, n’a pas été migré.    |

### <a name="x-financial-statements"></a>Tableaux d’analyse X++

| &nbsp;  | &nbsp; |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Motif de l’abandon/de la suppression</strong> |                         Cette fonctionnalité a été remplacée par une autre.                         |
|  <strong>Remplacé par une autre fonctionnalité ?</strong>  | Management Reporter (appelé <strong>États financiers</strong> dans la version actuelle de Dynamics AX) |
|     <strong>Zones de produit affectées</strong>     |                                              Comptabilité                                              |
|             <strong>Statut</strong>             |                                      Supprimé à partir de Dynamics AX 2012                                      |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]