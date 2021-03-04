---
title: Réapprovisionnement sur la capacité de l’emplacement
description: Cette rubrique fournit des informations sur la fonctionnalité Réapprovisionnement sur la capacité de l’emplacement. Cette fonctionnalité permet de créer tout le travail de réapprovisionnement qui sera nécessaire pour la journée et gère la disponibilité de ce travail de réapprovisionnement pour garantir que le site de prélèvement ne soit pas à court de stock ni ne dépasse la capacité.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8e9ae16fea892d1d6b6a6b5d06137576623e7f5b
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428278"
---
# <a name="replenishment-over-location-capacity"></a>Réapprovisionnement sur la capacité de l’emplacement

[!include [banner](../includes/banner.md)]

Certains entrepôts à volume élevé ou à espace restreint doivent expédier plus de quantité d’un article en une journée que celle du lieu de prélèvement. La fonctionnalité *Réapprovisionnement sur la capacité de l’emplacement* permet de créer tout le travail de réapprovisionnement qui sera nécessaire pour la journée et gère la disponibilité de ce travail de réapprovisionnement pour garantir que le site de prélèvement ne soit pas à court de stock ni ne dépasse la capacité.

La fonctionnalité permet de créer plus de travaux de réapprovisionnement que ce qui peut en tenir à un emplacement, et elle empêche le travail de réapprovisionnement de se terminer lorsque l’emplacement est plein. À mesure que le stock de l’emplacement de prélèvement tombe en dessous d’un seuil configurable, plus de travail de réapprovisionnement est rendu disponible.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Activer la fonctionnalité Réapprovisionnement sur la capacité de l’emplacement

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre suivant) :

1. Blocage des tâches à l’échelle de l’organisation
1. Réapprovisionnement sur la capacité de l’emplacement

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configurer la fonctionnalité pour l’exemple de scénario

Cette section fournit des instructions et un exemple de la configuration de cette fonctionnalité et prépare des exemples de données pour l’exemple de scénario fourni plus loin dans cette rubrique.

### <a name="enable-sample-data"></a>Activer les exemples de données

