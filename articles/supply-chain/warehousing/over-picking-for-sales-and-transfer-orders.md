---
title: Prélèvement excessif pour les commandes client et les ordres de transfert
description: Cette rubrique explique comment activer le prélèvement excessif pour les commandes client et les ordres de transfert.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3c6f9d386f79754edce38e4e2cf4c9bfefbce69bdb252e8754f39d909827fa02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722149"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Prélèvement excessif pour les commandes client et les ordres de transfert

[!include [banner](../includes/banner.md)]

Cette rubrique présente un scénario qui montre comment permettre à un collaborateur spécifique ou à tous les collaborateurs de prélever excessivement. Le processus de prélèvement excessif permet un prélèvement excessif contrôlé pendant le travail de prélèvement.

Le prélèvement excessif en entrepôt est un concept simple. Le système permet aux collaborateurs de prélever plus d’articles que ceux spécifiés pour une commande. Cependant, il prend toujours en compte la limite de livraison excessive définie au niveau de la ligne pour l’ordre de transfert ou la commande client. Si cette limite est dépassée, l’application Warehouse Management informe les collaborateurs qu’ils dépassent la limite de livraison excessive.

La fonction de prélèvement excessif aide à minimiser la maintenance et aide également votre configuration à rester flexible. Vous pouvez définir un ou plusieurs éléments de menu de l’appareil mobile et activer le prélèvement excessif pour seulement certains d’entre eux. Vous pouvez également empêcher les collaborateurs sélectionnés de prélever excessivement des commandes client et/ou des ordres de transfert sans avoir à modifier les éléments de menu. Au lieu de cela, vous pouvez désactiver l’une de ces fonctionnalités ou les deux dans les configurations de collaborateur appropriées.

La fonction de prélèvement excessif peut aider les collaborateurs à économiser du temps et des efforts lorsqu’ils prélèvent et expédient des articles. Par exemple, la fonctionnalité permet aux collaborateurs d’effectuer ces tâches :

- Compenser les pertes lors du prélèvement ou de l’expédition.
- Évitez d’avoir à déballer certains matériaux d’emballage pendant le processus de prélèvement.
- Compenser les dommages causés à l’article pendant le transport.
- Expédier un écart de quantité ou d’unité de mesure.
- Minimiser la rupture des quantités sur les contenants.
- Évitez le gaspillage de matériaux et la rareté des matériaux coûteux.
- Mesurer la quantité prélevée après prélèvement (par exemple, via la pondération des camions).

> [!IMPORTANT]
> La fonction de prélèvement excessif s’applique uniquement à la préparation et au traitement des commandes client et des commandes de transfert. Le réapprovisionnement ne prend pas en charge le prélèvement excessif. Lorsque le travail de réapprovisionnement est exécuté, le système ne permet pas aux utilisateurs de prélever excessivement.

Ce scénario dans cette rubrique présente comment configurer et utiliser la fonctionnalité de prélèvement excessif.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Conditions préalables du scénario : rendre les données de démonstration disponibles

Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur *USMF* avant de commencer.

## <a name="scenario-setup"></a>Configuration d’un scénario

Avant de travailler sur l’exemple de scénario, vous devez activer le prélèvement excessif à la fois pour le collaborateur concerné et l’élément de menu concerné.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Configurer un collaborateur pour permettre le prélèvement excessif

Voici la procédure générale de configuration d’un collaborateur pour activer le prélèvement excessif pour les commandes client et les ordres de transfert séparément. Cette configuration contrôle quel collaborateur de prélèvement peut effectuer le prélèvement excessif et si ce collaborateur peut effectuer un prélèvement excessif à la fois pour les ordres de transfert et les commandes client.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.
1. Dans le volet de liste, sélectionnez **Julia Funderburk**.
1. Dans le raccourci **Utilisateurs**, sélectionnez la ligne qui a les valeurs suivantes. Si aucune ligne existante n’a ces valeurs, créez-la.

    - **ID d’utilisateur :** *24*
    - **Nom d’utilisateur :** *WH 24*
    - **Entrepôt par défaut :** *24*
    - **Nom du menu :** *Principal*

1. Dans le raccourci **Travail**, définissez les valeurs suivantes pour l’utilisateur *24* si elles ne sont pas déjà définies :

    - **Autoriser le prélèvement excessif des ventes :** *Oui*
    - **Autoriser le prélèvement excessif d’ordre de transfert :** *Oui*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Paramétrer une option de menu d’appareil mobile pour autoriser le prélèvement excessif

