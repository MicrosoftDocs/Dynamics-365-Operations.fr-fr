---
title: Tâches périodiques dans la facturation des contrats récurrents
description: Cette rubrique décrit les tâches périodiques disponibles dans Facturation de contrat récurrent.
author: JodiChristiansen
ms.date: 04/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786968"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Tâches périodiques dans la facturation des contrats récurrents

Cette rubrique décrit les tâches périodiques disponibles dans Facturation de contrat récurrent.

## <a name="generate-invoice"></a>Générer une facture

Utilisez la page **Générer une facture** pour créer des factures récurrentes mensuelles en masse à partir des informations que vous avez paramétrées sur les pages **Tous les échéanciers de facturation** et **Afficher les détails de facturation**. Lorsqu’une facture est créée, la description de l’article de la ligne de traitement des commandes client est mise à jour avec la description de l’article et les dates de début et de fin de facturation de l’échéance facturée.

## <a name="generate-invoice-batch-processing"></a>Générer un traitement par lots des factures

Utilisez la page **Générer le traitement par lots de factures** pour créer des factures récurrentes via un traitement par lots récurrent. Les paramètres disponibles sont les mêmes que les paramètres de la page **Générer une facture**, mais ils peuvent être enregistrés dans un traitement par lots qui peut être exécuté plusieurs fois.

## <a name="price-update"></a>Mise à jour des prix

Utilisez l’utilitaire de mise à jour des prix pour mettre à jour les prix de plusieurs articles sur plusieurs échéanciers de facturation en une seule action. Les prix peuvent être mis à jour en fonction d’un pourcentage spécifié ou d’un montant spécifié. La liste des lignes affiche uniquement les prix unitaires actuels des articles. Elle n’affiche pas les prix après la mise à jour des prix.

Notez les points suivants concernant l’utilitaire de mise à jour des prix :

- Si la commande client pour une année spécifique a déjà été créée (c’est-à-dire que les articles ont été facturés), le prix des articles n’est pas affecté.
- L’utilitaire de mise à jour des prix peut être utilisé pour les articles de ligne dont le statut est **Actif** ou **En attente**. Pour les articles en attente, l’option **Ajuster le programme** doit avoir été définie sur **Non** lorsque la retenue a été placée.
- L’utilitaire de mise à jour des prix ne peut pas être utilisé pour les articles de ligne qui sont des articles d’utilisation, qui utilisent l’escalade, la facturation par étapes ou le partage des revenus.

### <a name="price-update-example"></a>Exemple de mise à jour de prix

Un échéancier de facturation est créé et un article de renouvellement est ajouté. Le prix unitaire est de 750 USD. La première année de l’article est payée le 15 décembre 2021. L’échéancier de facturation est créé pour la période du 1er janvier au 31 décembre 2022.

Au moment du renouvellement, le processus **Générer une facture** crée la commande client pour l’année 2022. Après l’exécution de l’utilitaire de mise à jour des prix, le prix est mis à jour de 750 USD à 800 USD.

La commande client et l’échéancier de facturation pour 2022 ne sont pas affectés, et le prix unitaire reste 750 USD, car l’échéancier de facturation pour 2022 a déjà été facturé. La ligne de l’échéancier de facturation et les détails de la ligne pour 2023 sont mis à jour vers 800 USD, car l’échéancier de facturation pour 2023 n’a pas encore été facturé.

### <a name="update-prices--flat-pricing-method"></a>Mettre à jour les prix - Méthode de tarification forfaitaire

Lorsque vous mettez à jour les prix des articles qui utilisent la méthode de tarification forfaitaire, vous pouvez spécifier un pourcentage ou un montant pour augmenter le prix.

Pour exécuter l’utilitaire de mise à jour des prix pour les articles qui utilisent la méthode de tarification forfaitaire, procédez comme suit.

