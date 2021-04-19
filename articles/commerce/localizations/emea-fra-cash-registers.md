---
title: Fonctionnalité de caisse enregistreuse pour la France
description: Cette rubrique fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la France. Elle fournit également des instructions pour paramétrer la fonctionnalité.
author: EvgenyPopovMBS
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: France
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-2-28
ms.dyn365.ops.version: 7.3.2
ms.openlocfilehash: bb92dd807dcd4d58994ffe14b2e3988cbafea46f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798811"
---
# <a name="cash-register-functionality-for-france"></a>Fonctionnalité de caisse enregistreuse pour la France

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la France dans Dynamics 365 Commerce. Elle fournit également des instructions pour paramétrer la fonctionnalité.

Cette fonctionnalité contient les parties suivantes :

- Les fonctionnalités de point de vente (PDV) courantes disponibles pour les clients de tous les pays ou régions. Les exemples comprennent une option d’enregistrement des différents événements dans le journal d’audit du PDV.
- Des fonctionnalités spécifiques pour la France, telles que les signatures numériques pour les transactions de vente.

## <a name="overview"></a>Vue d’ensemble

### <a name="common-pos-features"></a>Fonctionnalités de PDV courantes

Pour connaître les fonctionnalités de PDV disponibles pour les clients dans tous les pays ou régions, voir [Page d’accueil de Commerce](../index.md).

Les fonctionnalités de localisation PDV suivantes disponibles pour les clients de tous les pays ou régions peuvent désormais être utilisées spécifiquement pour la France :

- **Enregistrer des événements supplémentaires dans le journal d’événements d’audit du PDV.** Si l’option **Audit** dans le profil de fonctionnalité du PDV est définie sur **Oui**, les événements suivants sont enregistrés dans le journal d’événements d’audit du PDV :

    - Connexion
    - Déconnexion
    - Impression d’une copie d’un ticket de caisse
    - Démarrage du mode hors ligne
    - Fin du mode hors ligne
    - Nettoyage des transactions de la base de données des canaux

### <a name="france-specific-pos-features"></a>Fonctionnalités du PDV spécifiques à la France

Les fonctionnalités du PDV spécifiques à la France sont activées lorsque le champ **Code ISO** dans le profil de fonctionnalité du PDV est défini sur **FR**.

#### <a name="digital-signing-overview"></a>Présentation de la signature numérique

Les types de données suivants (transactions et événements) sont signés numériquement dans le PDV :

- Transactions de vente
- Copies des tickets de caisse
- États des équipes clôturées/Z
- Événements d’audit

La signature est créée puis enregistrée dans la base de données des canaux lorsque la transaction est finalisée ou que l’événement est enregistré. Les données signées sont une chaîne de texte composée de plusieurs champs de données. Ces champs varient en fonction du type de données. Le processus général de signature inclut les étapes suivantes :

1. Selon le type de données, sélectionnez le prochain numéro séquentiel à des fins de signature.
2. Extrayez les champs de données qui doivent être signés de l’enregistrement qui est signé.
3. Créez une chaîne composée d’une liste séparée par des virgules des champs de données.
4. Ajoutez la signature précédente pour le même type de données.
5. Calculez un code de hachage de la chaîne à l’aide de l’algorithme SHA-x.
6. Chiffrez la chaîne obtenue à l’aide d’un certificat numérique.
7. Effectuez la transformation base64url pour la chaîne obtenue.
8. Stockez la chaîne utilisée pour signer, le numéro séquentiel, la signature, et l’empreinte du certificat dans un enregistrement de réponse fiscal lié à la transaction ou à l’événement.
9. Transférez la réponse fiscale au système ERP (enterprise resource planning) dans Siège, avec la transaction ou l’événement.

#### <a name="digital-signing-of-sales-transactions"></a>Signature numérique des transactions de vente

Seules les transactions pour les ventes en espèces sont signées. Voici quelques exemples de transactions exclues du processus de signature :

- Acomptes (dépôts sur comptes client)
- Devis
- Acomptes pour les commandes client (dépôts sur commandes client)
- Émission d’une carte cadeau et ajout de fonds à une carte cadeau
- Transactions hors ventes (entrée de fond de caisse, vidage de caisse, etc.)

