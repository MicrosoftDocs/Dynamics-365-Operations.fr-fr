---
title: Initialiser Commerce Scale Unit (cloud)
description: Cet article explique comment initialiser Commerce Scale Unit (cloud) dans Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 06/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 969dd220a7b73a676b9cf5ac26223ebd9b3f2296
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942850"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Initialiser Commerce Scale Unit (cloud)

[!include[banner](../includes/banner.md)]

Cet article explique comment initialiser Commerce Scale Unit (cloud) dans Microsoft Dynamics 365 Commerce.

Si vous utilisez un bac à sable de niveau 2 ou un environnement de production doté de la version d’application 8.1.2.x ou ultérieure, vous devez initialiser Commerce Scale Unit (cloud) avant de pouvoir utiliser la fonctionnalité de canal de vente au détail pour les opérations de point de vente (PDV) ou pour les opérations de commerce électronique qui utilisent Retail Server dans le cloud. L’initialisation déploiera Commerce Scale Unit (cloud).

> [!IMPORTANT]
> Pour les clients existants utilisant la fonctionnalité de canal de vente au détail dans le cloud, afin d’assurer une assistance continue et ininterrompue pour votre entreprise, nous vous demandons de mettre à jour vos canaux de vente au détail pour utiliser Commerce Scale Unit. Les nouveaux environnements déployés sans Commerce Scale Unit ne recevront plus de mises à jour de qualité et de service pour les composants de canal de vente au détail hébergés dans le cloud. Aucune action n’est requise pour les clients qui utilisent exclusivement Commerce Scale Unit (auto-hébergé). Contactez votre Microsoft FastTrack Solution Architect si vous avez besoin d’une extension.

## <a name="prerequisites"></a>Conditions préalables

1. Déployez un bac à sable de niveau 2 ou un environnement de production doté de la version 8.1.2.x ou ultérieure.
2. Vous pouvez déployer vous-même jusqu’à 2 composants Commerce Scale Unit par environnement. Si vous avez besoin de plus de 2 unités d’échelle commerciale par environnement, dans Microsoft Dynamics Lifecycle Services (LCS), créez une demande d’assistance et entrez **Demande de composants Commerce Scale Unit supplémentaires** et indiquez l’ID d’environnement, le nombre de composants Commerce Scale Units et les régions de centre de données souhaitées. La demande sera traitée dans les cinq jours ouvrables. Si vous n’avez pas besoin de plus de 2 composants Commerce Scale Units par environnement, vous n’avez pas besoin de créer une demande de support. 
3. Vous devez disposer des autorisations du propriétaire de projet dans Lifecycle Services avant de pouvoir initialiser Commerce Scale Unit.
4. Assurez-vous que les clés de configuration de licence Retail sont activées dans votre environnement. Pour en savoir plus, voir [État des codes licence et des clés de configuration](../sysadmin/license-codes-configuration-keys-report.md). Les clés suivantes doivent être activées pour utiliser Commerce Scale Unit.

    - RetailBasic
    - RetaileCommerce : si vous envisagez d’utiliser le commerce électronique pour Dynamics 365 Commerce.
    - RetailGiftCard : si vous envisagez d’utiliser des cartes-cadeaux.
    - RetailInvent : si vous envisagez d’utiliser l’inventaire.
    - RetailModernPos : si vous envisagez d’utiliser un point de vente (PDV).
    - RetailReplenishment : si vous envisagez d’utiliser des réapprovisionnements.
    - RetailScheduler
    - RetailStores : si vous envisagez d’utiliser un PDV.


## <a name="region-availability"></a>Disponibilité régionale
Commerce Scale Unit est disponible pour un déploiement dans les régions suivantes.

