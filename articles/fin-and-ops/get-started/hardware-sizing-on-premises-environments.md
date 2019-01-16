---
title: "Configuration requise pour le calibrage de matériel pour les environnements sur site"
description: "Cette rubrique répertorie la configuration requise pour le calibrage de matériel pour les environnements sur site."
author: kfend
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: d277bc4c4c815317bade8a04b9111232fb707086
ms.contentlocale: fr-fr
ms.lasthandoff: 12/18/2018

---

# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>Configuration requise pour le calibrage de matériel pour les environnements sur site

[!include [banner](../includes/banner.md)]

Avant de commencer le processus de calibrage du matériel et de l'infrastructure pour un environnement sur site, familiarisez-vous avec la [Configuration requise](system-requirements.md) et les [Instructions de paramétrage et de déploiement](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md) pour obtenir des connaissances approfondies de l'infrastructure sous-jacente.

> [!NOTE]
> Faites attention aux meilleures pratiques de paramétrage système pour des résultats optimaux.

Après avoir vérifié la documentation, vous pouvez commencer le processus d'évaluation de votre volume transactionnel et d'utilisateur simultanés et calibrer votre environnement selon le débit moyen du noyau.

## <a name="factors-that-affect-sizing"></a>Facteurs qui affectent le calibrage

Tous les facteurs affichés dans l'illustration suivante contribuent au calibrage. Plus les informations collectées sont détaillées, plus vous pouvez déterminer précisément le calibrage. Le calibrage du matériel, sans données de prise en charge, est susceptible d'être inexact. La configuration requise minimale pour les données nécessaires est la ligne de transaction de chargement de pointe horaire.

