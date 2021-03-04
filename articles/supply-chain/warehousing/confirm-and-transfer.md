---
title: Confirmer et transférer
description: Cette rubrique explique comment utiliser la fonctionnalité Confirmer et transférer, qui permet aux utilisateurs d'expédier des chargements hors de l'entrepôt avant de finaliser toutes les tâches associées à ces chargements.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6104e457a62f340951c187d0f2dbe48b0dffdf7f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427655"
---
# <a name="confirm-and-transfer"></a>Confirmer et transférer

[!include [banner](../includes/banner.md)]

La fonctionnalité *Confirmer et transférer* permet aux utilisateurs d'expédier des chargements hors de l'entrepôt avant de finaliser toutes les tâches associées à ces chargements. Lors de la réception d'une expédition comprenant des lignes de chargement qui n'ont pas été entièrement prélevées, l'utilisateur qui confirme est invité à fractionner les quantités restantes dans un nouveau chargement ou à annuler les quantités incomplètes.

Les systèmes configurés pour autoriser les scénarios de prise en charge du fractionnement du chargement pour les chargements planifiés et partiellement chargés doivent être adaptés en raison de circonstances nouvelles ou changeantes.

Le client comprend une logique qui permet de fermer et de confirmer comme expédié un chargement partiellement chargé. Toutes les expéditions et lignes de chargement restantes (y compris les quantités de ligne complètes ou partielles) sont ensuite transférées vers un chargement et une expédition nouvellement créés, si ce transfert est nécessaire et que la configuration le permet. De nouvelles expéditions et de nouveaux chargements sont automatiquement créés sur la base des critères initiaux de création d'expédition et de chargement, et leurs principaux attributs restent inchangés. Une option permet également d'annuler automatiquement les quantités restantes si un ordre de travail n'a pas encore été créé et que l'utilisateur juge cette annulation nécessaire.

Cette fonctionnalité prend en charge les scénarios où le chargement complet ne tient pas dans un seul camion ou une partie du chargement doit quitter l'entrepôt avant que le reste du chargement ne soit prêt pour l'expédition. Dans ces scénarios, les produits restants peuvent être transférés vers un nouveau chargement et, par conséquent, vers un nouveau camion. Étant donné que cette fonctionnalité peut être utilisée avec des chargements destinés autrement à exiger l'expédition du chargement complet, elle offre une flexibilité supplémentaire afin que les responsables du transport puissent résoudre des scénarios non standard ou imprévus.

Lorsqu'un chargement est fractionné, la fonctionnalité *Confirmer et transférer* effectue les actions suivantes :

- De nouveaux chargements et de nouvelles expéditions sont créés selon les besoins. Chaque chargement ou expédition aura la plupart des mêmes attributs que le chargement ou l'expédition d'origine. L'exception est le statut du chargement, qui sera recalculé en fonction du statut du travail.
- L'utilisateur est informé de la création d'un nouveau chargement. L'utilisateur est également informé de l'ID du nouveau chargement.
- Les lignes de chargement, les en-têtes de travail et les lignes de travail fractionnés sont mis à jour avec les nouvelles informations de chargement et d'expédition.
- Si une expédition entière est fractionnée, l'expédition est conservée et seules les références de chargement sont mises à jour. Si l'expédition doit être fractionnée, une nouvelle expédition est créée.

Lorsque les quantités restantes sont annulées, les quantités de ligne de chargement qui n'ont pas été prélevées et auxquelles aucun travail non annulé n'est associé sont supprimées du chargement. Si un travail est en cours, l'utilisateur ne peut que fractionner le chargement. Les quantités restantes ne peuvent pas être annulées.

Vous ne pouvez fractionner que les chargements qui répondent à l'ensemble des critères suivants :

- Une ou plusieurs lignes de chargement ont prélevé des quantités.
- Le statut de chargement est inférieur à Chargé.
- Il n'existe aucune donnée de ligne de chargement. (Ces données sont créées par consolidation du contenant dans l'emplacement intermédiaire et la fonctionnalité *Confirmer et transférer* ne prend pas en charge la consolidation du contenant.)
- Aucun stock n'est actuellement en attente de conditionnement dans un emplacement de conditionnement. (La fonctionnalité *Confirmer et transférer* ne prend pas en charge le stock qui a été prélevé au poste de conditionnement mais qui n'a pas encore été conditionné.)