Les données signées pour une transaction de vente sont une chaîne de texte composée des champs de données suivants :

1. Montant total des lignes de vente. Le montant inclut la taxe par taux de taxe.
2. Montant total des ventes. Le montant inclue la taxe.
3. Date et heure de la transaction, au format AAAAMMJJHHMMSS.
4. Numéro de caisse enregistreuse.
5. Numéro séquentiel de la transaction de vente signée.
6. Type de la transaction de vente.
7. Valeur (O/N) qui indique si la transaction est la première transaction de vente signée pour la caisse enregistreuse.
8. La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour la première transaction de vente signée.

Vous pouvez afficher la signature de transaction, avec les données de transaction utilisées pour la générer, sous le raccourci **Transactions fiscales** de la page **Transactions de magasin** dans Siège.

#### <a name="digital-signing-of-receipt-copies"></a>Signature numérique des copies de tickets de caisse

Lorsqu’une copie d’un ticket de caisse est imprimée, l’événement est enregistré dans le journal d’événements d’audit du PDV. Seuls les copies des tickets de caisse des transactions de vente signées sont signées. Les données signées pour un événement de copie de ticket de caisse sont une chaîne de texte composée des champs de données suivants :

1. Numéro de ticket de caisse de la transaction de vente originale.
2. Le type de transaction de la transaction de vente d’origine.
3. Numéro de copie de ticket de caisse pour cette transaction de vente.
4. ID de personnel de l’opérateur qui imprime la copie de ticket de caisse.
5. Date et heure de l’événement de copie de ticket de caisse, au format AAAAMMJJHHMMSS.
6. Numéro séquentiel de l’événement de copie de ticket de caisse signée.
7. Valeur (O/N) qui indique si la transaction est le premier événement de copie de ticket de caisse signée pour la caisse enregistreuse.
8. La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour le premier événement de copie de ticket de caisse signée.

Vous pouvez afficher la signature de la copie de ticket de caisse, avec les données d’événement utilisées pour la générer, sous l’onglet **Signature** de la page **Événements d’audit** dans Siège.

#### <a name="digital-signing-of-closed-shifts"></a>Signature numérique des équipes clôturées

Lorsqu’une équipe est clôturée, l’événement est enregistré dans le journal d’événements d’audit du PDV. Les données signées pour un événement de clôture d’équipe sont une chaîne de texte composée des champs de données suivants :

1. Montant total des ventes. Le montant inclut la taxe par taux de taxe.
2. Montant total des ventes. Le montant inclue la taxe.
3. Date et heure de l’événement de clôture d’équipe, au format AAAAMMJJHHMMSS.
4. Numéro séquentiel de l’événement de clôture d’équipe.
5. Valeur (O/N) qui indique si la transaction est le premier événement de clôture d’équipe signée pour la caisse enregistreuse.
6. La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour le premier événement de clôture d’équipe signée.

Vous pouvez afficher la signature d’une équipe de travail clôturée, avec les données d’équipe utilisées pour la générer, sous l’onglet **Signature** de la page **Équipes** dans Siège.

#### <a name="digital-signing-of-events"></a>Signature numérique des événements

Les données signées pour un événement autre qu’une copie de ticket de caisse ou de clôture d’équipe sont une chaîne de texte composée des champs de données suivants :

1. Numéro séquentiel de l’événement de l’événement signé.
2. Code d’événement prédéfini.
3. Description de l’événement.
4. Date et heure de l’événement.
5. ID du personnel de l’opérateur ayant déclenché l’événement.
6. Numéro de caisse enregistreuse.
7. Valeur (O/N) qui indique si la transaction est le premier événement signé pour la caisse enregistreuse.
8. La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour le premier événement signé.

Vous pouvez afficher la signature de l’événement, avec les données d’événement utilisées pour la générer, sous l’onglet **Signature** de la page **Événements d’audit** dans Siège.

#### <a name="receipts"></a>Réceptions

Les tickets de caisse pour la France peuvent inclure des informations supplémentaires implémentées à l’aide de champs personnalisés :