[![Calibrage du matériel pour les environnements sur site](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

De gauche à droite, le premier facteur, et le plus important, nécessaire pour estimer précisément le calibrage est un profil de transaction ou une caractérisation de transaction. Il est important de toujours rechercher le volume transactionnel de pointe horaire. S'il existe des plusieurs périodes de pointe, ces périodes doivent être précisément définies.

À mesure que vous comprenez la charge qui impacte votre infrastructure, vous devez également comprendre plus en détails les facteurs suivants :

- **Transactions** : Les transactions ont généralement certaines pointes au cours à jour de la même journée/semaine. Cela dépend la plupart du temps du type de transaction. Les entrées de temps et de dépenses affichent généralement des pointes une fois par semaine, alors que les entrées de commande client arrivent souvent en vrac via l'intégration ou arrivent au goutte à goutte pendant la journée.
- **Nombre d'utilisateurs simultanés** : Le nombre d'utilisateurs simultanés est le deuxième facteur de calibrage. Vous ne pouvez pas obtenir des estimations de calibrage fiables selon le nombre d'utilisateurs simultanés, ce qui signifie que si ce sont les seules données disponibles, estimez un nombre approximatif, puis révisez-le lorsque vous avez davantage de données. Une définition exacte d'utilisateur simultané signifie que :

    - Les utilisateurs nommés ne sont pas des utilisateurs simultanés.
    - Les utilisateurs simultanés sont toujours un sous-ensemble d'utilisateurs nommés. 
    - La charge de travail de pointe définit la simultanéité maximale du calibrage.

    Les critères pour les utilisateurs simultanés nécessitent qu'ils satisfassent aux critères suivants :

    - Connecté.
    - Exécution de transactions/recherches lors du comptage.
    - Pas une session inactive.

- **Composition des données** : Concerne principalement la configuration et le paramétrage de votre système. Par exemple, combien d'entités juridiques vous aurez, le nombre d'articles, le nombre de niveaux de nomenclature, et la manière dont le paramétrage complexe de la sécurité sera effectué. Chacun de ces facteurs peut avoir un petit impact sur les performances, de sorte que les facteurs puissent être contrepassés à l'aide de choix intelligents quand il s'agit de l'infrastructure.
- **Extensions** : Les personnalisations peuvent être simples ou complexes. Le nombre de personnalisations et la nature de la complexité et de l'utilisation a un impact variable sur la taille de l'infrastructure requise. Pour des personnalisations complexes, il est recommandé d'effectuer des évaluations des performances pour vérifier qu'elles sont pas uniquement testées pour le rendement mais pour aider également à comprendre les besoins de l'infrastructure. Cela est encore plus essentiel lorsque des extensions ne sont pas codées selon les meilleures pratiques de performances et d'évolutivité.
- **Génération d'états et analyses** : Ces facteurs incluent des requêtes lourdes par rapport aux différentes bases de données des systèmes de base de données Finance and Operations. Compréhension et réduction de la fréquence lorsque l'exécution coûteuse d'états vous permettra de comprendre l'impact de ceux-ci.
- **Solutions tierces** : Ces solutions, comme les éditeurs de logiciels, ont les mêmes implications et recommandations que les extensions.

## <a name="sizing-your-finance-and-operations-environment"></a>Calibrage de votre environnement Finance and Operations

Pour comprendre vos besoins en calibrage, vous devez connaître le volume de pointe des transactions que vous devez traiter. La plupart des systèmes connexes, comme Management Reporter ou SSRS, sont moins critiques pour la mission. Par conséquent, ce document se concentre principalement sur Microsoft Dynamics AX Application Object Server (AOS) et SQL Server.

> [!NOTE]
> En général, les niveaux de calcul montent en puissance et doivent être paramétrés de façon N+1, c.-à-d. si vous estimez trois Microsoft Dynamics AX Application Object Server (AOS), ajoutez un quatrième Microsoft Dynamics AX Application Object Server (AOS). Le niveau de base de données doit être configuré avec un paramétrage à haute disponibilité Always-On.

## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Calibrage

- 3 000 à 15 000 lignes de transaction par heure par noyau sur le serveur de base de données.
- Taux de noyau Microsoft Dynamics AX Application Object Server (AOS) vers SQL de 3:1 pour le SQL Server principal. Les noyaux supplémentaires sont requis conformément à la configuration à haute disponibilité choisie.

    - Le traitement des opérations lourdes de base de données peut faire régresser cela à 2:1.

- Les facteurs suivants influencent les variations :

    - Les paramètres utilisés.
    - Les niveaux d'extensions.
    - Utilisation de fonctionnalités supplémentaires, telles que le journal de base de données et les alertes. L'enregistrement de base de données extrême réduire davantage le débit horaire par noyau sous le niveau de 3 000 lignes.
    - Complexité de la composition des données : Un plan de comptes unique et un plan de comptes détaillé a des implications sur le débit (comme exemple).
    - Caractérisation de la transaction.
    - 2 Go à 4 Go de mémoire pour chaque noyau.
    - Les bases de données auxiliaires sur le serveur de base de données comme bases de données Management reporter et SSRS.
    - Temp DB = 15 % de la taille de la base de données, avec autant de fichiers comme processeurs physiques.
    - Taille et débit du réseau SAN basés sur le volume/l'utilisation totaux de la transaction simultanée.

### <a name="high-availability"></a>Haute disponibilité

Nous vous recommandons de toujours utiliser SQL Server dans un cluster ou une configuration en miroir. Le second nœud SQL doit avoir le même nombre de noyaux que le nœud principal.

### <a name="active-directory-federation-services-ad-fs"></a>Services ADFS (Active Directory Federation Services)

Pour le calibrage d'AD FS, voir la [documentation relative à la capacité du server AD FS](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

Une [feuille de calibrage](http://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx) est disponible pour planifier le nombre d'instances dans votre déploiement.

## <a name="aos-online-and-batch"></a>Microsoft Dynamics AX Application Object Server (AOS) (en ligne et par traitement par lots)

### <a name="sizing"></a>Calibrage

- Calibrage par volume/utilisation de transactions

    - 2 000 à 6 000 lignes par noyau
    - 16 Go par instance
    - Cadre standard – 4 à 24 noyaux
    - 10 à 15 utilisateurs professionnels par noyau
    - 15 à 25 utilisateurs d'Activity par noyau
    - 25 à 50 membres d'équipe par noyau

- Traitement par lots

    - 1 à 4 threads de traitement par lots par noyau
    - Calibrage basé sur la caractérisation de la fenêtre de traitement par lots

- Notez que Microsoft Dynamics AX Application Object Server (AOS), la gestion des données, et le traitement par lots ont le même rôle dans Service Fabric. Vous devez calibrer ces trois charges de travail combinées, et ne pas les séparer comme dans Microsoft Dynamics AX 2012.
- Les mêmes facteurs de variabilité pour SQL Server s'appliquent ici.

### <a name="high-availability"></a>Haute disponibilité

- Assurez-vous que vous disposez d'au moins 1 à 2 Microsoft Dynamics AX Application Object Server (AOS) disponibles de plus que vous estimez.
- Assurez-vous d'avoir au moins 3 à 4 hôtes virtuels disponibles.

## <a name="management-reporter"></a>Management Reporter

Dans la plupart des cas, à moins qu'utilisés intensivement, la configuration requise minimale recommande d'utiliser deux nœuds. Seuls dans les cas où il existe une utilisation intensif vous aurez besoin de plus de deux nœuds. Effectuez une mise à l'échelle au besoin.

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services

Pour le lancement général de disponibilité, seul un nœud SSRS peut être déployé. Surveillez votre nœud SSRS lors de test et augmentez le nombre de noyaux disponibles pour SSRS au besoin. Veillez à ce que vous ayez un nœud secondaire préconfiguré disponible sur un hôte virtuel qui est différent de celui indiqué dans la VM SSRS. Cela est important s'il y a un problème avec la machine virtuelle qui héberge SSRS ou le serveur virtuel. Si tel est le cas, elle doit être remplacée.

## <a name="environment-orchestrator"></a>Orchestrateur d'environnement

Le service Orchestrator est le service qui assure le déploiement et les communications liées à LCS. Ce service est déployé comme Service Fabric principal et nécessite au moins trois VM. Ce service est coïmplanté avec les services d'orchestration Service Fabric. Ils doivent être calibrés en fonction de la charge de pointe du cluster. Pour plus d'informations, voir [Considérations relatives à la planification de la capacité du cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-capacity).

## <a name="virtualization-and-oversubscription"></a>Virtualisation et sursouscription

Les services critiques pour la mission comme Microsoft Dynamics AX Application Object Server (AOS) doivent être hébergés sur des hôtes virtuels qui ont des ressources dédiées : des noyaux, de la mémoire et un disque.

