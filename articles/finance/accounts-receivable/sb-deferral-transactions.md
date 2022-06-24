---
title: Transactions de report dans la facturation des abonnements
description: Cet article décrit les différentes transactions qui peuvent être utilisées dans les transactions de report dans le cadre des reports de revenus et de dépenses dans la facturation des abonnements.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c3862f1a250bf8e56303975b5c6a3560cd84c1e7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872584"
---
# <a name="deferral-default-transactions"></a>Transactions de report par défaut

Cet article décrit les transactions qui autorisent les reports de revenus et de dépenses. Les échéanciers de report sont toujours basés sur un document d’origine ou un calendrier de facturation dont ils dépendent. Les échéanciers de report sont créés sur la base de valeurs par défaut, et ne peuvent pas être saisis ou créés séparément.

## <a name="sales-order-transaction-deferral"></a>Report de transaction de commande client

Utilisez la page **Reports** ou **Créer un avoir** pour saisir ou modifier les paramètres de report d’une ligne de commande client.

> [!NOTE]
> Lorsqu’une commande client est créée à partir d’un échéancier de facturation, toutes les valeurs de la page **Reports** ou **Créer un avoir** sont en lecture seule et les paramètres de report ne peuvent pas être modifiés. Pour modifier les valeurs, utilisez la page **Modifier l’échéancier**.

### <a name="edit-deferral-options"></a>Modifier les options de report

Pour modifier les options de report d’une ligne, procédez comme suit.

1. Créez une transaction de commande client.
2. Sélectionnez la ligne, puis sélectionnez **Reports**.
3. Sur la page **Report de transaction**, l’option **Reporté** doit être définie sur **Oui**. Modifiez les autres champs selon vos besoins.
4. Pour afficher un aperçu de l’échéancier de report, sélectionnez **Aperçu**.
5. Si vous avez apporté des modifications au report de transaction, sélectionnez **OK** et retournez à la page de transaction.
6. Validez et comptabilisez la transaction.

Une fois la transaction validée, ouvrez la page **Tous les échéanciers de report** pour consulter l’échéancier de report.

### <a name="create-a-credit-note"></a>Création d’un avoir

Pour créer un avoir, procédez comme suit.

1. Créez une transaction de commande client.
2. Dans la section **Lignes de commande client**, sélectionnez l’article pour lequel vous souhaitez créer un avoir.
3. Sélectionnez **Ligne de commande client** \> **Nouveau**, puis sélectionnez **Avoir**.
4. Sélectionnez **Reports**.
5. Sur la page **Report de transaction de commande client**, définissez l’option **Ajuster l’échéancier existant** sur **Oui** pour l’article.
6. Dans le champ **Échéancier ajusté**, sélectionnez l’échéancier de report auquel vous souhaitez appliquer l’avoir.
7. Mettrez à jour les champs **Recalculer la date** et **Date de fin** selon vos besoins.
8. Cliquez sur **OK**.
9. Terminez la validation de la transaction de commande client.

### <a name="purchase-orders-and-purchase-invoices"></a>Commandes fournisseur et factures d’achat

Si vous souhaitez utiliser la fonctionnalité de report pour une commande fournisseur, générez d’abord la facture. Utilisez ensuite la page **Factures fournisseur en attente** pour modifier ou ajouter des articles de report. Vous ne pouvez pas modifier ou ajouter des reports directement sur une commande client.

1. Utilisez la page **Factures fournisseur en attente** pour saisir une facture fournisseur.

    Lorsque vous saisissez une ligne, le report est automatiquement défini pour l’article ou la catégorie d’approvisionnement que vous sélectionnez. Ce report est basé sur la configuration du report de la page **Valeurs par défaut de report**. Les reports peuvent être modifiés ou ajoutés au niveau de la distribution.

3. Sur la ligne d’achat, sélectionnez **Finances \> Répartir les montants**.
4. Pour chaque montant de distribution, sélectionnez **Reports**. Lorsque la facture est validée, un échéancier de report est créé pour chaque distribution pour laquelle un report est défini.

### <a name="tax"></a>Taxes

Dans certains cas, le montant de la taxe peut être totalement ou partiellement non récupérable. Si le montant de taxe d’une ligne reportable contient un montant non récupérable, le montant de taxe non récupérable est inclus dans le montant de l’échéancier de report lors de la validation de la facture.

