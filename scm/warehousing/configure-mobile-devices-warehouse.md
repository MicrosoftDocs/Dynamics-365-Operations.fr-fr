---
title: "Paramétrer des appareils mobiles pour un travail d&quot;entrepôt"
description: "Cet article décrit la manière de configurer les options de menu utilisées par les collaborateurs d&quot;entrepôt pour travailler sur un appareil mobile."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 34d7b246d74d1546b54494944903d160e31f7678
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-mobile-devices-for-warehouse-work"></a>Paramétrer des appareils mobiles pour un travail d'entrepôt

Cet article décrit la manière de configurer les options de menu utilisées par les collaborateurs d'entrepôt pour travailler sur un appareil mobile.

**Remarque :** cet article s'applique aux fonctionnalités du module Gestion de l'entrepôt. Il ne s'applique pas aux fonctionnalités du module Gestion du stock. Les options de menu qui s'affichent dans les menus d'un appareil mobile d'entrepôt sont configurées dans la page **Options de menu d'appareil mobile**. Comme les options de menu peuvent être placées dans différents menus, il est facile de configurer les structures de menu de manière à ce que seuls des types de travail spécifiques soient visibles par des utilisateurs spécifiques. Vous pouvez configurer les options de menu pour effectuer les tâches suivantes :

-   Traiter une recherche ou effectuer une activité, telle que l'impression d'une étiquette, la génération de contenants, le démarrage d'un ordre d'exécution ou la recherche rapide d'informations sur les articles dans un emplacement.
-   Créer le travail qui sera effectué via un autre processus. Par exemple, la réception d'un article pour une commande fournisseur peut créer le travail de rangement pour un autre collaborateur.
-   Effectuer un travail créé par un autre processus (travail existant), comme le travail de rangement créé lors de la réception d'un article pour une commande fournisseur.

Pour créer une option de menu pour une activité ou une recherche, définissez le champ **Mode** sur **Indirect**. La liste des options **Code activité** devient alors disponible pour vous permettre de sélectionner le type de recherche ou d'activité auquel l'option de menu s'applique. Pour créer une option de menu pour générer le travail d'entrepôt, définissez le champ **Mode** sur **Travail**. La liste des options **Processus de création de travail** devient alors disponible. Pour créer une option de menu pour traiter le travail d'entrepôt existant, définissez le champ **Mode** sur **Travail**, puis définissez l'option **Utiliser un travail existant** sur **Oui**. **Remarque :** des champs supplémentaires peuvent être disponibles pour les options de menu selon le mode sélectionné pour l'option de menu, et si l'option de menu est utilisée pour effectuer un travail existant. Pour plus d'informations sur les sélections de champs supplémentaires, voir la section « Options de menu supplémentaires » plus loin dans cet article.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Configurer des options de menu pour les activités et les recherches
Si le champ **Mode** d'une option de menu est défini sur **Indirect**, vous pouvez créer une option de menu pour effectuer une activité ou une recherche générale qui ne crée pas de travail. Il peut s'agir par exemple de la réimpression des étiquettes de contenant ou d'une recherche sur les articles dans un emplacement. Le tableau suivant répertorie les options disponibles.