> [!NOTE]
> Cette fonctionnalité diffère de la fonctionnalité de chargement du transport, qui devrait être utilisée dans les entrepôts qui ne peuvent jamais planifier et créer de chargements avant le prélèvement, mais qui chargent à la place l'espace de transport disponible une fois le prélèvement terminé.
>
> Utilisez la fonctionnalité *Confirmer et transférer* dans les cas où les chargements sont généralement planifiés et créés à l'avance, mais où des exceptions se produisent parfois lorsque le chargement n'est pas adapté au transport disponible (comme un camion).

## <a name="turn-on-confirm-and-transfer"></a>Activer la fonctionnalité Confirmer et transférer

Avant de pouvoir utiliser la fonctionnalité *Confirmer et transférer*, celle-ci doit être activée dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Confirmer et transférer*

## <a name="set-up-confirm-and-transfer"></a>Configurer la fonctionnalité Confirmer et transférer

Pour utiliser la fonctionnalité *Confirmer et transférer*, vous devez l'activer dans chaque modèle de chargement approprié. En outre, selon vos besoins, vous souhaitez peut-être préparer vos modèles de travail pour prendre en charge la fonctionnalité. Si vous souhaitez exécuter l'exemple de scénario fourni plus loin dans cette rubrique, configurez votre système comme décrit dans cette section. (Ce scénario est basé sur les données de démonstration **USMF**.)

### <a name="prepare-your-load-templates"></a>Préparer vos modèles de chargement

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Chargement \> Modèles de chargement**.
1. Dans le volet Actions, sélectionnez **Modifier** pour afficher la page en mode d'édition.
1. Cochez la case **Autoriser le fractionnement du chargement lors de la confirmation de l'expédition** pour chaque modèle existant où vous souhaitez activer la fonctionnalité. Vous pouvez également sélectionner **Nouveau** pour créer un nouveau modèle et le configurer selon vos besoins. Chaque chargement que vous créez en utilisant ce modèle héritera de cette fonctionnalité. (Si vous utilisez les données de démonstration **USMF**, activez la fonctionnalité pour le modèle de chargement **Conteneur de 20**.)

### <a name="prepare-your-work-templates"></a>Préparer vos modèles de travail

Cette configuration n'est pas requise dans toutes les situations. L'exemple illustré ici garantit que le travail peut être réparti par expédition pour prendre en charge l'exemple de scénario fourni plus loin dans cette rubrique. Il existe également d'autres moyens d'atteindre ce résultat.

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Dans la grille de la partie supérieure de la page, sélectionnez un modèle de travail existant où vous souhaitez configurer la fonctionnalité *Confirmer et transférer*. (Si vous utilisez les données de démonstration **USMF**, sélectionnez le modèle de travail **51 Prélever pour échelonner**.) Vous pouvez également créer un nouveau modèle de travail.
1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue **Vente**.
1. Dans la boîte de dialogue **Vente**, sous l'onglet **Tri**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Transactions de travail temporaire*
    - **Table dérivée :** *Transactions de travail temporaire*
    - **Champ :** *ID expédition*
    - **Ordre de tri :** *Croissant*

1. Cliquez sur **OK** pour enregistrer vos paramètres et fermer la boîte de dialogue **Vente**.
1. Si vous recevez un message indiquant que le regroupement sera réinitialisé, sélectionnez **Oui** pour continuer.
1. Dans la grille de la partie supérieure de la page **Modèles de travail**, sélectionnez le modèle que vous venez de modifier, puis, dans le volet Actions, sélectionnez **Décompositions de l'en-tête de travail**.
1. Dans le volet Actions, sélectionnez **Modifier** pour afficher la page en mode d'édition.
1. Dans la grille, définissez les valeurs suivantes :

    - **Nom de la table :** *Transactions de travail temporaire*
    - **Nom du champ :** *ID expédition*
    - **Regrouper selon ce champ :** Cochez cette case.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Fermez la page.

## <a name="scenario"></a>Scénario

Ce scénario montre un exemple où le processus de prélèvement n'est pas encore terminé, mais les articles qui ont été prélevés jusqu'à présent doivent être chargés dans un camion et expédiés quand même. Par conséquent, l'utilisateur peut fractionner les lignes de chargement non prélevées dans un nouveau chargement. Toutes les relations de données seront ensuite automatiquement mises à jour.