Voici la procédure générale de configuration d’un élément de menu d’un appareil mobile pour activer le prélèvement excessif. Selon les besoins de votre entreprise pour le niveau d’autorisation du collaborateur qui utilisera le menu de l’appareil mobile, certains paramètres peuvent être activés ou désactivés.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet de liste, sélectionnez l’enregistrement nommé *Prélèvement ventes*. Si aucun enregistrement existant ne porte ce nom, créez-le. Confirmez ou définissez les valeurs suivantes pour l’enregistrement :

    - **Nom de l’élément de menu :** *Prélèvement ventes*
    - **Titre :** *Prélèvement des ventes*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*
    - **Dirigé par :** *Utilisateur dirigé*
    - **Remplacer le contenant cible :** *Oui*
    - **Remplacer le contenant pendant le placement :** *Oui*
    - **Maintenir le travail verrouillé par l’utilisateur :** *Oui*
    - **Autoriser le prélèvement excessif :** *Oui*

> [!IMPORTANT]
> Une fois que les paramètres pertinents pour le collaborateur et l’élément de menu de l’appareil mobile sont activés, le prélèvement excessif ne peut être traité que via l’appareil mobile.

## <a name="example-scenario"></a>Exemple de scénario

Une fois les conditions préalables, la configuration des collaborateurs et la configuration des éléments de menu en place, vous êtes prêt à utiliser la fonctionnalité.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Créer une commande client qui permet une livraison excédentaire

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-001*
    - **Entrepôt :** *24*

1. Cliquez sur **OK**.
1. La nouvelle commande client est ouverte. Dans l’organisateur **Lignes de commande client**, ajoutez une ligne présentant les paramètres suivants :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *10*

1. Sur le raccourci **Détails de ligne**, sur l’onglet **Livraison**, définissez le champ **Livraison excédentaire** sur *10*.
1. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.
1. Fermez la page **Réservation**.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

Une fois le lancement terminé, vous recevez des messages d’information indiquant les ID de vague et de chargement créés.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Obtenez l’ID de travail et le numéro de contenant pour la nouvelle commande

Lorsque vous avez lancé la commande client dans l’entrepôt, le système doit avoir créé un ID de travail comportant une ligne de prélèvement. Suivez ces étapes pour trouver l’ID de travail et les attributions de contenants.

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Dans la grille **Vue d’ensemble**, recherchez la colonne **Numéro de commande** pour la commande que vous venez de créer. Pour cette commande client, notez l’ID de travail correspondant.
1. Sélectionnez la ligne de chaque nouvelle commande client pour afficher les informations associées dans la grille **Lignes**. Notez l’emplacement à partir duquel l’article sera prélevé.
1. Accédez à **Gestion des stocks \> Recherches et états \> Stock disponible**.
1. Dans le volet Actions, sélectionnez **Dimensions**.
1. Dans la boîte de dialogue **Afficher la dimension**, assurez-vous que les cases **Contenant**, **Entrepôt** et **Numéro d’article** sont cochées, puis sélectionnez **OK**.
1. Dans le volet **Filtre**, définissez les filtres suivants :

    - **Numéro d’article** – **fait partie de** – *A0001*
    - **Entrepôt** – **commence par** – *24*

1. Sélectionnez **Appliquer**.
1. Notez les valeurs du **contenant** affichées.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>Prélèvement excessif de la commande en utilisant l’application mobile Warehouse Management

1. Connectez-vous à l’application mobile Gestion des entrepôts en tant qu’utilisateur de l’entrepôt *24*.
1. Allez à **Sortant \> Prélèvement des ventes**.
1. Dans le champ **Scannez lID de travail ou le contenant**, entrez l’ID de travail qui a été créé pour la commande client.
1. Sélectionnez **OK** (symbole de coche).
1. Sélectionnez **Prélèvement excessif**.
1. Définissez le champ **Qté prélèvement** sur *14*.
1. Sélectionnez **OK** (symbole de coche).

    Sur la page **prélèvement excessif**, vous recevez le message suivant : « La livraison excédentaire de la ligne est de 40,00 %, mais la livraison excédentaire autorisée n’est que de 10,00 %. » Ce message indique que la quantité de prélèvement que vous avez saisie dépasse la limite de livraison excédentaire. La limite de livraison excédentaire pour la ligne de commande client est de 10 %. Par conséquent, pour une quantité spécifiée de 10, vous ne pouvez prélever excessivement que de 1, pour une quantité totale de prélèvement de 11.

1. Définissez le champ **Qté prélèvement** sur *11*.
1. Sélectionnez **OK** (symbole de coche).
1. Dans le champ **Contenant**, saisissez le contenant noté dans la section précédente.
1. Dans le champ **Contenant cible**, entrez un contenant cible. Notez que l’emplacement du prélèvement (*FLOOR-001*), l’article (*A0001*) et la quantité (*11 pièces*) sont indiqués.
1. Sélectionnez **OK** (symbole de coche).
1. Examinez les informations sur la page **Commandes client - Placer**. Le champ **Loc** doit indiquer que les articles sélectionnés vont à l’emplacement *BAYDOOR*.
1. Sélectionnez **OK** (symbole de coche).

Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ». Ce message indique que l’ID de travail de la commande client a été complété et que la quantité prélevée excessivement ne dépasse pas la limite de livraison excédentaire de 10 pour cent.