- **Type de transaction** – Vous pouvez ajouter un champ à une mise en page du format de ticket de caisse pour identifier le type de transaction. Par exemple, un ticket de caisse inclut le texte « Ventes ».
- **Numéro séquentiel de transaction de vente signée** – Un ticket de caisse peut inclure le numéro séquentiel d’une transaction de vente signée. Ce numéro est utilisé pour associer le ticket de caisse imprimé à une signature numérique dans la base de données.
- **Extraire de la signature numérique** – Un ticket de caisse peut inclure un extrait de la signature numérique. Cet extrait permet de confirmer que la transaction est signée. Il est composé d’une concaténation des troisième, septième, treizième et dix-neuvième symboles de la signature.
- **Réimprimer le numéro** – Un ticket de caisse d’origine ou une copie de ticket de caisse peut inclure le numéro de la copie du ticket de caisse. Pour un ticket de caisse d’origine, la valeur est **0** (zéro).
- **Nombre de lignes** – Un ticket de caisse peut inclure le nombre de lignes d’articles imprimées sur le ticket de caisse.
- **Totaux des ventes** – Les champs personnalisés des totaux de tickets de caisse excluent les montants hors ventes des montants de transaction totaux. Les montants hors ventes incluent les montants des opérations suivantes :

    - Acomptes (dépôts sur comptes client)
    - Acomptes pour les commandes client (dépôts sur commandes client)
    - Émission d’une carte cadeau
    - Ajout de fonds à une carte cadeau

- **Données de certification** – Un ticket de caisse peut inclure la catégorie et le numéro du certificat de conformité qu’un organisme autorisé a émis conformément aux exigences de certification de la norme NF 525.
- **Numéro de version** – Un ticket de caisse peut inclure le numéro de version du PDV.

#### <a name="restricting-the-duration-of-shifts"></a>Limitation de la durée des équipes

Il existe une option pour appliquer la clôture d’équipe quotidienne dans le PDV. Une équipe ne peut pas durer plus longtemps que la durée spécifiée dans le champ **Heure de clôture de l’équipe de travail**. Plusieurs minutes avant cette heure, l’opérateur commencera à recevoir des avertissements que l’équipe doit être clôturée. Le nombre de minutes est déterminé par la valeur du champ **Intervalle de clôture de l’équipe de travail (minutes)**.

#### <a name="x-and-z-reports"></a>États X et Z

Les informations qui sont incluses dans les états X et Z sont basées sur les besoins français :

- **Total des ventes** de l’équipe. Ces informations incluent les montants uniquement pour les transactions de ventes au comptant. Les acomptes et les opérations d’émission d’une carte cadeau sont exclues.
- **Total des retours** de l’équipe.
- **Total général cumulé**. Ce montant est calculé comme le montant total général cumulé de l’équipe précédente plus le montant total des ventes de cette équipe moins la valeur absolue du total des retours de cette équipe.
- **Total général perpétuel cumulé**. Ce montant est calculé comme le montant total général perpétuel cumulé de l’équipe précédente plus le montant total des ventes de cette équipe plus la valeur absolue du total des retours de cette équipe.
- Montants de taxe sur la valeur ajoutée (VAT) par taux de taxe.

Les totaux sont également stockés dans l’enregistrement de l’équipe clôturée et transférés dans Siège.

#### <a name="period-grand-total-journal"></a>Journal du total général de la période

Les journaux du total général de la période synthétisent les totaux des ventes par magasin et par période fiscale.

Les journaux du total général de la période sont tenus à jour sur la page **Journal du total général de la période**. Pour créer un journal, vous devez spécifier un magasin. Si des journaux précédent existent pour le magasin, la prochaine période fiscale après le dernier journal clôturé pour le magasin est automatiquement utilisée comme période de journal. Si aucun journal précédent n’existent, vous pouvez spécifier la date de fin du journal. Dans ce cas, la période fiscale qui inclut la date spécifiée est utilisée comme période de journal.

Le journal peut ensuite être calculé. Les équipes clôturées au cours de la période de journal sont sélectionnées, et les totaux sont calculés pour les équipes. Vous pouvez afficher les totaux de taxe du journal par code taxe. Vous pouvez également afficher les équipes qui sont incluses dans le journal.

