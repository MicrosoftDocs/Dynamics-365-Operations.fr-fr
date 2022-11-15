---
title: Automatisation de l’approvisionnement sur commande
description: Cet article décrit comment configurer et utiliser les différentes améliorations ajoutées par la fonctionnalité d’automatisation de l’approvisionnement à la commande.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d376c2f4d8514a4e6122e2e94455d57a39d2babf
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740192"
---
# <a name="make-to-order-supply-automation"></a>Automatisation de l’approvisionnement sur commande

[!include [banner](../includes/banner.md)]

La fonctionnalité *Automatisation de l’approvisionnement sur commande* ajoute plusieurs améliorations à Microsoft Dynamics 365 Supply Chain Management. Ces améliorations vous permettent d'effectuer les tâches suivantes :

- Affichez la charge de capacité des ressources pour une période définie par l’utilisateur et activez ainsi l’évaluation à long terme de la charge de capacité.
- Améliorez la flexibilité en contrôlant la tolérance de retard (jours négatifs) pour chaque plan directeur.
- Maintenez la disponibilité des produits pour les commandes de dernière minute et optimisez l’utilisation de l’offre existante en rattachant la dernière offre possible à une demande au lieu d’utiliser la première offre possible.
- Gardez l’affectation des composants flexible pour les ordres de fabrication après confirmation, afin que le système puisse optimiser les changements de demande de dernière minute. En d’autres termes, limitez la notation à un seul niveau.
- Contrôlez la politique d’exécution pour chaque commande client. Les paramètres par défaut sont issus de la configuration client.
- Améliorez le flux d'informations intersociétés Les bons de commande sont mis à jour afin d’inclure des champs pour le mode de livraison, les conditions de livraison et le numéro d’article externe. Cette modification garantit que des informations détaillées sur la demande peuvent être transmises à l’entreprise fournisseur.

Cet article explique comment configurer et utiliser chaque amélioration.

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>Activez la fonction d’automatisation de l’approvisionnement sur commande

Avant de pouvoir utiliser la fonctionnalité décrite dans cet article, vous devez l'activer pour votre système. L'administration peut utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), où la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Planification générale*
- **Nom de la fonctionnalité :** *Automatisation de l’approvisionnement sur commande*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>Définissez le nombre de jours à afficher sur la page de charge de capacité

La page **Capacité de charge** vous permet d’évaluer la capacité disponible d’une ressource. La fonctionnalité *Automatisation de l’approvisionnement sur commande* améliore la page **Capacité de charge** en ajoutant un champ **Nombre de jours**. Vous pouvez utiliser ce champ pour limiter le nombre de jours que la grille **Aperçu** affiche. La valeur que vous définissez est enregistrée dans la mémoire. Par conséquent, si vous quittez la page et y revenez plus tard, la grille **Aperçu** affichera toujours le nombre de jours que vous avez spécifié pour la dernière fois.

Pour ouvrir la page **Capacité de charge** afin de pouvoir évaluer la capacité disponible pour une ressource individuelle, suivez ces étapes.

1. Accédez à **Administration d’organisation \> Ressources \> Ressources**.
1. Sélectionner une ressource à inspecter.
1. Dans le volet Action, sur l’onglet **Ressource**, dans le groupe **Afficher**, sélectionnez **Charge maximale**.
1. Utilisez le filtre **Nombre de jours** pour limiter le nombre de jours que la grille **Aperçu** affiche.

Pour ouvrir la page **Capacité de charge** afin de pouvoir évaluer la capacité disponible pour un groupe de ressources, suivez ces étapes.

1. Allez dans **Administration d’organisation \> Ressources \> Groupes de ressources**.
1. Sélectionner un groupe de ressources à inspecter.
1. Dans le volet Action, sur l’onglet **Groupe de ressources**, dans le groupe **Afficher**, sélectionnez **Charge maximale**.
1. Utilisez le filtre **Nombre de jours** pour limiter le nombre de jours que la grille **Aperçu** affiche.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Appliquer un seul niveau de marquage lorsque vous confirmez des ordres planifiés

Le *Marquage* est utilisé pour relier l’offre et la demande. Il ressemble à l’*origine des besoins*, qui indique comment la planification prévoit de couvrir la demande. Cependant, le marquage est plus permanent que l'origine des besoins. La caractéristique *Automatisation de l’approvisionnement sur commande* ajoute la possibilité de limiter le marquage des stocks à un seul niveau lorsque les commandes planifiées sont confirmées. Elle ajoute les nouvelles options suivantes au champ **Mettre à jour le marquage** dans la boîte de dialogue **Confirmation** lorsque vous confirmez une commande planifiée :

