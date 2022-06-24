---
title: Reports de revenus et de dépenses dans la facturation des abonnements
description: Cet article explique comment configurer la fonctionnalité de reports de revenus et de dépenses dans la facturation des abonnements.
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
ms.openlocfilehash: 209afd08c0c7e3cbd63ed95613b1d1dec94856f5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908094"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Reports de revenus et de dépenses dans la facturation des abonnements

Cet article explique comment configurer et utiliser la fonctionnalité de reports de revenus et de dépenses dans la facturation des abonnements. Les échéanciers de report sont toujours basés sur un document d’origine sous-jacent ou un calendrier de facturation dont ils dépendent. Parce qu’ils sont créés sur la base de valeurs par défaut, ils ne peuvent pas être saisis ou créés séparément.

Le processus de configuration et d’utilisation des reports de revenus et de dépenses se déroule sur plusieurs pages :

- Sur la page **Paramètres de report des revenus et des dépenses** page, vous pouvez définir les préférences de l’entreprise.
- Sur la page **Valeurs par défaut de report**, vous pouvez configurer les comptes et modèles par défaut utilisés pour les échéanciers de report.
- Sur les pages **Modèles de report** et **Modèles de report basés sur des événements**, vous pouvez définir les modèles qui sont utilisés pour les échéanciers de report.
- Sur la page **Tous les échéanciers de report**, vous pouvez afficher et modifier n’importe quel échéancier de report.

Les reports de revenus et de dépenses peuvent être utilisés avec la facturation des contrats récurrents.

## <a name="revenue-and-expense-deferral-parameters"></a>Paramètres de report des revenus et des dépenses

La page **Paramètres de report des revenus et des dépenses** contient les champs suivants.