> [!NOTE]
> Les valeurs spécifiques décrites dans ce scénario sont basées sur les données de démonstration **USMF**. Nous vous recommandons d'utiliser ces données de démonstration lorsque vous démontrez ou apprenez à utiliser la fonctionnalité. Si vous n'utilisez pas les données de démonstration **USMF**, remplacez vos propres valeurs selon les besoins.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>Étape 1 : Créer un chargement contenant plusieurs lignes de chargement

Avant de pouvoir utiliser cette fonctionnalité, vous devez avoir un chargement contenant plusieurs lignes de chargement. Vous devez également vous assurer que les emplacements de prélèvement disposent d'un stock suffisant pour tous les articles des commandes client que vous créerez. Passez en revue la configuration de l'instruction d'emplacement (**Gestion des entrepôts \> Paramétrage \> Instructions d'emplacement**) et prenez note des emplacements de prélèvement utilisés pour le prélèvement des commandes client. Si vous devez ajuster le stock, créez des mouvements manuels, utilisez le réapprovisionnement ou utilisez tout autre flux, selon les besoins.

Pour créer un chargement éligible, commencez par créer trois commandes client en procédant comme suit.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ouvrir la boîte de dialogue **Créer une commande client**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes (au minimum) :

    - Dans l'organisateur **Client**, définissez le champ **Compte client** sur *US-004* (*Cave Wholesales*).
    - Dans l'organisateur **Général**, définissez le champ **Entrepôt** sur *51*.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.
1. Votre nouvelle commande client est ouverte. Dans la grille **Lignes de commande client**, ajoutez une ligne présentant les valeurs suivantes :

    - **Numéro d'article :** *M9200*
    - **Quantité :** *40*
    - **Unité :** *ea*

1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Dans le volet Actions, sélectionnez **Réserver un lot** pour ouvrir la page **Réservation**.
1. Réservez le stock sur la ligne de vente, puis fermez la page **Réservation**.
1. Répétez les étapes 1 à 4 pour ajouter une deuxième commande client pour le même client et le même entrepôt.
1. Ajoutez deux lignes de vente présentant les valeurs suivantes. Après avoir ajouté chaque ligne, réservez le stock correspondant comme décrit dans les étapes 6 à 8.

    - **Ligne 1 :** Définissez le champ **Numéro d'article** sur *M9200*, le champ **Quantité** sur *30* et le champ **Unité** sur *ea*.
    - **Ligne 2 :** Définissez le champ **Numéro d'article** sur *M9201*, le champ **Quantité** sur *20* et le champ **Unité** sur *ea*.

1. Répétez les étapes 1 à 4 pour ajouter une troisième commande client pour le même client et le même entrepôt.
1. Ajoutez deux lignes de vente présentant les valeurs suivantes. Après avoir ajouté chaque ligne, réservez le stock correspondant comme décrit dans les étapes 6 à 8.

    - **Ligne 1 :** Définissez le champ **Numéro d'article** sur *M9201*, le champ **Quantité** sur *20* et le champ **Unité** sur *ea*.
    - **Ligne 2 :** Définissez le champ **Numéro d'article** sur *M9202*, le champ **Quantité** sur *60* et le champ **Unité** sur *ea*.

#### <a name="load-planning-workbench"></a>Atelier de planification des chargements

L'atelier de planification des chargements utilisera l'ID du modèle de chargement pour créer les expéditions et libérer les lignes de commande client dans l'entrepôt.

1. Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.
1. Dans le champ **Entrepôt**, sélectionnez *51*.

    Vous allez maintenant créer le chargement pour les commandes client que vous venez de créer.

1. Sous l'onglet **Lignes de vente**, dans la grille, sélectionnez les lignes de vente pour les nouvelles commandes client.
1. Dans le volet Actions, sous l'onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez **Dans un nouveau chargement**.
1. Dans la boîte de dialogue **Affectation d'un modèle de chargement**, dans le champ **ID modèle de chargement**, sélectionnez *Conteneur de 20*.
1. Cliquez sur **OK**.
1. Dans la section **Chargements** de la page **Atelier de planification des chargements**, dans la grille, recherchez l'ID du chargement nouvellement créé pour l'entrepôt *51*. Faites défiler vers la droite jusqu'à ce que la colonne **Autoriser le fractionnement du chargement lors de la confirmation de l'expédition** s'affiche. La case doit être cochée pour votre chargement.
1. Sélectionnez le chargement.
1. Dans le menu **Libérer** au-dessus de la grille, sélectionnez **Libérer dans l'entrepôt** pour créer un travail.
1. Dans la boîte de dialogue **Libérer le chargement dans l'entrepôt**, vérifiez que l'organisateur **Enregistrements à inclure** affiche votre ID de chargement.
1. Cliquez sur **OK**.

    Vous pouvez recevoir un message « Traitement de l'opération en cours » pendant que le système crée les expéditions et le travail.

