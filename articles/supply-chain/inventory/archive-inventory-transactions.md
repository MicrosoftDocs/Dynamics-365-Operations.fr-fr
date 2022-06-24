---
title: Archiver les mouvements de stock
description: Cet article décrit comment archiver les données de transaction d’inventaire pour améliorer les performances du système.
author: yufeihuang
ms.date: 05/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c63cdee862e2e22649a3eb58ae37597741770e14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874099"
---
# <a name="archive-inventory-transactions"></a>Archiver les mouvements de stock

[!include [banner](../../includes/banner.md)]

Au fil du temps, le tableau des transactions d’inventaire (`InventTrans`) continuera de croître et de consommer plus d’espace de base de données. Par conséquent, les requêtes effectuées sur la table deviendront progressivement plus lentes. Cet article décrit comment utiliser la fonctionnalité *Archivage des transactions d’inventaire* pour archiver les données sur les transactions d’inventaire afin d’améliorer les performances du système.

> [!NOTE]
> Seules les transactions de stock mises à jour financièrement peuvent être archivées dans une période comptable fermée sélectionnée. Pour être archivées, les mouvements de stock sortants mis à jour financièrement doivent avoir un statut de sortie de *Vendu*, et les transactions d’inventaire entrantes doivent avoir un statut de réception de *Acheté*.

Lorsque vous archivez des transactions d’inventaire, toutes les transactions associées sont déplacées vers la table `InventTransArchive`. Les transactions de sortie de stock et les transactions de réception de stock sont archivées séparément, en fonction de la combinaison de l’ID article (`itemId`) et l’ID de la dimension d’inventaire (`inventDimId`), et ils sont placés dans le numéro récapitulé et dans les transactions de réception récapitulées.

Si une combinaison de `itemId` et de `inventDimId` ne contient qu’une seule transaction de réception ou de sortie, la transaction ne sera pas archivée.

## <a name="turn-on-the-feature-in-your-system"></a>Activez la fonctionnalité dans votre système

Si votre système n’inclut pas déjà les fonctionnalités décrites dans cet article, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Archivage des transactions d’inventaire*. Notez que cette fonctionnalité ne peut pas être désactivée une fois qu'elle a été activée.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Éléments à prendre en compte avant d’archiver les transactions d’inventaire

Avant d’archiver les transactions d’inventaire, vous devez envisager les scénarios commerciaux suivants, car ils seront affectés par l’opération :

- Lorsque vous auditez des transactions d’inventaire à partir de documents associés, tels que des lignes de commande fournisseur, elles sont affichées comme archivées. Pour consulter les transactions archivées, vous devez aller à **Gestion de l’inventaire \> Tâches périodiques \> Nettoyer \> Archive des transactions d’inventaire**.
- La clôture de l’inventaire ne peut pas être annulée pour les périodes archivées. Avant de pouvoir annuler une clôture de stock, vous devez contrepasser l’archive des mouvements de stock pour la période concernée.
- La conversion des coûts standard ne peut pas être effectuée pour les périodes archivées. Avant de pouvoir effectuer une conversion de coût standard, vous devez contrepasser l’archive des mouvements de stock pour la période concernée.
- Les rapports d’inventaire issus des transactions d’inventaire seront affectés lorsque vous archiverez les transactions d’inventaire. Ces rapports comprennent le rapport sur le vieillissement des stocks et les rapports sur la valeur des stocks.
- Les prévisions d’inventaire peuvent être affectées si elles sont exécutées pendant l’horizon temporel des périodes archivées.

## <a name="prerequisites"></a>Conditions préalables

Les transactions de stock ne peuvent être archivées que pendant les périodes où les conditions suivantes sont remplies :

- La période comptable doit être clôturée.
- La clôture de l’inventaire doit être exécutée à la date de fin de période de l’archive ou après cette date.
- La période doit être au moins un an avant la date de la période de début de l’archive.
- Il ne doit y avoir aucun recalcul d’inventaire existant.