| Option                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aucun(e)                        | Cette valeur par défaut n'active pas d'activité ni de recherche.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| À propos de                       | Afficher des informations sur le système, telles que le numéro de version, l'ID d'entrepôt et le collaborateur actuellement connecté.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Modifier l'entrepôt            | Modifier l'entrepôt auquel un collaborateur est connecté.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Recherche d'emplacement            | Afficher des informations sur les articles et les quantités pour un emplacement.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Recherche de contenant       | Afficher la quantité d'articles dans un contenant et l'emplacement du contenant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Démarrer l'ordre de fabrication      | Démarrer un ordre d'exécution.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Production au rebut            | Entrer la quantité d'articles au rebut créés lors de la production pour chaque ligne de nomenclature.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Dernière palette de production      | Indiquer que la dernière palette d'articles a été produite pour un ordre de fabrication, et que le statut de l'ordre de fabrication doit être mis à jour sur **Déclaré terminé**. Le statut des matières premières qui n'ont pas été consommées lors de la production passe de **Prélevé** à **En commande**, et les articles peuvent être renvoyés au stock.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Recherche d'article                | Numériser un article pour déterminer sa progression dans l'entrepôt. La recherche renvoie tous les emplacements et quantités pour l'article numérisé.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Réimprimer l'étiquette               | Réimprimer une étiquette de contenant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Création de contenant         | Créer un contenant parent en combinant plusieurs contenants dans le même emplacement. Cette option peut s'avérer utile si vous déplacez plusieurs contenants simultanément. Une fois le contenant parent déplacé, vous devez le décomposer en contenants avant de prélever des articles de chaque contenant. **Astuce :** pour déplacer un contenant parent, vous devez utiliser un appareil mobile qui est configuré pour créer des mouvements.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Décomposition du contenant         | Décomposer un contenant afin de pouvoir prélever des articles des contenants qui le composent.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Vérification à l'arrivée du chauffeur             | Si vous utilisez Gestion du transport, enregistrer l'arrivée d'un chauffeur en numérisant l'ID de chargement sortant, l'ID de rendez-vous ou l'ID d'expédition. Pour cette option, un chargement doit être affecté au rendez-vous et son statut doit être **Chargé**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Vérification au départ du chauffeur            | Enregistrer qu'un chauffeur a terminé son rendez-vous.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Effacer le cache de souche de numéros | Supprimer les numéros de souche du cache de souche de numéros. Cette activité est généralement exécutée par un administrateur système pour résoudre les problèmes de mise en cache lors de l'utilisation d'appareils mobiles.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Modifier la disposition de traitement par lots    | Permettre à un collaborateur de spécifier le code disposition de lot d'un article et d'un lot. Cette sélection met à jour le code disposition spécifié pour le lot.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Afficher la liste des travaux en cours      | Afficher la liste des travaux disponibles à un utilisateur donné. L'utilisateur peut ensuite sélectionner le travail à effectuer et être dirigé vers celui-ci. Cette liste peut être affichée sur les tablettes dont la taille d'écran est d'au moins 7 pouces. Lorsque vous sélectionnez cette option, les options de menu **Modifier la requête** et **Liste de champs** deviennent disponibles. La page **Modifier la requête** permet de paramétrer les critères pour le travail qui s'affiche dans la liste. La page **Liste de champs** permet de sélectionner les champs qui s'affichent dans la liste des travaux. Par exemple, vous pouvez réduire le nombre de champs qui s'affichent pour permettre à l'utilisateur de sélectionner plus rapidement l'élément de travail le plus approprié. Dans l'organisateur **Général**, dans le champ **Enregistrements par page**, vous pouvez également sélectionner le nombre d'enregistrements de travail visibles par page. Si l'option **Autoriser les utilisateurs à filtrer le travail par type de transaction** est sélectionnée, la liste des travaux inclut un contrôle supplémentaire **Filtrer le travail** qui permet à l'utilisateur de filtrer le travail par type de transaction. Dans la liste des travaux, seul le travail auquel les utilisateurs sont autorisés à accéder est visible. Vous devez vous assurer que les utilisateurs disposent d'autorisations pour une ou plusieurs options de menu dirigées par l'utilisateur qui prennent en charge les types de classe de travail spécifiques auxquels ils doivent pouvoir accéder. Les autorisations sont vérifiées lorsqu'un utilisateur tente d'effectuer un travail de la liste. |

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Configurer des options de menu pour créer un travail pour un autre collaborateur ou un autre processus
Vous pouvez paramétrer une option de menu qui crée un travail pour un autre collaborateur après l'exécution d'une première action sur l'appareil mobile. Par exemple, lorsqu'un collaborateur utilise un appareil mobile pour recevoir un article, le travail de rangement est créé pour un autre collaborateur. Pour paramétrer une option de menu qui crée un travail, dans la page **Options de menu d'appareil mobile**, dans le champ **Mode**, sélectionnez **Travail**. Dans le tableau suivant, les options du champ **Processus de création du travail** sont classées par type d'ordre d'exécution.