| Champ | Description |
|---|---| 
| Onglet **Échéancier** | |
| Égal par période | <p>Spécifiez si le nombre de jours d’une période est utilisé lorsque le montant par période est calculé pour un échéancier de report :</p><ul><li>**Oui** : Le montant pour chaque période est le même, quel que soit le nombre de jours de la période. Les périodes partielles (telles que les périodes au début ou à la fin d’un échéancier de report) seront calculées au prorata.</li><li>**Non** : Le montant est calculé sur la base du nombre de jours de chaque période.</li></ul><p>Vous pouvez remplacer ce paramètre au niveau de la transaction.</p> |
| Option de report de la remise sur vente | <p>Spécifiez si des échéanciers de report distincts sont créés pour la remise et les montants de la commande client :</p><ul><li>**Échéancier distinct pour la remise** : le montant de la remise est séparé du montant du revenu.<p>Dans ce cas, deux échéanciers de report sont créés lorsqu’une commande client est créée puis validée. Les montants de remise et de revenu seront affichés sur différents comptes de report.</p></li><li>**Fusionner la remise avec le revenu** : le montant de la remise est combiné au montant du revenu. Un échéancier de report est créé et le montant de la remise et le montant du produit sont validés sur le même compte de report.<p>Dans ce cas, un échéancier de report est créé lorsqu’une commande client est créée puis validée. Le montant de la remise et le montant du produit sont comptabilisés dans le même compte de report.</p></li></ul><p>**Remarque :** pour appliquer des remises aux articles qui utilisent la fonctionnalité de revenus non facturés, sélectionnez l’option **Échéancier distinct pour la remise**. Les remises peuvent ensuite être appliquées à tous les articles, que la fonction de revenus non facturés soit utilisée ou non. Si l’option **Fusionner la remise avec le revenu** est sélectionnée, les remises ne peuvent pas être appliquées aux articles qui utilisent la fonction de revenus non facturés.</p> |
| Option de report de la remise sur achat | <p>Sélectionnez si des échéanciers de report distincts sont créés pour la remise et les montants de la commande fournisseur :</p><ul><li>**Échéancier distinct pour la remise** : le montant de la remise est séparé du montant de la dépense.<p>Dans ce cas, deux échéanciers de report sont créés lorsqu’une commande fournisseur est créée puis validée. Les montants de remise et de dépense seront affichés sur différents comptes de report.</p></li><li>**Fusionner la remise avec le revenu** : le montant de la remise est combiné au montant de la dépense. Un échéancier de report est créé et le montant de la remise et le montant de la dépense sont validés sur le même compte de report.<p>Dans ce cas, un échéancier de report est créé lorsqu’une commande fournisseur est créée puis validée. Le montant de la remise et le montant de la dépense sont comptabilisés dans le même compte de report.</p></li></ul> |
| Consolider les périodes précédentes | <p>Spécifiez si les lignes d’échéances de report des périodes précédentes sont regroupées :</p><ul><li>**Oui** : si la date de début du report se situe dans une période antérieure à la date de transaction, tous les montants jusqu’à la période de la date de transaction sont combinés sur une seule ligne de l’échéancier de report.</li><li>**Non** : les montants de toutes les périodes sont conservés sur des lignes d’échéancier de report distinctes.<p>Si la date de début du report se situe dans la même période ou dans une période ultérieure à la date de transaction, cette option n’a aucun effet.</p></li></ul><p>Ce paramètre peut être mis à jour au niveau de la transaction.</p> |
| Date de début du report par défaut | <p>Sélectionnez la règle utilisée pour déterminer la date de début de l’échéancier de report :</p><ul><li>**Date de transaction** : utilisez la date de la transaction comme date de début.</li><li>**Début du mois en cours** : utilisez le premier du mois en cours comme date de début. Si la date de transaction est le premier de n’importe quel mois, le premier du mois en cours est la date de début.</li><li>**Début du mois suivant** : utilisez le premier du mois suivant comme date de début. Si la date de la transaction est le 1e, elle est utilisée. Sinon, le premier du mois suivant est utilisé.</li><li>**Règle de 15** : si la date de transaction se situe entre le premier et le quinze, utilisez le premier du mois en cours comme date de début. Si la date de transaction est entre le seize et la fin du mois, utilisez le premier du mois suivant comme date de début.</li></ul><p>Vous pouvez mettre à jour ce paramètre au niveau de la transaction.</p> |
| Méthode de report à court terme | <p>Sélectionnez la méthode de report à court terme : **Aucun**, **Périodes glissantes** ou **Année fixe**.</p><p>|
| Méthode de validation des reports | <p>Sélectionnez la méthode utilisée pour créer les transactions de report:</p><ul><li>**Bilan** : utilisez la méthode de comptabilisation au bilan pour créer des transactions de report.</li><li>**Résultat** : utilisez la méthode de comptabilisation au résultat pour créer des transactions de report. Lorsque des transactions sont validées, vous pouvez consulter le bordereau de facture pour voir les écritures supplémentaires qui équilibrent les montants de reconnaissance initiale et de reconnaissance compensée.</li></ul> |
| Contrepasser les profits et les pertes sur crédit | <p>**Remarque :** ce champ est disponible uniquement lorsque le champ **Méthode de comptabilisation des reports** est défini sur **Résultat**.</p><p>Spécifiez si les montants de résultat sont annulés lorsqu’une annulation, une résiliation ou un remboursement est appliqué à un échéancier de facturation ou à une commande client :</p><ul><li>**Oui** : annule le résultat et applique un montant d’ajustement de crédit à l’échéancier de report.<p>Si l’annulation se produit au milieu d’une période de facturation, les montants sont calculés au prorata.</p></li><li>**Non** : aucune transaction d’annulation n’est créée pour le résultat lorsqu’une annulation, une résiliation ou un remboursement est appliqué à un échéancier de facturation ou à une commande client.</li></ul> |
| Onglet **Reconnaissance** | |
| Valider automatiquement les journaux généraux | <p>Spécifiez si les écritures au journal créées par les reports de produit et de dépenses sont automatiquement validées :</p><ul><li>**Oui** : valide automatiquement les écritures au journal créées par les reports de produit et de dépenses.<p>**Conseil :** en sélectionnant **Oui**, vous pouvez contribuer à éviter les incohérences comptables causées par des modifications manuelles des pièces justificatives.</p></li><li>**Non** : les écritures au journal créées par les reports de produit et de dépenses ne sont pas validées automatiquement. Vous devez valider manuellement les journaux.</li></ul> |
| Résumer le journal de constatation | <p>Précisez si les bons de reconnaissance sont regroupés par défaut :</p><ul><li>**Oui** : crée un seul bordereau pour toutes les lignes de reconnaissance qui ont la même date. Toutes les lignes d’un bordereau qui ont le même compte sont regroupées sur une seule ligne.</li><li>**Non** : créer un bordereau pour chaque ligne de reconnaissance.</li></ul><p>Vous pouvez mettre à jour ce paramètre sur la page **Traitement de la reconnaissance**.</p> |
| Nom du journal par défaut | Sélectionnez le nom du journal pour les journaux créés à partir des processus de report de produits et de dépenses, tels que le traitement de la reconnaissance. |
| Description de la ligne de journal de constatation | <p>Sélectionnez la description qui apparaît dans la description de la ligne de pièce justificative du journal :</p><ul><li>**Dates d’échéance** : affiche les dates des échéances dans la description de la ligne de journal.</li><li>**Détails de la transaction d’origine** : affiche les informations de transaction d’origine dans la description de la ligne de journal.<p>**Exemple :** USMF-0001, CIV-00839, Revenus logiciels</p></li></ul> |
| Onglet **Souches de numéros** | Utilisez cet onglet pour définir les valeurs par défaut des souches de numéros de bail. L’assistant de génération de souches de numéros permet de générer et d’attribuer automatiquement des souches de numéros. Vous n’avez pas à modifier la souche de numéros, sauf si vous souhaitez apporter des modifications manuelles aux souches de numéros générées. |
| Numéro de l’échéancier | Le numéro utilisé par la souche pour les échéanciers de report. |

