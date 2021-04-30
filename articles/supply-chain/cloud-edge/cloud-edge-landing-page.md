---
title: Utiliser des unités d'échelle pour augmenter la résilience des charges de travail de Supply Chain Management
description: Cette rubrique fournit des informations sur les unités d’échelle de Cloud et de Edge pour les charges de travail de fabrication et de gestion d’entrepôt.
author: cabeln
ms.date: 04/13/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c47088edd89413d196e904bc7eaa115585bf8464
ms.sourcegitcommit: 639175a39da38edd13e21eeb5a1a5ca62fa44d99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "5899141"
---
# <a name="use-scale-units-to-help-increase-resilience-for-supply-chain-management-workloads"></a>Utiliser des unités d'échelle pour augmenter la résilience des charges de travail de Supply Chain Management

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> La fonctionnalité d'unité d'échelle pour Microsoft Dynamics 365 Supply Chain Management est mise à votre disposition selon les conditions qui régissent l'utilisation du service. Pour plus d’informations, consultez les [Informations légales de Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> En activant les unités d’échelle cloud et Edge, vous confirmez que vous comprenez que certaines données liées à la configuration et au traitement des unités d’échelle cloud et Edge peuvent être stockées dans un centre de données situé aux États-Unis. Pour en savoir plus sur le traitement des données pour les unités d'échelle cloud et de périphérie, consultez la section [Traitement des données lors de la gestion des unités d'échelle](#data-processing-management), plus loin dans cette rubrique.

## <a name="core-value-proposition-for-scale-units"></a>Proposition de valeur fondamentale pour les unités d'échelle

Les entreprises qui travaillent avec la fabrication et la distribution doivent être en mesure d’exécuter des processus commerciaux clés 24 heures sur 24, 7 jours sur 7, sans interruption et à grande échelle. Les unités à l’échelle du Cloud et de Edge permettent aux entreprises d’exécuter sans interruption des processus de fabrication et d’entrepôt critiques, même lorsqu’elles sont confrontées à des problèmes occasionnels de connectivité réseau ou de latence.

Les unités d’échelle du Cloud et de Edge permettent la répartition des charges de travail d’exécution de l’atelier et de l’entrepôt entre différents environnements. Cette fonctionnalité peut aider à améliorer les performances, à éviter les interruptions de service et à maximiser la disponibilité. Les unités d'échelle sont fournies via les compléments suivants pour votre abonnement Supply Chain Management :

- Complément Cloud Scale Unit pour Dynamics 365 Supply Chain Management (*disponible en avril 2021*)
- Complément Edge Scale Unit pour Dynamics 365 Supply Chain Management (*disponible prochainement*)

Les fonctionnalités de charge de travail sont publiées en continu au travers d'améliorations incrémentielles.

## <a name="scale-units-and-dedicated-workloads"></a>Unités de mise à l’échelle et charges de travail dédiées

Les unités de mise à l’échelle étendent votre environnement de hub Supply Chain Management central en ajoutant une capacité de traitement dédiée. Les unités de mise à l’échelle peuvent s’exécuter dans le cloud. Elle peuvent également fonctionner en périphérie, sur site dans les locaux de votre établissement.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 avec unités de mise à l’échelle":::

Les unités d'échelle offrent résilience, fiabilité et évolutivité pour les charges de travail affectées. Les unités d'échelle en périphérie peuvent être temporairement déconnectées de l'environnement du hub cloud, et les employés peuvent continuer à travailler sur les charges de travail affectées en périphérie.

Une *charge de travail* est un ensemble défini de fonctionnalités d’entreprise qui peut être factorisé et délégué à une unité d’échelle. Bien que la charge de travail pour la gestion de l'entrepôt ait été publiée, la charge de travail pour l'exécution de la fabrication est toujours en version préliminaire.

Vous pouvez configurer un environnement de hub et les unités d'échelle cloud pour des charges de travail sélectionnées à l’aide du [portail de gestionnaire d’unité d’échelle](https://sum.dynamics.com). Vous pouvez également affecter plusieurs charges de travail par unité d'échelle. Pour plus d'informations sur les conditions préalables et les limitations des unités d'échelle cloud dans la version actuelle, consultez la section [Conditions préalables et limitations pour les unités d'échelle cloud](#cloud-scale-unit-prerequisites), plus loin dans cette rubrique.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Capacités de charge de travail de gestion d’unité d’échelle dédiées dans une unité d’échelle

La charge de travail de gestion de l'entrepôt est la première charge de travail distribuée pour les unités d'échelle qui a été publiée en disponibilité générale.

Pour la gestion de l'entrepôt, les unités d'échelle offrent les fonctionnalités suivantes :

- Le système peut traiter des méthodes de vague sélectionnées pour les commandes client et le réapprovisionnement de la demande.
- Les employés de l’entrepôt peuvent exécuter les ventes et demander le travail d’entrepôt de réapprovisionnement à l’aide de l’application mobile Gestion des entrepôts.
- Les employés de l’entrepôt peuvent se renseigner sur les stocks disponibles à l’aide de l’application mobile Gestion des entrepôts.
- Les employés de l’entrepôt peuvent créer et exécuter des mouvements de stock à l’aide de l’application mobile Gestion des entrepôts.
- Les employés des entrepôts peuvent enregistrer des commandes fournisseur et faire du rangement en utilisant l’application mobile Gestion des entrepôts.

Pour plus d’informations, voir [Charges de travail de gestion des entrepôts pour les unités d’échelle cloud et de périphérie](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Capacités de charge de travail d’exécution de fabrication dédiées dans une unité d’échelle

La première parution de la charge de travail de fabrication est actuellement en version préliminaire et offre les fonctionnalités suivantes :

- Les opérateurs de machines et les superviseurs d’atelier peuvent accéder au plan de production opérationnel.
- Les opérateurs de machine peuvent maintenir le plan à jour en exécutant des tâches de fabrication discrètes et de processus.
- Le superviseur de l’atelier peut ajuster le plan opérationnel.
- Les collaborateurs peuvent accéder aux heures et aux présences pour les points d’entrée et de sortie à la périphérie, afin de garantir un calcul correct de leur rémunération.

Pour plus d’informations, voir [Charges de travail d’exécution de la fabrication pour les unités d’échelle cloud et de périphérie](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Éléments à prendre en compte avant d'activer la topologie hybride distribuée pour Supply Chain Management

En activant la topologie hybride distribuée, vous transformez votre environnement cloud Supply Chain Management afin qu'il fonctionne comme un hub. Vous pouvez également associer des environnements supplémentaires configurés en tant qu'unités d'échelle dans le cloud ou en périphérie.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Conditions préalables et limitations pour les unités d'échelle cloud

Dans la version actuelle des unités d'échelle, certaines fonctionnalités ne sont pas encore disponibles, mais peuvent être ajoutées dans les versions incrémentielles au fil du temps.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Vous devez être un client sous licence de Supply Chain Management

Pour intégrer la topologie distribuée, vous devez disposer d'une licence Supply Chain Management. Votre environnement cloud existant deviendra le hub de votre topologie hybride. Vous pouvez déclarer à la fois les environnements de bac à sable et les environnements de production en tant qu'environnements de hub, et vous pouvez ajouter des unités d'échelle en fonction des compléments que vous acquérez.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>Votre projet existant doit être administré via la version commerciale globale de LCS

Votre projet Microsoft Dynamics Lifecyle Services (LCS) existant doit répondre aux exigences de version suivantes :

- Le projet doit être administré via la version commerciale globale de LCS à l'adresse [lcs.dynamics.com](https://lcs.dynamics.com).
- Les versions locales de LCS (telles que [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) et [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)) ne sont pas pris en charge.
- Les versions Governmental Cloud de LCS ne sont pas prises en charge.
- La version Mooncake de LCS n'est pas prise en charge.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>Votre environnement de production actuel doit être de type Libre service dans LCS.

Votre environnement de production actuel doit être étiqueté avec le type **Libre service** type in LCS. Ce type indique que le locataire de votre projet LCS a déjà été converti afin de prendre en charge le modèle d'hébergement Azure Service Fabric.

> [!IMPORTANT]
> Les types d'environnement qui s'exécutent en tant qu'infrastructure en tant que service (IaaS) ne sont pas pris en charge. Ces environnements sont généralement étiquetés avec le type **Géré par Microsoft** dans LCS. Si vous disposez d'environnements de ce type, collaborez avec votre contact Microsoft pour établir la chronologie de votre migration vers le type **Libre service**.

Microsoft est en train de faire passer tous les environnements cloud de Supply Chain Management d'un modèle IaaS à une topologie hébergée dans Service Fabric. Cette transition apporte une meilleure évolutivité et facilite la gestion des services. Par conséquent, les opérations de déploiement et de maintenance sont plus rapides. De même, les composants de service sont en cours de migration vers le concept de microservices, et le modèle d'hébergement de services va [opérer une transition](https://docs.microsoft.com/virtualization/windowscontainers/about/containers-vs-vm) d'un modèle de machine virtuelle (VM) à une architecture conteneurisée légère.

Pour finir, la même infrastructure de services en conteneurs basée sur Service Fabric alimentera à la fois les instances cloud et de périphérie du service, que l'instance soit un hub dans le cloud ou une unité d'échelle dans le cloud ou en périphérie.

Avant de pouvoir intégrer la topologie hybride qui prend en charge les unités d'échelle, le locataire de votre projet doit être transféré vers le modèle hébergé par Service Fabric. En outre, tout environnement qui fera office de hub doit être converti.

> [!TIP]
> Pour vous renseigner sur le statut du locataire de votre projet LCS, recherchez le type de votre environnement dans [LCS](https://lcs.dynamics.com/), ou contactez votre partenaire ou votre contact Microsoft.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>Les environnements de données d'entreprise locaux (sur site) ne sont pas pris en charge en tant que hubs pour les unités d'échelle

Les environnements sur site ne peuvent pas fonctionner comme hubs pour les unités d'échelle. Les environnements hub doivent toujours être hébergés dans le cloud.

#### <a name="scale-unit-management-capabilities-are-limited"></a>Les fonctionnalités de gestion des unités d'échelle sont limitées

Les fonctionnalités de gestion utiles pour déplacer les charges de travail sont limitées. Certaines opérations de gestion ne sont pas prises en charge en libre service, et vous devrez peut-être demander une assistance à votre partenaire ou contact Microsoft. Les exemples incluent des déplacements de charge de travail entre unités d'échelle et des déplacements ponctuels provisoires dans le cadre de scénarios catastrophe.

#### <a name="metrics-and-measurements-arent-yet-available"></a>Les métriques et les mesures ne sont pas encore disponibles

Les métriques et mesures susceptibles de vous aider à sélectionner la meilleure application pour vos unités d'échelle ne sont pas encore disponibles. Collaborez avec votre contact Microsoft ou votre partenaire d'implémentation pour sélectionner l'application la plus avantageuse.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Traitement des données lors de la gestion des unités d'échelle

Lorsque vous activez votre environnement Dynamics 365 pour prendre en charge la topologie hybride distribuée pour les unités d'échelle cloud et de périphérie, certains services de gestion seront hébergés uniquement aux États-Unis, comme pour LCS. Ce comportement affecte le transfert et le stockage de certaines informations administratives et de configuration utilisées par le [portail de gestionnaire d’unité d’échelle](https://sum.dynamics.com). Voici quelques exemples :

- Vos noms et ID de locataire
- Vos ID de projet LCS
- Les adresses e-mail de l'administrateur et du propriétaire du projet utilisées pour la connexion
- Les ID d’environnement pour le hub et les unités d’échelle
- Les configurations de charge de travail, y compris les noms et adresses physiques des entités juridiques et des établissements, afin que votre topologie puisse être affichée sur une carte géographique
- Les mesures collectées (telles que la latence et le débit) qui seront affichées sur la page d'analyse de la carte pour vous aider à sélectionner l'emploi le plus avantageux de vos unités d'échelle

Les données transférées et stockées dans les centres de données des États-Unis seront supprimées conformément aux politiques de conservation des données de Microsoft. La protection de vos données personnelles est importante pour Microsoft. Pour en savoir plus, lisez notre [Déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboarding-in-two-stages"></a>L'intégration en deux phases

Le processus d'intégration à la topologie hybride distribuée comporte deux phases. Au cours de la première phase, vous devez valider les personnalisations pour vous assurer qu'elles fonctionnent dans la topologie distribuée qui comporte les unités d'échelle. Les environnements de bac à sable et de production ne sont déplacés qu'au cours de la deuxième phase.

### <a name="stage-1-evaluate-customizations-in-one-box-development-environments"></a>Phase 1 : évaluer les personnalisations dans des environnements de développement monoblocs

Avant de commencer à intégrer vos environnements bac à sable ou de production, nous vous recommandons d'explorer les unités d'échelle dans une configuration de développement, comme un environnement monobloc (également appelé environnement de niveau 1), afin de pouvoir valider les processus, les personnalisations et les solutions. Au cours de cette phase, les données et les personnalisations seront appliquées aux environnements monoblocs. Un environnement prend le rôle de hub, et l'autre prend le rôle d'unité d'échelle. Cette configuration constitue le meilleur moyen d'identifier et de résoudre les problèmes. La dernière version en accès anticipé (PEAP) peut également être utilisée pour accomplir cette phase.

Pour la phase 1, vous devez utiliser les [outils de déploiement d'unité d'échelle pour les environnements de développement monoblocs](https://github.com/microsoft/SCMScaleUnitDevTools). Ces outils vous permettent de configurer le hub et les unités d'échelle dans un ou deux environnements monoblocs distincts. Les outils sont fournis sous forme de version binaire et en code source sur GitHub. Consultez le wiki du projet, qui comprend un [Guide d'utilisation pas à pas](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) qui décrit l'utilisation des outils.

### <a name="stage-2-acquire-add-ins-and-deploy-in-your-sandbox-and-production-environments"></a>Phase 2 : acquérir des compléments et les déployer dans vos environnements bac à sable et de production

Pour intégrer l'un de vos environnements de bac à sable ou de production à la nouvelle topologie, vous devez acquérir des compléments pour une ou plusieurs unités d'échelle cloud (et, à l'avenir, pour les unités d'échelle de périphérie). Les compléments attribueront les emplacements de projet et d'environnement correspondants dans [LCS](https://lcs.dynamics.com/) afin que les environnements d'unité d'échelle puissent être déployés.

> [!NOTE]
> Les compléments d'unité d'échelle ne sont pas couplés à un nombre limité d'utilisateurs, mais peuvent être utilisés par n'importe quel utilisateur de l'abonnement existant, en fonction des rôles attribués par l'administrateur.

Les unités d'échelle sont proposées dans le cadre de plusieurs unités de gestion des stocks (SKU) et options de tarification. Par conséquent, vous pouvez choisir l'option qui répond le mieux à votre volume de transactions mensuel prévu et à vos exigences de performances.

La SKU d'entrée de gamme est connue sous le nom de *Basique*, et la SKU la plus performante est connue sous le nom de *Standard*. Chaque SKU est préchargée avec un nombre spécifique de transactions mensuelles. Cependant, vous pouvez augmenter le budget mensuel des transactions en ajoutant des compléments de dépassement pour chaque SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Compléments pour les unités d'échelle cloud":::

> [!TIP]
> Pour identifier le dimensionnement qui répond le mieux à vos besoins, collaborez avec votre partenaire et Microsoft pour comprendre la taille de transaction mensuelle dont vous avez besoin.

L'achat de chaque complément d'unité d'échelle vous donne non seulement un volume mensuel de transactions, mais vous donne également droit à un nombre spécifique d'emplacements d'environnement dans LCS. Pour chaque complément d'unité d'échelle cloud, vous avez droit à un nouvel emplacement de production et un nouvel emplacement sandbox. Au cours du processus d'intégration, un nouveau projet LCS sera ajouté avec ces emplacements. Les droits d'utilisation des emplacements sont liés, de sorte que les emplacements doivent être utilisés comme unités d'échelle disposant d'un hub cloud.

Les compléments excédentaires ne vous donnent pas droit à de nouveaux emplacements d'environnement.

Si vous souhaitez acquérir plus d'environnements bac à sable, vous pouvez acheter des emplacements sandbox standards supplémentaires. Microsoft peut ensuite vous aider à activer ces emplacements en tant qu'unités d'échelle bac à sable pour la topologie hybride.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Intégrer la topologie hybride distribuée pour Supply Chain Management

### <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Sélectionner le locataire de votre projet LCS et le processus d’intégration détaillé

Une fois que vous avez terminé de planifier la manière dont vous intégrerez la topologie hybride distribuée pour Supply Chain Management, vous utiliserez le [portail de gestionnaire d’unité d’échelle](https://aka.ms/SCMSUM) pour commencer le processus d'intégration. Dans le portail, sélectionnez l'onglet **Locataires Dynamics 365**. Cet onglet affiche la liste des locataires dont votre compte fait partie et dont vous êtes propriétaire ou administrateur d’environnement pour un projet LCS.

Si le locataire que vous recherchez ne figure pas dans la liste, accédez à [LCS](https://lcs.dynamics.com/v2) et assurez-vous que vous êtes un administrateur d’environnement ou un propriétaire de projet du projet LCS pour ce locataire. Seuls les comptes Azure Active Directory (Azure AD) du locataire sélectionné sont autorisés à mener à bien l’inscription.

> [!NOTE]
> Une fois que vous avez appliqué les modifications à LCS, la liste des locataires peut prendre jusqu’à 30 minutes pour refléter les modifications.

Pour chaque locataire, la liste affiche le statut de l'intégration.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Liste des locataires sous l'onglet Locataires Dynamics 365":::

Sélectionnez **Cliquer ici pour commencer** pour demander l'intégration du locataire LCS. Vous devez accepter les conditions. Vous devez également fournir une adresse e-mail professionnelle à laquelle Microsoft peut envoyer des communications liées au processus d’intégration.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Soumission d’inscription d’un locataire":::

Microsoft examinera votre demande et vous informera des étapes suivantes en envoyant un e-mail à l’adresse que vous avez indiquée sur le formulaire d’inscription. Microsoft travaillera en étroite collaboration avec vous pour activer les unités d'échelle dans la topologie hybride pour votre scénario d'entreprise.

Une fois l'intégration terminée, vous pouvez utiliser le port pour configurer les unités d'échelle et les charges de travail.

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gérez les unités d’échelle cloud et les charges de travail à l’aide du portail de gestionnaire d’unité d’échelle

Aller au [portail de gestionnaire d’unité d’échelle](https://aka.ms/SCMSUM) et connectez-vous à l’aide de votre compte de locataire. Sur la page **Configurer les unités d’échelle**, vous pouvez ajouter un environnement de hub s’il n’est pas déjà répertorié. Vous pouvez ensuite sélectionner le hub que vous souhaitez configurer avec des unités d’échelle et des charges de travail.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Expérience de gestion des unités d’échelle et de la charge de travail":::

Pour ajouter une ou plusieurs unités d’échelle disponibles dans vos abonnements, sélectionnez **Ajouter des unités d’échelle**.

Sur l’onglet **Charges de travail définies**, utilisez le bouton **Créer une charge de travail** pour ajouter une charge de travail de gestion d’entrepôt à l’une de vos unités d’échelle. Pour chaque charge de travail, vous devez spécifier le contexte des processus qui appartiendront à la charge de travail. Pour les charges de travail de gestion d’entrepôt, le contexte est un entrepôt spécifique dans un site et une entité juridique spécifiques.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Création de charge de travail":::

> [!TIP]
> Au fil du temps, des améliorations incrémentielles seront ajoutées à l'expérience de gestionnaire des unités d'échelle pour faciliter les opérations de gestion du cycle de vie. Les fonctionnalités spécifiques de la version actuelle sont documentées dans un manuel d'intégration mis à la disposition des clients qui sont en cours d'intégration à la topologie hybride distribuée pour Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
