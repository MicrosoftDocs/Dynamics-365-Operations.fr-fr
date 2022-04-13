---
title: Créer des échéanciers de facturation
description: Cette rubrique explique comment créer, supprimer et modifier des calendriers de facturation.
author: JodiChristiansen
ms.date: 02/09/2022
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
ms.openlocfilehash: 2c4e3c0edadd00fd3a3f2ae9968248a226147996
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462585"
---
# <a name="create-billing-schedules"></a>Créer des échéanciers de facturation

[!include [banner](../includes/banner.md)]

Sur la page **Calendrier de facturation**, vous pouvez créer, supprimer ou modifier des calendriers de facturation. Vous pouvez également consulter la liste des calendriers de facturation. Lorsque vous créez un calendrier de facturation, ses valeurs par défaut sont déterminées par le groupe de facturation qui lui est associé. Des informations complémentaires sont mises en place sur la page **Paramètres de facturation des contrats récurrents**.

## <a name="create-a-billing-schedule"></a>Créer un calendrier de facturation

Pour créer un calendrier de facturation, procédez comme suit :

1. Dans la page **Calendrier de facturationprogramme**, sélectionnez **Nouveau**.
2. Dans la boîte de dialogue **Créer un calendrier de facturation**, dans le champ **Groupe d’échéancier de facturation**, sélectionnez un groupe d’échéanciers de facturation.
3. Dans le champ **Compte client**, sélectionnez un compte client.
4. Dans le champ **Date de début**, sélectionnez la date de début, puis dans le champ **Nombre de périodes**, entrez le nombre de périodes. Le champ **Date de fin** est mis à jour en fonction du nombre de périodes que vous saisissez. Si vous mettez à jour le champ **Date de fin de facturation**, le champ **Nombre de périodes** est mis à jour pour **0** (zéro).
5. Cliquez sur **OK**.
6. Sur la page **Calendrier de facturation**, dans l’onglet **Général**, dans le champ **Description**, entrez une description du calendrier de facturation.
7. Dans le champ **Modèle de jalon**, sélectionnez un modèle de jalon pour **Facturation d’étape**.

Des domaines tels que **Compte de facturation** et **Code de devise** sont mis à jour avec les informations du client.

Les champs **Fréquence de facturation** et **Intervalle de facturation** sont automatiquement définis, en fonction du groupe d’échéanciers de facturation sélectionné.

8. Pour créer des factures séparées, définissez l’option **Facturer séparément** sur **Oui**.
9. Pour renouveler automatiquement un calendrier de facturation après la dernière période de facturation, définissez l’option **Renouveler automatiquement** sur **Oui**, puis définissez le champ **Lignes à ajouter par renouvellement**.

Les champs **Paramètres** sont automatiquement définis, en fonction des valeurs de la page **Paramètres de facturation des contrats récurrents**.

10. Pour répartir au prorata le montant d’un échéancier de facturation, définissez l’option **Prorata des périodes partielles** sur **Oui**.
11. Pour aligner les lignes de détail de l’échéancier de facturation sur la fin d’un mois, définissez l’option **Aligner sur le mois** sur **Oui**.
12. Dans les champs **Date de début du contrat** et **Date de fin du contrat**, saisissez les dates de début et de fin du contrat. Ces dates sont à titre indicatif uniquement.

Le champ **Paiement** affiche les informations de paiement client du client. Lorsqu’un élément de campagne est en attente ou résilié, les informations de paiement ne peuvent pas être modifiées.

> [!NOTE]
> Lorsque vous consolidez des factures par poste, la valeur des champs **Modalités de paiement**, **Méthode** et **Calendrier de facturation** doivent correspondre. Sinon, les factures ne peuvent pas être consolidées.

