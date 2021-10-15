---
title: Programme d’approvisionnement
description: Cette rubrique fournit des informations sur la page Programme d’approvisionnement et ses fonctionnalités.
author: ChristianRytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0d2f0f38d86ae307ef80bd02901e19a08d5e30ae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578366"
---
# <a name="supply-schedule"></a>Programme d’approvisionnement

[!include [banner](../includes/banner.md)]

La page **Programme d’approvisionnement** affiche un aperçu complet de l’offre et de la demande pour un produit ou une famille de produits. Les informations sont filtrées par emplacement, plan principal et périodes. Vous pouvez également utiliser la page pour créer des commandes, modifier des commandes planifiées existantes et exécuter une planification générale.

## <a name="open-the-supply-schedule-page"></a>Ouvrir la page Programme d’approvisionnement

Vous pouvez ouvrir la page **Programme d’approvisionnement** de l’une des manières suivantes :

- Accédez à **Planification \> Planification \> Programme d’approvisionnement**. Dans la boîte de dialogue **Modifier le filtre**, spécifiez le plan et le produit que vous recherchez en entrant des valeurs de filtre dans les champs fournis. (Dans le reste de cette rubrique, la collection de valeurs de filtre que vous entrez est appelée « le filtre » ou « le filtre actuel ».) Lorsque vous avez terminé, sélectionnez **OK**.
- Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**. Sélectionnez ou ouvrez un produit. Ensuite, dans le volet Actions, sous l’onglet **Plan**, dans le groupe **Vue**, sélectionnez **Programme d’approvisionnement**.
- Accédez à **Planification \> Installer \> Prévision de la demande \> Clés de répartition par article**. Sélectionnez une clé de répartition par article qui est utilisée comme famille de produits. Puis, dans le volet Actions, sélectionnez **Programme d’approvisionnement**.
- Accédez à **Planification \> Planification \> Ordres prévisionnels**. Sélectionnez ou ouvrez un ordre prévisionnel. Ensuite, dans le volet Actions, sous l’onglet **Vue**, dans le groupe **Vue**, sélectionnez **Programme d’approvisionnement**.

> [!NOTE]
> Lorsque vous ouvrez la page **Programme d’approvisionnement** d’un produit, d’une famille de produits ou d’un ordre planifié, vous n’avez pas besoin de saisir de valeurs de filtre. Le système utilise le modèle de période par défaut.

## <a name="use-the-supply-schedule-page"></a>Utiliser la page Programme d’approvisionnement

La page **Programme d’approvisionnement** se compose d’une section supérieure, du raccourci **Inventaire de fin de période**, du raccourci supplémentaire qui devient visible en fonction de la ligne sélectionnée dans la section supérieure et du volet Récapitulatif. (Pour ouvrir le volet Récapitulatif et afficher un récapitulatif, sélectionnez **Informations connexes** sur le bord droit de la page.)

### <a name="upper-section"></a>Partie supérieure

La partie supérieure de la page **Programme d’approvisionnement** contient une grille qui affiche les données suivantes pour un produit ou une famille de produits. Ces données sont ventilées par périodes définies par la valeur **Modèle de période** depuis le filtre.

- **Inventaire de début de période** : cette ligne indique le solde de stock prévu au début de la période si toutes les commandes du système se produisent.
- **Inventaire de fin de période** : cette ligne indique le solde de stock prévu à la fin de la période si toutes les commandes du système se produisent.
- **Inventaire lié à la fin de période** : cette ligne indique le montant des stocks à la fin de la période qui est indexé sur la demande future.
- **Offre nette de la période** : cette ligne montre la différence entre l’offre et la demande dans la période.
- **Inventaire minimum** : ce nœud affiche le stock de sécurité d’un produit ou d’une famille de produits. Pour développer ou réduire ce nœud, sélectionnez-le, puis sélectionnez **Développer** ou **Réduire** sur la barre d’outils. Ce nœud est affiché uniquement lorsqu’il existe un stock de sécurité pour le produit ou la famille de produits.
- **Demande** : ce nœud affiche la demande pour un produit ou une famille de produits. La demande est regroupée par type de transaction. Pour développer ou réduire ce nœud, sélectionnez-le, puis sélectionnez **Développer** ou **Réduire** sur la barre d’outils. Les types de transaction de demande incluent les ventes, les transferts et les journaux d’inventaire. Ce nœud est affiché uniquement lorsqu’il existe une demande pour le produit ou la famille de produits.
- **Offre** : ce nœud affiche l’offre pour un produit ou une famille de produits. L’offre est regroupée par type de transaction. Pour développer ou réduire ce nœud, sélectionnez-le, puis sélectionnez **Développer** ou **Réduire** sur la barre d’outils. Les types de transaction d’approvisionnement incluent la production, l’achat et les transferts. Ce nœud est affiché uniquement lorsqu’il existe une offre pour le produit ou la famille de produits.