### <a name="variance"></a>Écart

Si le montant sur la ligne de facture fournisseur diffère du montant sur la ligne de commande fournisseur, des distributions d’écart sont créées. Si la ligne est reportée, le compte général de ces distributions est défini sur le compte de report et les montants sont inclus dans le montant de l’échéancier de report lorsque la facture est validée. Ces distributions sont nommées **Écart de prix** et **Écart de coût**.

### <a name="general-journals-and-invoice-journals"></a>Journaux des opérations diverses et journaux des factures

Utilisez la page **Reports** pour saisir les paramètres de report d’une ligne de justificatif de journal. Vous pouvez également prévisualiser l’échéancier de report pour les reports linéaires. Lorsque vous saisissez une ligne, le report est automatiquement défini en fonction de la configuration des comptes de report sur la page **Valeurs par défaut de report**. Vous pouvez modifier manuellement les options de report pour chaque ligne. Lorsque le justificatif de journal est validé, l’échéancier de report est créé.

#### <a name="post-and-transfer"></a>Valider et transférer

Pour valider le justificatif de journal, utilisez la commande **Valider et transférer**. Les options de report suivront la ligne à laquelle le justificatif s’applique. Pour les justificatifs qui ne comportent pas d’erreurs, un échéancier de report est créé s’il est reporté. Pour un justificatif qui comporte une erreur et qui est transféré, toutes les options de report sont également transférées avec lui.

#### <a name="tax"></a>Taxes

Dans certains cas, le montant de la taxe peut être totalement ou partiellement non récupérable. Si le montant de taxe d’une ligne reportable contient un montant non récupérable, le montant de taxe non récupérable est inclus dans le montant de l’échéancier de report lors de la validation de la facture.

## <a name="free-text-invoice-transaction-deferral"></a>Report de transaction de facture financière

Utilisez la page **Reports** pour saisir les paramètres de report d’une distribution de ligne de facture financière. Lorsqu’une distribution est entrée, le report est automatiquement défini en fonction des paramètres de report sur la page **Valeurs par défaut de report**.

## <a name="fields"></a>Champs

La page **Report de transaction** contient les champs suivants.