Lorsque le journal est calculé, il peut être clôturé. Un journal clôturé ne peut pas être modifié, et un autre journal ne peut pas être créé pour une période précédente, la même période, ou une période les recoupant. Toutefois, le dernier journal clôturé pour un magasin peut être annulé. Dans ce cas, un autre journal peut être créé pour le même magasin et la même période.

Un journal clôturé est numériquement signé. Vous pouvez afficher la signature du journal, avec les données du journal utilisées pour la générer, sous l’onglet **Détails de la signature** de la page **Journal du total général de la période** dans Siège.

#### <a name="archive"></a>Archiver

Une archive est un fichier XML qui peut être exporté depuis un journal du total général de la période qui a été clôturé. Elle comprend les totaux de la période clôturée, et des données détaillées sur les transactions de vente et les événements. Le fichier exporté est numériquement signé, et la signature est contenue dans un fichier distinct.

Le format de l’archive est implémenté à l’aide de la [gestion des états électroniques (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).

## <a name="setting-up-commerce-for-france"></a>Configuration de Commerce pour la France

Cette section décrit les paramètres Commerce spécifiques et recommandés pour la France. Pour plus d’informations, voir [Page d’accueil de Commerce](../index.md).

Pour utiliser la fonctionnalité spécifique pour la France, vous devez effectuer les tâches suivantes :

- Définissez le champ **Pays/région** sur **FRA** (France) dans l’adresse principale de l’entité juridique.
- Définissez le champ **Code ISO** sur **FR** (France) dans le profil de fonctionnalité du PDV de chaque magasin situé en France.

Vous devez également spécifier les paramètres suivants pour la France. Notez que vous devez exécuter des tâches de distribution appropriées après que vous avez terminé le paramétrage.

### <a name="set-up-the-legal-entity"></a>Paramétrer l’entité juridique

Vous devez apporter les modifications suivantes dans la page **Entités juridiques**. Ces paramètres sont utilisés dans le format d’archive.

- Dans l’organisateur **Informations sur le compte en banque**, dans le champ **Numéro d’acheminement**, spécifiez l’identifiant TVA de l’organisation.
- Dans l’organisateur **Génération d’état statutaire**, dans le champ **Code NAF**, spécifiez le code NAF (Nomenclature des Activités Françaises) de l’organisation.
- Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, spécifiez le numéro de SIRET (Système d’identification du répertoire des établissements) de l’organisation.

### <a name="set-up-vat-per-french-requirements"></a>Paramétrer la TVA selon les exigences de la France


Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation de la taxe, voir [Vue d’ensemble des taxes](../../financials/general-ledger/indirect-taxes-overview.md).


Vous devez également spécifier des groupes de taxe et activer l’option **Prix, taxe incluse** pour les magasins situés en France.

### <a name="set-up-functionality-profiles"></a>Paramétrage des profils de fonctionnalité

Vous devez activer l’audit en définissant l’option **Audit** sur **Oui**.

Pour appliquer la clôture d’équipe quotidienne, vous devez apporter les modifications suivantes :

- Définissez l’option **Appliquer la clôture quotidienne de l’équipe de travail** sur **Oui**.
- Définissez les champs **Heure de clôture de l’équipe de travail** et **Intervalle de clôture de l’équipe de travail (minutes)**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Vous pouvez configurer les champs de texte en langue étrangère et personnalisés utilisés dans les formats de ticket de caisse du PDV. La société par défaut de l’utilisateur qui crée le paramétrage de ticket de caisse doit être la même entité juridique que celle dans laquelle le paramétrage du texte en langue étrangère est créé. Sinon, les mêmes textes en langue étrangère doivent être créés dans la société par défaut et l’entité juridique de l’utilisateur du magasin pour lequel le paramétrage est créé.

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins. Toutefois, les valeurs **ID texte** que vous utilisez doivent être uniques, elles doivent être égales ou supérieures à 900001.

| ID langue | ID texte | ID texte                   |
|-------------|---------|---------------------------|
| fr-FR       | 900001  | Type de transaction          |
| fr-FR       | 900002  | Numéro séquentiel         |
| fr-FR       | 900003  | Signature numérique         |
| fr-FR       | 900004  | Réimprimer le numéro            |
| fr-FR       | 900005  | Montant de la taxe de vente          |
| fr-FR       | 900006  | Total des ventes               |
| fr-FR       | 900007  | Taxe totale           |
| fr-FR       | 900008  | Total des ventes TTC |
| fr-FR       | 900009  | Numéro de création              |
| fr-FR       | 900010  | Catégorie de certification    |
| fr-FR       | 900011  | Numéro de certificat        |
| fr-FR       | 900012  | Nombre de lignes                |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** que vous avez spécifiées dans la page **Texte en langue étrangère**.

| Nom                  | Type    | ID texte de la légende |
|-----------------------|---------|-----------------|
| TRANSACTIONTYPE       | Ticket de caisse | 900001          |
| SEQUENTIALNUMBER      | Ticket de caisse | 900002          |
| DIGITALSIGNATURE      | Ticket de caisse | 900003          |
| REPRINTNUMBER         | Ticket de caisse | 900004          |
| SALESTAXAMOUNT        | Ticket de caisse | 900005          |
| SALESTOTAL            | Ticket de caisse | 900006          |
| SALESTOTALTAX         | Ticket de caisse | 900007          |
| SALESTOTALINCLUDETAX  | Ticket de caisse | 900008          |
| BUILDNUMBER           | Ticket de caisse | 900009          |
| CERTIFICATIONCATEGORY | Ticket de caisse | 900010          |
| CERTIFICATENUMBER     | Ticket de caisse | 900011          |
| LINECOUNT             | Ticket de caisse | 900012          |

### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour chaque format de ticket de caisse nécessaire, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer**.

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans les sections du ticket de caisse approprié. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente.

- **En-tête :** Ajoutez le champ suivant :

    - **Type de transaction** – Ce champ identifie le type de ticket de caisse.

- **Lignes :** Nous vous recommandons d’ajouter les champs standard suivants :

    - **Prix unitaire TTC**
    - **Prix total avec taxe**
    - **ID taxe**

- **Pied de page :** Ajoutez les champs suivants :

    - **Total des ventes** – Ce champ permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant est hors taxe. Les acomptes et les opérations de carte cadeau sont exclues.
    - **Taxe totale** – Ce champ permet d’imprimer le montant total des taxes des ventes de disponibilités. Les acomptes et les opérations de carte cadeau sont exclues. 
    - **Total des ventes TTC** – Ce champ permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant inclue la taxe. Les acomptes et les opérations de carte cadeau sont exclues.
    - **ID taxe** – Ce champ standard active une synthèse de taxe à imprimer par code taxe. Le champ doit être ajouté sur une nouvelle ligne.
    - **Montant de la taxe de vente** – Ce champ permet d’imprimer le montant des taxes des ventes de disponibilités par code de taxe. Les acomptes et les opérations de carte cadeau sont exclues. Le champ doit être ajouté à la même ligne que le champ **ID taxe**.
    - **Numéro séquentiel** – Ce champ imprimer le numéro séquentiel d’une transaction de vente signée.
    - **Signature numérique** – Ce champ imprime l’extraction de la signature numérique.
    - **Réimprimer le numéro** – Ce champ imprime le numéro d’une copie de ticket de caisse.
    - **Numéro de version** – Ce champ permet d’imprimer le numéro de version du PDV.
    - **Catégorie de certification** – Ce champ imprime la catégorie du certificat de conformité qu’un organisme autorisé a émis conformément aux exigences de certification de la norme NF 525.
    - **Numéro du certificat** – Ce champ imprime le numéro du certificat de conformité qu’un organisme autorisé a émis conformément aux exigences de certification de la norme NF 525.
    - **Nombre de lignes** – Ce champ imprime le nombre de lignes d’articles imprimées sur un ticket de caisse.
    - **Texte** – Ajouter un champ de texte et spécifie l’identifiant TVA de l’organisation.
    - **Texte** – Ajouter un champ de texte et spécifie le code NAF de l’organisation.
    - **Texte** – Ajouter un champ de texte et spécifie le numéro de SIRET de l’organisation.
    - **Nom du magasin** – Ce champ standard imprime le nom du magasin.
    - **Adresse du magasin** – Ce champ standard imprime l’adresse du magasin.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Configurer et concevoir les formats de tickets de caisse](../receipt-templates-printing.md).