| Localisation mondiale | Région              | Disponibilité        | Commentaires                  |
|-----------------|---------------------|---------------------|---------------------------|
| AMÉRIQUES        | Est des États-Unis             | Disponibilité générale |                           |
| AMÉRIQUES        | Est des États-Unis 2           | Disponibilité générale |                           |
| AMÉRIQUES        | Centre-nord des États-Unis    | Capacité limitée    |                           |
| AMÉRIQUES        | Centre-sud des États-Unis    | Capacité limitée    |                           |
| AMÉRIQUES        | Centre des États-Unis          | Disponibilité générale |                           |
| AMÉRIQUES        | Ouest des États-Unis             | Disponibilité générale |                           |
| AMÉRIQUES        | Ouest des États-Unis 2           | Disponibilité générale |                           |
| AMÉRIQUES        | Canada Centre      | Capacité limitée    |                           |
| AMÉRIQUES        | Canada Est         | Capacité limitée    |                           |
| AMÉRIQUES        | USA Centre-Ouest     | Capacité limitée    |                           |
| APAC            | Est de l’Australie      | Disponibilité générale |                           |
| APAC            | Sud-est de l’Asie      | Capacité limitée | Aucun déploiement autorisé    |
| APAC            | Est du Japon          | Disponibilité générale |                           |
| APAC            | Ouest du Japon          | Disponibilité générale |                           |
| APAC            | Sud-est de l’Australie | Disponibilité générale |                           |
| APAC            | Est de l’Asie           | Capacité limitée    |                           |
| APAC            | Inde Sud         | Capacité limitée | Aucun déploiement autorisé    |
| APAC            | Inde Centre       | Capacité limitée    | Nécessite un processus d’approbation |
| EMEA            | Ouest de l’Europe         | Disponibilité générale |                           |
| EMEA            | Nord de l’Europe        | Disponibilité générale |                           |
| EMEA            | Royaume-Uni Sud            | Capacité limitée    |                           |
| EMEA            | Royaume-Uni Ouest             | Capacité limitée    |                           |
| Suisse     | Suisse Nord   | Capacité limitée    | Nécessite un processus d’approbation |
| Émirats arabes unis             | Émirats arabes unis Nord           | Capacité limitée    | Nécessite un processus d’approbation |

La capacité de déploiement dans les régions à capacité limitée est extrêmement limitée. Les demandes de déploiement sont évaluées au cas par cas. Si vous avez un besoin commercial impérieux de déploiement dans des régions à capacité limitée, vous pouvez déposer une demande d’assistance pour être ajouté à la liste d’attente. Les zones à capacité limitée ne permettent actuellement pas le déploiement de Commerce Scale Unit pour le moment. 

![Carte présentant la disponibilité selon la région.](media/Commerce-Scale-Unit-Region-Availability.png "Carte présentant la disponibilité selon la région")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Initialiser Commerce Scale Unit dans le cadre du déploiement d’un nouvel environnement

Veuillez vous assurer que le siège social est disponible. Ceci est nécessaire pour enregistrer l’unité d’échelle auprès du siège social pendant le processus d’initialisation. Il n’est pas recommandé d’initialiser une unité d’échelle lorsque le siège social est en cours de maintenance, car elle peut devenir indisponible pendant son processus de maintenance.

1. Assurez-vous que l’environnement du siège social est disponible et non en [Mode maintenance](../sysadmin/maintenance-mode.md).
2. Dans LCS, sur la page des détails de l’environnement, sélectionnez **Fonctionnalités de l’environnement \> Commerce**.
3. Sur la page de déploiement de la configuration de Commerce, sélectionnez **Initialiser**.
4. Sélectionnez la version de Commerce Scale Unit à initialiser.
5. Sélectionnez une région dans laquelle initialiser Commerce Scale Unit.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Configurer les canaux pour utiliser Commerce Scale Unit

Après le déploiement de Commerce Scale Unit, vous devez vous assurer que vos canaux sont configurés pour utiliser la base de données. 

Pour configurer vos canaux pour utiliser la base de données Commerce Scale Unit, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration du siège \> Commerce Planification \> Base de données des canaux**.
1. Dans le volet gauche, sélectionnez une base de données de canaux.
1. Sur le raccourci **Canal de vente au détail**, sélectionnez **Ajouter**, puis sélectionnez votre canal de vente au détail dans la liste déroulante.
1. Sélectionnez **Ajouter**, puis sélectionnez votre chaîne en ligne dans la liste déroulante. 

Lorsque cela est terminé, accédez à **Retail et Commerce \> Informatique Retail et Commerce \> Programme de distribution**, et exécutez la tâche 9999.

