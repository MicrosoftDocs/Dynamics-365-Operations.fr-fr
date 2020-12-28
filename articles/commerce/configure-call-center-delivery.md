---
title: Configurer les modes de livraison et les frais du centre d'appels
description: Cette rubrique décrit la procédure de paramétrage des modes de livraison et des frais pour une commande du centre d'appels dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9919e76b5e3eb1a43c5a0ecd5dda1462bedad4f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412173"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Configurer les modes de livraison et les frais du centre d'appels

[!INCLUDE [banner](includes/banner.md)]

Lorsqu'une commande client est passée dans Dynamics 365 Commerce, si la personne qui saisit la commande client est associée à un canal du centre d'appels, une logique et des règles sont utilisées pour valider le mode de livraison et calculer les frais associés à la commande.

Lorsque vous créez une commande client, vous pouvez sélectionner un mode de livraison dans l'en-tête de la commande client et les lignes de la commande client. Par défaut, le mode de livraison sélectionné dans l'en-tête est utilisé pour toutes les lignes de la commande client. Toutefois, vous pouvez remplacer le mode de livraison par défaut sur des lignes individuelles si nécessaire. Vous pouvez également définir un mode de livraison dans un enregistrement client. Ainsi, lorsque des commandes sont créées pour le client, ce mode de livraison est utilisé par défaut dans l'en-tête de la commande client.

Commerce a des fonctionnalités permettant aux utilisateurs de limiter les modes de livraison qui peuvent être utilisés par un canal, les modes de livraison qui peuvent être utilisés pour un produit et les modes de livraison qui sont valides pour des destinations d'expédition spécifiques. Les frais peuvent également être définis afin que des frais supplémentaires soient ajoutés à la commande d'un client, selon les modes de livraison sélectionnés pour la commande client et la valeur totale de la commande.

## <a name="define-delivery-modes"></a>Définir les modes de livraison

Avant de spécifier les modes de livraison qui peuvent être utilisés pour les commandes du centre d'appels et de définir les règles et les frais associés, vous devez définir les modes de livraison. Allez dans **Ventes et marketing \> Paramétrage \> Distribution \> Modes de livraison**. Sélectionnez **Nouveau** pour créer un mode de livraison. Sinon, sélectionnez un mode de livraison existant dans la liste, puis sélectionnez **Modifier** pour apporter des modifications.

Dans le champ **Mode de livraison**, vous pouvez saisir une combinaison de caractères alphanumériques, selon les besoins de votre entreprise. Vous pouvez ensuite utiliser le champ **Description** pour fournir un contexte supplémentaire. Les champs **Groupe de frais** et **Expédition** sont facultatifs et sont expliqués en détail plus loin dans cette rubrique.

Dans l'organisateur **Canaux Commerce**, ajoutez tout canal qui doit être autorisé à utiliser le mode de livraison lorsque des transactions de vente sont créées dans ce canal.

Dans l'organisateur **Produits**, vous pouvez spécifier les produits et/ou les catégories de produits pour lesquels le mode de livraison peut ou pas être utilisé. Par exemple, si un produit ne peut pas être expédié par avion en raison des restrictions appliquées aux matières dangereuses, vérifiez que le produit ou la catégorie de produit est exclu de tous les modes de livraison impliquant le transport aérien.

Dans l'organisateur **Adresses**, vous pouvez spécifier les pays, régions ou états pour lesquels le mode de livraison peut ou pas être utilisé. Par exemple, les commandes à destination d'Hawaï ou de l'Alaska ne peuvent pas être expédiées par voie terrestre. Par conséquent, ces états doivent être exclus des modes de livraison associés à un service de livraison terrestre, mais inclus dans les modes de livraison associés à un service de livraison aérienne.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Valider les modes de livraison pour une commande du centre d'appels

Une fois que les modes de livraison sont définis, vous devez exécuter le traitement par lots **Traiter les modes de livraison**. Cette tâche rend les modes de livraison disponibles afin qu'ils puissent être utilisés dans les processus de commande client pour les canaux. Pour exécuter la tâche **Traiter les modes de livraison**, accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Traiter les modes de livraison**. Cette tâche doit être exécutée chaque fois que de nouveaux modes de livraison sont ajoutés à un canal ou que des modifications sont apportées aux relations existantes entre le mode de livraison et le canal.