| Champ | Description |
|-------|-------------|
| Différé | <p>Spécifiez si la ligne est un report :</p><ul><li>**Oui** : la ligne est un report.</li><li>**Non** : la ligne n’est pas un report.</li></ul><p>Lorsque cette option est définie sur **Oui**, l’option **Ajuster l’échéancier existant** n’est pas disponible. Pour les articles et les frais déjà configurés comme reportés, cette option est définie sur **Oui**. Pour les articles et les frais qui ne sont pas configurés comme reportés, définissez cette option sur **Oui**.</p> |
| Ajuster l’échéancier existant | <p>Spécifiez si la ligne est un ajustement à un échéancier de report existant :</p><ul><li>**Oui** : la nouvelle ligne de vente est un ajustement à un échéancier de report existant. Dans ce cas, vous pouvez sélectionner un échéancier de report dans le champ **Échéancier ajusté**.</li><li>**Non** : la nouvelle ligne de vente n’est pas un ajustement à un échéancier de report existant.</li></ul><p>Lorsque cette option est définie sur **Oui**, l’option **Reporté** n’est pas disponible.</p> |
| Échéancier ajusté | <p>Sélectionnez l’échéancier de report que la ligne est en train d’ajuster. Toutes les valeurs de la page sont ensuite mises à jour avec les valeurs provenant de l’échéancier de report d’origine. Ces valeurs ne peuvent pas être modifiées.</p><p>Ce champ n’est disponible que lorsque l’option **Ajuster l’échéancier existant** est définie sur **Oui**.</p> |
| Date de recalcul | <p>Spécifiez la date de début de la période à partir de laquelle vous souhaitez recalculer le montant restant. La date par défaut est la date de la prochaine période non reconnue.</p><p>Ce champ n’est disponible que lorsque l’option **Ajuster l’échéancier existant** est définie sur **Oui**.</p> |
| Date de fin | <p>Selon le type de report, la date de fin peut ou non être mise à jour :</p><ul><li>Pour un report linéaire, précisez la nouvelle date de fin de l’échéancier. La date de fin existante de l’échéancier de report est la valeur par défaut.</li><li>Pour un report basé sur un événement, spécifiez la date de fin de la ligne d’événement de crédit. Cette date peut être vide.</li></ul><p>Ce champ n’est disponible que lorsque l’option **Ajuster l’échéancier existant** est définie sur **Oui**.</p> |
| Numéro d’échéancier de facturation | <p>Le numéro de l’échéancier de facturation.</p><p>Ce champ est disponible uniquement pour les échéanciers de facturation des contrats récurrents.</p> |
| Méthode d’ajustement des reports | <p>La méthode d’ajustement de report. La valeur correspond à la valeur sur la page **Traitement des résiliations en masse** pour l’échéancier de facturation du contrat récurrent.</p><p>Ce champ est disponible uniquement pour les échéanciers de facturation des contrats récurrents.</p> |
| **Comptes - Produit** | |
| Compte de report | <p>Le compte de report, qui est le compte d’imputation qui apparaît sur la page **Commande client**.</p><p>Si la ligne n’est pas reportée, ce champ est vide. Dans ce cas, le compte d’imputation est le compte de produit par défaut.</p> |
| Compte de constatation | <p>Spécifiez le compte utilisé lorsqu’un report est reconnu. Ce compte doit différer du compte de report.</p><p>Quand l’option **Reporté** est initialement définie sur **Oui**, les valeurs de dimension utilisées dans le compte de report sont copiées dans le compte de reconnaissance. Si la dimension du compte de report n’existe pas pour le compte de reconnaissance, elle est ignorée.</p> |
| Compte de constatation initiale | <p>Sélectionnez le compte pour la reconnaissance initiale du produit. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat** sur la page **Paramètres de report des revenus et des dépenses**.</p> |
| Compte de contrepartie de constatation | <p>Sélectionnez le compte pour la contrepartie de la reconnaissance du produit. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat** sur la page **Paramètres de report des revenus et des dépenses**.</p> |
| **Comptes - Remise** | Cette section n’apparaît que pour les éléments reportés. Elle est masquée pour les frais reportés. |
| Compte de report | <p>Spécifiez le numéro de compte de report de la remise. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Option de report de remise** est défini sur **Échéancier distinct pour la remise** sur la page **Paramètres de report des revenus et des dépenses** et qu’une remise est appliquée à la ligne.</p> |
| Compte de constatation | <p>Spécifiez le numéro de compte de reconnaissance de la remise. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Option de report de remise** est défini sur **Échéancier distinct pour la remise** sur la page **Paramètres de report des revenus et des dépenses** et qu’une remise est appliquée à la ligne.</p> |
| Compte de constatation initiale | <p>Sélectionnez le compte pour la reconnaissance initiale de la remise. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat** sur la page **Paramètres de report des revenus et des dépenses** et qu’une remise est appliquée à la ligne.</p> |
| Compte de contrepartie de constatation | <p>Sélectionnez le compte pour la contrepartie de la reconnaissance du produit. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat** sur la page **Paramètres de report des revenus et des dépenses** et qu’une remise est appliquée à la ligne.</p> |
| **Comptes - Consommation** | Cette section n’apparaît que pour les éléments reportés. Elle est masquée pour les frais reportés. |
| Compte de report | <p>Spécifiez le numéro de compte de report de consommation.</p><p>Pour les produits standards, deux échéanciers de report sont créés :</p><ul><li>**Ventes standards** : un échéancier de produit qui a un solde créditeur. Dans ce cas, sélectionnez le compte de report de consommation.</li><li>**Consommation** : un échéancier de dépense de consommation (coût des marchandises vendues \[COGS\]) qui a un solde débiteur. Dans ce cas, sélectionnez le compte de reconnaissance de consommation.</li></ul><p>Lorsque la facture est validée, le montant de la consommation est validé sur le compte de report de consommation spécifié. Ces champs ne sont pas disponibles pour les articles de service.</p> |
| Compte de constatation | Spécifiez le numéro de compte de reconnaissance de consommation. |
| Compte de constatation initiale | <p>Spécifiez le compte pour le montant initial de reconnaissance de consommation. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat** sur la page **Paramètres de report des revenus et des dépenses**.</p> |
| Compte de contrepartie de constatation | <p>Spécifiez le compte pour le montant de contrepartie de reconnaissance de consommation. La valeur par défaut provient de la page **Valeurs par défaut de report**.</p><p>Ce champ n’est disponible que lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat** sur la page **Paramètres de report des revenus et des dépenses**.</p> |
| **Planifier** | |
| Type de programme | <p>Sélectionnez le type d’échéancier de report : **Linéaire** (par défaut) ou **Basé sur des événements**.</p><p>Les options qui s’affichent sur la page sont basées sur le type d’échéancier de report que vous sélectionnez.</p><p>Si le modèle par défaut est défini sur la page **Valeurs par défaut de report** de la ligne de transaction, le type d’échéancier de report est basé sur le type de modèle sélectionné.</p> |
| **Échéancier - Linéaire** | |
| Consolider les périodes précédentes | <p>Spécifiez si vous souhaitez regrouper les lignes d’échéances de report des périodes antérieures :</p><ul><li>**Oui** : regroupe les lignes d’échéance de report des périodes antérieures.</li><li>**Non** : ne regroupe pas les lignes d’échéance de report des périodes antérieures.</li></ul><p>La valeur par défaut provient de la page **Paramètres de report des revenus et des dépenses**.</p> |
| Égal par période | <p>Spécifiez si le nombre de jours de chaque période est égal ou varie selon la période :</p><ul><li>**Oui** : chaque période a le même nombre de jours.</li><li>**Non** : les périodes n’ont pas le même nombre de jours.</li></ul><p>Lorsque cette option est définie sur **Non**, le nombre de jours dans une période est pris en compte lorsque le montant de chaque période pour un échéancier de report est calculé.</p><p>La valeur par défaut provient de la page **Paramètres de report des revenus et des dépenses**.</p> |
| Programmer à partir d’un modèle | <p>Précisez si l’échéancier de report est créé sur la base d’un modèle ou d’une date de fin :</p><ul><li>**Oui** : l’échéancier de report est créé sur la base d’un modèle.</li><li>**Non** : l’échéancier de report est créé sur la base d’une date de fin.</li></ul> |
| Modèle | Sélectionnez le modèle de report. |
| Remplacer la date de début | <p>Indiquez si vous souhaitez remplacer la date de début :</p><ul><li>**Oui** : remplace la date de début par la date que vous saisissez dans le champ **Date de début**.</li><li>**Non** : la date de début est la **Date de début de report par défaut** qui s’applique à la date de facturation indiquée sur la page **Validation de la facture**. Cette règle peut être définie sur la page **Paramètres de report des revenus et des dépenses**.</li></ul> |
| Date de début du report | Spécifiez la date de début du report. La date de la transaction est la valeur par défaut. |
| Date de fin du report | <p>la date de fin du report.</p><p>Cette date est automatiquement calculée en fonction du modèle de report. Si aucun modèle n’est sélectionné, vous devez saisir manuellement la date.</p> |
| **Échéancier - Basé sur des événements** | |
| Modèle | <p>Sélectionnez le modèle basé sur des événements. Ce champ est facultatif.</p><p>Si vous sélectionnez un modèle, les valeurs du modèle écrasent toutes les données basées sur les événements et les lignes d’événement.</p> |
| Type de répartition | <p>Sélectionnez le type de répartition pour les lignes d’événement :</p><ul><li>**Montants variables** : un montant de répartition spécifique est saisi pour chaque ligne.</li><li>**Montants égaux** : le montant est réparti de manière égale pour chaque ligne.</li><li>**Pourcentage** : un montant basé sur la valeur de pourcentage saisie pour chaque ligne est alloué.</li><li>**Pourcentage d’achèvement** : une valeur d’achèvement cumulée est entrée pour chaque ligne.</li><p>**Quantité variable** : une quantité spécifique de répartition est entrée pour chaque ligne.</li></ul><p>**Remarque :** si vous souhaitez sélectionner **Pourcentage d’achèvement**, les dates doivent être dans l’ordre croissant.</p> |
| **Créer des événements séparés par unité** | |
| Description | <p>Spécifiez si vous souhaitez séparer les événements par unité :</p><ul><li>**Oui** : sépare les lignes d’événement afin qu’il y ait une ligne par quantité.<p>Par exemple, il y a trois lignes d’événement et la facture a une quantité de quatre. Dans ce cas, l’échéancier de report qui en résulte comporte 12 lignes.</p></li><li>**Non** : ne sépare pas les lignes d’événement.</li></ul> |
| Compte d’expiration | <p>Sélectionnez le compte utilisé pour les lignes reconnues expirées. Vous pouvez sélectionner le compte après la création de l’échéancier de report.</p><p>Si une date d’expiration est définie pour un événement, pendant le processus de reconnaissance, le montant de la reconnaissance est versé sur le compte d’expiration au lieu du compte de reconnaissance.</p> |
| **Échéancier - Lignes basées sur des événements** | |
| Description | Description de l’événement. |
| Date de fin du report | <p>Sélectionnez la date de fin de l’événement.</p><p>**Remarque :** si vous sélectionnez une date de fin, le champ **Date d’expiration** est effacé. Vous ne pouvez pas utiliser à la fois une date de fin et une date d’expiration.</p> |
| Date d’expiration | <p>Sélectionnez la date d’expiration de l’événement.</p><p>**Remarque :** si vous sélectionnez une date de fin, le champ **Date d’expiration** est effacé. Vous ne pouvez pas utiliser à la fois une date de fin et une date d’expiration.</p> |
| Quantity | <p>Spécifiez la quantité de la répartition. La valeur par défaut pour toutes les lignes est **0** (zéro). Si vous mettez à jour la quantité, la quantité totale de toutes les lignes doit être égale ou inférieure à la quantité spécifiée pour la ligne sur la commande client.</p><p>Ce champ n’est disponible que si le champ **Type de répartition** est défini sur **Quantité variable**.</p><p>Si la quantité de l’article de la ligne sur la commande client est modifiée de sorte qu’elle devienne inférieure à la quantité d’origine et que la facture est créée, moins de lignes basées sur des événements sont créées. La quantité totale répartie ne dépasse pas la quantité spécifiée sur la commande client ou l’échancier de facturation d’origine.</p> |
| Pourcentage de répartition | <p>Spécifiez le pourcentage de répartition. Si le champ **Type de répartition** est défini sur **Pourcentage** ou **Pourcentage d’achèvement**, vous pouvez saisir manuellement un pourcentage. Sinon, il est automatiquement calculé.</p><p>Si le champ **Type de répartition** est défini sur **Pourcentage**, le total des pourcentages doit être égal à 100.</p> |
| Montant | <p>Spécifiez le montant de la répartition. Si le champ **Type de répartition** est défini sur **Montants variables** ou **Pourcentage d’achèvement**, vous pouvez saisir manuellement un montant.</p><p>Si le champ **Type de répartition** est défini sur **Pourcentage d’achèvement**, et que vous entrez un montant ici, la valeur du champ **Pourcentage d’achèvement** est calculée automatiquement.</p><p>En raison des arrondis, le montant calculé peut ne pas correspondre exactement à ce qui est saisi manuellement. Si vous avez besoin d’un montant exact, définissez le champ **Type de répartition** sur **Montants variables**.</p> |
| Pourcentage d’achèvement | <p>Spécifiez le pourcentage d’achèvement. La valeur doit être un nombre compris entre 0 (zéro) et 100.</p><p>Ce champ n’est disponible que si le champ **Type de répartition** est défini sur **Pourcentage d’achèvement**.</p> |
| Montant d’achèvement | <p>Le total calculé pour toutes les lignes de l’échéancier de report.</p><p>Si le champ **Type de répartition** est défini sur **Pourcentage d’achèvement**, vous pouvez saisir manuellement un montant. Dans ce cas, la valeur du champ **Pourcentage d’achèvement** est calculée en fonction du montant que vous saisissez.</p><p>En raison des arrondis, le montant calculé peut ne pas correspondre exactement à ce qui est saisi manuellement.</p><p>Ce champ n’est disponible que si le champ **Type de répartition** est défini sur **Pourcentage d’achèvement**.</p> |
| Reconnaître lors de la validation | <p>Précisez si la ligne est reconnue automatiquement dès que la transaction est validée :</p><ul><li>**Sélectionné** : la ligne est reconnue automatiquement dès que la transaction est validée.</li><li>**Désélectionné** : la ligne n’est pas reconnue dès que la transaction est validée.</li></ul> |
| Compte de constatation | <p>Spécifiez le compte de reconnaissance pour l’événement, si le compte diffère du compte utilisé pour l’ensemble de l’échéancier de report.</p><p>Vous pouvez utiliser ce champ conjointement avec l’option **Reconnaître lors de la validation**.</p> |