## <a name="archive-inventory-transactions"></a>Archiver les mouvements de stock

Pour archiver les transactions de stock, procédez comme suit.

1. Aller à **Gestion des stocks** \> **Tâches périodiques** \> **Nettoyer** \> **Archive des transactions d’inventaire**.

    La page **Archive des transactions d’inventaire** apparaît et affiche une liste des enregistrements de processus archivés.

    ![Page Archive des transactions de stock.](media/archive-inventory-empty.png "Page Archive des transactions de stock")

1. Dans le volet Actions, sélectionnez **Archive des transactions d’inventaire** pour créer une archive de transactions d’inventaire.
1. Dans la boîte de dialogue **Archive des transactions d’inventaire**, sur le raccourci **Paramètres**, définissez les champs suivants :

    - **De la date dans la période comptable fermée** – Sélectionnez la date de transaction la plus récente à inclure dans l’archive.
    - **À la date dans la période comptable fermée** – Sélectionnez la date de transaction la plus ancienne à inclure dans l’archive.

    ![Boîte de dialogue Archive des transactions de stock.](media/archive-inventory-dates.png "Boîte de dialogue Archive des transactions de stock")

    > [!NOTE]
    > Seules les périodes qui respectent les [conditions préalables](#prerequisites) sera disponible pour la sélection.

1. Sur le raccourci **Exécuter en arrière-plan**, configurez les détails du traitement par lots selon vos besoins. Suivez les étapes habituelles pour les travaux par lots dans Microsoft Dynamics 365 Supply Chain Management.
1. Cliquez sur **OK**.
1. Vous recevez un message qui vous invite à confirmer que vous souhaitez continuer. Lisez attentivement le message, puis sélectionnez **Oui** pour continuer.

    Vous recevez un message indiquant que votre travail d’archivage des transactions d’inventaire a été ajouté à la file d’attente par lots. Le travail commencera maintenant à archiver les transactions d’inventaire de la période sélectionnée.

## <a name="view-archived-inventory-transactions"></a>Afficher les transactions de stock archivées

La page **Archive des transactions d’inventaire** affiche votre historique d’archivage complet. Chaque ligne de la grille affiche des informations telles que la date de création de l’archive, l’utilisateur qui l’a créée et son statut.

![Page Historique de l’archivage des transactions d’inventaire.](media/archive-inventory-full.png "Page Historique de l’archivage des transactions d’inventaire")

Dans la liste déroulante en haut de la page, sélectionnez l’une des valeurs suivantes pour filtrer les archives affichées dans la grille :

- **Actif** – Afficher uniquement les archives actives, pas les archives inversées.
- **Tout** – Afficher toutes les archives, actives et inversées.

Pour chaque archive de la grille, les informations suivantes sont fournies :

- **Actif** – Une coche indique que l’archive est active.
- **Date de début** – La date de la transaction la plus ancienne pouvant être incluse dans l’archive.
- **Date de fin** – La date de la transaction la plus récente pouvant être incluse dans l’archive.
- **Programmé par** – Le compte utilisateur qui a créé l’archive.
- **Exécuté** – Date de création de l’archive.
- **Annuler** – Une coche indique que l’archive a été annulée.
- **Arrêter la mise à jour actuelle** – Une coche indique que l’archive est en cours, mais qu’elle a été suspendue.
- **État** – Le statut de traitement de l’archive. Les valeurs possibles sont *Attente*, *En cours*, et *Terminé*.

La barre d’outils au-dessus de la grille fournit les boutons suivants que vous pouvez utiliser pour travailler avec une archive sélectionnée :

- **Transactions archivées** – Afficher les détails complets de l’archive sélectionnée. La page **Transactions archivées** qui apparaît montre toutes les transactions dans l’archive.

    ![Page des transactions archivées.](media/archive-inventory-transactions.png "Page des transactions archivées")

    Pour afficher plus d’informations sur une transaction spécifique sur la page **Transactions archivées**, sélectionnez-le dans la grille, puis, dans le volet Actions, sélectionnez **Détails de la transaction archivée**. La page **Détails de la transaction archivés** qui apparaît affiche des informations telles que l’écriture comptable, les références de comptabilité auxiliaire associées et les dimensions financières.

- **Suspendre l’archivage** – Suspend une archive sélectionnée en cours de traitement. La pause prend effet uniquement après la génération de la tâche d’archivage. Par conséquent, il peut y avoir un court délai avant que la pause ne prenne effet. Si une archive a été mise en pause, une coche apparaît dans son champ **Arrêter la mise à jour actuelle**.
- **Reprendre l’archivage** – Reprendre le traitement d’une archive sélectionnée en cours de suspension.
- **Annuler** – Annulez l’archive sélectionnée. Vous ne pouvez annuler une archive que si son champ **État** est défini sur *Terminé*. Si une archive a été annulée, une coche apparaît dans son champ **Annuler**.

## <a name="extend-your-code-to-support-custom-fields"></a>Étendez votre code pour prendre en charge les champs personnalisés

Si la table `InventTrans` contient un ou plusieurs champs personnalisés, vous devrez peut-être étendre le code pour les prendre en charge, selon la façon dont ils sont nommés.

- Si les champs personnalisés de la table `InventTrans` ont les mêmes noms de champ que dans la table `InventtransArchive`, cela signifie qu'ils sont mappés 1:1. Par conséquent, vous pouvez simplement mettre les champs personnalisés dans le groupe de champs `InventoryArchiveFields` de la table `inventTrans`.
- Si les noms de champs personnalisés dans la table `InventTrans` ne correspondent pas aux noms de champ dans la table `InventtransArchive`, vous devez ajouter du code pour les mapper. Par exemple, si vous avez un champ système appelé `InventTrans.CreatedDateTime`, vous devez alors créer un champ dans la table `InventTransArchive` avec un nom différent (comme `InventtransArchive.InventTransCreatedDateTime`) et ajouter des extensions aux classes `InventTransArchiveProcessTask` et `InventTransArchiveSqlStatementHelper`, comme illustré dans l'exemple de code suivant.

L'exemple de code suivant affiche un exemple du mode d'ajout de l'extension requise à la classe `InventTransArchiveProcessTask`.

```xpp
[ExtensionOf(classStr(InventTransArchiveProcessTask))]
Final class InventTransArchiveProcessTask_Extension
{

    protected void addInventTransFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTrans, ModifiedBy))
            .add(fieldStr(InventTrans, CreatedBy)).add(fieldStr(InventTrans, CreatedDateTime));

        next addInventTransFields(_selectionObject);
    }


    protected void addInventTransArchiveFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTransArchive, InventTransModifiedBy))
            .add(fieldStr(InventTransArchive, InventTransCreatedBy)).add(fieldStr(InventTransArchive, InventTransCreatedDateTime));

        next addInventTransArchiveFields(_selectionObject);
    }
}
```

L'exemple de code suivant affiche un exemple du mode d'ajout de l'extension requise à la classe `InventTransArchiveSqlStatementHelper`.

```xpp
[ExtensionOf(classStr(InventTransArchiveSqlStatementHelper))]
final class InventTransArchiveSqlStatementHelper_Extension
{
    private str     inventTransModifiedBy;  
    private str     inventTransCreatedBy;
    private str     inventTransCreatedDateTime;

    protected void initialize()
    {
        next initialize();
        inventTransModifiedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, ModifiedBy)).name(DbBackend::Sql);
        inventTransCreatedDateTime = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedDateTime)).name(DbBackend::Sql);
        inventTransCreatedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedBy)).name(DbBackend::Sql);
    }

    protected str buildInventTransArchiveSelectionFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransArchiveSelectionFieldsStatement();
        
        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransModifiedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedDateTime)).name(DbBackend::Sql));
        }

        return ret;
    }

    protected str buildInventTransTargetFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransTargetFieldsStatement();

        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransModifiedBy);
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedBy);
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedDateTime);
        }

        return ret;
    }
}
```