## <a name="deferral-templates"></a>Modèles de report

Utilisez la page **Modèles de report** pour définir les modèles linéaires utilisés pour les échéanciers de report.

Voici quelques-uns des avantages de l’utilisation d’un modèle :

* La durée du report est calculée automatiquement.
* Vous autorisez les échéanciers de report qui ont des périodes où la reconnaissance est ignorée.
* Vous pouvez automatiser les reports en attribuant le modèle à un produit, un groupe de produits, une catégorie de produits, des clients ou un groupe de clients. L’affectation des modèles s’effectue à partir de la page **Valeurs par défaut de report**.

Plusieurs fréquences de périodes sont disponibles pour les modèles : quotidiennes, mensuelles ou périodes fiscales.

Les lignes de modèle sont constituées d’un type (**Reconnu** ou **Ignoré**) et de la durée de la période. Les lignes ignorées ont un montant de 0 (zéro) sur les lignes de l’échéancier de report. Ce comportement peut être utile si vous ne souhaitez pas reconnaître les revenus dans toutes les périodes.

### <a name="create-a-deferral-template"></a>Créer un modèle de report

Pour créer un modèle de report, procédez comme suit.

1. Sur la page **Modèles de report**, sélectionnez **Nouveau**.
2. Dans le champ **Modèle**, entrez un nom.
3. Entrez une description dans le champ **Description**.
4. Dans le champ **Fréquence de la période**, sélectionnez la fréquence de la période.
5. Sélectionnez **Ajouter** pour ajouter une ligne en haut de la liste des lignes, ou sélectionnez **Ajouter à la fin** pour ajouter une ligne en bas de la liste.
6. Dans le champ **Type**, sélectionnez le type de période.
7. Dans le champ **Durée de la période**, spécifiez la durée de la période.
8. Répétez les étapes 5 à 7 pour chaque ligne supplémentaire nécessaire.
9. Cliquez sur **Enregistrer**.

## <a name="deferral-defaults"></a>Valeurs par défaut des reports

Utilisez la page **Valeurs par défaut de report** pour configurer des comptes de report par défaut pour les articles et pour attribuer des modèles par défaut aux articles reportables. Vous pouvez également configurer des comptes de report pour les frais et attribuer des modèles aux frais reportables.

**Report par article**

Pour les transactions qui comportent un article (par exemple, des commandes client), vous pouvez affecter des comptes et des modèles à des articles et à des clients spécifiques. Ces paramètres seront utilisés comme valeurs par défaut lorsqu’une transaction sera reportée. Pour rendre la transaction reportable par défaut, vous devez paramétrer les articles sur la page **Articles reportables**.

**Report par compte**

Pour les transactions qui n’ont pas d’articles (par exemple, les journaux des opérations diverses), vous pouvez spécifier les comptes de report. Lorsque ces comptes sont utilisés sur une ligne de transaction, la transaction est automatiquement marquée comme reportée. Le modèle et le compte de reconnaissance correspondants seront affectés à la ligne de transaction.