1. Sur la page utilitaire **Mise à jour des prix**, sélectionnez la méthode de tarification **Forfaitaire**.
2. Dans le champ **Méthode d’augmentation**, sélectionnez la méthode d’augmentation utilisée pour mettre à jour le prix des articles.
3. En fonction de la méthode d’augmentation que vous avez sélectionnée, spécifiez le pourcentage dans le champ **Pour cent** ou le montant dans le champ **Montant**.
4. Dans le raccourci **Enregistrements à inclure**, utilisez le bouton **Filtre** pour ajouter des filtres de données.
5. Sélectionnez **Afficher l’aperçu** pour la plage d’enregistrements.
6. Si vous ne souhaitez pas traiter certaines lignes, marquez-les, puis sélectionnez **Supprimer**.
7. Cliquez sur **OK**.

### <a name="update-prices--standard-pricing-method"></a>Mettre à jour les prix - Méthode de tarification standard

Si le prix d’un article a été modifié dans l’enregistrement de l’article, il peut être mis à jour pour toutes les lignes de l’échéancier de facturation si l’article utilise la méthode de tarification standard.

1. Sur la page utilitaire **Mise à jour des prix**, sélectionnez la méthode de tarification **Standard**.
2. Dans le raccourci **Enregistrements à inclure**, utilisez le bouton **Filtre** pour ajouter des filtres de données.
3. Sélectionnez **Afficher l’aperçu** pour la plage d’enregistrements.
4. Si vous ne souhaitez pas traiter certaines lignes, marquez-les, puis sélectionnez **Supprimer**.
5. Cliquez sur **OK**.

## <a name="mass-hold-processing"></a>Traitement de retenue en masse

Utilisez la page **Retenue en masse** pour appliquer les options de retenue à plusieurs échéanciers de facturation simultanément.

Pour mettre un seul échéancier de facturation ou une seule ligne d’échéancier de facturation en attente, ouvrez la page **Tous les échéanciers de facturation** et sélectionnez **Mettre en attente**. Pour supprimer une retenue, utilisez la page **Supprimer la retenue**.

### <a name="put-billing-schedules-on-hold"></a>Mettre les échéanciers de facturation en attente

Pour suspendre plusieurs échéanciers de facturation, procédez comme suit.

1. Sur la page **Retenue en masse**, définissez le champ **Options de processus** sur **Appliquer la retenue**.
2. Dans le champ **Code motif**, sélectionnez un nouveau code motif.
3. Définissez l’option **Ajuster le programme** :

    - **Oui** – Si vous définissez l’option sur **Oui**, indiquez une date de blocage dans le champ **Date de retenue**. Toutes les lignes d’échéancier de facturation après la date de blocage sont supprimées.
    - **Non** – Les échéances de facturation ne sont pas modifiées. Seul le statut est modifié. Il est mis à jour sur **En attente**.

4. Dans le raccourci **Enregistrements à inclure**, utilisez le bouton **Filtre** pour ajouter des filtres de données.
5. Sélectionnez **Afficher l’aperçu** pour la plage d’enregistrements.
6. Si vous ne souhaitez pas traiter certaines lignes, marquez-les, puis sélectionnez **Supprimer**.
7. Cliquez sur **OK**.

Lorsque vous revenez à la liste des échéanciers de facturation, vous devriez voir que le statut des échéanciers de facturation a été changé en **En attente**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Supprimer un blocage de plusieurs échéanciers de facturation

1. Sur la page **Retenue en masse**, définissez le champ **Options de processus** sur **Supprimer la retenue**.
2. Dans le champ **Code motif**, entrez un nouveau code motif.
3. Dans le champ **Supprimer la date**, sélectionnez la date à laquelle la retenue doit être supprimée.
4. Définissez les champs **Date de reprise** et **Date de report** selon vos besoins. La date de report est ajoutée à toutes les lignes qui sont reportables.
5. Dans le raccourci **Enregistrements à inclure**, utilisez le bouton **Filtre** pour ajouter des filtres de données.
6. Sélectionnez **Afficher l’aperçu** pour la plage d’enregistrements.
7. Si vous ne souhaitez pas traiter certaines lignes, marquez-les, puis sélectionnez **Supprimer**.
8. Cliquez sur **OK**.

