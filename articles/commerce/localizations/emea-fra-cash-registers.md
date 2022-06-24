---
title: Fonctionnalité de caisse enregistreuse pour la France
description: Cet article fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la France. Elle fournit également des instructions pour paramétrer la fonctionnalité.
author: EvgenyPopovMBS
manager: annbe
ms.date: 05/17/2022
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
ms.openlocfilehash: 6656194f84a95fb8163b6793b453ead10a7f959e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885423"
---
# <a name="cash-register-functionality-for-france"></a>Fonctionnalité de caisse enregistreuse pour la France

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la France dans Microsoft Dynamics 365 Commerce. Elle fournit également des instructions pour paramétrer la fonctionnalité.

La fonctionnalité de caisse enregistreuse pour la France est constituée des éléments suivants :

- Fonctionnalités de points de vente (POS) courantes disponibles pour les clients dans tous les pays ou régions, telles que la possibilité d’enregistrer divers événements dans le journal d’audit de POS.
- Des fonctionnalités spécifiques pour la France, telles que les signatures numériques pour les transactions de vente.

## <a name="certification-information"></a>Informations sur la certification

Cette version de la fonctionnalité de caisse enregistreuse pour la France a passé un audit selon les exigences de certification NF 525 et se voit attribuer un certificat de conformité ayant la catégorie et numéro suivant : 

- **Microsoft Dynamics 365 Commerce, version 10** :

    - Catégorie de certification : B
    - Numéro de certificat : 0203