<table>
<tbody>
<tr>
<th>Type d'ordre d'exécution</th>
<th>Option</th>
<th>Description</th>
</tr>
<tr>
<td rowspan="8">Commande fournisseur</td>
<td>Réception de ligne de commande fournisseur</td>
<td>Enregistrez la réception d'une quantité d'un article à l'aide du numéro de commande fournisseur et du numéro de ligne de commande fournisseur, puis créez le travail de rangement pour un autre collaborateur.</td>
</tr>
<tr>
<td>Réception et rangement de la ligne de commande fournisseur</td>
<td>Enregistrez la réception d'une quantité d'un article à l'aide du numéro de commande fournisseur et du numéro de ligne de commande fournisseur et rangez les articles. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Réception d'article de commande fournisseur</td>
<td>Enregistrez la réception d'une quantité d'un article pour une commande fournisseur en enregistrant le numéro de bon de commande ou le numéro d'article, puis créez le travail de rangement pour un autre collaborateur.</td>
</tr>
<tr>
<td>Réception et rangement de l'article de commande fournisseur</td>
<td>Enregistrez la réception d'une quantité d'un article pour une commande fournisseur en enregistrant le numéro de commande fournisseur et en rangeant l'article. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Réception de contenant</td>
<td>Acceptez un chargement entrant à l'aide de l'ID de contenant.</td>
</tr>
<tr>
<td>Réception et rangement de contenant</td>
<td>Acceptez et rangez un chargement entrant à l'aide de l'ID de contenant.</td>
</tr>
<tr>
<td>Réception des articles du chargement</td>
<td>Enregistrez la réception d'une quantité d'un chargement à l'aide de l'ID de chargement, puis créez le travail de rangement pour un autre collaborateur. Le numéro d'article et les dimensions de produit mettent en correspondance la réception et les lignes de commande fournisseur.</td>
</tr>
<tr>
<td>Réception et rangement des articles du chargement</td>
<td>Enregistrez la réception d'un chargement à l'aide de l'ID de chargement et rangez les articles. Le numéro d'article et les dimensions de produit mettent en correspondance la réception et les lignes de commande fournisseur. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Ordre de retour</td>
<td>Réception d'un ordre de retour</td>
<td>Enregistrez la réception d'une quantité d'un article en enregistrant le numéro de retour marchandises RMA, puis créez le travail de rangement pour un autre collaborateur.</td>
</tr>
<tr>
<td>Réception et rangement d'ordre de retour</td>
<td>Enregistrez la réception d'une quantité d'un article en enregistrant le numéro de retour marchandises RMA et en rangeant les articles. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Ordre de transfert</td>
<td>Réception des articles de l'ordre de transfert</td>
<td>Enregistrez la réception d'une quantité d'un article, puis créez le travail de rangement pour un autre collaborateur.

<strong>Remarque :</strong> utilisez cette option uniquement si les articles ont été expédiés d'un entrepôt qui n'est pas activé pour les processus de gestion des entrepôts.</td>
</tr>
<tr>
<td>Réception et rangement des articles de l'ordre de transfert</td>
<td>Enregistrez la réception d'une quantité d'un article et rangez les articles. Le même collaborateur effectue les deux actions.

<strong>Remarque :</strong> utilisez cette option uniquement si les articles ont été expédiés d'un entrepôt qui n'est pas activé pour les processus de gestion des entrepôts.</td>
</tr>
<tr>
<td>Réception de ligne d'ordre de transfert</td>
<td>Enregistrez la réception d'une quantité d'un article, puis créez le travail de rangement pour un autre collaborateur.</td>
</tr>
<tr>
<td>Réception et rangement de la ligne d'ordre de transfert</td>
<td>Enregistrez la réception d'une quantité d'un article et rangez les articles. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Production</td>
<td>Déclaration de fin</td>
<td>Enregistrez une quantité d'un article fini qui a été terminé pour une production, puis créez le travail de rangement pour un autre collaborateur. La quantité peut correspondre à une partie ou à la quantité totale qui a été prévue pour la production.</td>
</tr>
<tr>
<td>Déclarer comme terminé et ranger</td>
<td>Enregistrez une quantité d'un article fini qui a été terminé pour une production et rangez les articles. La quantité peut correspondre à une partie ou à la quantité totale qui a été prévue pour la production. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Indiquez qu'un kanban est terminé, puis créez le travail de rangement pour un autre collaborateur.</td>
</tr>
<tr>
<td>Rangement de kanban</td>
<td>Indiquez qu'un kanban est terminé, puis rangez les articles. Le même collaborateur effectue les deux actions.</td>
</tr>
<tr>
<td>Stock</td>
<td>Mouvement</td>
<td>Indiquez que les articles ont été déplacés d'un emplacement vers un autre. Le collaborateur spécifie l'emplacement depuis lequel les articles sont déplacés et l'emplacement où ils sont déplacés.</td>
</tr>
<tr>
<td>Contrôle</td>
<td>Modifiez le statut du stock disponible pour un contenant ou un emplacement pour indiquer que les articles en stock endommagés ou manquants ne sont pas disponibles.</td>
</tr>
<tr>
<td>Mouvement par modèle</td>
<td>Déplacez des articles d'un emplacement vers un autre d'une façon semi-automatisée. Le collaborateur sélectionne l'emplacement depuis lequel déplacer les articles, et Microsoft Dynamics 365 for Operations utilise l'instruction d'emplacement pour déterminer où déplacer les articles.</td>
</tr>
<tr>
<td>Transfert d'entrepôt</td>
<td>Indiquez que les articles ont été transférés d'un entrepôt vers un autre. Cette option nécessite que le collaborateur soit autorisé à effectuer le travail dans les deux entrepôts.