> [!NOTE]
> Pour supprimer une retenue, vous devez définir la valeur **Supprimer le remplacement du groupe d’utilisateurs en attente** sur la page **Paramètres de facturation des contrats récurrents**.

Par exemple, une ligne de facturation a une date de début au 1er février 2022 et une date de fin au 28 février 2022. Le montant de facturation de 200 USD. Le champ **Date de retenue** est défini sur 10 février 2022. Par conséquent, la période de février est ajustée pour exclure toute date postérieure au 10 février. La nouvelle période va du 1er février au 9 février et le montant est de 64,29 USD (au prorata quotidien). Toutes les lignes d’échéancier de facturation à compter du 10 février sont supprimées.

Si le processus **Supprimer la retenue** est terminé et que le champ **Supprimer la date** est défini sur 10 février 2022, il y aura deux périodes de facturation. La première période de facturation va du 1er février au 9 février et le montant est de 64,29 USD. La deuxième période de facturation s’étend du 10 février au 28 février et le montant est de 135,71 USD.

## <a name="mass-termination-processing"></a>Traitement de résiliation en masse

Utilisez la page **Résiliation en masse** pour résilier les lignes de l’échéancier de facturation qui sont actuellement affichées en spécifiant une date de résiliation.

Si vous utilisez des reports de revenus et de dépenses, les échéanciers de facturation où le champ **Date de résiliation** est défini sur **Ajuster le programme** sur la page **Tous les échéanciers de facturation** sont éligibles pour un remboursement.

Les échéanciers de facturation qui utilisent la fonctionnalité d’allocation d’articles multiples (MEA) n’apparaissent pas sur la page **Résiliation en masse**. Vous pouvez toujours résilier un échéancier de facturation individuel en utilisant la fonctionnalité de résiliation de l’échéancier de facturation.

> [!NOTE]
> Les lignes d’échéancier de facturation qui sont actuellement incluses dans un traitement par lots **Générer une facture** ne sont pas disponibles pour ce processus.

