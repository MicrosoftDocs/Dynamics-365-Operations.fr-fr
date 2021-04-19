---
title: Gestion des unités d’échelle du Cloud et de Edge avec les charges de travail de fabrication et de gestion de l’entreposage
description: Cette rubrique fournit des informations sur les unités d’échelle de Cloud et de Edge pour les charges de travail de fabrication et de gestion d’entrepôt.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3eacc9d0cf53fa8af3ff166006cb8fab32445331
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836708"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Gestion des unités d’échelle du Cloud et de Edge avec les charges de travail de fabrication et de gestion de l’entreposage

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Les unités d’échelle du Cloud et de Edge permettent la répartition des charges de travail d’exécution de l’atelier et de l’entrepôt entre différents environnements. Cette fonctionnalité peut aider à améliorer les performances, à éviter les interruptions de service et à maximiser la disponibilité. Il est fourni par les compléments suivants :

- Complément Cloud Scale Unit pour Dynamics 365 Supply Chain Management
- Complément d’unité d’échelle Edge pour Dynamics 365 Supply Chain Management

Les entreprises qui travaillent avec la fabrication et la distribution doivent être en mesure d’exécuter des processus commerciaux clés 24 heures sur 24, 7 jours sur 7, sans interruption et à grande échelle. Les unités à l’échelle du Cloud et de Edge permettent aux entreprises d’exécuter sans interruption des processus de fabrication et d’entrepôt critiques, même lorsqu’elles sont confrontées à des problèmes occasionnels de connectivité réseau ou de latence.

## <a name="public-preview-information"></a>Informations de version préliminaire publique

La version préliminaire fournit un environnement qui fonctionne comme un hub basé sur le cloud de votre environnement Dynamics 365 Supply Chain Management et un environnement qui fonctionne comme une unité à l’échelle du cloud.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Aperçu de la disponibilité

L’aperçu des unités à l’échelle du Cloud et de Edge sera disponible pour les clients existants de Supply Chain Management en octobre 2020.