<strong>Remarque :</strong> cette option de menu nécessite un journal de transfert de stock par défaut avec le champ <strong>Création du n° document</strong> défini sur <strong>Validation</strong>.</td>
</tr>
<tr>
<td>Chargement de contenant</td>
<td>Utilisez cette option lorsque vous paramétrez votre entrepôt pour la première fois. Numérisez tous les contenants dans tous les emplacements de l'entrepôt. Les emplacements doivent faire l'objet d'un contrôle de contenant. Vous ne pouvez pas utiliser cette option si le <strong>numéro de série</strong> ou le <strong>numéro de lot</strong> est répertorié au-dessus de l'<strong>emplacement</strong> dans la hiérarchie de réservation du stock.</td>
</tr>
<tr>
<td>Inventaire tournant</td>
<td>Ajustement en entrée</td>
<td>Augmentez la quantité des articles en stock. Spécifiez l'emplacement, le contenant, l'article, la quantité, l'unité de mesure, et le statut.</td>
</tr>
<tr>
<td>Ajustement en sortie</td>
<td>Réduisez la quantité des articles en stock. Spécifiez l'emplacement, le contenant, l'article, la quantité, l'unité de mesure, et le statut du stock.</td>
</tr>
<tr>
<td>Inventaire tournant ponctuel</td>
<td>Démarrez un compte pour un emplacement. Le collaborateur doit compter tous les articles dans l'emplacement. Lorsque le résultat d'un compte est inférieur à la quantité prévue, la quantité manquante est considérée comme une perte.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Configurer des options de menu pour traiter le travail existant
Outre la configuration des options de menu pour créer le travail d'entrepôt, vous pouvez paramétrer des options de menu pour traiter le travail qui a déjà été créé. Définissez le champ **Mode** sur **Travail**, puis sélectionnez l'option **Utiliser un travail existant**. Certaines options supplémentaires deviennent alors disponibles sous l'onglet **Général**. Vous pouvez contrôler l'accès à l'option de menu en affectant une ou plusieurs classes de travail dans l'organisateur **Classe de travail**. Les classes de travail définissent le travail que l'option de menu peut traiter. La classe de travail permet également d'autoriser l'accès à des rôles utilisateur spécifiques ou de séparer le traitement pour différents types d'opérations. Le tableau suivant décrit les options disponibles.

<table>




<thead>
<tr class="header">
<th>Option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aucun(e)</td>
<td>Cette valeur par défaut ne traite pas le travail.</td>
</tr>
<tr class="even">
<td>Dirigé par le système</td>
<td>Microsoft Dynamics 365 for Operations contrôle le type de travail affecté à un collaborateur et l'ordre dans lequel le collaborateur effectue le travail. Lorsque vous sélectionnez cette option, vous pouvez cliquer sur <strong>Travail dirigé par le système</strong> dans le volet Actions pour ouvrir la page <strong>Ordre de tri dirigé par le système</strong>, dans laquelle vous pouvez paramétrer les critères de tri pour le travail. Les critères de tri contrôlent l'ordre dans lequel le collaborateur réalise le travail. Vous pouvez ajouter autant de critères que nécessaire.</td>
</tr>
<tr class="odd">
<td>Dirigé par l'utilisateur</td>
<td>Le collaborateur sélectionne le travail à effectuer et l'ordre d'exécution.</td>
</tr>
<tr class="even">
<td>Regroupement d'utilisateurs</td>
<td>Le collaborateur regroupe le travail manuellement. Cette option est utile, par exemple, lorsqu'un collaborateur peut prélever plusieurs articles en même temps dans un emplacement. Une fois que le collaborateur a terminé de prélever les articles requis, il peut les ranger.</td>
</tr>
<tr class="odd">
<td>Regroupement système</td>
<td>Microsoft Dynamics 365 for Operations regroupe le travail d'un collaborateur en fonction d'un champ spécifié. Par exemple, un travail de prélèvement est groupé lorsqu'un collaborateur numérise un ID d'expédition, un ID de chargement, ou n'importe quelle valeur pouvant lier chaque unité de travail. Si vous sélectionnez cette option, les champs suivants sont requis :
<ul>
<li><strong>Champ de regroupement système</strong> – Sélectionnez le champ qu'un collaborateur numérise pour grouper le travail.</li>
<li><strong>Étiquette de regroupement système</strong> – Entrez le texte indiquant au collaborateur ce qu'il doit numériser pour grouper le travail.</li>
</ul></td>
</tr>
<tr class="even">
<td>Utilisateur validé dirigé</td>
<td>Le collaborateur sélectionne le travail à effectuer lorsque le travail est associé à une entité supérieure, telle qu'un chargement ou une expédition. Le collaborateur détermine l'ordre dans lequel les articles sont prélevés. Si vous sélectionnez cette option, les champs suivants sont requis :
<ul>
<li><strong>Champ Utilisateur validé dirigé</strong> – Sélectionnez le champ que le collaborateur numérise pour grouper le travail.</li>
<li><strong>Étiquette d'utilisateur validé dirigé</strong> – Entrez le texte indiquant au collaborateur quoi numériser lorsque le travail de prélèvement est groupé par le système.</li>
</ul>
Cette option est utile, par exemple, lorsque plusieurs palettes sont prévues pour un chargement. Si vous sélectionnez le champ <strong>LoadId</strong> dans le champ <strong>Utilisateur validé dirigé</strong>, le collaborateur peut prélever toute palette associée au chargement. Le collaborateur reçoit un message d'erreur s'il analyse un article qui n'est pas associé au chargement.</td>
</tr>
<tr class="odd">
<td>Prélèvement de groupement</td>
<td>Le collaborateur regroupe le travail en clusters. Les groupements permettent aux collaborateurs de prélever des articles d'un emplacement unique pour plusieurs ordres d'exécution simultanément.</td>
</tr>
<tr class="even">
<td>Regroupement d'inventaires tournants</td>
<td>Le collaborateur sélectionne une zone, un pool de travail ou un emplacement, et Microsoft Dynamics 365 for Operations affecte le travail en fonction de la sélection. Si cette option est sélectionnée, vous pouvez cliquer sur <strong>Inventaire tournant</strong> dans le volet Actions pour spécifier des informations supplémentaires à afficher, et vous pouvez également spécifier le nombre de fois que le collaborateur doit répéter l'opération si une différence est trouvée.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Options de menu supplémentaires
D'autres options de menu sont disponibles dans la page **Options de menu d'appareil mobile**. Les options varient selon le processus pour lequel vous configurez l'option de menu. 