13. Dans l’onglet **Adresse**, vous pouvez consulter et mettre à jour les champs **Adresse de livraison** et **Facturer à l’adresse**.
14. Dans l’onglet **Informations de contact**, vous pouvez associer un compte d’utilisateur final au calendrier de facturation.
15. Dans les champs **Informations de contact**, vous pouvez saisir un contact, une adresse e-mail et une adresse Internet.
16. Pour suivre les informations sur les commissions des partenaires, définissez les champs **Compte partenaire** et **Taux de commission du partenaire**. Ces champs sont à titre indicatif uniquement.
17. Dans l’onglet **Total**, vous pouvez voir les différents totaux qui ont été calculés pour le calendrier de facturation.
18. Dans l’onglet **En attente**, vous pouvez afficher des informations d’audit sur le moment où le calendrier de facturation a été mis en attente lorsque la suspension a été supprimée.
19. Dans l’onglet **Résiliation**, vous pouvez afficher un historique des résiliations qui ont été appliquées ou supprimées du calendrier de facturation.
20. Cliquez sur **Enregistrer**.
21. Dans l’organisateur **Lignes de calendrie de facturation**, sélectionnez **Ajouter une ligne**.
22. Dans le champ **Numéro d’article**, sélectionnez le numéro d’article. Si l’article ajouté est un article parent dans une répartition des revenus, les lignes sont automatiquement mises à jour avec les articles enfants. Vous ne pouvez modifier que l’élément parent dans une répartition des revenus. Tous les éléments enfants sont ensuite mis à jour en conséquence.
23. Dans le champ **Type d’article**, sélectionnez le type d’article.
24. Mettez à jour les dates de début et de fin.
25. Avant la création des factures, vous pouvez modifier la fréquence de facturation en mettant à jour le champ **Fréquence de facturation**. Une fois la première facture du calendrier de facturation créée, la fréquence de facturation ne peut plus être modifiée.
26. Dans le champ **Unité**, sélectionnez l’unité de mesure pour l’article.
27. Dans le champ **Méthode de tarification**, sélectionnez la méthode de tarification pour l’article.

Le champ **Prix unitaire** est automatiquement défini à partir de l’inventaire. Cependant, vous pouvez le mettre à jour si vous modifiez la méthode de tarification sur **Fixe**.

## <a name="remove-a-line-item"></a>Supprimer une ligne

Pour supprimer un élément d’un calendrier de facturation, procédez comme suit.

1. Sur la page **Calendrier de facturation**, dans le champ **Numéro d’horaire**, sélectionnez le numéro de l’échéancier de facturation à modifier.
2. Sur la raccourci **Lignes d’échéancier de facturation**, sélectionnez la ligne à supprimer, puis sélectionnez **Supprimer**.
3. Cliquez sur **Enregistrer**.

Le reste de cette rubrique décrit les actions et les détails disponibles pour les lignes du raccourci **Lignes d’échéancier de facturation**.

## <a name="billing-schedule-line-actions"></a>Actions sur les échéances de facturation

Les boutons via le raccourci **Lignes d’échéancier de facturation** vous permet d’appliquer des actions à des lignes individuelles.