Pour utiliser [l’exemple de scénario](#example-scenario) à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="location-profile"></a>Profil d’emplacement

Activez la fonctionnalité Réapprovisionnement sur la capacité de l’emplacement sur le profil d’emplacement.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacements**.
1. Dans le volet gauche, sélectionnez **PICK-06**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans l’organisateur **Réapprovisionnement**, définissez les valeurs suivantes :

    - **Dépasser la capacité de l’emplacement :** *Oui*

        Lorsque ce champ est activé, la capacité maximale de l’emplacement pourra être dépassée par le travail de réapprovisionnement. Cela active également d’autres champs sur l’organisateur **Réapprovisionnement**.

    - **Type de seuil de disponibilité de travail :** *Quantité*

        Ce champ définit la méthode utilisée pour déterminer quand plus de travail doit être libéré. Vous pouvez procéder à une libération par quantité ou par pourcentage :

        - *Pourcentage* – Sélectionnez cette option pour utiliser un pourcentage de capacité basé sur des limites de stockage ou des volumes. La sélection de cette option active le champ **Pourcentage de débordement** et désactive les deux champs liés à la quantité, **Quantité de débordement** et **Unité de débordement**.

            Vous pouvez utiliser cette option si les emplacements de prélèvement utilisent la volumétrie.

            Si cette option est sélectionnée, définissez le champ **Pourcentage de débordement** sur le pourcentage auquel des travaux de réapprovisionnement supplémentaires seront disponibles.

        - *Quantité* – Sélectionnez cette option pour utiliser une valeur de quantité spécifique. La sélection de cette option désactive le champ **Pourcentage de débordement** et les champs **Quantité de débordement** et **Unité de débordement**.

            Utilisez cette option lorsque vous n’utilisez pas de volumétrie pour les emplacements qui sont en cours de réapprovisionnement, ou lorsque vous avez des quantités cohérentes pour lesquelles vous souhaitez que plus de stock soit amené à l’emplacement.

           Si cette option est sélectionnée, définissez les champs **Quantité de débordement** et **Unité de débordement** sur la quantité et l’unité auxquelles plus de travail de réapprovisionnement sera disponible.

    - **Quantité de dépassement :** *0,65*

        Ce champ définit la quantité de débordement de l’emplacement.

        Le travail sera disponible lorsque la somme de la quantité disponible à l’emplacement et la quantité de travail sont inférieures à cette valeur. Tout travail de réapprovisionnement supérieur à cette valeur sera bloqué et doit être débloqué manuellement.

        Les limites de stockage sur site sont prises en compte lors du calcul de la quantité de travail.

    - **Unité de débordement :** *PL*

        Ce champ définit l’unité associée à la quantité de débordement.

        Dans ce cas, des travaux de réapprovisionnement supplémentaires seront disponibles lorsque l’emplacement sera réduit à 0,65 palette (PL).

    - **Pourcentage de dépassement**

        Ce champ définit le pourcentage de débordement de l’emplacement.

        Le travail sera disponible lorsque la somme de la quantité disponible à l’emplacement et la quantité de travail sont inférieures à ce pourcentage. Tout pourcentage de quantité de travail de réapprovisionnement supérieur à cette valeur sera bloqué et doit être débloqué manuellement.

        Les limites de stockage sur site sont prises en compte lors du calcul du pourcentage de travail. Si aucune limite de stockage d’emplacement n’est définie, le pourcentage de quantité de travail est calculé par volume si les contraintes de volume sont définies pour le profil d’emplacement.

> [!IMPORTANT]
> Si vous utilisez les données de démonstration pour l’entité juridique **USMF** et que vous avez précédemment activé la fonctionnalité *Positionnement des contenants d’emplacement*, vous devez désactiver la fonction **Activer le positionnement des contenants** pour le profil d’emplacement **BULK-06** pour terminer les étapes mobiles dans l’exemple de scénario.

### <a name="wave-step-code"></a>Code étape de vague

> [!NOTE]
> Pour configurer un code d’étape de vague comme décrit ici, vous devrez peut-être d’abord utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonctionnalité nommée *Code d’étape de vague à l’échelle de l’organisation*.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**.
1. Sélectionnez **Nouveau** et définissez les valeurs suivantes :

    - **Code étape de vague :** *Réappro.*
    - **Description étape de vague :** *Réapprovisionnement*
    - **Type étape de vague :** *Réapprovisionnement*

1. Sélectionnez **Enregistrer**.

### <a name="replenishment-template"></a>Modèle de réapprovisionnement

Les modèles de réapprovisionnement constituent un ensemble de règles contrôlant quand et comment un emplacement est réapprovisionné.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Réapprovisionnement \> Modèles de réapprovisionnement**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la section **Aperçu**, sélectionnez la ligne où le champ **Modèle de réapprovisionnement** est défini sur *Réapprovisionnement de la demande*.
1. Définissez les valeurs suivantes :

    - **Code étape de vague :** *Réappro.*
    - **Autoriser la demande de vague à utiliser des quantités non réservées :** *Oui*

1. Sélectionnez **Enregistrer**.

### <a name="wave-template"></a>Modèle de vague

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans le volet gauche, définissez le champ **Type de modèle de vague** sur *Expédition*.
1. Sélectionnez le modèle **61 Shipping** dans la liste.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le raccourci **Général**, définissez l’option **Automatiser la libération du travail de réapprovisionnement** sur *Oui*.

    Définissez cette option sur *Oui* pour créer un travail de réapprovisionnement basé sur la demande et le libérer automatiquement. Vous devez ajouter la méthode de vague de réapprovisionnement au modèle de vague, puis créer un modèle de réapprovisionnement du type **Demande de vague**. Paramétrez un modèle de réapprovisionnement sur la page **Modèles de réapprovisionnement**. Pour configurer un modèle de réapprovisionnement, vous devez ajouter la méthode de réapprovisionnement au modèle de vague.

1. Sur l’organisateur **Méthodes**, dans la colonne **Méthodes sélectionnées**, recherchez la ligne suivante :

    - **Nom de la méthode :** *réapprovisionner*
    - **Nom :** *Réapprovisionnement*

1. Définissez le champ **Code d’étape de vague** pour cette ligne sur *Réappro.*.
1. Sélectionnez **Enregistrer**.

## <a name="example-scenario"></a>Exemple de scénario

Après avoir mis à disposition tous les exemples de données décrits précédemment et les avoir configurés, vous pouvez suivre ce scénario pour essayer la fonctionnalité *Réapprovisionnement sur la capacité de l’emplacement*. Les valeurs affichées dans ce scénario supposent que vous travaillez avec les données de démonstration standard, que vous avez sélectionné l’entité juridique **USMF** et que vous avez préparé les exemples d’enregistrements décrits plus haut dans cette rubrique. Ce scénario sert également d’exemple pour indiquer comment la fonctionnalité peut être utilisée dans un cadre de production.

### <a name="create-replenishment-work"></a>Créer un travail de réapprovisionnement

#### <a name="create-sales-order-1"></a>Créer une commande client 1

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ouvrir une boîte de dialogue de création de commande client.
1. Dans la boîte de dialogue, définissez les valeurs suivantes :

    - **Compte client :** *US-007*
    - **Entrepôt :** *61*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle comprend une nouvelle ligne vide sur l’organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *T0100*
    - **Quantité :** *40*

1. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot**.
1. Fermez la page.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Vous recevez des messages d’informations indiquant que l’ID de vague et l’ID d’expédition ont été créés. Une vague de réapprovisionnement est également créée.

    Vous recevez également un message d’avertissement indiquant : « L’ID de travail XXXX ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »

#### <a name="create-sales-order-2"></a>Créer une commande client 2

1. Sur la page **Toutes les commandes client**, dans le volet Actions, sélectionnez **Nouveau** pour ouvrir une boîte de dialogue de création de commande client.
1. Dans la boîte de dialogue, définissez la valeur suivante :

    - **Compte client :** *US-001*
    - **Entrepôt :** *61*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle comprend une nouvelle ligne vide sur l’organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *T0100*
    - **Quantité :** *60*

1. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot**.
1. Fermez la page.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Vous recevez des messages d’informations indiquant que l’ID de vague et l’ID d’expédition ont été créés. Une vague de réapprovisionnement est également créée.

    Vous recevez également un message d’avertissement indiquant : « L’ID de travail XXXX ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »

#### <a name="create-sales-order-3"></a>Créer une commande client 3

1. Sur la page **Toutes les commandes client**, dans le volet Actions, sélectionnez **Nouveau** pour ouvrir une boîte de dialogue de création de commande client.
1. Dans la boîte de dialogue, définissez les valeurs suivantes :

    - **Compte client :** *US-004*
    - **Entrepôt :** *61*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle comprend une nouvelle ligne vide sur l’organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *T0100*
    - **Quantité :** *30*

1. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot**.
1. Fermez la page.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Vous recevez des messages d’informations indiquant que l’ID de vague et l’ID d’expédition ont été créés. Une vague de réapprovisionnement est également créée.

    Vous recevez également un message d’avertissement indiquant : « L’ID de travail XXXX ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »

#### <a name="view-work-details"></a>Afficher les détails du travail

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Dans la section **Aperçu**, filtrez la colonne **Entrepôt** pour l’entrepôt *61*.
1. Vous devriez voir que sept ID de travail ont été créés pour les trois commandes client à la demande.

    - Trois des sept ID de travail ont une valeur de **Type d’ordre de travail** de *Réapprovisionnement* et quatre ont une valeur de **Type d’ordre de travail** de *Commandes client*.
    - Les trois ID de travail qui ont une valeur de **Type d’ordre de travail** de *Réapprovisionnement* ont les mêmes emplacements de *Prélèvement* et *Rangement* dans la section **Lignes** :

        - **Prélèvement :** *02A01R5S1B*
        - **Rangement :** *06A01R2S1B*

    - Deux ID de travail ont été créés pour la commande client 1.

1. Notez les ID de travail des commandes client.

En fonction de vos quantités disponibles, les quantités de travail créées peuvent varier légèrement. Toutefois, dans l’ensemble, les en-têtes de travail créés doivent correspondre à cet exemple de scénario.

#### <a name="on-hand-inventory-license-plate-id"></a>ID contenant du stock disponible

Plus tard dans ce scénario, vous utiliserez l’application d’entrepôt (ou un émulateur), où vous devez identifier le contenant pour terminer les scénarios de prélèvement et de réapprovisionnement.

Pour trouver les ID de contenant dont vous aurez besoin ultérieurement, procédez comme suit.

1. Accédez à **Gestion des stocks \> Recherches et états \> Stock disponible**.
1. Sélectionnez le bouton **Afficher les filtres** pour ouvrir le volet des filtres.
1. Entrez les critères de filtrage suivants pour obtenir les contenants du scénario. Utilisez le filtre *commence par*.

    - **Numéro d’article :** *T0100*
    - **Entrepôt :** *61*

1. Sélectionnez **Appliquer**.
1. Dans le volet Actions, sélectionnez **Dimensions**.
1. Dans la boîte de dialogue **Affichage des dimensions**, dans la section **Dimensions de stockage**, sélectionnez toutes les valeurs.
1. Dans la section **Transactions**, sélectionnez **Numéro d’article** et **Quantité \<\> 0**.
1. Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue.
1. La grille **Disponible** montre les numéros de contenants pour l’article *T0100* à chaque emplacement. Notez le contenant qui se trouve à chaque emplacement, car vous aurez besoin de ces informations plus tard.
1. Fermez la page.

### <a name="process-steps"></a>Étapes du processus

Vous effectuerez le réapprovisionnement de l’emplacement d’entrepôt pour les deux premiers ID de travail. Les travaux du troisième réapprovisionnement seront bloqués jusqu’à ce que le niveau de stock dans le lieu de prélèvement tombe en dessous du seuil.

#### <a name="replenishment"></a>Réapprovisionnement

1. Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *61*. (Entrez *61* comme ID utilisateur et *1* comme mot de passe.)
1. Allez dans **Stock \> Réapprovisionnement**.

    Vous êtes invité à terminer le premier travail de réapprovisionnement. Le numéro d’article, la quantité et l’emplacement du prélèvement sont affichés.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.
1. Sélectionnez le bouton **OK** (symbole de coche).

    Le système génère un numéro de contenant cible pour le nouveau contenant de l’article prélevé.

1. Sélectionnez **OK** pour confirmer la valeur.

    Un travail de mise en place est affiché qui demande à l’utilisateur de placer le contenant cible à l’emplacement de réapprovisionnement. L’emplacement de *Rangement* devrait être **06A01R2S1B**.

1. Confirmez les détails du rangement et sélectionnez **OK**.

    Vous recevez un message « Travail terminé » et les détails de la prochaine tâche de prélèvement de réapprovisionnement sont affichés : le numéro d’article, la quantité et l’emplacement de prélèvement. L’emplacement de prélèvement sera le même que le premier emplacement de réapprovisionnement. Par conséquent, le contenant aura le même ID de contenant que celui utilisé pour la première tâche de travail de réapprovisionnement.

1. Répétez les étapes précédentes pour terminer le travail de réapprovisionnement pour la deuxième tâche de travail. La quantité et le contenant cible seront différentes de la quantité et du contenant cible pour la première tâche de travail.

Une fois le second travail de réapprovisionnement terminé, vous recevez un message « Travail terminé ». L’appareil mobile vous informe également qu’il n’y a pas de travail disponible, même s’il reste du travail de réapprovisionnement. Ce problème se produit, car le travail de réapprovisionnement a un état de disponibilité de *Suspendu* et est donc marqué comme **Bloqué**.

Le statut *Suspendu* a été déclenché, car le profil d’emplacement du lieu de prélèvement auquel le travail est affecté a une valeur de **Quantité de débordement** de *0,65 PL*. Les deux tâches de réapprovisionnement précédentes ont rempli l’emplacement presque à sa limite de dépassement de capacité pour l’article *T0100*. (La conversion d’unité pour l’article est de *1 PL = 100 unités*.) Par conséquent, les travaux de réapprovisionnement restants entraîneraient un dépassement de la limite de dépassement de l’emplacement.

Jusqu’à ce qu’un stock suffisant soit sélectionné à partir de l’emplacement pour le ramener en dessous du seuil de validation du travail sur l’élément de menu de l’appareil mobile, ce travail de réapprovisionnement restera bloqué.

#### <a name="sales-order-pick"></a>Prélèvement de commande client

Avant que la tâche de travail de réapprovisionnement restante ne puisse être terminée, l’emplacement de prélèvement doit être épuisé à un niveau où le travail de réapprovisionnement restant peut être débloqué. En d’autres termes, la somme de la quantité de stock disponible dans l’emplacement et la quantité de réapprovisionnement ne peut pas dépasser la valeur de la **Quantité de débordement**. Lorsque cette somme est inférieure à la quantité de débordement, le travail de réapprovisionnement restant sera débloqué.

1. Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *61*. (Entrez *61* comme ID utilisateur et *1* comme mot de passe.)
1. Allez à **Sortant \> Prélèvement des ventes**.
1. Saisissez le premier ID de travail pour la commande client 1.

    Reportez-vous aux ID de travail des commandes client dont vous avez pris note précédemment, sur la page **Détails du travail**. L’ID de travail que vous entrez ici générera un travail de prélèvement pour une quantité de 10 pièces à partir de deux emplacements distincts.

1. Cliquez sur **OK**.

    La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de sélection pour le premier emplacement.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.
1. Sélectionnez le bouton **OK** (symbole de coche).

    La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement pour l’emplacement suivant.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.
1. Sélectionnez le bouton **OK** (symbole de coche).

    La page **Commandes client : Rangement** vous demande de ranger les deux travaux de prélèvement terminés à l’emplacement de transfert sortant.

1. Cliquez sur **OK**.

    Vous recevez un message « Travail terminé ».

1. Saisissez le second ID de travail pour la commande client 1.

    Il n’y a qu’une seule tâche de prélèvement pour cet ID de travail.

1. Cliquez sur **OK**.

    La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.

    Le contenant que vous spécifiez sera l’un des contenants générés par le système à partir des tâches de réapprovisionnement. Pour vous assurer que vous saisissez le bon ID de contenant, vérifiez le stock sur la page **Stock disponible** pour l’article, l’emplacement et la quantité.

1. Sélectionnez le bouton **OK** (symbole de coche).
1. Confirmez les instructions de la tâche de rangement vers l’emplacement intermédiaire sortant.
1. Cliquez sur **OK**.

    Vous recevez un message « Travail terminé ».

Le prélèvement de la commande client 2 est bloqué, car la tâche de réapprovisionnement à laquelle elle est liée n’est pas terminée. Actuellement, il y a encore une quantité de 30 unités à l’emplacement de prélèvement et la quantité de réapprovisionnement pour la commande client 2 est de 60 unités. La somme du stock disponible et du stock de réapprovisionnement (90 unités) dépasse la quantité de débordement de 0,65 PL (ou 65 unités). Avant que le travail de réapprovisionnement puisse être terminé, la commande client 3 doit être prélevée.

1. Saisissez l’ID de travail pour la commande client 3.

    Il n’y a qu’une seule tâche de prélèvement pour cet ID de travail.

1. Cliquez sur **OK**.

    La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.

    Le contenant que vous spécifiez sera l’un des contenants générés par le système à partir des tâches de réapprovisionnement. Pour vous assurer que vous saisissez le bon ID de contenant, vérifiez le stock sur la page **Stock disponible** pour l’article, l’emplacement et la quantité.

1. Sélectionnez le bouton **OK** (symbole de coche).
1. Confirmez les instructions de la tâche de rangement vers l’emplacement intermédiaire sortant.
1. Cliquez sur **OK**.

    Vous recevez un message « Travail terminé ».

Dès que la somme de la quantité disponible sur l’emplacement de prélèvement et de la quantité de réapprovisionnement est inférieure au seuil, vous pourrez traiter le travail de réapprovisionnement restant.

Revenez à la page **Détails du travail** et notez que la disponibilité du travail de réapprovisionnement pour la partie finale du réapprovisionnement (pour la commande client 2) est *Ouverte*, car il y a maintenant suffisamment d’espace à l’emplacement pour accepter le réapprovisionnement.

Vous pouvez désormais traiter ce travail de réapprovisionnement via l’appareil mobile.

1. Allez dans **Stock \> Réapprovisionnement**.

    Vous êtes invité à terminer le travail de réapprovisionnement restant. Le numéro d’article, la quantité et l’emplacement du prélèvement sont affichés.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.
1. Sélectionnez le bouton **OK** (symbole de coche).

    Le système génère un numéro de contenant cible pour le nouveau contenant de l’article prélevé.

1. Sélectionnez **OK** pour confirmer la valeur.

    Un travail de mise en place est affiché qui demande à l’utilisateur de placer le contenant cible à l’emplacement de réapprovisionnement. L’emplacement de *Rangement* devrait être **06A01R2S1B**.

1. Confirmez les détails du rangement et sélectionnez **OK**.

    Vous recevez les messages « Travail terminé » et « Aucun travail disponible ».

Vous pouvez maintenant prélever la commande client 2. Elle a été débloquée lorsque le travail de réapprovisionnement lié à la commande client a été terminé.

1. Saisissez l’ID de travail pour la commande client 2.

    Il n’y a qu’une seule tâche de prélèvement pour cet ID de travail.

1. Cliquez sur **OK**.

    La page des tâches **Commandes client : Prélèvement** affiche le numéro d’article, la quantité et l’emplacement de prélèvement.

1. Dans le champ **LP**, entrez le numéro de contenant de l’article à l’emplacement indiqué.

    Le contenant que vous spécifiez sera le contenant généré par le système à partir de la tâche de réapprovisionnement. Pour vous assurer que vous saisissez le bon ID de contenant, vérifiez le stock sur la page **Stock disponible** pour l’article, l’emplacement et la quantité.

1. Sélectionnez le bouton **OK** (symbole de coche).
1. Confirmez les instructions de la tâche de rangement vers l’emplacement intermédiaire sortant.
1. Cliquez sur **OK**.

    Vous recevez un message « Travail terminé ».

## <a name="notes-and-tips"></a>Remarques et conseils

- Cette fonctionnalité fonctionne avec tous les types de réapprovisionnement : demande de vague, min/max, demande de chargement et créneaux.
- Vous pouvez remplacer manuellement la disponibilité du travail de réapprovisionnement pour chaque en-tête de travail à partir de la page **Détails du travail** si vous le souhaitez.
- Lorsque le système définit la disponibilité du travail de réapprovisionnement, il prend en compte tout stock qui se trouve déjà à l’emplacement avant la fin des travaux
- Chaque travail de commande client est lié à un travail de réapprovisionnement spécifique. Il n’existe pas de fonctionnalité de disponibilité du travail de vente correspondante.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]