Le tableau suivant décrit ces options.

<table>




<thead>
<tr class="header">
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Autoriser le fractionnement du travail</td>
<td>Sélectionnez cette option pour autoriser les utilisateurs à placer des articles pour un ordre d'exécution dans plusieurs contenants. Cette option est utile, par exemple, si le contenant cible est complet et le collaborateur doit ajouter les articles restants dans un autre contenant. Le collaborateur peut cliquer sur <strong>Complet</strong> pour indiquer que le contenant est complet et arrêter de recevoir des travaux de prélèvement pour celui-ci. L'emplacement de rangement des articles prélevés est ensuite affiché, et le travail de prélèvement déjà termine est déplacé vers un nouvel ordre d'exécution. Le travail de prélèvement restant pour le contenant cible reste dans l'ordre d'exécution d'origine.</td>
</tr>
<tr class="even">
<td>Ancrage</td>
<td>Sélectionnez cette option pour permettre aux collaborateurs de spécifier un emplacement qui remplace l'emplacement intermédiaire ou de chargement suggéré. Tout le travail de rangement restant est dirigé vers le nouvel emplacement. Cette option est utile, par exemple, lorsqu'un collaborateur doit placer des articles de la commande 1 dans un emplacement intermédiaire dans le Quai 1, mais ne peut pas, car un chargement précédent n'a pas libéré l'emplacement. Au lieu d'attendre que l'emplacement intermédiaire du Quai 1 devienne disponible, le collaborateur peut décider d'utiliser l'emplacement intermédiaire du Quai 2. Dans ce cas, il remplace l'emplacement intermédiaire suggéré. L'emplacement de rangement de tous les articles restants pour l'ordre d'exécution est ensuite mis à jour avec l'emplacement intermédiaire du Quai 2. Si vous sélectionnez cette option, vous devez définir le champ <strong>Ancrer par</strong>.</td>
</tr>
<tr class="odd">
<td>Ancrer par</td>
<td>Si vous utilisez l'ancrage, vous devez spécifier si vous souhaitez ancrer par expédition ou par chargement.</td>
</tr>
<tr class="even">
<td>ID modèle d'audit</td>
<td>Sélectionnez le modèle d'audit de travail qui interrompra le processus de travail pour cette option de menu afin qu'une autre opération puisse être exécutée. Par exemple, si cette option de menu est pour le travail entrant, le modèle d'audit peut exiger que le collaborateur vérifie la température dans le conteneur de livraison. Le point où le processus est interrompu est spécifié dans le modèle d'audit. Ce point peut être, par exemple, lorsqu'un travail est démarré ou terminé ou que son statut change.</td>
</tr>
<tr class="odd">
<td>ID profil de groupement</td>
<td>Sélectionnez le profil de groupement à utiliser pour le prélèvement de groupement. Le profil de groupement inclut des paramètres tels que la création automatique de groupements, les noms des postes et le nombre d'unités de travail auxquels ils peuvent être affectés, la répartition des groupes dans différentes unités, et si une vérification est requise. Ce champ n'est disponible que si l'option <strong>Prélèvement de groupement</strong> est sélectionnée dans le champ <strong>Dirigé par</strong>.</td>
</tr>
<tr class="even">
<td>Compter d'abord la quantité totale d'articles</td>
<td>Sélectionnez cette option pour exiger d'un collaborateur qu'il compte la quantité totale en premier lors d'un compte. Si une différence est détectée, le collaborateur doit fournir des informations supplémentaires, telles que le numéro de contenant, le numéro de lot et les numéros de série.</td>
</tr>
<tr class="odd">
<td>Créer un mouvement</td>
<td>Sélectionnez cette option pour permettre à un collaborateur de créer le travail d'un mouvement, mais sans effectuer le travail immédiatement. Cette option est utile si, par exemple, une inspection de qualité est terminée et le contrôleur souhaite que l'article soit déplacé de la zone d'inspection de qualité.</td>
</tr>
<tr class="even">
<td>Code instructions</td>
<td>Pour utiliser une instruction d'emplacement spécifique, sélectionnez le code instructions associé à l'instruction d'emplacement. Ce champ est disponible lorsque vous créez un travail et que le processus de création de travail est <strong>Mouvement par modèle</strong>.</td>
</tr>
<tr class="odd">
<td>Désactiver les seuils d'inventaire tournant</td>
<td>Sélectionnez cette option pour ignorer les seuils d'inventaire tournant. Si vous sélectionnez cette option, le travail d'inventaire tournant n'est pas créé lorsque les valeurs de seuil sont dépassées.</td>
</tr>
<tr class="even">
<td>Afficher le code disposition de traitement par lots</td>
<td>Sélectionnez cette option pour afficher les codes disposition de lot. Par exemple, vous pouvez afficher les codes disposition de lot lorsque vous recevez un lot retourné. Les collaborateurs peuvent ensuite évaluer le statut ou la qualité d'un lot et sélectionner le code approprié. Les règles du code disposition de lot déterminent si le lot est disponible à d'autres processus d'entrepôt. Si vous ne sélectionnez pas cette option, l'un des codes disposition de lot ci-dessous est utilisé :
<ul>
<li>Si vous recevez un nouveau numéro de lot, le code disposition de lot par défaut spécifié dans le groupe de modèles d'article est utilisé.</li>
<li>Le code disposition de lot qui est déjà affecté au lot est utilisé.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Afficher le code disposition</td>
<td>Sélectionnez cette option pour afficher les codes disposition. Par exemple, vous pouvez afficher les codes disposition lorsque vous recevez des articles retournés. Les collaborateurs peuvent ensuite évaluer le statut ou la qualité des articles et sélectionner le code approprié. Les règles du code disposition déterminent si les articles sont disponibles à d'autres processus d'entrepôt.</td>
</tr>
<tr class="even">
<td>Afficher le statut de stock</td>
<td>Sélectionnez cette option pour afficher le statut des articles en stock. Pour plus d'informations, voir <a href="/inventory/inventory-statuses.md">Avantages de l'utilisation de statuts de stock</a>. Cette option est disponible pour toutes les options de menu qui utilisent le travail existant, hormis l'inventaire tournant.</td>
</tr>
<tr class="odd">
<td>Afficher le résumé de l'écran de prélèvement</td>
<td>Sélectionnez cette option pour afficher un résumé du travail de prélèvement pour l'ordre d'exécution sélectionné. Le résumé est affiché jusqu'à ce que la première ligne de travail soit traitée pour l'ordre d'exécution.</td>
</tr>
<tr class="even">
<td>Générer un contenant</td>
<td>Sélectionnez cette option pour générer un numéro unique de contenant selon la sélection de la souche de numéros. Par exemple, vous pouvez générer un numéro de contenant pour les articles reçus pour les commandes fournisseur.</td>
</tr>
<tr class="odd">
<td>Rangement du groupe</td>
<td>Sélectionnez cette option pour grouper le travail de rangement. Cette option est disponible lorsque le travail a été groupé par le collaborateur ou par Microsoft Dynamics 365 for Operations. Lorsque le collaborateur a terminé tout le travail de prélèvement dans le groupe, le travail de rangement est créé pour le même groupe.</td>
</tr>
<tr class="even">
<td>Types d'ajustements de stock</td>
<td>Sélectionnez le type d'ajustement de stock qui détermine le journal d'inventaire utilisé pour valider l'ajustement, et si supprimer des réservations. Ce champ n'est disponible que pour les processus de création de travail <strong>Ajustement en entrée</strong> ou <strong>Ajustement en sortie</strong>.</td>
</tr>
<tr class="odd">
<td>Remplacer le numéro de traitement par lots</td>
<td>Sélectionnez cette option pour que les collaborateurs qui doivent enregistrer une quantité comme terminée pour un ordre de fabrication puissent entrer un numéro de lot qui diffère du numéro de lot affecté à l'ordre de fabrication.</td>
</tr>
<tr class="even">
<td>Remplacer le contenant cible</td>
<td>Sélectionnez cette option pour permettre aux collaborateurs de spécifier un numéro de contenant cible différent du contenant cible suggéré. Utilisez cette option lorsque la première sélection d'un ordre d'exécution concerne la quantité entière d'un article dans un contenant. Cette option est utile si, par exemple, une palette est réutilisée.</td>
</tr>
<tr class="odd">
<td>Prélever et emballer</td>
<td>Sélectionnez cette option pour permettre aux collaborateurs d'associer un travail pour une commande client ou un chargement dans une seule unité de travail. Un collaborateur peut effectuer le travail uniquement pour la commande client ou le chargement. Cette option est utile si, par exemple, vous devez augmenter une quantité pour une commande client après que le chargement et que l'expédition et le travail ont été créés pour la commande client. Cette option est disponible lorsque l'option de menu utilise le travail existant, et le travail est dirigé par l'utilisateur ou le système.</td>
</tr>
<tr class="even">
<td>Aucun(e)</td>
<td>Indiquez si le collaborateur doit prélever en premier le lot le plus ancien dans un emplacement. Les options suivantes sont disponibles :
<ul>
<li><strong>Aucun</strong> – Le collaborateur peut prélever n'importe quel lot dans l'emplacement. Le collaborateur ne reçoit aucun message.</li>
<li><strong>Avertir</strong> – Le collaborateur peut prélever n'importe quel lot dans l'emplacement, mais il reçoit un message d'avertissement si un lot n'est pas le plus ancien.</li>
<li><strong>Forcer</strong> – Le collaborateur doit prélever en premier le lot le plus ancien dans l'emplacement. Il reçoit un message d'erreur si un lot n'est pas le plus ancien. <strong>Remarque :</strong> cette option est pertinente uniquement si <strong>Numéro du lot</strong> est inférieure à <strong>Emplacement</strong> dans la hiérarchie de réservation affectée à l'article.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Imprimer l'étiquette</td>
<td>Sélectionnez cette option pour permettre aux collaborateurs d'imprimer des étiquettes de contenant.</td>
</tr>
<tr class="even">
<td>Champ de regroupement système</td>
<td>Sélectionnez le champ qui détermine comment Microsoft Dynamics 365 for Operations groupe les travaux de prélèvement pour les collaborateurs. Par exemple, si vous sélectionnez le champ <strong>ShipmentId</strong>, le collaborateur numérisera l'ID d'expédition pour regrouper les travaux de prélèvement. Tout le travail d'expédition est alors affecté au collaborateur. Ce champ nécessite la création d'une option de menu pour utiliser le travail existant qui est groupé par le système. Vous devez également entrer du texte dans le champ <strong>Étiquette de regroupement système</strong> pour indiquer au collaborateur ce qu'il doit numériser.</td>
</tr>
<tr class="odd">
<td>Étiquette de regroupement système</td>
<td>Entrez le texte qui indique au collaborateur quoi numériser lorsque le travail de prélèvement est groupé par Microsoft Dynamics 365 for Operations. Par exemple, si vous utilisez le champ <strong>ShipmentId</strong> pour grouper le travail de prélèvement par expédition, vous pouvez entrer <strong>ID expédition</strong> dans le champ. Ce champ nécessite la création d'une option de menu pour utiliser le travail existant qui est groupé par le système. Vous devez également sélectionner le champ de groupement en fonction du champ <strong>Champ de regroupement système</strong>.</td>
</tr>
<tr class="even">
<td>Utiliser les données par défaut</td>
<td>Sélectionnez cette option pour activer le bouton <strong>Données par défaut</strong> du volet Actions, permettant de sélectionner les champs qui affichent les données dont un collaborateur a généralement besoin dans son travail quotidien. Cette option est utile si, par exemple, un collaborateur prélève souvent des articles à partir du même emplacement. Vous pouvez sélectionner le champ <strong>Emplacement d'origine</strong> pour afficher l'emplacement par défaut.</td>
</tr>
<tr class="odd">
<td>Champ Utilisateur validé dirigé</td>
<td>Sélectionnez le champ qu'un collaborateur numérisera pour grouper le travail. Par exemple, si vous sélectionnez <strong>LoadId</strong>, un collaborateur peut prélever tout travail associé à un chargement sélectionné. Vous devez également entrer du texte dans le champ <strong>Étiquette d'utilisateur validé dirigé</strong> pour indiquer au collaborateur ce qu'il doit numériser.</td>
</tr>
<tr class="even">
<td>Étiquette d'utilisateur validé dirigé</td>
<td>Entrez le texte qui indique au collaborateur quoi numériser lorsque le travail de prélèvement est groupé par un champ utilisateur validé dirigé. Par exemple, si vous utilisez le champ <strong>LoadId</strong> pour regrouper le travail de prélèvement pour un chargement, vous pouvez entrer <strong>ID chargement</strong> dans le champ.</td>
</tr>
<tr class="odd">
<td>Code modèle de travail</td>
<td>Sélectionnez le modèle de travail qui crée le travail pour un processus. Par exemple, si vous recevez un article pour une commande fournisseur, le travail de rangement sera généré selon le modèle de travail. Si vous ne sélectionnez pas un modèle de travail, Microsoft Dynamics 365 for Operations affecte un modèle selon des critères de requête. Pour plus d'informations sur les modèles de travail, voir <a href="control-warehouse-location-directives.md">Contrôle du travail d'entrepôt à l'aide de modèles de travail et d'instructions d'emplacement</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>Exiger que les collaborateurs confirment le produit, l'emplacement ou la quantité en prélevant des articles
Vous pouvez paramétrer des confirmations de travail qui exigent que le collaborateur utilise un appareil mobile pour enregistrer l'emplacement ou la quantité lorsqu'il effectue un travail dans l'entrepôt. Les confirmations de travail permettent de garantir que le collaborateur se trouve à l'emplacement correct, ou traite la quantité correcte d'articles. Vous pouvez également activer Microsoft Dynamics 365 for Operations pour confirmer automatiquement l'enregistrement du collaborateur. Si vous activez la confirmation automatique, vous ne pouvez pas également demander de confirmer l'emplacement ou la quantité. Les confirmations de travail incluent également les produits et les variantes de produit. En outre, vous pouvez enregistrer des confirmations en numérisant un code-barres. Pour confirmer les produits et les variantes de produit, vous devez entrer un ID pour le produit ou la variante de produit. Cela peut être un ID produit, un ID de recherche de produit, un ID externe, un code GTIN ou un code-barres. Une fois l'ID entré ou le code-barres numérisé, les dimensions de la variante de produit sont affichées dans l'appareil mobile. 