### <a name="configure-the-digital-signature-parameters-for-headquarters"></a>Configurer les paramètres de signature numérique de Siège

Pour signer numériquement les journaux du total général de la période et les archives, vous devez définir des paramètres de signature numérique. La signature s’effectue à l’aide d’un certificat numérique enregistré dans le stockage Microsoft Azure KeyVault. Les étapes suivantes doivent être effectuées avant d’utiliser un certificat enregistré dans le stockage du coffre de clés :

- Le stockage du coffre de clés doit être créé. Il est recommandé de déployer le stockage dans la même zone géographique que l’Unité d’échelle commerciale.
- Le certificat doit être téléchargé vers le stockage du coffre de clés.
- L’application Serveur d’objets d’application (AOS) doit être autorisée pour lire les secrets du stockage du coffre de clés.

Pour plus d’informations sur l’utilisation du coffre de clés, voir [Prise en main d’Azure KeyVault](https://docs.microsoft.com/azure/key-vault/key-vault-get-started).

Puis, sur la page **Paramètres du coffre de clés**, vous devez spécifier les paramètres d’accès au stockage du coffre de clés :

- **Nom** et **Description** – Nom et description du stockage du coffre de clés.
- **URL du coffre de clés** – URL du stockage du coffre de clés.
- **Client du coffre de clés** – ID client interactif de l’application Azure Active Directory (Azure AD) associée au stockage du coffre de clés à des fins d’authentification. Ce client doit avoir accès en lecture aux secrets du stockage.
- **Clé secrète du coffre de clés** – Clé secrète associée à l’application Azure AD utilisée pour l’authentification dans le stockage du coffre de clés.
- **Nom**, **Description**, et **Référence secrète** – Nom, description, et référence secrète du certificat.

Enfin, dans la page **Paramètres Commerce**, vous devez spécifier les paramètres des signatures numériques :

- **Certificat** – Sélectionnez le certificat que vous avez configuré à l’étape précédente.
- **Fonction de hachage** – Spécifiez l’un des algorithmes de hachage cryptographique pris en charge par Microsoft .NET, tel que **SHA1**.
- **Encodage** – Spécifiez l’encodage des données signées, tel que **UTF-8**.

### <a name="configure-the-archive-export-format"></a>Configurez le format d’exportation d’archive

Vous pouvez charger la configuration ER pour l’archive de Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques](../../dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Vous devez télécharger les versions suivantes, ou les versions ultérieures, des configurations :

- Modèle données **Canal de vente au détail data.version.2**
- Mise en correspondance de modèle de données **Archivage DMM.version.2.3**
- Format **Archive de données Retail FR .version.2.5**

Après l’importation des configurations, dans la page **Paramètres Commerce**, sous l’onglet **Documents électroniques**, dans le champ **Format d’exportation de l’archive des données de vente au détail**, sélectionnez le format **Archive de données Retail FR .version.2.5**.

### <a name="renitialize-commerce-components"></a>Réinitialiser les composants Commerce

> [!NOTE]
> Vous ne devez effectuer les étapes de cette section que si vous mettez à jour un environnement existant.

Pour activer les événements d’audit, vous devez réinitialiser les énumérations Commerce Extensible. Pour activer la transmission de données spécifiques à la France du PDV au siège, vous devez réinitialiser le Planificateur de commerce.

Dans le raccourci **Général** de la page **Paramètres Commerce**, cliquez sur **Initialiser**. Pour en savoir plus, voir [Initialisation des données de départ dans de nouveaux environnement Retail](../enable-configure-retail-functionality.md)

Il existe une option pour configurer séparément le planificateur. Cliquez sur **Planificateur de commerce** \> **Initialiser le planificateur de commerce**. Dans la page **Initialiser le planificateur de commerce**, cliquez sur **OK**.

### <a name="configure-channel-components"></a>Configurer des composants de canal

Pour activer la fonctionnalité spécifique à la France, vous devez configurer les extensions des composants de canal. Pour plus d’informations, voir les [instructions de déploiement](./emea-fra-deployment.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]