| Bouton | Description |
|--------|-------------|
| Ajouter la ligne | Ajouter une ligne au calendrier de facturation. |
| Ajouter à partir de la liste d’articles | Ajoutez plusieurs éléments à un calendrier de facturation en les sélectionnant dans une liste. |
| Exécute la suppression | <p>Permet de supprimer la ligne sélectionnée du calendrier de facturation.</p><p>Pour les éléments faisant partie d’une répartition des revenus, vous ne pouvez supprimer que l’élément parent. Tous les éléments enfants associés sont alors automatiquement supprimés.</p> |
| Afficher les détails de facturation | Afficher les détails de la facturation. |
| Terminer | <p>Terminer les lignes sélectionnées. Ce bouton est disponible uniquement lorsque les lignes sélectionnées ont un statut **Actif**.</p><p>Pour les éléments faisant partie d’une répartition des revenus, vous ne pouvez résilier que l’élément parent.</p> |
| Supprimer la résiliation | <p>Supprimez la résiliation des lignes sélectionnées. Ce bouton est disponible uniquement lorsque les lignes sélectionnées ont un statut **Résilié**.</p><p>Pour les éléments faisant partie d’une répartition des revenus, vous ne pouvez supprimer la résiliation que de l’élément parent.</p> |
| Mettre en attente | <p>Sélectionnez les détails pour mettre la ligne sélectionnée en attente.</p><p>Pour les éléments faisant partie d’une répartition des revenus, vous ne pouvez mettre que l’élément parent en attente.</p> |
| Supprimer la retenue | <p>Supprimez la suspension de la ligne sélectionnée.</p><p>Pour les éléments faisant partie d’une répartition des revenus, vous ne pouvez supprimer la retenue que de l’élément parent.</p> |
| Réaffectation et rabais | Ce bouton n’est pas disponible pour les éléments faisant partie d’une répartition des revenus, à l’exception des éléments parents pour lesquels la répartition des revenus utilise le mode d’attribution **Montant nul**. |
| Reports | <p>Entrez les options de report pour la ligne sélectionnée.</p><p>Ce bouton n’est pas disponible pour les articles parents dans une répartition des revenus.</p> |
| Répartition des jalons | <p>Examinez et mettez à jour les informations d’allocation des jalons pour la ligne sélectionnée.</p><p>Ce bouton est disponible uniquement lorsque l’élément de ligne de l’échéancier de facturation est un élément jalon.</p> |
| Support et renouvellement | <p>Vérifiez et mettez à jour les informations de support et de renouvellement pour la ligne sélectionnée.</p><p>Ce bouton est disponible uniquement lorsque l’élément de ligne de l’échéancier de facturation est un élément de support ou de renouvellement.</p> |
| Afficher les dimensions | Afficher ou masquer les colonnes de dimension qui apparaissent dans la grille **Lignes d’échéancier de facturation**. |
| Calculer le prix unitaire | <p>Calculez le prix unitaire de l’article, afin que le client puisse payer le montant du contrat en plusieurs versements (par exemple, quotidiennement, mensuellement, trimestriellement, semestriellement ou annuellement). Vous pouvez sélectionner le prix du contrat et la fréquence des prix.</p><p>Vous pouvez afficher une piste d’audit des modifications : l’ancien prix et la fréquence du contrat, le nouveau prix et la fréquence du contrat, l’utilisateur qui a effectué la modification, ainsi que la date et l’heure de la modification.</p> |
| Date d’alignement | <p>Spécifiez la date d’alignement pour les éléments de renouvellement.</p><p>Si vous sélectionnez un groupe d’articles dans le champ **Groupe d’articles**, tous les articles utilisent la date d’alignement du premier article du groupe d’articles dans le calendrier de facturation. Si le champ **Groupe d’articles** est vide, vous pouvez spécifier une date d’alignement à utiliser pour tous les éléments.</p><p>Ce bouton n’est disponible que si le champ **Fréquence de facturation** est défini sur **Annuelle**.</p> |
| Produit non facturé | <p>Configurez l’élément pour qu’il utilise la fonctionnalité de revenus non facturés. Vous pouvez ensuite spécifier les comptes de revenus non facturés et de remises non facturées pour l’article.</p><p>Ce bouton n’est disponible que pour les éléments dont le champ **Type d’élément** est défini sur **Standard**. Il n’est pas disponible pour les calendriers de facturation existants ou pour les lignes de calendrier de facturation où la facture a déjà été créée.</p> |
| Ajouter un enfant de répartition des revenus | <p>Sélectionnez un article enfant à ajouter à la commande client.</p><p>Ce bouton n’est disponible que pour les articles parents dans une répartition des revenus.</p> |
| Options de tarification avancées | Modifiez les options de tarification d’un article. |

## <a name="billing-schedule-line-details"></a>Détails sur les échéances de facturation

Lorsque vous sélectionnez une ligne via le raccourci **Lignes d’échéancier de facturation**, vous pouvez afficher des détails spécifiques pour cette ligne. Ces détails sont répartis entre différents onglets.

### <a name="general-tab"></a>Onglet Général

Les informations suivantes sont disponibles dans l’onglet **Général**.

| Champ ou section | Description |
|------------------|-------------|
| Utilisation | <p>Cette section fournit des informations sur les éléments d’utilisation. Elle contient les champs suivants :</p><ul><li>**Identifiant d’utilisation** – L’identifiant du compteur ou de l’article d’utilisation.</li><li>**Option de lecture** – L’option de lecture d’utilisation : **Lecture** ou **Consommation**.</li><li>**Consommation estimée** – Spécifiez la consommation estimée pour un élément d’utilisation qui a des périodes où la facture n’a pas été créée. Sur la page **Détails de facturation**, vous pouvez consulter les lignes de détails de facturation pour la consommation estimée.</li></ul> |
| Références externes\* | Cette rubrique contient les champs **Externe** et **Numéro de ligne**, où vous pouvez spécifier des informations de référence externes. |
| Jalon | <p>Cette section fournit des informations sur les éléments de jalon. Il contient le champ **Date d’achèvement estimée**, qui affiche la date d’achèvement de l’élément.</li></ul> |
| Texte | Commentaire de la ligne. Le texte est traduit dans la langue par défaut du client ou de l’entité juridique. |
| Groupe d’articles | Groupe d’articles pour l’article de ligne. |
| Date d’alignement | La date d’alignement pour le calendrier de facturation. |