De nombreux boutons de barre d’outils, affichages Récapitulatif et affichages Raccourci disponibles dépendent de vos sélections dans la section supérieure. En règle générale, vous choisissez un type de transaction en sélectionnant l’une des lignes sous le nœud **Offre** ou **Demande**. Vous choisissez ensuite une période en sélectionnant une colonne spécifique pour la ligne sélectionnée.

La barre d’outils au-dessus de la grille dans la partie supérieure de la page **Programme d’approvisionnement** propose les boutons suivants :

- **Développer/Réduire** : développer ou réduire un nœud sélectionné, tel que le nœud **Demande**, le nœud **Offre** et leurs sous-nœuds. (Les nœuds affichent un préfixe de type **\[+\]** ou **\[-\]** pour indiquer s’ils sont actuellement réduits ou développés.)
- **Nouveau** : ouvrez un menu où chaque commande, à son tour, ouvre une boîte de dialogue ou une page qui vous permet d’ajouter un type d’élément spécifique pour la sélection. Les commandes disponibles incluent **Approvisionnement prévisionnel**, **Ordre prévisionnel**, **Kanban planifié**, **Nouvel ordre de fabrication**, **Commande fournisseur** et **Ordre de transfert**.
- **Planification générale** : exécutez la planification générale. Une boîte de dialogue apparaît, dans laquelle vous pouvez spécifier le plan à exécuter. Par défaut, le champ **Plan principal** est défini pour correspondre au filtre actuel.
- **Déclaration et contrôle sans OF** : ouvrez la page **Déclaration et contrôle sans OF** du produit défini dans le filtre actuel.
- **Mettre à jour les ordres planifiés** : ouvrez la page **Ordres planifiés** qui affiche les ordres planifiés pour le produit ou la famille de produits défini dans le filtre actuel.
- **Niveau** : répartissez les ordres planifiés selon les paramètres de la boîte de dialogue qui apparaît.
- **Stratégie de plan matériel par emplacement** : ouvrez la page **Couverture de l’article** du produit défini dans le filtre courant.
- **Règle Kanban** : ouvrez la page **Règles Kanban** du produit défini dans le filtre actuel.

### <a name="fasttabs"></a>Raccourcis

La page **Programme d’approvisionnement** peut contenir les raccourcis suivants :

- **Inventaire de fin de période** : ce raccourci affiche les données d’inventaire de fin de période dans un format graphique.
- **Profil d’approvisionnement** : ce raccourci affiche les données d’approvisionnement dans un format graphique. Il devient visible lorsque vous sélectionnez un nœud **Offre** ou une ligne en dessous dans la section supérieure.
- **Résumé** : ce raccourci affiche les détails récapitulatifs liés au type de transaction que vous avez sélectionné dans la section supérieure. Par exemple, si vous sélectionnez **Ventes** sous le nœud **Demande**, ce raccourci affiche les champs liés aux commandes client, tels que **Lignes de commande client demandées** ou **Montant total**. Si vous sélectionnez **Ordres de fabrication** sous le sous-nœud **Production** du nœud **Offre**, ce raccourci affiche les champs liés aux ordres de fabrication, tels que **Ordres de fabrication programmés** ou **Total prévu**. Les valeurs des champs dépendent de la période que vous avez sélectionnée dans la section supérieure. 
- **\[Type de transaction\] - \[Période\]**  : ce raccourci affiche les commandes pour le type de transaction et la période que vous avez sélectionnés dans la section supérieure. Le nom du raccourci reflète ces sélections. Par exemple, il peut être nommé **Commandes client - File d’attente** ou **Ordres de fabrication - Semaine 37**.

### <a name="action-pane"></a>Volet Actions

Les boutons suivants sont disponibles dans le volet Actions :

- **Modifier le filtre** : ouvrez la boîte de dialogue **Modifier le filtre**, où vous pouvez mettre à jour les valeurs de filtre, puis rouvrez la page **Programme d’approvisionnement**, qui reflète les paramètres de filtre mis à jour.
- **Afficher les retards** : mettez en surbrillance les lignes pertinentes dans la section supérieure s’il existe une commande différée de ce type de transaction.

### <a name="factbox-pane"></a>Volet Récapitulatif

Pour ouvrir le volet Récapitulatif et afficher un récapitulatif, sélectionnez **Informations connexes** sur le bord droit de la page. Les Récapitulatifs suivants sont disponibles sur la page **Programme d’approvisionnement** :

- **Détails de l’article** : ce récapitulatif affiche des informations de base sur le produit défini dans le filtre actuel. Il est vide si vous avez défini une famille de produits dans le filtre.
- **Actions** : ce récapitulatif affiche les actions des commandes pour le type de transaction que vous avez sélectionné dans la section supérieure.
- **Retards** : ce récapitulatif affiche les retards des commandes pour le type de transaction que vous avez sélectionné dans la section supérieure.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