> [!NOTE] 
> La tâche 9999 synchronise tous les nouveaux produits et clients avec Commerce Scale Unit. Ce processus peut prendre un long moment. Si le canal doit être disponible uniquement pour la configuration du créateur de site de commerce électronique, vous pouvez exécuter la tâche 1070 au lieu de la tâche 9999.

### <a name="database-refresh-and-commerce-scale-units"></a>Actualisation de la base de données et des composants Commerce Scale Units

Avant de commencer, assurez-vous de bien connaître [Étapes à suivre après une actualisation de la base de données pour les environnements qui utilisent la fonctionnalité Commerce](../database/database-refresh.md).

Les enregistrements de base de données des canaux de l’unité d’échelle (sous la forme d’une base de données des canaux) ne peuvent pas passer d’un environnement à l’autre dans le cadre de l’actualisation de la base de données. En effet, les enregistrements représentent une configuration spécifique à l’environnement.

Après l’actualisation de la base de données, vous pouvez régénérer l’enregistrement de la base de données des canaux de l’unité d’échelle en émettant un redéploiement de votre unité d’échelle dans LCS. Toute opération de déploiement ou de maintenance dans l’unité d’échelle tentera d’enregistrer l’unité d’échelle auprès du siège, si l’enregistrement est détecté comme manquant.

Vous pouvez émettre un redéploiement de l’unité d’échelle, sans modifier aucun composant, en sélectionnant de déployer la même version que votre unité d’échelle est déjà. Cela peut être fait dans LCS en procédant comme suit :

1. Dans LCS, sur la page des détails de l’environnement, sélectionnez **Fonctionnalités de l’environnement \> Retail**.
2. Sur la page de configuration du déploiement, sélectionnez l’unité d’échelle que vous souhaitez redéployer.
3. Dans le menu de fonctionnement de l’unité d’échelle, sélectionnez **Mettre à jour**.
4. Sur le curseur, dans la liste déroulante pour **Sélectionner la version**, choisissez l’option **Spécifier une version**.
5. Dans la zone de texte sous **Spécifier une version**, tapez la version indiquée pour votre unité d’échelle, affichée à côté de l’étiquette **Version actuelle**.
6. Cliquez sur le bouton **Mettre à jour**.

Vous n’avez pas besoin de sélectionner **Mettre à jour les extensions**, même si vous avez déjà appliqué des extensions, car le dernier package d’extension appliqué à l’unité d’échelle est automatiquement sélectionné lors de la mise à jour d’une unité d’échelle.

Si vous avez plusieurs unités d’échelle, vous devez effectuer l’opération ci-dessus pour chaque unité d’échelle. Vous pouvez effectuer ces opérations en parallèle, si vous le souhaitez.

## <a name="deploy-additional-commerce-scale-units-optional"></a>Déployer des composants Commerce Scale Units supplémentaires (facultatif)