1. Dans la section **Chargements** de la page **Atelier de planification des chargements**, votre chargement devrait maintenant avoir le statut de chargement *Traité par vagues*. Sélectionnez le chargement, puis, dans le menu **Informations associées** au-dessus de la grille, sélectionnez **Détails de la vague** pour afficher les ID d'expédition que vous avez créés. Lorsque vous avez terminé, fermez la page **Vagues**.
1. Dans la section **Chargements** de la page **Atelier de planification des chargements**, sélectionnez le chargement, puis, dans le menu **Information associées** au-dessus de la grille, sélectionnez **Détails du travail** pour afficher le travail créé pour les commandes client.
1. Prenez note des ID de travail créés. Vous devrez peut-être faire défiler vers la droite pour afficher le numéro de commande client et l'ID d'expédition associés à l'ID de travail.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>Étape 2 : Configurer le flux d'exécution pour les appareils mobiles

Les tâches sur les appareils mobiles nécessiteront la saisie d'informations par l'utilisateur, telles que l'ID de travail ou l'ID de contenant. Dans les champs, ces informations sont généralement fournies pour les utilisateurs de l'entrepôt sous la forme de codes-barres qui sont disponibles dans la documentation, sur l'emballage ou le rayonnage. Pour effectuer les étapes sur l'appareil mobile pour les scénarios, assurez-vous d'avoir identifié les ID de travail des transactions et les ID de contenant de l'article et de l'emplacement dans les transactions.

1. Connectez-vous à l'appareil mobile en utilisant un ID d'utilisateur et un mot de passe pour l'entrepôt *51*.
1. Sélectionnez **Sortant**.
1. Sélectionnez **Prélèvement des ventes**.
1. Vous avez la possibilité d'entrer l'ID de travail ou l'ID de contenant. Entrez l'ID de travail pour la première commande client, puis sélectionnez **Entrée**.
1. Dans le champ **Empl**, entrez l'emplacement affiché pour confirmer l'emplacement de prélèvement. Sélectionnez ensuite **Entrée**.
1. Dans le champ **Contenant**, entrez l'ID de contenant. L'ID de contenant doit correspondre à l'article, l'entrepôt et l'emplacement de l'article en cours de prélèvement dans l'emplacement sélectionné. Lorsque vous avez terminé, sélectionnez **Entrée**.
1. Dans le champ **Article**, entrez le numéro d'article pour confirmer l'article prélevé, puis sélectionnez **Entrée**.
1. Dans le champ **Qté**, entrez la quantité de l'article prélevé, puis sélectionnez **Entrée**.
1. Dans le champ **Contenant cible**, entrez un ID de contenant cible. Les contenants cibles sont définis par l'utilisateur. Assurez-vous d'entrer un ID de contenant facile à mémoriser. Nous vous recommandons d'utiliser la date actuelle plus une séquence à deux chiffres (YYMMJJ\#\#) comme format, par exemple *19112301*. Lorsque vous avez terminé, sélectionnez **Entrée**.
1. Passez en revue les informations affichées. Ces informations correspondent aux informations de *Prélèvement* qui deviendront maintenant les données de *Rangement* pour la transaction de rangement. Lorsque vous avez terminé, sélectionnez **Entrée**.

    - Vous recevez un message **Travail terminé**.

1. Répétez les étapes 4 à 10 pour l'ID de travail de la deuxième commande client.

L'étape suivante consiste à charger les deux contenants prélevés dans le camion.