- *Norme à niveau unique* – Marquage à niveau unique est utilisé. Le marquage à niveau marque uniquement l’article principal, et non ses composants de nomenclature (BOM). Par conséquent, vous pouvez conserver une affectation de composants flexible pour les ordres de fabrication après la confirmation. Le marquage à niveau unique permet au système d’optimiser les changements de demande de dernière minute. Dans la *norme* marquage à niveau unique, les commandes de besoins sont marquées par rapport à leurs commandes d’exécution, mais les commandes d’exécution ne sont pas marquées s’il reste de la quantité.
- *Prolongé à niveau unique* – Marquage à niveau unique est utilisé. Dans le marquage *prolongé* à niveau unique, les commandes de besoins sont marquées par rapport à leurs commandes d’exécution, et les commandes d’exécution sont toujours marquées, indépendamment du fait qu'il reste ou non une quantité.

Ces options sont également disponibles dans le champ **Mettre à jour le marquage** sur l'onglet **Mise à jour standard** de la page **Paramètres de planification générale**, où vous définissez la sélection par défaut pour la boite de dialogue **Confirmation**.

Pour plus d’informations, consultez [Marquage du stock](planning-optimization/marking.md).

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Définir la tolérance de retard (jours négatifs) au niveau du plan directeur

La caractéristique *Automatisation de l’approvisionnement sur commande* ajoute la possibilité de configurer la tolérance de retard (jours négatifs) au niveau du plan directeur. Le paramètre est également disponible au niveau de la couverture de l’article et du groupe de couverture. Si des jours négatifs sont affectés à plusieurs niveaux, le système applique la hiérarchie suivante pour décider du paramètre à utiliser :

- Si les jours négatifs sont configurés sur la page **Plans principaux**, ce paramètre remplace tous les autres paramètres de jours négatifs lors de l’exécution du plan.
- Si des jours négatifs sont configurés sur la page **Couverture des éléments**, ce paramètre remplace le paramètre du groupe de couverture.
- Les jours négatifs qui sont configurés sur la page **Groupes de couverture** s’appliquent uniquement si les jours négatifs n’ont pas été configurés pour un article ou un plan directeur pertinent.

Pour définir des jours négatifs pour un plan directeur, suivez ces étapes.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan directeur dans le volet liste ou créez-en un nouveau.
1. Sur le raccourci **Plages de gestion en jours**, définissez l’option **Jours négatifs** sur *Oui*.
1. Dans le champ voisin, entrez le nombre de jours négatifs à autoriser.