**Tous les types de transaction (par exemple, dans les onglets Commande client, Achats et Journal des opérations diverses)**

Les comptes sur la page sont les comptes principaux qui n’ont pas de dimensions financières. Les dimensions financières du compte de reconnaissance proviennent du client ou de l’article, en fonction de votre organisation.

Chaque ligne de modèle doit avoir soit un modèle linéaire, soit un modèle basé sur un événement. Elle ne peut pas avoir les deux.

### <a name="for-sales-orders"></a>Pour les commandes client

Pour spécifier les valeurs par défaut de report pour les commandes client, procédez comme suit.

1. Sur l’onglet **Commande client**, sélectionnez le type de report.
2. Sélectionnez **Ajouter** pour ajouter une ligne.
3. Dans le champ **Code article**, sélectionnez le code article. Le code article détermine la façon dont les valeurs par défaut du report sont appliquées.
4. Spécifiez comment le code article est appliqué :

    * Si le champ **Code article** est défini sur **Table** ou **Groupe**, sélectionnez la relation d’article dans le champ **Relation d’article**.
    * Si le champ **Code article** est défini sur **Catégorie**, sélectionnez la relation de catégorie dans le champ **Relation de catégorie**.
    * Si le champ **Code article** est défini sur **Tout**, les valeurs par défaut s’appliquent à tous les enregistrements applicables.

5. Spécifiez comment le code de compte est appliqué :

    * Si le champ **Code de compte** est défini sur **Table** ou **Groupe**, sélectionnez la relation de compte dans le champ **Relation de compte**.
    * Si le champ **Code de compte** est défini sur **Tout**, le compte s’applique à tous les enregistrements.

6. Dans le champ **Compte principal**, sélectionnez le compte principal pour le report.
7. Si le champ **Méthode de comptabilisation des reports** est défini sur **Résultat**, sélectionnez le compte de revenu initial dans le champ **Compte de revenu initial** et le compte de contrepartie du résultat dans le champ **Compte de contrepartie du résultat**.
8. Si le champ **Méthode de report à court terme** est défini sur **Périodes glissantes** ou **Année fixe**, sélectionnez le compte de report à court terme dans le champ **Compte de report à court terme**.
9. Pour un modèle, vous pouvez sélectionner **Ajouter** pour ajouter une ligne.
10. Dans le champ **Code article**, sélectionnez le code article.
11. Spécifiez comment le code article est appliqué :

    * Si le champ **Code article** est défini sur **Table** ou **Groupe**, sélectionnez la relation d’article dans le champ **Relation d’article**.
    * Si le champ **Code article** est défini sur **Catégorie**, sélectionnez la relation de catégorie dans le champ **Relation de catégorie**.
    * Si le champ **Code article** est défini sur **Tout**, les valeurs par défaut s’appliquent à tous les enregistrements applicables.

12. Spécifiez comment le code de compte est appliqué :

    * Si le champ **Code de compte** est défini sur **Table** ou **Groupe**, sélectionnez la relation de compte dans le champ **Relation de compte**.
    * Si le champ **Code de compte** est défini sur **Tout**, le compte s’applique à tous les enregistrements applicables.
    * Sélectionnez le modèle linéaire dans le champ **Modèle linéaire** ou le modèle basé sur les événements dans le champ **Modèle basé sur les événements**.

13. Cliquez sur **Enregistrer**.

### <a name="for-purchase-orders"></a>Pour les commandes fournisseur

Pour spécifier les valeurs par défaut de report pour les commandes fournisseur, procédez comme suit.

1. Sur l’onglet **Achat**, sélectionnez le type de report.
2. Sélectionnez **Ajouter** pour ajouter une ligne.
3. Dans le champ **Code article**, sélectionnez le code article.
4. Spécifiez comment le code article est appliqué :

    * Si le champ **Code article** est défini sur **Table** ou **Groupe**, sélectionnez la relation d’article dans le champ **Relation d’article**.
    * Si le champ **Code article** est défini sur **Catégorie**, sélectionnez la relation de catégorie dans le champ **Relation de catégorie**.
    * Si le champ **Code article** est défini sur **Tout**, les valeurs par défaut s’appliquent à tous les enregistrements applicables.