Pour plus d’informations sur chaque champ et le processus, voir [Résilier les échéanciers de facturation](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Processus d’archivage en masse

Utilisez la page **Archivage en masse** pour archiver plusieurs échéanciers de facturation. Seuls les échéanciers de facturation terminés peuvent être archivés.

Une fois qu’un échéancier de facturation a été archivé, les événements suivants se produisent :

- Le statut du paiement devient **Archivé**.
- Les échéanciers de facturation sont définitivement verrouillés.
- Les lignes d’échéancier de facturation ne sont plus disponibles sur les pages de demande.

> [!NOTE]
> L’archivage d’un échéancier de facturation est une action permanente et irréversible.

Pour archiver les échéanciers de facturation, procédez comme suit :

1. Sur la page **Archivage en masse**, dans le champ **Date de fin de facturation**, indiquez une date de fin de facturation. Pour afficher tous les échéanciers de facturation terminés, laissez ce champ vide.
2. Dans le raccourci **Enregistrements à inclure**, utilisez le bouton **Filtrer** pour limiter l’affichage des enregistrements.
3. Sélectionnez **Afficher l’aperçu**.
4. Si vous ne souhaitez pas archiver certains enregistrements, marquez-les, puis sélectionnez **Supprimer**.
5. Sélectionnez **OK** pour archiver les enregistrements sur la page.

## <a name="mass-stubbing-process"></a>Processus de substitution en masse

Utilisez la page **Substitution en masse** pour marquer toutes les lignes d’échéancier de facturation sélectionnées comme étant facturées (substitution) ou non facturées (substitution inversée). Le talonnage ou le talonnage inverse sont le plus souvent effectués sur des lignes d’échéancier de facturation importées qui ont été précédemment facturées dans un autre système. Les lignes d’échéancier de facturation substituées sont affichées comme substitution et ne créent pas de facture pour le client.

### <a name="stub-records"></a>Enregistrements souches

1. Sur la page **Substitution en masse**, dans le champ **Options de processus**, sélectionnez **Substitution**.
2. Dans le champ **Date limite**, définissez une date limite pour spécifier les lignes auxquelles vous souhaitez appliquer le processus. Seuls les enregistrements dont la date de début de facturation est antérieure ou égale à la date limite spécifiée seront affichés.
3. Sélectionnez **Voir l’aperçu** pour afficher les lignes que vous souhaitez remplacer.
4. Pour exclure une ligne du processus, marquez-la, puis sélectionnez **Supprimer**.
5. Sélectionnez **Processus** pour substituer les lignes.

### <a name="reverse-stub-records"></a>Inverser les enregistrements de substitutions

1. Sur la page **Substitution en masse**, dans le champ **Options de processus**, sélectionnez **Contrepasser le substitut**.
2. Dans le champ **Date limite**, définissez une date limite pour spécifier les lignes auxquelles vous souhaitez appliquer le processus. Seuls les enregistrements dont la date de début de facturation est antérieure ou égale à la date limite spécifiée seront affichés.
3. Sélectionnez **Voir l’aperçu** pour afficher les lignes dont vous souhaitez contrepasser la substitution.
4. Pour exclure une ligne du processus, marquez-la, puis sélectionnez **Supprimer**.
5. Sélectionnez **Processus** pour contrepasser la substitution des lignes.

## <a name="update-completion-date-process"></a>Mettre à jour le processus de date d’achèvement

Utilisez la page **Mettre à jour la date d’achèvement** pour mettre à jour la date d’achèvement d’articles de jalon spécifiques pour plusieurs échéanciers de facturation ou utilisateurs. Vous pouvez également mettre à jour le pourcentage d’achèvement des articles sur les modèles de jalon qui utilisent la méthode **Pourcentage terminé**.

1. Sur la page **Mettre à jour la date d’achèvement**, accédez à **Traitement des jalons**, puis sélectionnez **Mettre à jour le pourcentage d’achèvement**.
2. Dans le champ **Montant en pourcentage**, entrez le pourcentage total qui a été complété.
3. Sélectionnez le numéro d’article associé au modèle de jalon.
4. Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtre** pour sélectionner une valeur **Compte utilisateur final**, **Numéro d’échéancier de facturation** ou **Numéros d’article** comme critère de filtrage.
5. Sélectionnez **OK** pour traiter le changement. Lorsque le traitement est terminé, une nouvelle ligne est ajoutée à l’allocation de jalon. Cette ligne représente le pourcentage qui a été réalisé pour le modèle de jalon.

## <a name="unbilled-revenue-mass-processing"></a>Traitement en masse des produits non facturés

Utilisez la page **Traitement en masse des revenus non facturés** pour créer l’écriture au journal des revenus non facturés ou insérer le talon de l’écriture au journal pour un ou plusieurs échéanciers de facturation ou lignes de détails de facturation sélectionnés.

- **Créer une entrée de journal** – Créez des entrées de journal des revenus non facturés pour plusieurs lignes d’échéancier de facturation. Utilisez le bouton **Filtrer** dans le raccourci **Enregistrements à inclure** pour sélectionner la plage d’enregistrements à afficher dans la liste. La liste affiche uniquement les lignes d’échéancier de facturation pour lesquelles les écritures de journal des revenus non facturés n’ont pas été créées. Les écritures de journal initiales sont créées. Pour les articles reportés, les échéanciers de report sont également créés.
- **Écriture de journal de talon** – Marquez les lignes de l’échéancier de facturation pour lesquelles les écritures non facturées ont déjà été créées. Cette option est utilisée si l’écriture au journal non facturée a déjà été comptabilisée dans un autre système. Il marque le journal des revenus non facturés comme substitutions et ne valide pas un mouvement dans la comptabilité.
- **Inverser l’entrée de journal de substitution** – Inversez les entrées de journal de substitution qui ont été traitées. Si une erreur a été commise lors du traitement de la tâche **Substituer l’entrée du journal**, cette option effacera la case à cocher **Substitué** pour la ligne d’échéancier de facturation.
- **Substituer la ligne des détails de facturation** – Utilisez ce processus lorsque les revenus non facturés ont été traités dans un système externe et que certaines lignes de détails de facturation ont déjà été facturées. Ce processus garantira que le montant correct apparaît dans les comptes de revenus non facturés.
- **Contrepasser la ligne des détails de facturation du substitut** – Inverser les actions **Substituer la ligne des détails de facturation**.

Le champ **Nom de journal** est utilisé pour valider **Créer une entrée de journal** à la comptabilité.

> [!NOTE]
> Le processus de substitution ne comptabilise pas les montants dans la comptabilité. Le champ **Nom de journal** n’est pas disponible pour tous les processus de substitution et de substitution inversée.

### <a name="unbilled-revenue-stub-example"></a>Exemple de substitution de revenu non facturé

Un échéancier de facturation est établi pour un an, d’octobre 2021 à septembre 2022. Le produit non facturé a déjà été traité dans un système externe. Neuf mois de l’échéancier de facturation ont déjà été facturés. Le montant pour chaque période de facturation est de 250 USD. Au début de l’année, le montant total qui a été comptabilisé dans les revenus non facturés est de 3 000 USD. Après neuf mois, le montant de 2 250 USD a déjà été facturée, et il reste 750 USD en revenus non facturés.

Pour configurer l’échéancier de facturation où il ne reste que trois mois de revenus non facturés, procédez comme suit.

1. Sur la page **Afficher les détails de facturation**, créez un échéancier de facturation pour la période d’octobre 2021 à septembre 2022, numéro d’article S0001, et un montant de 250 USD par mois.
2. Sélectionnez **Créer une entrée de journal** pour l’échéancier de facturation. Le montant de 3 000 USD est comptabilisé dans les revenus non facturés.
3. Sélectionnez **Substituer la ligne des détails de facturation**, et précisez une date de mouvement de juin 2022 (neuf mois). Les lignes d’échéancier de facturation n’apparaîtront pas dans l’aperçu. Les lignes concernées sont basées sur la date de mouvement.
4. Cliquez sur **OK**.

Les neuf premiers mois qui ont été facturés sont tronqués.

[![Afficher la substitution des lignes de détails de facturation.](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

Le montant de 3 000 USD est inversé par rapport aux revenus non facturés, et le montant 750 USD des revenus non facturés qui reste est affiché. Pour afficher les écritures de produits non facturés, sélectionnez **Audit des écritures au journal des revenus non facturés** dans l’onglet **Renouvellements** de la page des détails de la ligne.

[![Audit d’entrée de journal du produit non facturé.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> L’écriture au journal des revenus non facturés peut être créée pour n’importe quelle période de renouvellement, à condition que toutes les lignes de détails de facturation de la période précédente aient été facturées. Par exemple, une ligne d’échéancier de facturation a une fréquence de facturation mensuelle pour une période de 12 mois, de janvier à décembre 2021. La ligne a trois termes : le terme initial, un deuxième terme (janvier à décembre 2022) et un troisième terme (janvier à décembre 2023). Une fois la facture créée pour toutes les lignes de détail de facturation des 12 premiers mois en 2021, l’écriture au journal pour les revenus non facturés peut être créée pour le deuxième terme.
>
> Pour les articles différés qui utilisent la fonction de revenu non facturé, la ligne de facturation et les lignes de remise sont traitées. Pour ces articles, l’écriture au journal des produits non facturés et l’échéancier de report pour la ligne de facturation et la ligne de remise sont créés.
>
> Les écritures de journal créées pour les articles non reportables et les articles reportables affichent un crédit sur différents comptes de produits.