\* Lorsque vous consolidez des factures par poste sur la page **Générer une facture**, les champs **Référence externe** doivent correspondre. Si même un caractère est différent, les articles ne seront pas regroupés sur la facture. Aucun contrôle de validation n’est effectué sur l’un ou l’autre des champs de la section **Référence externe**, et la valeur dans le champ **Numéro de ligne** doit être un entier positif.

### <a name="address-tab"></a>Onglet Adresse

Les informations suivantes sont disponibles dans l’onglet **Adresse**.

| Champ | Description |
|-------|-------------|
| Adresse de livraison | <p>Sélectionnez l’adresse de livraison de l’article de ligne. L’adresse de livraison par défaut est l’adresse de livraison principale du raccourci **Adresse**.</p><p>Lorsque vous modifiez l’adresse, vous pouvez sélectionner les options d’adresse suivantes :</p><ul><li>**Adresses** – Sélectionnez une adresse pour le client actuel.</li><li>**Utilisé** – Sélectionnez une adresse actuellement utilisée pour le client actuel.</li><li>**Autre adresse** – Sélectionnez une adresse pour n’importe quel enregistrement client.</li></ul><p>Pour les articles qui utilisent le fractionnement des revenus, seule l’adresse de l’article parent peut être modifiée. L’adresse des éléments enfants correspond à l’adresse du parent et ne peut pas être modifiée séparément.</p> |
| Adresse de facturation | <p>Sélectionnez l’adresse de facturation de l’article de ligne. L’adresse de livraison par défaut est l’adresse de livraison principale du raccourci **Adresse**. Vous pouvez modifier l’adresse selon vos besoins, en fonction de l’objectif des adresses disponibles :</p><ul><li>Si aucune des adresses n’a pour but de **Facturer**, l’adresse de facturation par défaut est l’adresse principale du client, quel que soit le but.</li><li>Si une ou plusieurs des adresses ont pour but de **Facturer**, l’adresse de facturation par défaut est l’adresse qui a été saisie en dernier.</li><li>Si une ou plusieurs des adresses ont pour but de **Facturer**, et que l’une des adresses de facturation est définie comme adresse principale, l’adresse de facturation par défaut est l’adresse qui a pour but de **Facturer** et est définie comme adresse principale.</li><li>Pour les articles qui utilisent le fractionnement des revenus, seule l’adresse de l’article parent peut être modifiée. L’adresse des éléments enfants correspond à l’adresse du parent et ne peut pas être modifiée séparément.</li></ul> |

### <a name="product-tab"></a>Onglet Produit

Les informations suivantes sont disponibles dans l’onglet **Produit**.

| Champ ou section | Description |
|------------------|-------------|
| Dimensions de stockage | <p>Cette section affiche les informations de stockage de l’élément. Il contient le champ **Numéro de série**, qui affiche le numéro de série de l’article.</p><p>Le numéro de série est copié à partir de la commande client initiale au cours du processus de support et de renouvellement. Pour les articles qui utilisent le fractionnement des revenus, le numéro de série de l’article parent est copié sur tous les articles enfants. Le numéro de série est copié lorsque l’option **Copier le numéro de série** est définie sur **Oui** sur la page **Paramètres de facturation des contrats récurrents**.</li></ul> |
| Dimensions de produit | Les détails du produit pour l’article et les valeurs sont automatiquement mis à jour, en fonction de la valeur **Numéro de variante** sélectionnée pour la ligne d’échéancier de facturation. |

### <a name="account-tab"></a>Onglet Compte

Les informations suivantes sont disponibles dans l’onglet **Compte**.

| Champ | Description |
|-------|-------------|
| Compte principal | Le compte principal qui est créé sur la ligne de vente. La valeur par défaut provient de la commande client. Ce champ peut être vide. |
| Dimensions financières des articles | <p>Les valeurs de dimension financière par défaut, basées sur l’enregistrement du client et de l’article.</p><p>Pour les articles qui utilisent le fractionnement des revenus, les articles enfants utilisent les valeurs de dimension financière des enregistrements de client et d’article, comme décrit précédemment. Si vous devez mettre à jour les valeurs de dimension financière des éléments enfants, vous pouvez importer l’entité de données.</p> |

### <a name="renewals-tab"></a>Onglet Renouvellements

Les informations suivantes sont disponibles dans l’onglet **Renouvellements**.