5. Spécifiez comment le code de compte est appliqué :

    * Si le champ **Code de compte** est défini sur **Table** ou **Groupe**, sélectionnez la relation de compte dans le champ **Relation de compte**.
    * Si le champ **Code de compte** est défini sur **Tout**, le compte s’applique à tous les enregistrements applicables.

6. Dans le champ **Compte principal**, sélectionnez le compte principal pour le report.
7. Si le champ **Méthode de comptabilisation des reports** est défini sur **Résultat**, sélectionnez le compte de revenu initial dans le champ **Compte de revenu initial** et le compte de contrepartie du résultat dans le champ **Compte de contrepartie du résultat**.
8. Si le champ **Méthode de report à court terme** est défini sur **Périodes glissantes** ou **Année fixe**, sélectionnez le compte de report à court terme dans le champ **Compte de report à court terme**.
9. Pour un modèle, sélectionnez **Ajouter** pour ajouter une ligne. 
10. Dans le champ **Code article**, sélectionnez le code article.
11. Spécifiez comment le code article est appliqué :

    * Si le champ **Code article** est défini sur **Table** ou **Groupe**, sélectionnez la relation d’article dans le champ **Relation d’article**.
    * Si le champ **Code article** est défini sur **Catégorie**, sélectionnez la relation de catégorie dans le champ **Relation de catégorie**.
    * Si le champ **Code article** est défini sur **Tout**, les valeurs par défaut s’appliquent à tous les enregistrements applicables.

12. Spécifiez comment le code de compte est appliqué :

    * Si le champ **Code de compte** est défini sur **Table** ou **Groupe**, sélectionnez la relation de compte dans le champ **Relation de compte**.
    * Si le champ **Code de compte** est défini sur **Tout**, le compte s’applique à tous les enregistrements applicables.
    * Sélectionnez le modèle linéaire dans le champ **Modèle linéaire** ou le modèle basé sur les événements dans le champ **Modèle basé sur les événements**.

13. Cliquez sur **Enregistrer**.

### <a name="for-general-journals"></a>Pour les journaux des opérations diverses

Pour spécifier les valeurs par défaut de report pour les écritures du journal des opérations diverses, procédez comme suit.

1. Sélectionnez l’onglet **Journal des opérations diverses**.
2. Pour un report, sélectionnez **Ajouter** pour ajouter une ligne.
3. Si le champ **Méthode de report à court terme** est défini sur **Périodes glissantes** ou **Année fixe**, sélectionnez le compte de report à court terme dans le champ **Compte de report à court terme**.
4. Dans le champ **Compte de report**, sélectionnez le compte de report.
5. Dans le champ **Compte de reconnaissance**, sélectionnez le compte de reconnaissance.
6. Si le champ **Méthode de comptabilisation des reports** est défini sur **Résultat**, sélectionnez le compte de revenu initial dans le champ **Compte de revenu initial** et le compte de contrepartie du résultat dans le champ **Compte de contrepartie du résultat**.
7. Sélectionnez le modèle linéaire dans le champ **Modèle linéaire** ou le modèle basé sur les événements dans le champ **Modèle basé sur les événements**.
8. Cliquez sur **Enregistrer**.

### <a name="for-free-text-invoices"></a>Pour les factures financières

Pour spécifier les valeurs par défaut de report pour les factures financières, procédez comme suit.

1. Sélectionnez l’onglet **Facture financière**.
2. Pour un report, sélectionnez **Ajouter** pour ajouter une ligne.
3. Spécifiez comment le code de compte est appliqué :

    * Si le champ **Code de compte** est défini sur **Table** ou **Groupe**, sélectionnez la relation de compte dans le champ **Relation de compte**.
    * Si le champ **Code de compte** est défini sur **Tout**, le code de compte s’applique à tous les enregistrements applicables.