Le tableau suivant décrit les différents types de travail avec lesquels vous pouvez utiliser des confirmations de travail.

| Option                 | Description                                                                |
|------------------------|----------------------------------------------------------------------------|
| Prélever                   | Exigez la confirmation lorsque des articles sont prélevés.                                |
| Placer                    | Exigez la confirmation lorsque des articles sont placés dans un emplacement.                     |
| Comptage               | Exigez la confirmation lors d'un inventaire tournant.                                |
| Ajustements            | Exigez la confirmation lorsque des quantités en stock sont ajustées.               |
| Personnalisée                 | Exigez la confirmation pour un travail personnalisé.                                      |
| Contrôle             | Exigez la confirmation lorsque des articles sont déplacés en zone de contrôle.                   |
| Création de contenant | Exigez la confirmation lorsque des articles sont consolidés pour générer un contenant. |
| Imprimer                  | Exigez la confirmation lorsque des étiquettes de contenant sont imprimées.                |
| Modification de statut          | Exigez la confirmation lorsque le statut du stock est modifié.              |

**Remarque :** vous ne pouvez demander la confirmation du produit que pour les types de prélèvement et de rangement.

<a name="see-also"></a>Voir également :
--------

[Paramètres d'affichage de l'appareil mobile de l'entrepôt](change-warehouse-mobile-device-displays.md)

[Configurer une option de menu de périphérique portable pour terminer le travail du type commande fournisseur (guide de tâche)](https://ax.help.dynamics.com/en/wiki/set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order/)

[Configurer une option de menu de périphérique portable pour enregistrer les articles reçus (guide de tâche)](https://ax.help.dynamics.com/en/wiki/set-up-a-mobile-device-menu-item-to-register-received-items/)