Lorsque vous exécutez le traitement par lots **Traiter les modes de livraison**, vous pouvez accéder à **Commerce et vente au détail \> Canaux \> Centres d'appels \> Tous les centres d'appels**. Dans la page **Tous les centres d'appels**, dans le volet Actions, sous l'onglet **Paramétrage**, sélectionnez **Modes de livraison**. La page **Modes de livraison** répertorie tous les modes de livraison valides pour le canal sélectionné du centre d'appels. Pour modifier les modes de livraison existants ou pour ajouter de nouveaux modes de livraison, sélectionnez **Gérer les modes de livraison**. Notez que la tâche **Traiter les modes de livraison** doit être exécutée chaque fois que des modifications sont apportées.

## <a name="define-charges-for-delivery-services"></a>Définir les frais pour les services de livraison

Lorsque des commandes client sont créées pour les clients, une société peut ajouter des frais qui sont automatiquement calculés selon les modes de livraison sélectionnés pour la commande. Ces frais peuvent être configurés pour être identiques pour tous les clients et modes de livraison. Les frais peuvent également varier, selon le client et/ou les modes de livraison sélectionnés pour la commande client.

Pour définir les frais, accédez à **Commerce et vente au détail \> Paramétrage du canal \> Frais \> Frais auto**. Sélectionnez **Nouveau** pour ajouter de nouveaux frais. Sinon, sélectionnez une entrée existante, puis sélectionnez **Modifier**.

Les frais peuvent être définis pour être calculés au niveau de l'en-tête de la commande ou des lignes de la commande. Utilisez le champ **Niveau** pour sélectionner le niveau souhaité.

Les frais peuvent être définis pour un client spécifique, un groupe de clients ou tous les clients. Dans le champ **Code compte**, sélectionnez **Table** pour définir les frais appliqués uniquement à un client spécifique. Sélectionnez **Groupe** pour définir les frais associés à un groupe de clients spécifique. Sélectionnez **Tous** pour appliquer les frais à chaque client qui passe une commande client qui utilise le mode de livraison associé. Si vous avez sélectionné **Table** ou **Groupe** dans le champ **Code compte**, sélectionnez le client ou le groupe de clients dans le champ **Relation compte**.

Les frais peuvent être configurés pour être appliqués pour un mode de livraison spécifique, un groupe de modes de livraison ou tous les modes de livraison. Si vous sélectionnez **Table** dans le champ **Code mode de livraison**, vous devez sélectionner un mode de livraison spécifique dans le champ **Groupe Mode de livraison**. Si vous sélectionnez **Groupe**, vous devez sélectionner un groupe de modes de livraison dans le champ **Groupe Mode de livraison**. Les groupes de modes de livraison sont définis sous **Commerce et vente au détail \> Paramétrage du canal \> Frais \> Groupe de frais de livraison**. Ils peuvent ensuite être associés à un ou plusieurs modes de livraison dans la page **Modes de livraison**. Si vous sélectionnez un groupe lorsque vous définissez les frais, tout mode de livraison associé au groupe de livraison sélectionné utilise ces frais. Enfin, si vous sélectionnez **Tous** dans le champ **Code mode de livraison**, tous les modes de livraison utilisent les frais. Par conséquent, vous ne sélectionnez pas de valeur dans le champ **Groupe Mode de livraison**.

Dans la section **Lignes**, vous pouvez définir un ou plusieurs frais par devise, selon vos besoins. Les frais doivent être associés à un code frais qui définit les règles de validation financière pour les frais. Le champ **Catégorie** permet de définir le mode de calcul des frais. Par exemple, si les clients doivent être soumis à un taux forfaitaire de $9,95 pour qu'une commande soit expédiée selon un mode de livraison spécifique, utilisez la catégorie **Fixe**. Si l'entreprise décide de facturer aux clients un pourcentage du total de la commande pour couvrir les frais de livraison, utilisez la catégorie **Pourcentage**. Les frais réels appliqués aux clients sont définis dans le champ **Valeur des frais**.

Les sociétés configurent souvent des frais progressifs. Dans ce cas, le montant que les clients paient pour la livraison est basé sur la valeur de la commande. Pour configurer les frais progressifs, entrez des valeurs dans les champs **Montant de départ** et **Montant d'arrivée** et définissez les frais proprement dit dans le champ **Valeur des frais**. Par exemple, pour les commandes qui ont une valeur inférieure à $50, un détaillant facture $5,95 pour l'expédition par voie terrestre. Pour les commandes qui ont une valeur supérieure ou égale à $50, mais inférieure à $100, le détaillant facture $7,95. Enfin, pour les commandes qui ont une valeur supérieure ou égale à $100, le détaillant ne facture aucun frais d'expédition. L'illustration suivante présente la configuration de ces frais.

![Exemple de frais progressifs fixes](media/fixedtieredcharges.png)