4. Dans le champ **Compte de report**, sélectionnez le compte de report.
5. Si le champ **Méthode de report à court terme** est défini sur **Périodes glissantes** ou **Année fixe**, sélectionnez le compte de report à court terme dans le champ **Compte de report à court terme**.
6. Dans le champ **Compte de reconnaissance**, sélectionnez le compte de reconnaissance.
7. Si le champ **Méthode de comptabilisation des reports** est défini sur **Résultat**, sélectionnez le compte de revenu initial dans le champ **Compte de revenu initial** et le compte de contrepartie du résultat dans le champ **Compte de contrepartie du résultat**.
8. Sélectionnez le modèle linéaire dans le champ **Modèle linéaire** ou le modèle basé sur les événements dans le champ **Modèle basé sur les événements**.
9. Cliquez sur **Enregistrer**.

### <a name="for-invoice-journals"></a>Pour les journaux des factures

Pour spécifier les valeurs par défaut de report pour les écritures du journal des factures, procédez comme suit.

1. Sélectionnez l’onglet **Journal des factures**.
2. Pour un report, sélectionnez **Ajouter** pour ajouter une ligne.
3. Spécifiez comment le code de compte est appliqué :

    * Si le champ **Code de compte** est défini sur **Table** ou **Groupe**, sélectionnez la relation de compte dans le champ **Relation de compte**.
    * Si le champ **Code de compte** est défini sur **Tout**, le code de compte s’applique à tous les enregistrements applicables.

4. Dans le champ **Compte de report**, sélectionnez le compte de report.
5. Si le champ **Méthode de report à court terme** est défini sur **Périodes glissantes** ou **Année fixe**, sélectionnez le compte de report à court terme dans le champ **Compte de report à court terme**.
6. Dans le champ **Compte de reconnaissance**, sélectionnez le compte de reconnaissance.
7. Si le champ **Méthode de comptabilisation des reports** est défini sur **Résultat**, sélectionnez le compte de revenu initial dans le champ **Compte de revenu initial** et le compte de contrepartie du résultat dans le champ **Compte de contrepartie du résultat**.
8. Sélectionnez le modèle linéaire dans le champ **Modèle linéaire** ou le modèle basé sur les événements dans le champ **Modèle basé sur les événements**.
9. Cliquez sur **Enregistrer**.

### <a name="items-that-are-deferred-by-default"></a>Articles reportés par défaut

Utilisez la page **Articles reportés par défaut** pour définir quels articles sont reportés par défaut. Vous pouvez configurer les types de transactions pour lesquelles les articles seront reportés. Vous pouvez spécifier si un seul article est reporté, ou un groupe ou une catégorie d’articles entiers.

Lorsque vous configurez des articles comme reportés, sélectionnez les comptes et les modèles par défaut sur la page **Valeurs par défaut de report**. Si les comptes et les modèles ne sont pas sélectionnés, les lignes de transaction où ces articles sont saisis ne seront pas reportées.

Pour les articles reportés en fonction de la catégorie de vente ou d’achat à laquelle ils sont associés, les paramètres de report sont basés sur la catégorie. Toutefois, si la catégorie n’est pas sélectionnée dans le champ **Relation de catégorie**, les paramètres de report de la catégorie dont le rang est le plus élevé sont utilisés. Par exemple, vous ajoutez une catégorie de vente **Vidéo domestique** mais pas de catégorie de vente **Télévision**. Lorsque vous ajoutez un article de report associé à la catégorie **Télévision**, les paramètres de report de la catégorie **Vidéo domestique** sont utilisés pour l’article.

### <a name="set-up-deferred-items"></a>Configurer des articles reportés

Pour configurer les articles différés par défaut, procédez comme suit.

1. Sur la page **Articles reportés par défaut**, sélectionnez l’onglet souhaité : **Commande client** ou **Achat**.
2. Sélectionnez **Ajouter** pour ajouter une ligne.
3. Dans le champ **Code article**, sélectionnez le code article.
4. Spécifiez comment le code article est appliqué :

    * Si le champ **Code article** est défini sur **Groupe** ou **Table**, sélectionnez la relation d’article dans le champ **Relation d’article**.
    * Si le champ **Code article** est défini sur **Catégorie**, sélectionnez la relation de catégorie dans le champ **Relation de catégorie**.

5. Répétez les étapes 2 à 4 pour chaque ligne supplémentaire nécessaire.
6. Cliquez sur **Enregistrer**.

## <a name="deferred-charges"></a>Frais reportés

Utilisez la page **Frais reportés** pour définir quels frais sont reportés par défaut.