Pour plus d’informations sur l’utilisation de jours négatifs, consultez [Tolérance de retard (jours négatifs)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Contrôle de la séquence d'origine des besoins utilisée lors de la planification générale

Le plan directeur utilise une *séquence d’origine des besoins* pour déterminer quelle offre couvrira quelle demande. La caractéristique *Automatisation de l’approvisionnement sur commande* ajoute une nouvelle option **Utiliser la dernière offre possible** qui vous donne plus de contrôle sur la séquence d'origine des besoins. La nouvelle option vous permet de garder les produits disponibles pour les commandes de dernière minute et d'optimiser l’utilisation de l’offre existante en rattachant la dernière offre possible à une demande au lieu d’utiliser la première offre possible.

Vous pouvez définir la séquence d’origine des besoins au niveau du plan directeur, de la couverture des articles ou du groupe de couverture. Si une séquence d'origine des besoins est configurée à plusieurs niveaux, le système applique la hiérarchie suivante pour décider du paramètre à utiliser :

- Si une séquence d'origine des besoins est configurée sur la page **Schémas directeurs**, ce paramètre remplace tous les autres paramètres de séquence d’origine des besoins lorsque le plan s’exécute.
- Si une séquence d'origine des besoins est configurée sur la page **Couverture des articles**, ce paramètre remplace le paramètre du groupe de couverture.
- La séquence d'origine des besoins qui est configurée sur la page **Groupes de couverture** s’applique uniquement si les paramètres de la séquence d’origine des besoins n’ont pas été configurés pour un article ou un plan directeur pertinent.

Pour configurer l’origine des besoins au niveau du groupe de couverture, suivez ces étapes.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Groupes de couverture**.
1. Sélectionnez un groupe dans le volet liste, ou créez-en un nouveau.
1. Sur le raccourci **Général**, dans la section **Séquence d’origine des besoins**, utilisez les champs **Consommer l’inventaire disponible** et **Utiliser la dernière offre** pour configurer votre séquence d'origine des besoins. Le tableau plus loin dans cette section montre comment ces paramètres sont combinés pour définir votre séquence d'origine des besoins.

Pour configurer l’origine des besoins au niveau de la couverture de l'article, suivez ces étapes.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez un produit dans la grille, ou créez-en un nouveau.
1. Dans le volet Actions, sur l’onglet **Plan**, sélectionnez **Couverture de l’article**.
1. La page **Couverture de l’article** fournit des lignes qui vous permettent de définir les règles de couverture qui s’appliquent à l’article dans chaque entrepôt. Sélectionnez une ligne existante dans la grille, ou créez-en une.
1. Sur l'onglet **Général**, sélectionnez la case à cocher **Remplacer la séquence d'origine des besoins**.
1. Utilisez les champs **Consommer l’inventaire disponible** et **Utiliser la dernière offre** pour configurer votre séquence d'origine des besoins. Le tableau plus loin dans cette section montre comment ces paramètres sont combinés pour définir votre séquence d'origine des besoins.

Pour configurer l’origine des besoins au niveau du plan directeur, suivez ces étapes.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan directeur dans le volet liste ou créez-en un nouveau.
1. Dans le raccourci **Général**, définissez l’option **Remplacer la séquence d'origine des besoins** sur *Oui*.
1. Utilisez les champs **Consommer l’inventaire disponible** et **Utiliser la dernière offre** pour configurer votre séquence d'origine des besoins. Le tableau plus loin dans cette section montre comment ces paramètres sont combinés pour définir votre séquence d'origine des besoins.

Le tableau suivant montre comment les paramètres **Consommer l’inventaire disponible** et **Utiliser la dernière offre** sont combinés pour établir votre séquence d'origine des besoins.

| | Utiliser la dernière offre possible = Oui | Utiliser la dernière offre possible = Non |
|---|---|---|
| **Consommer l’inventaire disponible** = *Avant toute offre* | <ol><li>Disponible</li><li>Approvisionnement existant pouvant répondre à la date de la demande</li><li>Approvisionnement existant qui ne peut pas répondre à la date de la demande, mais toujours dans les jours négatifs</li><li>Créez un nouvel approvisionnement (commande planifiée)</li></ol> | <ol><li>Disponible</li><li>Approvisionnement existant pouvant répondre à la date de la demande</li><li>Approvisionnement existant qui ne peut pas répondre à la date de la demande, mais toujours dans les jours négatifs</li><li>Créez un nouvel approvisionnement (commande planifiée)</li></ol> |
| **Consommer l’inventaire disponible** = *Après tout approvisionnement* | <ol><li>Approvisionnement existant pouvant répondre à la date de la demande</li><li>Disponible</li><li>Approvisionnement existant qui ne peut pas répondre à la date de la demande, mais toujours dans les jours négatifs</li><li>Créez un nouvel approvisionnement (commande planifiée)</li></ol> | <ol><li>Approvisionnement existant pouvant répondre à la date de la demande</li><li>Approvisionnement existant qui ne peut pas répondre à la date de la demande, mais toujours dans les jours négatifs</li><li>Disponible</li><li>Créez un nouvel approvisionnement (commande planifiée)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Examiner et définir la politique d’exécution qui s’applique à chaque commande client

Les politiques d'exécution contrôlent le pourcentage du prix total de la commande ou de la quantité totale de la commande qui doit être physiquement réservée avant qu'une commande client puisse être lancée à l'entrepôt. Vous pouvez définir une stratégie d’exécution globale par défaut, puis la remplacer pour des clients spécifiques selon vos besoins. La caractéristique *Automatisation de l’approvisionnement sur commande* ajoute la possibilité de voir quelle politique par défaut s’applique réellement à n’importe quelle commande et d’appliquer un remplacement spécifique à la commande si nécessaire.

- Pour définir la politique d’exécution globale par défaut pour les commandes client, accédez aux paramètres **Comptes débiteurs \> Configurer \> Comptes clients**. Ensuite, sur l'onglet **Gestion d’entrepôt**, définissez le champ **Politique d’exécution des commandes clients** au nom de la stratégie que vous souhaitez utiliser. 
- Pour définir une politique d’exécution spécifique au client pour les commandes client, accédez à **Comptes débiteurs \> Clients \> Tous les clients**. Ensuite, sur l'onglet **Entrepôt**, définissez le champ **Politique d’exécution** au nom de la stratégie que vous souhaitez utiliser.

Pour afficher la politique par défaut qui s’applique à n’importe quelle commande et appliquer un remplacement spécifique à la commande, suivez ces étapes.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Ouvrez la commande client que vous souhaitez inspecter ou modifier.
1. Sélectionnez la vue **En-tête**.
1. Sur le raccourci **Entrepôt**, passez en revue et modifiez les champs suivants si nécessaire :

    - **Politique d’exécution des commandes** – Sélectionnez la politique d’exécution à utiliser pour la commande sélectionnée. La politique par défaut sera remplacée. Pour utiliser la politique d’exécution par défaut qui s’affiche dans le champ **Politique d’exécution par défaut**, laissez ce champ vide.
    - **Politique d’exécution par défaut** – Ce champ affiche la politique d’exécution par défaut qui s’applique si le champ **Politique d’exécution des commandes** est vide. Ce champ est en lecture seule. S’il est vide, aucune stratégie d’exécution par défaut spécifique au client ou globale n’est définie.

    Si les deux champs **Politique d’exécution de commande** et **Politique d’exécution par défaut** sont vides, aucune politique d’exécution ne s'applique. Cependant, d’autres restrictions peuvent être en place et peuvent nécessiter que des réservations ou d’autres conditions soient remplies avant que la commande client puisse être lancée.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>Définissez le mode de livraison et les conditions sur les lignes de bon de commande individuelles

Tous les bons de commande comprennent les paramètres **Conditions de livraison** et **Mode de livraison** sur l’en-tête de la commande. La caractéristique *Automatisation de l’approvisionnement sur commande* ajoute ces paramètres à chaque ligne de commande. Par conséquent, vous pouvez définir des remplacements de la valeur **Conditions de livraison** et/ou **Mode de livraison** pour une ou toutes les lignes de commande selon les besoins. Pour les lignes où aucun remplacement n’est défini, la valeur de l’en-tête est utilisée. Vous pouvez spécifier si une modification de la valeur de l’un de ces champs ou des deux sur l’en-tête de la commande doit également mettre à jour toutes les lignes.

Pour spécifier ce qui doit arriver aux paramètres de ligne si un utilisateur modifie la valeur **Conditions de livraison** et/ou **Mode de livraison** sur un en-tête de commande, suivez ces étapes.

1. Accédez à **Approvisionnements \> Paramétrage \> Paramètres d’approvisionnements**.
1. Sur l'onglet **Général**, sur le raccourci **Valeurs et paramètres par défaut**, sélectionnez le lien **Mettre à jour les lignes de commande**.
1. Dans la boîte de dialogue **Mettre à jour les lignes de commande**, dans les champs **Mise à jour des conditions de livraison** et **Mettre à jour le mode de livraison**, sélectionnez l’une des valeurs suivantes :

    - *Jamais* – Ne mettez jamais à jour les lignes de commande après la modification des paramètres dans l’en-tête de commande.
    - *Toujours* – Toujours mettre à jour toutes les lignes de commande après la modification des paramètres dans l’en-tête de commande.
    - *Rapide* – Si un utilisateur modifie un ou les deux paramètres sur l’en-tête de la commande, ouvrez un robot de dialogue qui demande si l’utilisateur souhaite mettre à jour toutes les lignes afin qu’elles correspondent à la modification d’un ou des deux paramètres.

Pour définir les informations de livraison sur un en-tête de bon de commande, suivez ces étapes.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Ouvrez la commande client que vous souhaitez modifier.
1. Sélectionnez la vue **En-tête**.
1. Sur le raccourci **Livraison**, définissez les champs **Mode de livraison** et **Conditions de livraison** selon les besoins.
1. En fonction des paramètres de la page **Paramètres des approvisionnements**, il se peut que l’on vous demande si vous souhaitez appliquer vos modifications à toutes les lignes de commande.

Pour définir les remplacements des informations de livraison pour une ligne de commande fournisseur, suivez ces étapes.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Ouvrez la commande client que vous souhaitez modifier.
1. Sélectionnez la vue **Lignes**.
1. Sur le raccourci **Lignes de commande fournisseur**, sélectionnez la ligne à modifier.
1. Sur le raccourci **Détails de lignes**, sur l'onglet **Livraison**, définissez les champs **Mode de livraison** et **Conditions de livraison** selon les besoins. Effacez un ou les deux champs pour utiliser les paramètres correspondants sur l’en-tête.

Pour les commandes intersociétés, les valeurs pour les champs **Mode de livraison** et **Conditions de livraison** de chaque ligne de commande fournisseur seront synchronisés entre la commande fournisseur et sa commande client associée.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Synchroniser les ID et les descriptions des articles externes pour les commandes intersociétés

Pour les commandes intersociétés, la fonctionnalité *Automatisation de l’approvisionnement sur commande* permet de synchroniser les ID et les descriptions textuelles des articles externes sur les lignes de commande fournisseur avec les lignes de commande client intersociétés associées, que la commande fournisseur soit ou non destinée à une livraison directe. La fonctionnalité ajoute également la possibilité de spécifier le compte client externe final sur une commande fournisseur intersociétés. Le système prendra ensuite automatiquement les ID et les descriptions textuelles des articles externes de l’enregistrement client externe au lieu de l’enregistrement fournisseur intersociétés (interne).

Pour configurer un fournisseur intersociétés afin de synchroniser les ID et les noms d’articles externes entre les commandes fournisseurs intersociétés et leurs commandes client intersociétés associées, suivez ces étapes.

1. Accédez à **Approvisionnements \> Fournisseurs \> Tous les fournisseurs**.
1. Sélectionnez le fournisseur intersociétés que vous souhaitez configurer.
1. Dans le volet Action, sous l'onglet **Général**, dans le groupe **Configurer**, sélectionnez **Intersociétés**.
1. Sur la page **Intersociétés**, sur l'onglet **Politiques de commande fournisseur**, dans la section **Commande fournisseur intersociétés -\> Commande client intersociétés**, sélectionnez la case à cocher **ID et nom d’article externe** .

Pour spécifier le compte du client externe final pour une commande fournisseur intersociétés, suivez ces étapes. Le champ **Compte client** s’applique uniquement aux commandes fournisseurs intersociétés. Utilisez-le pour spécifier le numéro de compte du client qui recevra éventuellement les marchandises. Lorsque ce champ est défini, les lignes de commande fournisseur prendront les descriptions et les numéros des articles externes du compte client spécifié au lieu du fournisseur intersociété spécifié sur la commande fournisseur. Si vous modifiez le compte client ultérieurement, les descriptions et ID des articles externes seront mis à jour afin qu’ils correspondent aux valeurs du nouveau compte. Les descriptions et ID des articles externes de chaque ligne seront également synchronisés avec la commande client intersociété correspondante.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Ouvrez la commande fournisseur que vous souhaitez configurer, ou créez-en une nouvelle.
1. Sélectionnez la vue **En-tête**.
1. Dans la section **Référence**, définissez le champ **Compte client** au compte client externe concerné.

Pour spécifier les ID et les descriptions textuelles des articles externes pour une ligne de commande fournisseur pour une commande intersociétés, suivez ces étapes. Les valeurs que vous définissez seront synchronisées avec les lignes de commande client intersociétés associées, que la commande fournisseur soit ou non destinée à une livraison directe.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Ouvrez la commande fournisseur que vous souhaitez configurer, ou créez-en une nouvelle.
1. Sélectionnez la vue **Lignes**.
1. Sur le raccourci **Lignes de commande fournisseur**, sélectionnez la ligne à modifier.
1. Sur le raccourci **Détails de la ligne**, sur l'onglet **Général**, dans la section **Ligne de commande**, dans le champ **Texte**, fournissez une description externe de l’article spécifié sur la ligne de commande sélectionnée. Cette valeur sera synchronisée avec la ligne de commande client intersociétés associée.
1. Dans la section **Référence**, dans le champ **Externe**, indiquez un ID d’article externe pour l’article spécifié sur la ligne de commande sélectionnée. Cette valeur sera synchronisée avec la ligne de commande client intersociétés associée.

Pour plus d'informations, voir [Créer et facturer une commande client intersociétés pour un client externe](../sales-marketing/intercompany-sales-order-for-external-customer.md).