| Champ | Description |
|-------|-------------|
| Renouveler automatiquement | <p>Une valeur qui indique si la ligne d’échéancier de facturation est automatiquement renouvelée pour la prochaine période de facturation :</p><ul><li>**Oui** – La ligne d’échéancier de facturation est automatiquement renouvelée pour la prochaine période de facturation lorsque vous créez une facture.</li><li>**Non** – La ligne d’échéancier de facturation n’est pas renouvelée automatiquement. Vous devez renouveler manuellement le calendrier de facturation.</li></ul> |
| Lignes à ajouter par renouvellement | Le nombre de lignes à ajouter à un renouvellement d’échéancier de facturation. |

De plus, les boutons suivants sont disponibles dans l’onglet **Renouvellements**.

| Bouton | Description |
|--------|-------------|
| Audit d’entrée de journal du produit non facturé | Affichez toutes les modifications pour les articles qui utilisent la fonctionnalité de revenus non facturés. |
| Ajouter une période de renouvellement | Ajoutez une durée de renouvellement pour l’élément. La date de début de la nouvelle période de renouvellement est la date qui suit la date de fin de la période précédente. Les champs **Date de fin de renouvellement**, **Date de début du report**, **Date de fin du report**, **Quantité d’articles** et **Prix unitaire** peuvent être mis à jour. |
| Modifier la durée de renouvellement | <p>Modifier une durée de renouvellement. Pour la durée initiale, vous pouvez modifier les dates de début et de fin du report avant la création de l’écriture au journal initiale. Pour les trimestres suivants, la date de début ne peut pas être modifiée. C’est toujours la prochaine date après la fin du mandat précédent.</p><p>Si un terme de renouvellement existe après le terme que vous modifiez, les dates du terme ne peuvent pas être modifiées. Dans ce cas, seuls les champs **Quantité** et **Prix unitaire** de l’élément de renouvellement peuvent être mis à jour.</p><p>Par exemple, trois termes existent. <ul><li>Le premier trimestre ne peut pas être modifié car il a déjà commencé.</li><li>Pour le deuxième terme, seuls la quantité et le prix unitaire peuvent être modifiés.</li><li>Pour le troisième terme, toutes les valeurs à l’exception de la date de début peuvent être modifiées. De plus, l’option **Horaire à partir d’un modèle** vous permet de créer un calendrier de report basé sur le modèle de l’élément de revenu non facturé. Lorsque cette option est définie sur **Oui**, sélectionnez le modèle de report dans le champ **Modèle** et modifiez les dates de début et de fin du report selon vos besoins. Les conditions de renouvellement ultérieures utilisent le même modèle de report. Cependant, le modèle de report peut être modifié.</p></li></ul> |

### <a name="termination-tab"></a>Onglet Résiliation

Les informations suivantes sont disponibles dans l’onglet **Résiliation**.

| Champ | Description |
|-------|-------------|
| Date de fin de contrat | La date à laquelle la ligne d’échéancier de facturation est résiliée. La valeur par défaut provient du champ **Date de résiliation** dans l’en-tête. Vous pouvez modifier la valeur comme vous le voulez. |
| Type de résiliation | Type de résiliation. La valeur par défaut provient du champ **Type de résiliation** dans l’en-tête. |

### <a name="hold-tab"></a>Onglet En attente

Si des reports de revenus et de dépenses sont utilisés, l’onglet **En attente** affiche la date de report.

### <a name="escalation-and-discount-tab"></a>Onglet Escalade et remise

Les informations suivantes sont disponibles dans l’onglet **Escalade et remise**.

| Champ | Description |
|-------|-------------|
| Escalade | <p>Sélectionnez si les escalades sont autorisées pour la ligne d’échéancier de facturation. Toute ligne d’escalade de l’en-tête est appliquée lors de la création de la ligne d’échéancier de facturation.</p><ul><li>**Oui** – Aucune escalade ne peut être appliquée à la ligne. Lorsque cette option est sélectionnée, vous pouvez configurer les escalades pour les lignes d’échéancier de facturation sur la page **Escalade et remise**.</li><li>**Non** – Aucune escalade ne peut être appliquée à la ligne.</li></ul><p>Le réglage par défaut est basé sur le **Groupe d’échéanciers de facturation** choisi.</p> |

### <a name="price-changes-tab"></a>Onglet Changements de prix

Pour les lignes qui sont modifiées du prix **Standard** au prix **Fixe**, la grille sur l’onglet **Changements de prix** comprend les colonnes suivantes :

- Modifier la date
- Modifié par l’utilisateur
- Prix standard
- Prix fixe
- Mise à jour des prix