> [!NOTE]
> * Actuellement, les frais reportables ne sont disponibles que pour les commandes client.
> * Les frais ne peuvent être reportés qu’au niveau de la ligne. Pour reporter des frais au niveau de l’en-tête de la commande client, vous pouvez paramétrer les frais en tant qu’article reporté sur une ligne distincte de la commande client.
> * Pour reporter des frais pour une facture financière, vous devez saisir les frais sur une ligne de facture reportée distincte.
> * Cette fonctionnalité n’est pas disponible pour les frais d’assistance et la fonctionnalité de répartition des revenus.

### <a name="set-up-deferred-charges"></a>Configuration des frais reportés

Pour paramétrer les frais reportés, procédez comme suit.

1. Sur la page **Frais reportés**, sélectionnez **Ajouter** pour ajouter une ligne.
2. Dans le champ **Code frais**, sélectionnez le code frais.
3. Dans le champ **Relation des frais**, sélectionnez la relation des frais.
4. Répétez les étapes 1 à 3 pour chaque ligne supplémentaire nécessaire.
5. Cliquez sur **Enregistrer**.

## <a name="event-based-deferral-templates"></a>Modèles de report basés sur les événements

Utilisez la page **Modèles de report basés sur des événements** pour définir des modèles de report basés sur des événements que vous pouvez utiliser dans les transactions de report et attribuer sur la page **Valeurs par défaut de report**.

### <a name="create-an-event-based-template"></a>Créer un modèle basé sur des événements

Pour créer un modèle de report basé sur des événements, procédez comme suit.

1. Sur la page **Modèles de report basés sur des événements**, sélectionnez **Nouveau**.
2. Dans le champ **Modèle**, entrez un nom unique pour le modèle.
3. Entrez une description dans le champ **Description**.
4. Dans le champ **Type de répartition**, sélectionnez le type de répartition :

    * **Montant variable** : alloue un montant spécifique pour chaque ligne saisie.
    * **Montant égal** : alloue le même montant pour chaque ligne saisie. 
    * **Pourcentage** : alloue un montant basé sur la valeur de pourcentage saisie pour chaque ligne.
    * **Pourcentage d’achèvement** : alloue une valeur d’achèvement cumulée pour chaque ligne saisie.
    * **Quantité variable** : alloue une quantité spécifique pour chaque ligne saisie.

5. Définissez l’option **Créer des événements séparés par unité** sur **Oui** si vous souhaitez que chaque ligne d’événement soit répartie de manière égale selon le nombre d’unités sur la transaction de la facture. Définissez-la sur **Non** si vous ne souhaitez pas fractionner les lignes d’événement.
6. Dans le champ **Compte d’expiration**, sélectionnez le compte d’expiration.
7. Sélectionnez **Ajouter** pour ajouter une ligne en haut de la liste des lignes, ou sélectionnez **Ajouter à la fin** pour ajouter une ligne en bas de la liste.
8. Dans le champ **Description**, entrez la description de l’événement.
9. Si le champ **Type de répartition** est défini sur **Pourcentage**, spécifiez le pourcentage dans le champ **Pourcentage de répartition**. Le pourcentage doit être un nombre compris entre 0 (zéro) et 100. Si vous laissez vide le champ **Pourcentage de répartition**, le pourcentage est considéré comme 0. La somme de tous les pourcentages s’affiche dans le champ **Pourcentage total** au bas de la page et elle doit être égale à 100.
10. Dans le champ **Mois jusqu’à l’expiration**, spécifiez le nombre de mois pendant lesquels l’événement est valide. La date d’expiration du report de transaction est automatiquement saisie en fonction de cette valeur.
11. Cochez la case **Reconnaître lors de la validation** pour comptabiliser automatiquement le revenu lorsque la transaction est validée. Si vous laissez la case décochée, le revenu doit être reconnu manuellement.
12. Dans le champ **Compte de reconnaissance**, sélectionnez le compte de reconnaissance pour l’événement, si l’événement utilise un compte différent de l’ensemble de l’échéancier de report. Ce champ est utilisé avec la case à cocher **Reconnaître lors de la validation**.
13. Répétez les étapes 7 à 12 pour chaque ligne supplémentaire nécessaire.
14. Cliquez sur **Enregistrer**.