Pour accéder à la version préliminaire d’octobre 10.0.15/Platform update 39 pour le déploiement dans votre environnement [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2) vous devez faire partie du programme d’accès anticipé en version préliminaire (également appelé PEAP) pour Supply Chain Management. Vous pouvez rejoindre PEAP si vous êtes déjà membre du [Programme Dynamics Insider](https://experience.dynamics.com/insider) plus large. Sélectionnez simplement le programme spécifique nommé "Finance & Operations : programme d’accès anticipé en version préliminaire (PEAP)."

> [!IMPORTANT]
> La capacité d’unité d’échelle pour Supply Chain Management n’est disponible que si vous acceptez les [conditions de la version préliminaire du Cloud + Edge pour Finance and Operations](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Traitement des données pour la version préliminaire

Lors de la version préliminaire publique, certains services de gestion ne seront hébergés qu’aux États-Unis. Cependant, lorsque la fonctionnalité sera généralement disponible, ces services de gestion seront disponibles dans toutes les zones géographiques prises en charge par Supply Chain Management. Cela affecte le transfert et le stockage des informations administratives utilisées par le gestionnaire d’unité d’échelle, notamment :

- Vos noms et ID de locataire
- Vos ID de projet LCS
- E-mails de l’administrateur utilisés pour se connecter
- ID d’environnement pour le hub et les unités d’échelle
- Configurations des charges de travail
- Mesures collectées (telles que la latence et le débit) qui sont affichées sur la page d’analyse de la carte

Les données transférées et stockées dans les centres de données américains seront supprimées lorsque vos environnements de version préliminaire seront arrêtés.

### <a name="sign-up-for-the-preview"></a>Souscrire un aperçu

Pour vous inscrire à la version préliminaire de Cloud et Edge de Supply Chain Management, votre organisation doit déjà disposer d’un environnement cloud de Supply Chain Management en direct.

Les capacités de l’unité d’échelle sont actuellement en version préliminaire publique. Lorsque vous vous inscrivez, vous devez utiliser un compte d’utilisateur sur le locataire spécifique. Vous devez également être propriétaire de projet ou administrateur d’environnement dans LCS pour un projet Dynamics 365 LCS actif dans ce client.

Lorsque vous vous inscrivez à la version préliminaire, vous sélectionnez un locataire et suivez les étapes d’inscription. Dès que Microsoft pourra allouer une capacité de version préliminaire, nous vous enverrons un e-mail contenant les détails de mise en service et les codes de promotion (promo) pour deux environnements (un hub et une unité de mise à l’échelle) pour le projet LCS approprié. Vous pourrez ensuite déployer les deux environnements en tant qu’environnements sandbox de niveau 2. Ces environnements seront valables 60 jours à compter de la date de création des codes promotionnels. Vous ne devez pas utiliser les deux environnements tant que l’étape décrite dans le paragraphe suivant n’est pas terminée.

Une fois que vous avez confirmé avec Microsoft que les deux environnements ont été déployés à l’aide des codes promotionnels, l’un des environnements sera configuré pour fonctionner comme un hub et l’autre sera configuré pour fonctionner comme une unité d’échelle. Vous pouvez ensuite configurer les unités d’échelle et déployer les charges de travail de gestion et de fabrication de l’entrepôt sélectionnées à l’aide du [portail de gestionnaire d’unité d’échelle](https://aka.ms/SCMSUM).

Les environnements de version préliminaire seront automatiquement supprimés après 60 jours. Cependant, ils peuvent être supprimés plus tôt s’il semble qu’ils ne sont pas utilisés. Une fois vos environnements de version préliminaire supprimés, vous pouvez vous inscrire et faire la queue pour un nouveau déploiement de version préliminaire.

Pour vous inscrire à la version préliminaire, accédez au [portail de gestionnaire d’unité d’échelle](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Limitations applicables pendant la période de version préliminaire

> [!IMPORTANT]
> Pour la phase initiale du programme de version préliminaire de cette fonctionnalité, Microsoft prend en charge uniquement les hubs qui ont des unités à l’échelle du cloud, et non les hubs qui ont des unités à l’échelle Edge. Les unités à l’échelle Edge sont installées sur site et devraient être disponibles au cours d’une phase à venir du programme.

Étant donné que les unités d’échelle cloud et Edge sont une fonctionnalité version préliminaire, les services qui leur sont associés sont actuellement disponibles dans des pays et des régions limités. En activant les unités d’échelle cloud et Edge, vous confirmez que vous comprenez que certaines données liées à la configuration et au traitement des unités d’échelle cloud et Edge peuvent être stockées dans un centre de données situé aux États-Unis. En activant les unités d’échelle cloud et Edge, vous acceptez également les [conditions de version préliminaire Cloud + Edge pour Finance and Operations](https://Aka.ms/SCMCnETerms). Pour en savoir plus sur les unités d’échelle du cloud et Edge, consultez la [Documentation](https://aka.ms/scmcne).

La protection de vos données personnelles est importante pour Microsoft. Pour en savoir plus, lisez notre [Déclaration de confidentialité](https://aka.ms/privacy).

> [!IMPORTANT]
> Certaines fonctionnalités d’entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque les charges de travail sont utilisées sur des unités d’échelle. Pour plus d’informations sur les charges de travail fonctionnelles, voir les sections plus loin dans cette rubrique.

## <a name="scale-units-and-dedicated-workloads"></a>Unités de mise à l’échelle et charges de travail dédiées

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 avec unités de mise à l’échelle":::

Les unités de mise à l’échelle étendent votre environnement de hub Supply Chain Management central en ajoutant une capacité de traitement dédiée. Les unités de mise à l’échelle peuvent s’exécuter dans le cloud. Ils peuvent également fonctionner sur Edge dans les locaux de votre établissement local. Les unités de mise à l’échelle peuvent être temporairement déconnectées de l’environnement du hub. Lorsqu’elles sont connectées, les unités de mise à l’échelle reçoivent toutes les informations nécessaires pour exécuter le traitement dédié pour les charges de travail affectées.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Options des unités de mise à l’échelle dans la version préliminaire publique":::

Pour la version préliminaire publique, vous pouvez configurer un environnement de hub avec des charges de travail sélectionnées sur une unité d’échelle cloud à l’aide du portail de gestionnaire d’unité d’échelle. Les participants à la version préliminaire qui ont accès à un environnement local de données commerciales locales (LBD) peuvent également configurer l’environnement LBD en tant qu’unité à l’échelle Edge.

Une charge de travail est un ensemble défini de fonctionnalités d’entreprise qui peut être factorisé et délégué à une unité d’échelle. Actuellement, les fonctionnalité d’évaluation présente deux types de charges de travail :

- Contrôle et suivi de la production
- Gestion des entrepôts

Vous pouvez affecter un de chaque type de charge de travail par unité d’échelle. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Capacités de charge de travail d’exécution de fabrication dédiées dans une unité d’échelle

Pour l’exécution de la fabrication, les unités à l’échelle du cloud et de Edge offrent les capacités suivantes, même lorsque les unités de Edge ne sont pas connectées au cloud :

- Les opérateurs de machines et les superviseurs d’atelier peuvent accéder au plan de production opérationnel.
- Les opérateurs de machine peuvent maintenir le plan à jour en exécutant des tâches de fabrication discrètes et de processus.
- Le superviseur de l’atelier peut ajuster le plan opérationnel.
- Les collaborateurs peuvent accéder aux heures et aux présences pour les points d’entrée et de sortie à la périphérie, afin de garantir un calcul correct de la rémunération des collaborateurs.

Pour plus d’informations, consultez les [détails de la charge de travail de l’unité d’échelle de fabrication](cloud-edge-workload-manufacturing.md).

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Capacités de charge de travail de gestion d’unité d’échelle dédiées dans une unité d’échelle

Pour la gestion d’unité d’échelle, les unités à l’échelle du cloud et de Edge offrent les capacités suivantes, même lorsque les unités de Edge ne sont pas connectées au cloud :

- Le traitement des méthodes de vague sélectionnées est activé pour les commandes client et le réapprovisionnement de la demande.
- Les employés de l’entrepôt peuvent exécuter les ventes et demander le travail d’entrepôt de réapprovisionnement à l’aide de l’application mobile Gestion des entrepôts.
- Les employés de l’entrepôt peuvent se renseigner sur les stocks disponibles à l’aide de l’application mobile Gestion des entrepôts.
- Les employés de l’entrepôt peuvent créer et exécuter des mouvements de stock à l’aide de l’application mobile Gestion des entrepôts.
- Les employés des entrepôts peuvent enregistrer des commandes fournisseur et faire du rangement en utilisant l’application mobile Gestion des entrepôts.

Pour plus d’informations, voir les [détails de la charge de travail de l’unité d’échelle de l’entrepôt](cloud-edge-workload-warehousing.md).

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Unités de mise à l’échelle embarquées pour votre environnement de Supply Chain Management

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Déployez la version préliminaire pour les unités d’échelle cloud et Edge

L’illustration suivante montre le flux d’inscription et de provisionnement pour la version préliminaire publique pour les unités d’échelle cloud.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Aperçu des étapes d’inscription":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Sélectionnez le locataire de votre projet LCS et le processus d’aperçu détaillé

Dans la version préliminaire publique, le [portail de gestionnaire d’unité d’échelle](https://aka.ms/SCMSUM) affiche la liste des locataires dont votre compte fait partie et dont vous êtes propriétaire ou administrateur d’environnement pour un projet LCS.

Si le locataire que vous recherchez ne figure pas dans cette liste, accédez à [LCS](https://lcs.dynamics.com/v2) et assurez-vous que vous êtes un administrateur d’environnement ou un propriétaire de projet du projet LCS pour ce locataire. Notez que seuls les comptes Azure Active Directory (Azure AD) du locataire sélectionné sont autorisés à terminer l’expérience d’inscription.

> [!NOTE]
> Une fois que vous avez appliqué les modifications à LCS, la liste des locataires peut prendre jusqu’à 30 minutes pour refléter les modifications.

Pour chaque locataire, la liste affiche l’état de l’inscription.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Option d’inscription d’un locataire":::

Sélectionnez le lien **Cliquer ici pour vous inscrire** pour inscrire votre locataire LCS à participer à la version préliminaire. Vous devez accepter les conditions. Vous devez également fournir une adresse e-mail professionnelle à laquelle Microsoft peut envoyer des communications liées au processus d’inscription à la version préliminaire.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Soumission d’inscription d’un locataire":::

Microsoft examinera votre demande et vous informera des étapes suivantes en envoyant un e-mail à l’adresse que vous avez fournie sur le formulaire d’inscription.

Après avoir obtenu l’accès au programme de version préliminaire, vous recevrez deux codes promotionnels pour votre projet LCS. Vous pouvez désormais utiliser ces codes promotionnels pour déployer deux environnements dans LCS. Les environnements doivent utiliser PEAP version 10.0.15 ou ultérieure. Lorsque vous avez terminé d’appliquer les codes promotionnels, informez Microsoft (comme indiqué), afin que nous puissions terminer l’activation des environnements pour les fonctionnalités d’évaluation. Microsoft vous avertira lorsque cette étape de configuration sera terminée.

Vous pouvez maintenant commencer à configurer les unités d’échelle et les charges de travail dans votre environnement de version préliminaire.

> [!IMPORTANT]
> Lorsque vous configurez des unités d’échelle cloud, vous pouvez [effectuer toutes les étapes requises dans le portail de gestionnaire d’unité d’échelle](#scale-unit-manager-portal).
<!-- 
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gérez les unités d’échelle cloud et les charges de travail à l’aide du portail de gestionnaire d’unité d’échelle

Aller au [portail de gestionnaire d’unité d’échelle](https://aka.ms/SCMSUM) et connectez-vous à l’aide de votre compte de locataire. Sur la page **Configurer les unités d’échelle**, vous pouvez ajouter un environnement de hub s’il n’est pas déjà répertorié. Vous pouvez ensuite sélectionner le hub que vous souhaitez configurer avec des unités d’échelle et des charges de travail.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Expérience de gestion des unités d’échelle et de la charge de travail":::

Pour ajouter une ou plusieurs unités d’échelle disponibles dans votre topologie, sélectionnez **Ajouter des unités d’échelle**. Dans la version préliminaire, vous devriez voir l’unité d’échelle cloud que vous avez déployée à partir de l’un des codes promotionnels que vous avez reçus dans le cadre du programme de version préliminaire.

<!--  [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

Sur l’onglet **Charges de travail définies**, utilisez le bouton **Créer une charge de travail** pour ajouter une charge de travail de gestion d’entrepôt ou d’exécution de fabrication à l’une de vos unités d’échelle. Pour chaque charge de travail, vous devez spécifier le contexte des processus qui appartiendront à la charge de travail. Pour les charges de travail de gestion d’entrepôt, le contexte est un entrepôt spécifique dans un site et une entité juridique spécifiques. Pour les charges de travail d’exécution de fabrication, le contexte est un site spécifique dans une entité juridique.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Création de charge de travail":::

> [!IMPORTANT]
> Le portail de gestionnaire d’unité d’échelle dans la version préliminaire ne vous permet pas de supprimer des charges de travail des unités d’échelle ou d’annuler l’attribution d’une unité d’échelle d’un hub une fois l’affectation effectuée. Si vous devez supprimer une affectation, contactez votre personne contact pour la gestion du programme de version préliminaire.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->


[!INCLUDE[footer-include](../../includes/footer-banner.md)]