1. Connectez-vous à l'appareil mobile en utilisant un ID d'utilisateur et un mot de passe pour l'entrepôt *51*.
1. Sélectionnez **Sortant**.
1. Sélectionnez **Chargement des ventes**.
1. Entrez l'ID de contenant cible défini par l'utilisateur que vous avez créé pour le premier ID de travail dans la procédure précédente. Sélectionnez ensuite **Entrée** pour placer le contenant cible dans l'emplacement **STAGE**.
1. Entrez à nouveau l'ID de contenant cible, puis sélectionnez **Entrée** pour placer le contenant dans l'emplacement **BAYDOOR**.
1. Répétez les étapes 4 et 5 pour l'ID de contenant cible que vous avez créé pour le deuxième ID de travail.

Les deux ID de travail seront désormais fermés (chargés).

### <a name="step-3-confirm-the-outbound-shipment"></a>Étape 3 : Confirmer l'expédition sortante

Dans cette étape, vous allez confirmer les deux commandes client et le travail qui ont été effectués pour le chargement afin d'expédier les articles prélevés du chargement et de créer un nouveau chargement pour les articles non prélevés. La confirmation de l'expédition sortante doit être effectuée sur la page **Détails du chargement**.

1. Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.
1. Dans la section **Chargements**, dans la grille, sélectionnez la ligne associée à l'ID de chargement que vous avez créé.
1. Sélectionnez le lien ID de chargement pour ouvrir la page **Détails du chargement**.
1. Sur la page **Détails du chargement**, dans le volet Actions, sous l'onglet **Expédier et recevoir**, dans le groupe **Confirmer**, sélectionnez **Expédition sortante** pour lancer la confirmation.
1. Dans la boîte de dialogue **Confirmation de l'expédition**, dans le champ **Méthode de fractionnement du chargement lors de la confirmation de l'expédition**, sélectionnez *Fractionner la quantité dans un nouveau chargement*.
1. Cliquez sur **OK**.

    Vous pouvez recevoir un message « Traitement de l'opération en cours ».

    Vous recevez des messages d'information indiquant que l'expédition de votre chargement a été confirmé et qu'un nouveau chargement a été créé à partir de la quantité fractionnée.

Actualisez la page **Atelier de planification des chargements** pour afficher le chargement nouvellement créé.

Vous pouvez également confirmer que les relations de transaction ont été mises à jour comme suit :

- L'expédition et les lignes d'expédition restantes (non traitées) sont mises à jour avec le nouvel ID de chargement.
- La commande client est liée au nouvel ID de chargement.
- Le chargement d'origine ne contient pas les lignes de chargement restantes.
- Le travail restant a été mis à jour avec le nouvel ID de chargement.
- La vague reste la même.
- Le statut du nouveau chargement est correctement mis à jour. (Si le statut du travail est _En cours_, le statut du chargement doit également être _En cours_.)

## <a name="notes-and-tips"></a>Remarques et conseils

- Vous pouvez également activer le paramètre **Autoriser le fractionnement du chargement lors de la confirmation de l'expédition** après avoir créé le chargement avec le paramètre **Modèle de chargement** désactivé mais avant le démarrage du processus de chargement. Accédez au chargement souhaité, puis, dans la vue d'en-tête, activez le paramètre.
- L'option **Fractionner la quantité dans un nouveau chargement** fonctionne également lorsque certains des en-têtes de travail restants présentent le statut *En cours*. Par conséquent, vous pouvez toujours utiliser la fonctionnalité même si les travailleurs exécutent déjà les ordres de prélèvement.
- Si vous sélectionnez **Annuler la quantité non traitée** lorsqu'un travail restant présente le statut *Ouvert* ou *En cours*, vous recevez le message d'erreur suivant : « Impossible d'annuler la quantité restante pour le chargement. Il existe un travail pour le chargement. »
- Si vous sélectionnez **Annuler la quantité non traitée** lorsqu'il n'existe aucun travail restant mais des lignes de chargement ne sont pas libérées sur le chargement, vous recevez le message d'erreur suivant : « L'expédition du chargement n'a pas pu être confirmée, car la quantité de l'article dépasse le pourcentage défini pour la livraison incomplète. » Pour éviter l'erreur, vous pouvez définir le pourcentage de **Livraison incomplète** sur la ligne de chargement non libérée sur 100 %. Les lignes non libérées ne seront pas déplacées vers un nouveau chargement, mais le chargement actuel sera confirmé avec une livraison incomplète. Dans ce cas, vous ne pourrez pas libérer à nouveau la commande d'origine. Par conséquent, vous devrez la gérer d'une autre manière.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]