Un certificat à jour est disponible sur le [portail de l’organisme de certification](https://certificates.infocert.org/).

## <a name="common-pos-features"></a>Fonctionnalités de PDV courantes

Pour connaître les fonctionnalités de PDV disponibles pour les clients dans tous les pays ou régions, voir [Page d’accueil de Commerce](../index.md).

Les fonctionnalités de localisation PDV suivantes disponibles pour les clients de tous les pays ou régions peuvent désormais être utilisées spécifiquement pour la France :

- **Enregistrer des événements supplémentaires dans le journal d’événements d’audit du PDV.** Si l’option **Audit** dans le profil de fonctionnalité du PDV est définie sur **Oui**, les événements suivants sont enregistrés dans le journal d’événements d’audit du PDV :

    - Connexion
    - Déconnexion
    - Impression d’une copie d’un ticket de caisse
    - Démarrage du mode hors ligne
    - Fin du mode hors ligne
    - Application d’un remplacement de gestionnaire
    - Annulation d’une transaction 
    - Annulation d’une ligne de transaction
    - Nettoyage des transactions de la base de données des canaux
    - Application d’une mise à jour majeure du logiciel avec impact sur la conformité

## <a name="france-specific-pos-features"></a>Fonctionnalités du PDV spécifiques à la France

Les fonctionnalités de point de vente spécifiques à la France suivantes sont activées lorsque l’adresse principale de l’entité juridique à laquelle appartient le magasin est en France.

### <a name="digital-signing-overview"></a>Présentation de la signature numérique

Les types d’enregistrements suivants (transactions et événements) sont signés numériquement dans le PDV :

- Transactions de retour et de vente
- Copies des tickets de caisse
- Équipes clôturées/Z de caisse
- Événements d’audit

La signature est créée puis enregistrée dans la base de données des canaux lorsque la transaction est finalisée ou que l’événement est enregistré. Les données signées sont une chaîne de texte composée de plusieurs champs de données. Ces champs varient en fonction du type d’enregistrement. Le processus général de signature inclut les étapes suivantes :

1. Sélectionnez le numéro séquentiel suivant, à des fins de signature, pour le même registre et le même type d’enregistrement. 
1. Extrayez les champs de données qui doivent être signés de l’enregistrement qui est signé.
1. Créez une chaîne composée d’une liste séparée par des virgules des champs de données.
1. Ajoutez la signature précédente pour le même registre et le même type d’enregistrement.
1. Calculez un code de hachage de la chaîne.
1. Calculez une signature électronique asymétrique pour la chaîne résultante à l’aide d’un certificat numérique.
1. Effectuez la transformation base64url pour la chaîne obtenue.
1. Stockez la chaîne utilisée pour signer, le numéro séquentiel, la signature, l’identification de l’algorithme de hachage et l’empreinte du certificat dans un enregistrement de réponse fiscal lié à la transaction ou à l’événement.
1. Transférez la réponse fiscale au système ERP (enterprise resource planning) dans Commerce Headquarters, avec la transaction ou l’événement.

> [!NOTE]
> Les fonctions de hachage suivantes ne sont pas acceptables : CRC16, CRC32, SHA-1 et MD5. Commerce prend uniquement en charge les fonctions de hachage SHA256, SHA384 et SHA512. Si vous souhaitez utiliser une fonction de hachage différente, vous devez implémenter une personnalisation.
>
> Vous pouvez utiliser soit un certificat numérique délivré par un organisme accrédité, soit un certificat auto-signé pour la signature numérique. Seuls les certificats qui ont des clés privées RSA-2048 bits ou Elliptic Curve Digital Signature Algorithm (ECDSA) 224 bits minimum sont acceptables. Commerce ne prend en charge que les clés RSA-2048 bits ou plus. Si vous souhaitez utiliser une clé ECDSA, vous devez implémenter une personnalisation.

### <a name="digital-signing-of-sales-and-return-transactions"></a>Signature numérique des transactions de retour et de vente

Seules les transactions pour les ventes en espèces et les retours sont signées. Voici quelques exemples de transactions exclues du processus de signature :

- Acomptes (dépôts sur comptes client)
- Devis
- Acomptes pour les commandes client (dépôts sur commandes client)
- Émission d’une carte cadeau et ajout de fonds à une carte cadeau
- Transactions hors ventes (entrée de fond de caisse, vidage de caisse, etc.)

Les données signées pour une transaction de vente ou de retour sont une chaîne de texte composée des champs de données suivants :

- Montant total de la vente ou du retour, taxes incluses selon le taux d’imposition.
- Montant total de la vente ou de retour, taxes comprises.
- Date et heure de la transaction, au format AAAAMMJJHHMMSS.
- Numéro de caisse enregistreuse.
- Numéro séquentiel de la transaction de vente ou de retour signée pour le registre.
- Type de transaction de vente ou de retour.
- Valeur (O/N) qui indique si la transaction est la première transaction de vente ou de retour signée pour la caisse enregistreuse.
- La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour la première transaction de vente ou de retour signée.

> [!NOTE]
> Pour la signature numérique, les transactions de retour sont considérées comme des transactions de vente régulières. Par conséquent, le processus de signature pour les transactions de retour est le même que le processus de signature pour les transactions de vente, et les transactions de retour sont incluses dans la même séquence de signatures que les transactions de vente. Le montant total d’un retour est négatif. En d’autres termes, il inclut un signe moins lorsqu’il est ajouté à la chaîne de texte signée.

Vous pouvez afficher la signature de transaction, avec les données de transaction utilisées pour la générer, sous le raccourci **Transactions fiscales** de la page **Transactions de magasin** dans Commerce Headquarters. En sélectionnant **Données étendues**, vous pouvez afficher des propriétés spécifiques de la transaction fiscale, telles que la signature, le numéro séquentiel, l’empreinte numérique du certificat et l’identification de l’algorithme de hachage. 

### <a name="digital-signing-of-receipt-copies"></a>Signature numérique des copies de tickets de caisse

Lorsqu’une copie d’un ticket de caisse est imprimée, l’événement est enregistré dans le journal d’événements d’audit du PDV. Seules les copies des tickets de caisse des transactions de vente signées sont signées. Les données signées pour un événement de copie de ticket de caisse sont une chaîne de texte composée des champs de données suivants :

- Numéro du registre à partir duquel la copie du ticket de caisse est imprimée.
- Numéro séquentiel de l’événement de copie de ticket de caisse signée pour le registre.
- Le type de transaction de la transaction de vente d’origine.
- Numéro de copie de ticket de caisse pour la transaction de vente.
- ID de personnel de l’opérateur qui imprime la copie de ticket de caisse.
- Date et heure de l’événement de copie de ticket de caisse, au format AAAAMMJJHHMMSS.
- Numéro de registre de la transaction de vente originale.
- Numéro séquentiel de la transaction de vente d’origine pour le registre.
- Valeur (O/N) qui indique si la transaction est le premier événement de copie de ticket de caisse signée pour la caisse enregistreuse.
- La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour le premier événement de copie de ticket de caisse signée.

Vous pouvez afficher la signature de la copie de ticket de caisse, avec les données d’événement utilisées pour la générer, sous l’onglet **Résultats de l’enregistrement fiscal** de la page **Événements d’audit** dans Commerce Headquarters.

### <a name="digital-signing-of-closed-shifts"></a>Signature numérique des équipes clôturées

Lorsqu’une équipe est clôturée, l’événement est enregistré dans le journal d’événements d’audit du PDV. Les données signées pour un événement de clôture d’équipe sont une chaîne de texte composée des champs de données suivants :

- Montant total des ventes et des retours pour l’équipe, taxes incluses selon le taux d’imposition.
- Montant total des ventes et des retours pour l’équipe, taxes incluses.
- Total général perpétuel cumulé des valeurs absolues des ventes et des retours pour les équipes du même registre, taxes comprises. 
- Date et heure de l’événement de clôture d’équipe, au format AAAAMMJJHHMMSS.
- Date et heure de l’équipe.
- Numéro séquentiel de l’événement de clôture d’équipe signé pour le registre.
- Valeur (O/N) qui indique si la transaction est le premier événement de clôture d’équipe signée pour la caisse enregistreuse.
- La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour le premier événement de clôture d’équipe signée.

> [!NOTE]
> En raison de l’exigence de maintenir une chaîne d’équipes fermées pour le même registre, la fermeture d’une équipe sur un registre différent de celui sur lequel l’équipe a été ouverte n’est pas prise en charge. Elle peut être ajoutée lors des mises à jour ultérieures.

Vous pouvez afficher la signature d’une clôture d’équipe, avec les données d’équipe utilisées pour la générer, sous l’onglet **Résultats de l’enregistrement fiscal** de la page **Équipes** dans Commerce Headquarters.

### <a name="digital-signing-of-events"></a>Signature numérique des événements

Les données signées pour un événement autre qu’une copie de ticket de caisse ou de clôture d’équipe sont une chaîne de texte composée des champs de données suivants :

- Numéro séquentiel de l’événement signé pour le registre.
- Code d’événement prédéfini.
- Description de l’événement.
- Date et heure de l’événement.
- ID du personnel de l’opérateur ayant déclenché l’événement.
- Numéro de caisse enregistreuse.
- Valeur (O/N) qui indique si la transaction est le premier événement signé pour la caisse enregistreuse.
- La signature précédente pour la même caisse enregistreuse. Une valeur vide est utilisée pour le premier événement signé.

Vous pouvez afficher la signature de l’événement, avec les données d’événement utilisées pour la générer, sous l’onglet **Résultats de l’enregistrement fiscal** de la page **Événements d’audit** dans Commerce Headquarters.

### <a name="receipts"></a>Réceptions

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

- **Données de certification** : un ticket de caisse peut inclure la catégorie et le numéro du certificat de conformité qu’un organisme autorisé a émis conformément aux exigences de certification de la norme NF 525.
- **Version du logiciel** : un ticket de caisse peut comprendre la version du logiciel qui a été certifiée selon les exigences de certification NF 525 et qui sert à établir les tickets de caisse.

### <a name="restricting-the-duration-of-shifts"></a>Limitation de la durée des équipes

Il existe une option pour appliquer la clôture d’équipe quotidienne dans le PDV. Une équipe ne peut pas durer plus longtemps que la durée spécifiée dans le champ **Heure de clôture de l’équipe de travail**. Plusieurs minutes avant cette heure, l’opérateur commencera à recevoir des avertissements que l’équipe doit être clôturée. Le nombre de minutes est déterminé par la valeur du champ **Intervalle de clôture de l’équipe de travail (minutes)**.

### <a name="x-and-z-reports"></a>X et Z de caisse

Les informations qui sont incluses dans les X et Z de caisse sont basées sur les besoins français :

- **Total des ventes** de l’équipe. Ces informations incluent les montants uniquement pour les transactions de ventes au comptant. Les acomptes et les opérations d’émission d’une carte cadeau sont exclues.
- **Total des retours** de l’équipe.
- **Total général perpétuel cumulé**. Ce montant est calculé comme le montant total général perpétuel cumulé de l’équipe précédente, plus le montant total des ventes de cette équipe, moins la valeur absolue du total des retours de cette équipe.
- **Total général perpétuel cumulé (valeur absolue)**. Ce montant est calculé comme le montant total général perpétuel cumulé de l’équipe précédente (valeur absolue), plus le montant total des ventes de cette équipe plus la valeur absolue du total des retours de cette équipe.
- Montants de taxe sur la valeur ajoutée (VAT) par taux de taxe.

Les totaux sont également stockés dans l’enregistrement de l’équipe clôturée et transférés dans Commerce Headquarters.

Vous pouvez exporter un Z de caisse à partir d’une équipe fermée dans Commerce headquarters. Un Z de caisse exporté est un fichier XML qui inclut les totaux pour l’équipe clôturée. Plus précisément, le fichier inclut les données décrites dans le tableau suivant.

| Élément/nœud                     | Commentaire |
|----------------------------------|---------|
| RegisterNumber                   | Identification du registre sur lequel l’équipe a été ouverte. |
| Date                             | Date de l’équipe. |
| TotalCashSales                   | Montant total des ventes, taxes comprises, pour l’équipe. |
| TotalCashReturns                 | Valeur absolue du montant total des retours, taxes comprises, pour l’équipe. |
| GrandTotal                       | Montant total des ventes, taxes comprises, moins la valeur absolue du montant total des retours, taxes comprises, pour l’équipe. |
| PerpetualGrandTotal              | Total général perpétuel cumulé pour l’équipe. Autrement dit, le total général perpétuel cumulé de l’équipe précédente du même registre, plus le montant total des ventes TTC pour l’équipe, moins la valeur absolue du montant total des retours TTC de l’équipe. |
| PerpetualGrandTotalAbsoluteValue | Total général perpétuel cumulé pour l’équipe. Autrement dit, le total général perpétuel cumulé de l’équipe précédente du même registre, plus le montant total des ventes TTC pour l’équipe, plus la valeur absolue du montant total des retours TTC de l’équipe. |
| ShiftLines                       | Collection de montants totaux généraux par taux d’imposition. |
| ShiftLine                        | Nœud pour le montant total général d’un taux d’imposition. |
| TotalInclTax                     | Montant total général d’un taux d’imposition pour l’équipe. |
| TaxRate                          | Taux d’imposition. |
| TaxAmount                        | Montant total général d’une taxe pour le taux d’imposition. |
| SequentialNumber                 | Numéro séquentiel de l’équipe ayant signé pour le registre. |
| DataToSign                       | Chaîne [créée à partir des éléments de l’enregistrement de l’équipe](#digital-signing-of-closed-shifts) et utilisée pour la signature. |
| DataToSignFormatVersion          | Version interne du format de données qui a été utilisé pour la signature. |
| Signature                        | Signature numérique de l’enregistrement de l’équipe. |
| HashAlgorithm                    | Algorithme de code de hachage utilisé pour hacher les données avant signature. |
| CertificateThumbprint            | Empreinte numérique du certificat utilisée pour la signature. |

Le fichier de Z de caisse exporté est numériquement signé, et la signature est contenue dans un fichier distinct.

### <a name="period-grand-total-journal"></a>Journal du total général de la période

Les journaux du total général de la période synthétisent les totaux des ventes par magasin et par période fiscale (par exemple, par mois). De plus, un journal annuel résume les totaux des ventes par magasin et par exercice.

Les journaux du total général de la période sont tenus à jour sur la page **Journal du total général de la période**. Pour créer un journal, vous devez spécifier un magasin. Si des journaux précédent existent pour le magasin, la prochaine période fiscale après le dernier journal clôturé pour le magasin est automatiquement utilisée comme période de journal. Si aucun journal précédent n’existe, vous pouvez spécifier la date de fin du journal. Dans ce cas, la période fiscale qui inclut la date spécifiée est utilisée comme période de journal.

Le journal peut ensuite être calculé. Les équipes clôturées au cours de la période de journal sont sélectionnées, et les totaux sont calculés pour les équipes. Vous pouvez afficher les totaux de taxe du journal par code taxe. Vous pouvez également afficher les équipes qui sont incluses dans le journal.

Lorsque le journal est calculé, il peut être clôturé. Un journal clôturé ne peut pas être modifié, et un autre journal ne peut pas être créé pour une période fiscale précédente, la même période, ou une période les recoupant. Toutefois, le dernier journal clôturé pour un magasin peut être annulé. Dans ce cas, un autre journal peut être créé pour le même magasin et la période fiscale.

Un journal clôturé est numériquement signé. Les données signées pour un journal clos sont une chaîne de texte composée des champs de données suivants :

- Montants totaux des ventes et des retours pour le magasin et la période, taxes incluses selon le taux d’imposition.
- Montant total des ventes et des retours pour le magasin et la période, taxes incluses.
- Total général perpétuel cumulé des valeurs absolues des ventes et des retours pour le magasin et la période, taxes comprises. 
- Date et heure de l’événement de clôture du journal, au format AAAAMMJJHHMMSS.
- Dates de début et de fin de la période.
- Numéro séquentiel du journal du total général de la période signée pour le magasin.
- Valeur (O/N) qui indique si le journal est le premier journal signé pour le magasin.
- Signature précédente pour le magasin et la période. Une valeur vide est utilisée pour le premier journal signé pour le magasin.

Vous pouvez afficher la signature du journal, avec les données du journal utilisées pour la générer, sous l’onglet **Détails de la signature** de la page **Journal du total général de la période** dans Commerce Headquarters.

Un journal du total général d’une période peut également être marqué comme **Annuel** quand il est créé. Un journal annuel résume les journaux du total général de la période pour les périodes fiscales d’un exercice. Un journal annuel peut être créé pour un exercice uniquement si un journal pour la dernière période fiscale de l’exercice a été créé, calculé et clôturé. Cependant, les journaux n’ont pas besoin d’exister pour *toutes* les périodes fiscales de l’exercice. Par exemple, si un nouveau magasin est ouvert au milieu de l’année, le premier journal correspond à la période fiscale au cours de laquelle le magasin est ouvert. Dans ce cas, le premier journal annuel résume les journaux pour les périodes fiscales à partir de la période fiscale au cours de laquelle le magasin est ouvert jusqu’à la dernière période fiscale de l’exercice.

### <a name="fiscal-archive"></a>Archives fiscales

Une archive fiscale est un fichier XML qui peut être exporté depuis un journal du total général de la période qui a été clôturée. Il comprend les totaux de la période clôturée. Il comprend également des données détaillées sur les transactions de vente et les événements. Le fichier exporté est numériquement signé, et la signature est contenue dans un fichier distinct. Les archives fiscales exportées doivent être conservées sur des supports externes sécurisés pendant la durée légale de conservation.

Commerce comprend également un outil qui peut être utilisé pour vérifier l’intégrité des archives fiscales et pour détecter les violations de la signature de l’archive et des chaînes d’enregistrements signés dans l’archive. Cet outil prend la forme d’un script Windows PowerShell disponible via le kit de développement logiciel (SDK) Commerce. Pour des informations détaillées sur la structure du format des archives fiscales et des conseils sur l’utilisation de l’outil de vérification de l’intégrité des archives fiscales, voir [Archives fiscales pour la France](./emea-fra-fiscal-archive.md).

## <a name="set-up-commerce-for-france"></a>Configurer Commerce pour la France

Cette section décrit les paramètres Commerce spécifiques et recommandés pour la France. Pour plus d’informations, voir [Page d’accueil de Commerce](../index.md).

Pour utiliser la fonctionnalité spécifique pour la France, vous devez effectuer les tâches suivantes :

- Définissez le champ **Pays/région** sur **FRA** (France) dans l’adresse principale de l’entité juridique.
- Définissez le champ **Code ISO** sur **FR** (France) dans le profil de fonctionnalité du PDV de chaque magasin situé en France.

Vous devez également spécifier les paramètres suivants pour la France. Notez que vous devez exécuter des tâches de distribution appropriées après que vous avez terminé le paramétrage.

### <a name="enable-features-for-france"></a>Activer les fonctionnalités pour la France

Vous devez activer les fonctionnalités suivantes dans l’espace de travail **Gestion des fonctionnalités** :

- (France) Activer les événements d’audit supplémentaires dans le PDV
- (France) Activer l’exportation d’un Z de caisse vers un fichier

### <a name="set-up-the-legal-entity"></a>Paramétrer l’entité juridique

Vous devez apporter les modifications suivantes dans la page **Entités juridiques**. Ces paramètres sont utilisés dans le format d’archive.

- Dans l’organisateur **Informations sur le compte en banque**, dans le champ **Numéro d’acheminement**, spécifiez l’identifiant TVA de l’organisation.
- Dans l’organisateur **Génération d’état statutaire**, dans le champ **Code NAF**, spécifiez le code NAF (Nomenclature des Activités Françaises) de l’organisation.
- Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, spécifiez le numéro de SIRET (Système d’identification du répertoire des établissements) de l’organisation.

### <a name="set-up-vat-per-french-requirements"></a>Paramétrer la TVA selon les exigences de la France

Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation de la taxe, voir [Vue d’ensemble des taxes](/dynamics365/finance/general-ledger/indirect-taxes-overview).

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
| fr-FR       | 900005  | Base de la taxe sur les ventes           |
| fr-FR       | 900006  | Montant de la taxe de vente          |
| fr-FR       | 900007  | Total des ventes               |
| fr-FR       | 900008  | Taxe totale           |
| fr-FR       | 900009  | Total des ventes TTC |
| fr-FR       | 900010  | Certificat NF 525        |
| fr-FR       | 900011  | Nombre de lignes                |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** que vous avez spécifiées dans la page **Texte en langue étrangère**.

| Nom                            | Type    | ID texte de la légende |
|---------------------------------|---------|-----------------|
| TRANSACTIONTYPE_FR              | Récépissé | 900001          |
| SEQUENTIALNUMBER_FR             | Récépissé | 900002          |
| DIGITALSIGNATURE_FR             | Récépissé | 900003          |
| REPRINTNUMBER_FR                | Récépissé | 900004          |
| SALESTAXBASIS_FR                | Récépissé | 900005          |
| SALESTAXAMOUNT_FR               | Récépissé | 900006          |
| SALESTOTAL_FR                   | Récépissé | 900007          |
| SALESTOTALTAX_FR                | Récépissé | 900008          |
| SALESTOTALINCLUDETAX_FR         | Récépissé | 900009          |
| CERTIFICATENUMBERANDCATEGORY_FR | Récépissé | 900010          |
| LINECOUNT_FR                    | Récépissé | 900011          |

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
    - **Taxe totale** – Ce champ permet d’imprimer le montant total des taxes des ventes de disponibilités. Les acomptes et les opérations de carte cadeau sont exclus. 
    - **Total des ventes TTC** – Ce champ permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant inclue la taxe. Les acomptes et les opérations de carte cadeau sont exclues.
    - **ID taxe** – Ce champ standard active une synthèse de taxe à imprimer par code taxe. Le champ doit être ajouté sur une nouvelle ligne.
    - **Base de la taxe de vente** – Ce champ permet d’imprimer la base des taxes des ventes de disponibilités par code de taxe. Les acomptes et les opérations de carte cadeau sont exclues. Le champ doit être ajouté à la même ligne que le champ **ID taxe**.
    - **Montant de la taxe de vente** – Ce champ permet d’imprimer le montant des taxes des ventes de disponibilités par code de taxe. Les acomptes et les opérations de carte cadeau sont exclus. Le champ doit être ajouté à la même ligne que le champ **ID taxe**.
    - **Numéro séquentiel** – Ce champ imprimer le numéro séquentiel d’une transaction de vente signée.
    - **Signature numérique** – Ce champ imprime l’extraction de la signature numérique.
    - **Réimprimer le numéro** – Ce champ imprime le numéro d’une copie de ticket de caisse.
    - **Certificat NF 525** : ce champ imprime la catégorie du certificat de conformité et son numéro qu’un organisme autorisé a émis conformément aux exigences de certification de la norme NF 525.

        > [!NOTE]
        > La catégorie et le numéro de certificat qui sont attribués à [Commerce](#certification-information) sont imprimés.

    - **Texte** : ajoutez un champ de texte et précisez la version du logiciel certifié conformément aux exigences de certification NF 525et utilisé pour produire des tickets de caisse (par exemple, **Microsoft Dynamics 365 Commerce v.10**).

        > [!NOTE]
        > Si vous personnalisez l’application POS et que vos personnalisations affectent la conformité de l’application, vous devrez peut-être demander un nouveau certificat de conformité à un organisme accrédité. Dans ce cas, vous devez remplacer la catégorie et le numéro de certificat et spécifier un numéro de version de logiciel correspondant. Sinon, les valeurs par défaut de la catégorie et du numéro de certificat seront imprimées.

    - **Nombre de lignes** – Ce champ imprime le nombre de lignes d’articles imprimées sur un ticket de caisse.
    - **Texte** – Ajouter un champ de texte et spécifie l’identifiant TVA de l’organisation.
    - **Texte** – Ajouter un champ de texte et spécifie le code NAF de l’organisation.
    - **Texte** – Ajouter un champ de texte et spécifie le numéro de SIRET de l’organisation.
    - **Nom du magasin** – Ce champ standard imprime le nom du magasin.
    - **Adresse du magasin** – Ce champ standard imprime l’adresse du magasin.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Configurer et concevoir les formats de tickets de caisse](../receipt-templates-printing.md).

### <a name="set-up-fiscal-registration"></a>Paramétrer l’enregistrement fiscal

Suivez les étapes de configuration de l’enregistrement fiscal décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](./setting-up-fiscal-integration-for-retail-channel.md) :

1. [Configurer un processus d’enregistrement fiscal](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Assurez-vous de noter les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à la France](#configure-the-fiscal-registration-process).
1. [Définir les paramètres de traitement des erreurs](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Activer l’exécution manuelle d’un enregistrement fiscal reporté](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

#### <a name="configure-the-fiscal-registration-process"></a>Configurer le processus d’enregistrement fiscal

Pour activer le processus d’enregistrement fiscal pour la France dans Commerce Headquarters, procédez comme suit.

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal à partir du SDK Commerce :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    2. Ouvrez la dernière branche de version disponible (par exemple, **[version/9.30](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.30)**).
    3. Ouvrez **src \> FiscalIntegration \> SequentialSignatureFrance \> Configurations**.
    4. Téléchargez le fichier de configuration du connecteur fiscal sur **Connecteur\> ConnectorMicrosoftSequentialSignatureFRA.xml** (par exemple, [le dossier pour version/9.30](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.30/src/FiscalIntegration/SequentialSignatureFrance/Configurations/Connector/ConnectorMicrosoftSequentialSignatureFRA.xml)).
    5. Téléchargez le fichier de configuration du fournisseur de document sur **DocumentProvider\> DocumentProviderMicrosoftSequentialSignatureFRA.xml** (par exemple, [le dossier pour version/9.30](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.30/src/FiscalIntegration/SequentialSignatureFrance/Configurations/DocumentProvider/DocumentProviderMicrosoftSequentialSignatureFRA.xml)).

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres partagés**. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**, et téléchargez le fichier de configuration du connecteur fiscal téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux** et chargez le fichier de configuration du fournisseur de documents fiscaux téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels des connecteurs**. Créez un profil fonctionnel de connecteur et sélectionnez le fournisseur de documents et le connecteur chargé précédemment. Mettez à jour les paramètres de mappage des données si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**. Créez un profil technique de connecteur et sélectionnez le connecteur chargé précédemment. Définissez le type de connecteur sur **Interne**. Mettez à jour les autres paramètres de connexion si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**, et créez un groupe de connecteurs fiscaux pour le profil fonctionnel de connecteur créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**. Créez un processus d’enregistrement fiscal, créez une étape du processus d’enregistrement fiscal et sélectionnez le groupe de connecteurs fiscaux créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment. Sur le raccourci **Services fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment. 
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**. Ouvrez le planning de distribution et sélectionnez les tâches **1070** et **1090** pour transférer des données vers la base de données des canaux.

### <a name="configure-the-digital-signature-parameters"></a>Configurer les paramètres de signature numérique

Vous devez configurer les certificats utilisés pour la signature numérique des enregistrements côté canal Commerce (transactions de vente et événements d’audit) et côté Commerce Headquarters (journaux du total général de la période, Z de caisse et archives fiscales). La signature s’effectue à l’aide d’un certificat numérique enregistré dans Azure Key Vault. Pour le mode hors ligne de Modern POS, la signature peut également être effectuée à l’aide d’un certificat numérique stocké en local sur la machine sur laquelle Modern POS est installé. La fonction [Profils de certificats définis par l’utilisateur pour les magasins de détail](./certificate-profiles-for-retail-stores.md) permet de configurer les certificats stockés dans Key Vault. Elle prend également en charge le basculement en mode hors ligne lorsque Key Vault ou Commerce Headquarters n’est pas disponible. Cette fonctionnalité étend la fonction [Gérer les clés secrètes pour les canaux de vente au détail](../dev-itpro/manage-secrets.md).

> [!NOTE]
> Vous pouvez utiliser soit un certificat numérique délivré par un organisme accrédité, soit un certificat auto-signé pour la signature numérique. Seuls les certificats qui ont des clés privées RSA-2048 bits ou Elliptic Curve Digital Signature Algorithm (ECDSA) 224 bits minimum sont acceptables. Commerce ne prend en charge que les clés RSA-2048 bits ou plus. Si vous souhaitez utiliser une clé ECDSA, vous devez implémenter une personnalisation.

Les étapes suivantes doivent être effectuées avant d’utiliser un certificat numérique enregistré dans le stockage Key Vault :

1. Le stockage du coffre de clés doit être créé. Il est recommandé de déployer le stockage dans la même zone géographique que l’Unité d’échelle commerciale.
1. Le certificat doit être téléchargé vers le stockage du coffre de clés.
1. L’application Serveur d’objets d’application (AOS) doit être autorisée pour lire les secrets du stockage du coffre de clés.

Pour plus d’informations sur l’utilisation du coffre de clés, voir [Prise en main d’Azure KeyVault](/azure/key-vault/key-vault-get-started).

Puis, sur la page **Paramètres du coffre de clés**, vous devez spécifier les paramètres d’accès au stockage Key Vault :

- **Nom** et **Description** – Nom et description du stockage du coffre de clés.
- **URL du coffre de clés** – URL du stockage du coffre de clés.
- **Client du coffre de clés** – ID client interactif de l’application Azure Active Directory (Azure AD) associée au stockage du coffre de clés à des fins d’authentification. Ce client doit avoir accès en lecture aux secrets du stockage.
- **Clé secrète du coffre de clés** – Clé secrète associée à l’application Azure AD utilisée pour l’authentification dans le stockage du coffre de clés.
- **Nom**, **Description**, et **Référence secrète** – Nom, description, et référence secrète du certificat.

Ensuite, vous devez configurer un profil de certificat pour vos certificats stockés dans Key Vault ou dans le stockage de certificats local. Le profil de certificat est utilisé pour la signature côté canal.

Pour configurer un profil de certificat pour vos certificats dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Administration système \> Paramétrage \> Profils de certificat**. 
1. Créez un profil certificat.
1. Sur le raccourci **Entités juridiques**, ajoutez les entités juridiques requises.
1. Sélectionnez **Paramètres**.
1. Ajoutez un nouveau certificat. Les certificats stockés dans Key Vault et les certificats locaux sont pris en charge. Vous pouvez ajouter autant de certificats que vous le souhaitez et définir des priorités pour les certificats. Si un certificat qui a une priorité plus élevée n’est pas disponible, le certificat suivant est utilisé, en fonction de la priorité.

    - Pour un certificat stocké dans Key Vault, vous devez sélectionner le certificat dans la liste déroulante.
    - Pour un certificat stocké localement, vous devez spécifier l’empreinte numérique du certificat.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**.
1. Sur le raccourci **Paramètres**, spécifiez les paramètres suivants pour les signatures numériques :

    - **Profil du certificat** : sélectionnez le profil de certificat configuré précédemment.
    - **Algorithme de hachage** : spécifiez l’un des algorithmes de hachage cryptographique pris en charge par Microsoft .NET, tel que **SHA256**.
    - **Activer le contrôle d’intégrité** : pour plus d’informations sur la procédure de contrôle d’intégrité, voir [Contrôle d’intégrité d’enregistrement fiscal](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

Enfin, sur la page **Paramètres Commerce** (**Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres Commerce**), vous devez spécifier les paramètres suivants pour la signature numérique côté Commerce Headquarters :

- **Certificat** : sélectionnez un certificat stocké dans Key Vault.
- **Fonction de hachage** – Spécifiez l’un des algorithmes de hachage cryptographique pris en charge par Microsoft .NET, tel que **SHA256**.
- **Encodage** – Spécifiez l’encodage des données signées, tel que **UTF-8**.

> [!NOTE]
> Les fonctions de hachage suivantes ne sont pas acceptables : CRC16, CRC32, SHA-1 et MD5. Commerce prend uniquement en charge les fonctions de hachage SHA256, SHA384 et SHA512. Si vous souhaitez utiliser une fonction de hachage différente, vous devez implémenter une personnalisation.

### <a name="configure-the-z-report-and-archive-export-formats"></a>Configurer les formats d’exportation des archives et des Z de caisse

Vous pouvez télécharger les configurations ER pour les Z de caisse et l’archive à partir de Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Vous devez télécharger les versions suivantes, ou les versions ultérieures, des configurations :

- Modèle données **Canal de vente au détail data.version.2**
- Mise en correspondance de modèle de données **Archivage DMM.version.2.3**
- Format **Z de caisse de la vente au détail (FR).version.24.23.3**
- Format **Archive des données de vente au détail (FR).version.2.5**

Après l’importation des configurations, sélectionnez les formats ER pour le Z de caisse et l’archive dans les champs suivants de l’onglet **Documents électroniques** de la page **Paramètres de Commerce** :

- **Format d’exportation d’un Z de caisse** : Sélectionnez le format **Z de caisse de la vente au détail (FR).version.24.23.3** ou le format que vous avez téléchargé précédemment.
- **Format d’exportation de l’archive des données de vente au détail** : Sélectionnez le format **Archive des données de vente au détail (FR).version.2.5** ou le format que vous avez téléchargé précédemment.

### <a name="reinitialize-commerce-components"></a>Réinitialiser les composants Commerce

> [!NOTE]
> Vous ne devez effectuer les étapes de cette section que si vous mettez à jour un environnement existant.

Pour activer les événements d’audit, vous devez réinitialiser les énumérations Commerce extensibles. Pour activer la transmission de données spécifiques à la France du PDV à Commerce Headquarters, vous devez réinitialiser le planificateur Commerce.

1. Sur la page **Paramètres Commerce**, sur le raccourci **Général**, sélectionnez **Initialiser**. Pour en savoir plus, voir [Initialisation des données de départ dans de nouveaux environnement Retail](../enable-configure-retail-functionality.md).
1. Il existe une option pour configurer séparément le planificateur. Accédez à **Planificateur Commerce** \> **Initialiser le planificateur Commerce**. Dans la boîte de dialogue **Initialiser le planificateur Commerce**, sélectionnez **OK**.

### <a name="configure-channel-components"></a>Configurer des composants de canal

Pour activer la fonctionnalité spécifique à la France, vous devez configurer les extensions des composants de canal. Pour plus d’informations, voir les [instructions de déploiement](./emea-fra-fi-deployment.md).

> [!NOTE]
> Cette version de la fonctionnalité Commerce pour la France est basée sur le [cadre de l’intégration fiscale](./fiscal-integration-for-retail-channel.md). Pour plus d’informations sur l’exemple de signature numérique hérité pour la France, voir [Instructions de déploiement de caisses enregistreuses pour la France (héritées)](./emea-fra-deployment.md).  Pour obtenir des instructions sur la façon d’activer la fonctionnalité d’intégration fiscale pour la France dans les environnements existants qui utilisent l’exemple de signature numérique hérité, voir [Effectuer une migration depuis l’ancienne fonctionnalité Commerce pour la France](./emea-fra-fi-migration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