Après avoir initialisé Commerce Scale Unit, vous pouvez déployer vous-même une deuxième unité d’échelle si votre licence vous le permet. Pour déployer plus de deux unités d’échelle, vous devez créer une demande de support. Dans la demande de support, indiquez le nombre de composants Commerce Scale Unit dont vous avez besoin, le nom de l’environnement et les régions souhaitées. Pour plus d’informations sur l’octroi de licence, voir [Guide de gestion des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Pour chaque composant Commerce Scale Unit supplémentaire déployé, nous vous recommandons de créer un groupe de bases de données de canaux distinct en suivant ces étapes.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce > Retail Headquarters > Configuration de Retail Planification > Groupe de base de données du canal**.
2. Créez un groupe de base de données de canal.
3. Accédez à **Retail et Commerce > Retail Headquarters > Configuration de Retail Planification > Base de données des canaux**, et sélectionnez la base de données de canaux qui correspond au composant Commerce Scale Unit récemment créé.
4. Sélectionnez **Modifier**, puis sélectionnez le nouveau groupe de bases de données de canaux.
5. Cliquez sur **Enregistrer**.
6. Sélectionnez **Exécuter la synchronisation complète des données** pour la base de données de canaux sélectionnée.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>Considérations supplémentaires si vous initialisez des composants de canal Commerce hébergés dans le cloud dans un environnement existant

Si vous utilisez déjà des composants de canal Commerce hébergés dans le cloud dans un environnement, l’initialisation de Commerce Scale Unit aidera à diminuer le temps d’arrêt qu’implique la mise à jour de ces composants. Une planification supplémentaire est requise avant l’initialisation de Commerce Scale Unit.

Lorsque vous initialisez votre premier composant Commerce Scale Unit dans un environnement qui utilise des composants de canal Commerce hébergés dans le cloud, le processus d’initialisation migre vos canaux associés aux composants de canal hébergés dans le cloud vers la première unité d’échelle. Les canaux associés aux unités d’échelle de magasin ne sont pas affectés.

Le processus de migration est transparent pour les canaux. Après le démarrage de l’initialisation de l’unité d’échelle, les opérations suivantes sont automatiquement effectuées :

1. Un nouveau composant Commerce Scale Unit sera créé et associé à l’environnement.
2. Le composant Commerce Scale Unit sera enregistré en tant que base de données de canaux disponible au siège.
3. Tous les canaux mappés vers la base de données de canaux **Par défaut** au siège seront mis à jour pour correspondre au nouveau composant Commerce Scale Unit.
4. Une synchronisation complète Commerce Data Exchange (CDX) sera effectuée pour transmettre les données des canaux à la nouvelle unité d’échelle.

**Planification et test de l’initialisation de Commerce Scale Unit** En règle générale, lors de l’initialisation de Commerce Scale Unit, vous devez prévoir une fenêtre d’indisponibilité de cinq heures pour les opérations en magasin ainsi que pour toutes les opérations de canal de commerce électronique qui utilisent Retail Server ou Cloud Point of Sale.

1. Effectuez une actualisation de la base de données de votre environnement de production vers un environnement sandbox UAT. 
2. Initialisez Commerce Scale Unit dans l’environnement sandbox UAT. 
3. Notez le temps d’initialisation pour terminer Commerce Scale Unit. Cela sera comparable au temps que prend cette opération dans votre environnement de production, pendant lequel les opérations en magasin et les opérations de commerce électronique ne seront pas disponibles.

Vous devez effectuer les étapes supplémentaires suivantes avant d’initialiser Commerce Scale Unit.

- **Fermer toutes les équipes du PDV** : après la migration, les utilisateurs du PDV ne pourront pas fermer les équipes qui étaient actives lors du processus de migration.
- **Valider que toutes les tâches de traction (P) ont été exécutées avec succès** : il est recommandé que les tâches de traction (P) synchronisant les transactions en attente soient terminées avant l’initialisation de CSU.
- **Se déconnecter de tous les périphériques du PDV** : les opérations du PDV ne sont pas prises en charge pendant la migration.
- **Rappeler et annuler toutes les transactions suspendues au PDV** : les transactions suspendues ne sont pas conservées dans le cadre de l’initialisation.

> [!IMPORTANT]
> Dans le cadre de l’initialisation de Commerce Scale Unit, les transactions précédemment suspendues seront perdues et ne pourront pas être rappelées. 

Voici ce qui se passe pendant la période d’initialisation :

- Les canaux de Commerce hébergés dans le cloud ne fonctionneront pas, sauf si vous activez la fonctionnalité hors ligne du PDV.
- Les périphériques du PDV avec la fonctionnalité hors ligne activée auront des fonctionnalités réduites.
- Tous les clients de commerce électronique qui dépendent de Retail Server seront interrompus.
- Les chaînes hébergées sur des composants Commerce Scale Unit (auto-hébergées) ne seront pas affectées.
- La fonctionnalité du siège social n’est pas affectée.

Voici ce qui se passe une fois l’initialisation terminée :

- L’état d’activation de tous les périphériques de PDV activés est conservé, ce qui signifie que les périphériques n’auront pas besoin d’être réactivés.
- Les instances de station matérielle autonome continueront de fonctionner.
- Les rapports côté canal du PDV seront réinitialisés et n’afficheront pas les données antérieures à l’initialisation.
- L’opération d’affichage du journal sera également réinitialisée et n’affichera pas les données antérieures à l’initialisation.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