Vous pouvez utiliser une combinaison de catégories pour les frais, selon les besoins de votre entreprise. Par exemple, pour toutes les commandes qui ont une valeur inférieure à $100, des frais fixes de $9,95 sont facturés pour l'expédition. Ensuite, pour les commandes dont la valeur est supérieure ou égale à $100, les frais de livraison sont calculés au taux de 5 % de la valeur de la commande. L'illustration suivante présente la configuration de ces frais.

![Exemple de frais progressifs mixtes](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Appliquer les modes de livraison lors de la saisie d'une commande dans un centre d'appels

Lorsqu'une commande client est créée, une valeur doit être spécifiée dans le champ **Mode de livraison** de l'organisateur **Livraison** de l'en-tête de la commande client. Ce champ peut être renseigné automatiquement, selon les valeurs par défaut de l'enregistrement client.

Le mode de livraison défini dans l'en-tête de la commande est automatiquement copié sur les lignes de la commande client lors de leur création. Toutefois, vous pouvez modifier le paramétrage du mode de livraison pour une ligne spécifique dans l'onglet **Livraison** de la section **Détails de ligne** de la page de saisie de la commande client.

Si le mode de livraison sélectionné n'est pas valide pour le produit ou l'adresse de livraison définie pour la commande ou la ligne de commande, vous recevez un message d'erreur. Vous devez alors sélectionner un mode de livraison qui a été défini pour prendre en charge cette configuration de produit ou d'adresse.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Calcul des frais de livraison lors de la saisie d'une commande

Si le paramètre **Activer l'achèvement de la commande** est activé pour le canal du centre d'appels, les frais d'expédition sont automatiquement calculés pour les commandes client lorsque les utilisateurs sélectionnent **Terminer**. Le message suivant s'affiche en haut de la page **Résumé de la commande client** : « Frais progressifs calculés ». Les frais calculés sont ajoutés à la valeur du champ **Total des ventes**. Dans l'organisateur **Montant**, le champ **Frais** affiche le montant total des frais qui ont été calculés pour la commande et les lignes. Pour afficher une analyse plus détaillée des frais, sélectionnez **Commande** dans la page **Résumé de la commande client**, puis sélectionnez l'option **Frais** pour afficher, ajouter ou modifier les frais. Notez que le calcul des frais de livraison dans l'en-tête de la commande est basé sur le mode de livraison associé à l'en-tête. Les frais de livraison au niveau de la ligne sont calculés sur la base du mode de livraison configuré pour la ligne de vente. Si plusieurs modes de livraison sont utilisés sur différentes lignes, des frais multiples peuvent être appliqués et ajoutés simultanément. Le montant total est alors affiché dans le champ **Frais** de la page **Résumé de la commande client**.

Si le paramètre **Activer l'achèvement de la commande** est désactivé, les utilisateurs doivent déclencher manuellement le calcul des frais. Dans la page **Commande client**, dans le volet Actions, sous l'onglet **Vendre**, dans le groupe **Calculer**, sélectionnez **Frais progressifs**. Le message « Frais progressifs calculés » s'affiche. Vous pouvez alors sélectionner l'option **Frais** sous l'onglet **Vendre** pour afficher, modifier ou supprimer les frais calculés.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Utiliser les modes de livraison expédiés dans les commandes du centre d'appels

Vous pouvez éventuellement associer un code d'expédition à un mode de livraison que vous configurez. Ce code est utilisé comme outil de tri de l'ordre de priorité et de génération d'états. Il ne génère pas actuellement de frais supplémentaires à appliquer à la commande. Pour paramétrer des codes d'expédition, accédez à **Ventes et marketing \> Paramétrage \> Distribution \> Codes d'expédition**.

Par exemple, pour les commandes à expédier par avion le lendemain, le prélèvement doit être effectué dans l'entrepôt avant 13h chaque jour. Dans ce cas, un code d'expédition peut être créé, et ce code peut être associé à tout mode de livraison le lendemain qui est configuré dans le système. Lorsque l'entrepôt crée sa vague de prélèvement, le code d'expédition approprié dans le champ **Expédition** peut être utilisé comme filtre, afin que le prélèvement soit exécuté uniquement pour les commandes dont les modes de livraison sont associés à ce code.

En outre, lorsqu'une commande du centre d'appels est saisie, un code d'expédition peut être manuellement appliqué à l'en-tête de la commande client ou à une ligne individuelle de la commande client. Le code peut également être utilisé pour les besoins de tri ou de génération d'états. Une commande doit parfois être traitée avec précaution en raison d'un problème de service client. Dans ce cas, un code d'expédition spécifique peut être appliqué à l'en-tête ou aux lignes de la commande pour aider à identifier et hiérarchiser la commande lors du processus d'exécution.
