---
title: Fonctionnalité de caisse enregistreuse pour la France
description: Cet article fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la France. Elle fournit également des instructions pour paramétrer la fonctionnalité.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: France
ms.author: josaw
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: 7.3.2
ms.search.industry: Retail
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
manager: annbe
ms.openlocfilehash: 7c5b5266a6e1e6dfa70e3b7753905cf33166a229
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631469"
---
# <a name="cash-register-functionality-for-france"></a>Fonctionnalité de caisse enregistreuse pour la France

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la France dans Microsoft Dynamics 365 Commerce. Elle fournit également des instructions pour paramétrer la fonctionnalité.

## <a name="certification-information"></a>Informations sur la certification

Cette version de la fonctionnalité de caisse enregistreuse pour la France a passé un audit selon les exigences de certification NF 525 et se voit attribuer un certificat de conformité ayant la catégorie et numéro suivant : 

- **Microsoft Dynamics 365 Commerce, version 10** :

    - Catégorie de certification : B
    - Numéro de certificat : 0498

Un certificat à jour est disponible sur le [portail de l’organisme de certification](https://certificates.infocert.org/).

Vous pouvez également afficher les informations de certification dans le point de vente (POS) dans la boîte de dialogue **Certification NF 525**. Vous pouvez ouvrir cette boîte de dialogue en sélectionnant **Voir les détails** dans la section **Certification NF 525** sous **France** sur la page **Paramètres**. Si des fonctionnalités spécifiques à la France sont [activées](#enable-features-for-france) dans l’espace de travail **Gestion des fonctionnalités**, et que la fonctionnalité d’enregistrement fiscal pour la France est correctement [activée et configurée](#set-up-fiscal-registration), la boîte de dialogue **Certification NF 525** affiche le nom et la version du logiciel certifié, la catégorie de certification et le numéro de certificat NF 525.

### <a name="nf-525-compliance-documentation"></a>Documentation de conformité NF 525

Le tableau suivant montre la documentation Dynamics 365 Commerce relative à la certification NF 525.

| Document | Description | Liens |
|----------|-------------|-------|
| <p>Conception de haut niveau</p><p>Architecture technique</p> | Cette documentation décrit le produit logiciel, ses composants et flux de données, ainsi que la conception technique du produit. | <p>[Page d’accueil Commerce](../index.md) et liens imbriqués</p><p>[Vue d’ensemble architecturale de Dynamics 365 Commerce](../commerce-architecture.md)</p><p>[Conception de la solution Commerce pour la France](#design-of-the-commerce-solution-for-france)</p> |
| <p>Spécification fonctionnelle</p><p>Documentation utilisateur</p> | Cette documentation décrit les fonctions du logiciel. | <p>[Page d’accueil Commerce](../index.md) et liens imbriqués</p><p>[Fonctionnalités du PDV spécifiques à la France](#france-specific-pos-features)</p> |
| Stratégie de contrôle de version | <p>Cette documentation décrit l’approche de gestion des versions et la procédure de gestion des versions pour le produit logiciel.</p><p>La version actuelle principale de Dynamics 365 Commerce est **10.0**. Les mises à jour de service pour cette version sont indiquées par un numéro consécutif après le numéro de version : **10.0.X**. Pour plus d’informations sur la stratégie du cycle de vie des logiciels et les mises à jour de service, utilisez les liens de ce tableau.</p> | <p>[Vue d’ensemble des mises à jour de service à une version](../../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md)</p><p>[Stratégie du cycle de vie de logiciel et versions de cloud](../../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)</p><p>[Disponibilité des mises à jour de service](../../fin-ops-core/fin-ops/get-started/public-preview-releases.md)</p><p>[Programmes de publication de Dynamics 365](/dynamics365/release-plans/)</p><p>[Nouveautés ou modifications dans Dynamics 365 Commerce](../get-started/whats-new-home-page.md)</p><p>[Conditions requises pour le contrôle de version du composant Dynamics 365 Commerce](../arch-component-versioning.md)</p> |
| Documentation organisationnelle | Cette documentation décrit le processus mis en place pour contrôler la conformité des produits logiciels. | [Ressources de globalisation](../../fin-ops-core/dev-itpro/lcs-solutions/country-region.md) |
| Documentation de maintenance | Cette documentation décrit la mise en œuvre et la maintenance de la solution logicielle. | <p>[Description de service](../../fin-ops-core/fin-ops/get-started/service-description.md)</p><p>[Avant d’acheter](../../fin-ops-core/fin-ops/get-started/before-you-buy.md)</p><p>[Guide des licences Dynamics 365](https://www.microsoft.com/licensing/docs/grid/Microsoft-Dynamics-365)</p><p>[Page d’accueil de gestion du cycle de vie de l’implémentation](../../fin-ops-core/fin-ops/imp-lifecycle/implementation-lifecycle.md)</p><p>[Synchronisation des programmes d’installation en libre-service dans Dynamics 365 Commerce](../dev-itpro/Synchronize-installers.md)</p><p>[Configurer Commerce pour la France](#set-up-commerce-for-france)</p><p>[Liste de contrôle de conformité](#compliance-checklist)</p><p>[Support Dynamics 365](https://dynamics.microsoft.com/support/)</p><p>[Soumission de demandes de service](../../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md)</p><p>[Vue d’ensemble des mises à jour de service à une version](../../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md)</p> |
| Documentation pour les auditeurs | Cette documentation décrit comment accéder aux données, aux fichiers et au processus utilisés par les autorités. | [Archives fiscales pour la France](./emea-fra-fiscal-archive.md) |

## <a name="design-of-the-commerce-solution-for-france"></a>Conception de la solution Commerce pour la France

L’illustration suivante présente la conception de haut niveau de la solution Commerce pour la France. Pour plus d’informations sur les composants Dynamics 365 Commerce, voir [Vue d’ensemble architecturale de Dynamics 365 Commerce](../commerce-architecture.md).

![Conception de haut niveau de la solution fiscale pour la France.](media/emea-fra-fiscal-solution.png)

Le flux de processus de haut niveau de bout en bout pour la France est le suivant :

1. Lorsque le processus de paiement est terminé pour une transaction de vente au PDV, ce dernier envoie une demande de signature numérique à Commerce Runtime (CRT) via Commerce Scale Unit (CSU). La signature numérique des transactions et des événements d’audit est mise en œuvre à l’aide du [Cadre d’enregistrement fiscal](./fiscal-integration-for-retail-channel.md) et un connecteur [interne](./fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-internally-in-the-crt).

    > [!NOTE]
    > Si le PDV est en mode hors ligne, la signature numérique se produit dans la copie locale de CRT sur la machine du PDV.

1. CRT prépare les données de transaction à signer. Pour plus d’informations sur les signatures numériques, consultez la section [Présentation de la signature numérique](#digital-signing-overview).
1. CRT envoie une demande à Commerce headquarters pour fournir un certificat numérique.
1. Commerce headquarters extrait le certificat numérique d’Azure Key Vault et le renvoie à CRT. Pour plus d’informations sur la façon dont Commerce gère les certificats numériques, consultez la section [Configurer les paramètres de signature numérique](#configure-the-digital-signature-parameters).

    > [!NOTE]
    > Si le PDV est en mode hors ligne, la copie locale de CRT utilise un certificat numérique installé localement sur la machine du PDV.

1. CRT signe numériquement les données de transaction. La signature, ainsi que les données signées et d’autres informations, sont enregistrées dans la base de données du canal (DB) dans une transaction fiscale liée à la transaction de vente. La signature est renvoyée au PDV.
1. Le point de vente demande un reçu de vente à CRT. CRT génère le reçu, y compris un extrait de la signature numérique de la transaction, et le renvoie au PDV. Le PDV envoie le reçu à l’imprimante de reçus.
1. Lorsque l’un des événements d’audit devant être signé numériquement se produit, les étapes ci-dessus, à l’exception de la réception, sont répétées pour l’événement d’audit. La signature de l’événement d’audit est enregistrée dans la BD de canal dans une transaction fiscale liée à l’événement d’audit.
1. Lorsque l’équipe est fermée, un événement d’audit de clôture d’équipe est enregistré et également signé numériquement. Le Z de caisse est imprimé sur l’imprimante de tickets.
1. Headquarters télécharge les données d’événement de transaction et d’audit ainsi que les transactions fiscales de CSU via Commerce Data Exchange (CDX). Les données sont stockées dans la BD de Headquarters pendant toute la durée de vie de votre environnement de production.
1. Dans le cadre de la procédure de clôture de l’exercice, un journal des totaux généraux de la période est traité dans Headquarters et une archive fiscale est produite à partir de la BD de Headquarters. L’archive comprend les totaux des ventes d’un magasin pour la période fiscale, ainsi que les détails et les signatures de toutes les équipes, transactions de vente et événements d’audit au cours de la période fiscale. Le journal du total général de la période et les archives fiscales sont signés numériquement. Pour plus d’informations sur les journaux de total général de période, voir [Journal du total général de la période](#period-grand-total-journal). Pour plus d’informations sur les archives fiscales, voir [Archives fiscales de la France](./emea-fra-fiscal-archive.md).

## <a name="france-specific-pos-features"></a>Fonctionnalités du PDV spécifiques à la France

Les fonctionnalités de point de vente spécifiques à la France suivantes sont activées lorsque l’adresse principale de l’entité juridique à laquelle appartient le magasin est en France.

### <a name="registration-of-audit-events"></a>Enregistrement des événements d’audit

Si l’option **Audit** dans le profil de fonctionnalité du PDV est définie sur **Oui**, les événements suivants sont enregistrés dans le journal d’événements d’audit du PDV :

- Connexion
- Déconnexion
- Impression d’une copie d’un ticket de caisse
- Démarrage du mode hors ligne
- Fin du mode hors ligne
- Application d’un remplacement de gestionnaire
- Annulation d’une transaction 
- Annulation d’une ligne de transaction
- Clôture d’une équipe
- Nettoyage des transactions de la base de données des canaux
- Application d’une mise à jour majeure du logiciel avec impact sur la conformité

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

Seuls les événements d’audit [spécifiques à la France](#registration-of-audit-events) sont signés. Trois séquences distinctes d’événements d’audit signés numériquement sont conservées par registre :

- Séquence des événements d’audit **Équipe de travail clôturée** qui sont enregistrés lorsque les équipes de travail sont clôturées
- Séquence des événements d’audit **Copie de ticket de caisse imprimée** qui sont enregistrés lors de l’impression des copies de ticket de caisse
- La séquence des autres événements d’audit signés

Les événements d’audit qui ne sont pas signés numériquement sont exclus de ces séquences.

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
- Informations sur une copie de ticket de caisse :

    - **Réimprimer le message** : une copie de ticket de caisse peut inclure une légende « Copie ».
    - **Réimprimer le numéro** – Un ticket de caisse d’origine ou une copie de ticket de caisse peut inclure le numéro de la copie du ticket de caisse. Pour un ticket de caisse d’origine, la valeur est **0** (zéro).
    - **Date de réimpression** : une copie du ticket de caisse peut inclure la date de la copie.
    - **Temps de réimpression** : une copie du ticket de caisse peut inclure l’heure de la copie au format 12 heures ou au format 24 heures.
    - **Réimprimer la signature** : la copie d’un ticket de caisse peut inclure un extrait de la signature numérique de la copie.

- **Nombre de lignes** – Un ticket de caisse peut inclure le nombre de lignes d’articles imprimées sur le ticket de caisse.
- **Totaux des ventes** – Les champs personnalisés des totaux de tickets de caisse excluent les montants hors ventes des montants de transaction totaux. Les montants hors ventes incluent les montants des opérations suivantes :

    - Acomptes (dépôts sur comptes client)
    - Acomptes pour les commandes client (dépôts sur commandes client)
    - Émission d’une carte cadeau
    - Ajout de fonds à une carte cadeau

- **Données de certification** : un ticket de caisse peut inclure la catégorie et le numéro du certificat de conformité qu’un organisme autorisé a émis conformément aux exigences de certification de la norme NF 525.
- **Version du logiciel** : un ticket de caisse peut comprendre la version du logiciel qui a été certifiée selon les exigences de certification NF 525 et qui sert à établir les tickets de caisse.

### <a name="restricting-the-duration-of-shifts"></a>Limitation de la durée des équipes

Il existe une option pour appliquer la clôture d’équipe quotidienne dans le PDV. Une équipe ne peut pas durer plus longtemps que la durée spécifiée dans le champ **Heure de clôture de l’équipe de travail**. (Temps d’utilisation de la machine sur laquelle le PDV est installé.) Plusieurs minutes avant cette heure, l’opérateur commencera à recevoir des avertissements que l’équipe doit être clôturée. Le nombre de minutes est déterminé par la valeur du champ **Intervalle de clôture de l’équipe de travail (minutes)**. Si l’équipe est clôturée et redémarrée dans l’intervalle d’avertissement, la vente peut continuer après l’heure de clôture de l’équipe. Sinon, l’achèvement de la transaction de vente sera bloqué et l’opérateur devra soit annuler soit suspendre la transaction, clôturer l’équipe, ouvrir une nouvelle équipe, puis rappeler et terminer la transaction.

### <a name="x-and-z-reports"></a>États X et Z

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
| PerpetualGrandTotalAbsoluteValue | Le total général perpétuel cumulé (valeur absolue) pour l’équipe. Autrement dit, le total général perpétuel cumulé (valeur absolue) de l’équipe précédente du même registre, plus le montant total des ventes TTC pour l’équipe, plus la valeur absolue du montant total des retours TTC de l’équipe. |
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

Les journaux des totaux généraux de la période résument les totaux des ventes par magasin et par période fiscale (par exemple, par mois) et doivent être utilisés dans le cadre de la procédure de clôture de la période fiscale. En outre, un journal annuel récapitule les totaux des ventes par magasin et par exercice financier et doit être utilisé dans le cadre de la procédure de clôture de l’exercice.

Avant de créer un journal des totaux généraux de la période, vous devez vous assurer que les données des ventes au détail pour le magasin et la période fiscale sont téléchargées vers Commerce headquarters et traitées dans les relevés de vente au détail.

Les journaux du total général de la période sont tenus à jour sur la page **Journal du total général de la période**.

1. Pour créer un journal, vous devez spécifier un magasin. Si des journaux précédent existent pour le magasin, la prochaine période fiscale après le dernier journal clôturé pour le magasin est automatiquement utilisée comme période de journal. Si aucun journal précédent n’existe, vous pouvez spécifier la date de fin du journal. Dans ce cas, la période fiscale qui inclut la date spécifiée est utilisée comme période de journal.
1. Le journal peut ensuite être calculé. Les équipes clôturées au cours de la période de journal sont sélectionnées, et les totaux sont calculés pour les équipes. Vous pouvez afficher les totaux des taxes du journal par code de taxe de vente et les équipes incluses dans le journal. Vous pouvez également sélectionner **Fonctions \> Effacer le journal** pour effacer les résultats du calcul et renvoyer le journal au statut **Nouveau**.
1. Lorsque le journal est calculé, il peut être clôturé. Un journal clôturé ne peut pas être modifié, et un autre journal ne peut pas être créé pour une période fiscale précédente, la même période, ou une période les recoupant. Toutefois, le dernier journal clôturé pour un magasin peut être annulé. Dans ce cas, un autre journal peut être créé pour le même magasin et la période fiscale.

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

Vous devez créer et clôturer des journaux de total général de période pour tous les magasins à chaque période fiscale. La maintenance des journaux peut être automatisée en utilisant les deux procédures périodiques suivantes qui peuvent être exécutées en mode de traitement par lots :

- **Créer des journaux du total général de la période** : cette procédure crée et éventuellement calcule les journaux des magasins sélectionnés pour une période donnée. Vous devez sélectionner une période spécifique pour la procédure. Par conséquent, vous devez créer manuellement un traitement par lots pour chaque période et ne pouvez pas utiliser la récurrence. La procédure ne ferme pas les journaux, car il est prévu que chaque journal soit validé manuellement avant d’être fermé.
- **Exporter l’archive** : cette procédure exporte les archives des magasins sélectionnés pour une période donnée. Vous devez sélectionner une période spécifique pour la procédure et ne pouvez pas utiliser la récurrence.

Un journal du total général d’une période peut également être marqué comme **Annuel** quand il est créé. Un journal annuel résume les journaux du total général de la période pour les périodes fiscales d’un exercice. Un journal annuel peut être créé pour un exercice uniquement si un journal pour la dernière période fiscale de l’exercice a été créé, calculé et clôturé. Cependant, les journaux n’ont pas besoin d’exister pour *toutes* les périodes fiscales de l’exercice. Par exemple, si un nouveau magasin est ouvert au milieu de l’année, le premier journal correspond à la période fiscale au cours de laquelle le magasin est ouvert. Dans ce cas, le premier journal annuel résume les journaux pour les périodes fiscales à partir de la période fiscale au cours de laquelle le magasin est ouvert jusqu’à la dernière période fiscale de l’exercice.

### <a name="fiscal-archive"></a>Archives fiscales

Une archive fiscale est un fichier XML qui peut être exporté depuis un journal du total général de la période qui a été clôturée. Il comprend les totaux de la période clôturée. Il comprend également des données détaillées sur les transactions de vente et les événements. Le fichier exporté est numériquement signé, et la signature est contenue dans un fichier distinct. Les archives fiscales exportées doivent être conservées sur des supports externes sécurisés pendant la durée légale de conservation.

Commerce comprend également un outil qui peut être utilisé pour vérifier l’intégrité des archives fiscales et pour détecter les violations de la signature de l’archive et des chaînes d’enregistrements signés dans l’archive. Cet outil prend la forme d’un script Windows PowerShell disponible via le kit de développement logiciel (SDK) Commerce. Pour des informations détaillées sur la structure du format des archives fiscales et des conseils sur l’utilisation de l’outil de vérification de l’intégrité des archives fiscales, voir [Archives fiscales pour la France](./emea-fra-fiscal-archive.md).

## <a name="set-up-commerce-for-france"></a>Configurer Commerce pour la France

Cette section décrit les paramètres Commerce spécifiques et recommandés pour la France. Pour plus d’informations sur les fonctionnalités et les paramètres courants de Commerce, consultez [Page d’accueil Commerce](../index.md).

Pour utiliser la fonctionnalité spécifique pour la France, vous devez effectuer les tâches suivantes :

- Définissez le champ **Pays/région** sur **FRA** (France) dans l’adresse principale de l’entité juridique.
- Définissez le champ **Code ISO** sur **FR** (France) dans le profil de fonctionnalité du PDV de chaque magasin situé en France.

Vous devez également spécifier les paramètres suivants pour la France. Notez que vous devez exécuter des tâches de distribution appropriées après que vous avez terminé le paramétrage.

1. [Activer les fonctionnalités Commerce](#enable-features-for-france) pour la France dans l’espace de travail **Gestion des fonctionnalités**.
1. [Spécifiez divers numéros d’enregistrement](#set-up-the-legal-entity) de l’organisation, comme l’identifiant TVA, sur la page **Entités juridiques**. Ces numéros d’enregistrement seront utilisés lors de l’exportation des archives fiscales.
1. [Configuration de la TVA](#set-up-vat-per-french-requirements) conformément à la réglementation française sur la TVA.
1. [Paramétrage des profils de fonctionnalité de PDV](#set-up-pos-functionality-profiles) pour activer les fonctionnalités et les options requises pour la France.
1. [Configurez des champs personnalisés](#configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts) et les [formats de ticket de caisse](#configure-receipt-formats) pour se conformer aux exigences réglementaires locales.
1. [Configurez la fonctionnalité d’enregistrement fiscal](#set-up-fiscal-registration) pour la France pour permettre la signature numérique des transactions de vente et des événements d’audit.
1. [Configurez les certificats numériques](#configure-the-digital-signature-parameters) et d’autres paramètres de signature numérique pour le canal Commerce et Commerce headquarters.
1. [Spécifiez les formats d’état électronique (ER)](#configure-the-z-report-and-archive-export-formats) qui devraient être utilisés pour exporter les états Z et les archives fiscales de Commerce headquarters.
1. [Réinitialisez les composants Commerce](#reinitialize-commerce-components) pour permettre des événements d’audit spécifiques à la France et la transmission de données spécifiques à la France du PDV à Commerce headquarters.
1. [Configurez les composants du canal](#configure-channel-components) pour activer les extensions des composants propres à la France.

    > [!IMPORTANT]
    > Vous devez configurer les composants du canal uniquement si vous utilisez Commerce version 10.0.28 ou antérieure. À partir de la version 10.0.29, tous les composants de canal de Commerce requis pour la France sont activés par défaut. Si vous utilisez la version 10.0.28 ou une version antérieure de Commerce et que vous migrez vers la version 10.0.29 ou une version ultérieure, vous devez suivre les étapes décrites dans [Migrer vers la version 10.0.29 ou ultérieure](./emea-fra-fi-deployment.md#migrate-to-commerce-version-10029-or-later).

1. [Activer la signature numérique en mode hors connexion](#enable-the-digital-signature-in-offline-mode).
1. [Validez votre configuration](#compliance-checklist) pour veiller à ce que toutes les fonctionnalités spécifiques à la France fonctionnent correctement.

### <a name="enable-features-for-france"></a>Activer les fonctionnalités pour la France

Vous devez activer les fonctionnalités suivantes dans l’espace de travail **Gestion des fonctionnalités** :

- (France) Activer les événements d’audit supplémentaires dans le PDV
- (France) Activer des informations supplémentaires dans des relevés générés en fin de journée dans le PDV
- (France) Activer l’exportation d’un Z de caisse vers un fichier

### <a name="set-up-the-legal-entity"></a>Paramétrer l’entité juridique

Vous devez apporter les modifications suivantes dans la page **Entités juridiques**. Ces paramètres sont utilisés dans le format d’archive.

- Dans l’organisateur **Informations sur le compte en banque**, dans le champ **Numéro d’acheminement**, spécifiez l’identifiant TVA de l’organisation.
- Dans l’organisateur **Numéros d’inscription**, dans le champ **Code NAF**, spécifiez le code NAF (Nomenclature des Activités Françaises) de l’organisation.
- Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, spécifiez le numéro de SIRET (Système d’identification du répertoire des établissements) de l’organisation.

### <a name="set-up-vat-per-french-requirements"></a>Paramétrer la TVA selon les exigences de la France

Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation de la taxe, voir [Vue d’ensemble des taxes](/dynamics365/finance/general-ledger/indirect-taxes-overview).

Vous devez également spécifier des groupes de taxe et activer l’option **Prix, taxe incluse** pour les magasins situés en France.

### <a name="set-up-pos-functionality-profiles"></a>Paramétrage des profils de fonctionnalité de PDV

Vous devez activer l’impression des états Z en définissant l’option **Imprimer le X/Z de caisse du PDV** sur **Oui**.

Vous devez activer l’audit en définissant l’option **Audit** sur **Oui**.

Pour appliquer la clôture d’équipe quotidienne, vous devez apporter les modifications suivantes :

- Définissez l’option **Appliquer la clôture quotidienne de l’équipe de travail** sur **Oui**.
- Définissez les champs **Heure de clôture de l’équipe de travail** et **Intervalle de clôture de l’équipe de travail (minutes)**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Vous pouvez configurer les champs de texte en langue étrangère et personnalisés utilisés dans les formats de ticket de caisse du PDV. La société par défaut de l’utilisateur qui crée le paramétrage de ticket de caisse doit être la même entité juridique que celle dans laquelle le paramétrage du texte en langue étrangère est créé. Sinon, les mêmes textes en langue étrangère doivent être créés dans la société par défaut et l’entité juridique de l’utilisateur du magasin pour lequel le paramétrage est créé.

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins. Toutefois, les valeurs **ID texte** que vous utilisez doivent être uniques, elles doivent être égales ou supérieures à 900001.

| ID langue | ID texte | Texte                      |
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
| fr-FR       | 900012  | Date de réimpression              |
| fr-FR       | 900013  | Temps de réimpression 12H          |
| fr-FR       | 900014  | Temps de réimpression 24H          |
| fr-FR       | 900015  | Réimprimer la signature numérique |

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
| REPRINTDATE_FR                  | Récépissé | 900012          |
| REPRINTTIME12H_FR               | Récépissé | 900013          |
| REPRINTTIME24H_FR               | Récépissé | 900014          |
| REPRINTDIGITALSIGNATURE_FR      | Récépissé | 900015          |

### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour chaque format de ticket de caisse nécessaire, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer**. Vous devez également configurer des profils matériels pour prendre en charge les imprimantes de ticket de caisse et pour activer la station matérielle. Pour plus d’informations sur l’utilisation des périphériques de PDV, voir [Périphériques](../retail-peripherals-overview.md).

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans les sections du ticket de caisse approprié. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente.

- **En-tête :** Ajoutez le champ suivant :

    - **Type de transaction** – Ce champ identifie le type de ticket de caisse.
    - **Réimprimer le message** : ce champ standard imprime une légende « Copie » sur une copie de ticket de caisse.

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
    - **Réimprimer le numéro** – Ce champ imprime le numéro d’une copie de ticket de caisse. Pour un ticket de caisse d’origine, la valeur est **0** (zéro).
    - **Réimprimer la date** : ce champ imprime la date d’une copie de ticket de caisse.
    - **Temps de réimpression 12H** ou **Temps de réimpression 24H** : ce champ imprime l’heure d’une copie du ticket de caisse au format sélectionné.
    - **Réimprimer la signature numérique** : ce champ imprime une extraction de la signature numérique d’une copie du ticket de caisse.
    - **Certificat NF 525** : ce champ imprime la catégorie du certificat de conformité et son numéro qu’un organisme autorisé a émis vers la version 10 de Dynamics 365 Commerce conformément aux exigences de certification de la norme NF 525.
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
1. [Activer l’exécution manuelle d’un enregistrement fiscal différé](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).

#### <a name="configure-the-fiscal-registration-process"></a>Configurer le processus d’enregistrement fiscal

Pour activer le processus d’enregistrement fiscal pour la France dans Commerce Headquarters, procédez comme suit.

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal à partir du SDK Commerce :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    2. Ouvrez la dernière branche de version disponible.
    3. Ouvrez **src \> FiscalIntegration \> SequentialSignatureFrance \> Configurations**.
    4. Téléchargez le fichier de configuration du connecteur fiscal sur **Connecteur \> ConnectorMicrosoftSequentialSignatureFRA.xml**.
    5. Téléchargez le fichier de configuration du fournisseur de document sur **DocumentProvider \> DocumentProviderMicrosoftSequentialSignatureFRA.xml**.

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

Pour configurer des certificats et des profils de certificat pouvant être utilisés pour la signature numérique, suivez les étapes dans [Configurer des profils de certificat](./certificate-profiles-for-retail-stores.md#set-up-certificate-profiles).

Une fois les profils de certificat configurés, accédez à **Vente au détail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques du connecteur**, sélectionnez le profil technique du connecteur que vous avez créé précédemment, puis, sur le raccourci **Paramètres**, définissez les paramètres suivants pour les signatures numériques :

- **Profil du certificat** : sélectionnez le profil de certificat configuré précédemment.
- **Algorithme de hachage** : spécifiez l’un des algorithmes de hachage cryptographique pris en charge par Microsoft .NET (par exemple, **SHA256**).
- **Activer le contrôle d’intégrité** : pour plus d’informations sur la procédure de contrôle d’intégrité, voir [Contrôle d’intégrité d’enregistrement fiscal](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

Enfin, sur la page **Paramètres Commerce** (**Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres Commerce**), vous devez spécifier les paramètres suivants pour la signature numérique côté Commerce Headquarters :

- **Certificat** : sélectionnez un certificat stocké dans Key Vault.
- **Fonction de hachage** – Spécifiez l’un des algorithmes de hachage cryptographique pris en charge par Microsoft .NET, tel que **SHA256**.
- **Encodage** – Spécifiez l’encodage des données signées, tel que **UTF-8**.
- Vous pouvez également spécifier une souche de numéros à utiliser pour la numérotation automatique des journaux de total général de la période. Sur l’onglet **Souches de numéros**, sélectionnez un enregistrement où le champ **Référence** est défini sur **Journal du total général de la période**, puis sélectionnez-y un code de souche de numéros.

> [!NOTE]
> Les fonctions de hachage suivantes ne sont pas acceptables : CRC16, CRC32, SHA-1 et MD5. Commerce prend uniquement en charge les fonctions de hachage SHA256, SHA384 et SHA512. Si vous souhaitez utiliser une fonction de hachage différente, vous devez implémenter une personnalisation.

### <a name="configure-the-z-report-and-archive-export-formats"></a>Configurer les formats d’exportation des archives et des Z de caisse

En fonction de vos objectifs, vous pouvez télécharger les configurations ER pour l’état Z et les archiver à partir des sources suivantes :

- Si vous n’avez pas besoin de personnaliser les configurations ER fournies par Microsoft ou de créer vos propres configurations ER, vous pouvez importer les configurations fournies par Microsoft à partir de Microsoft Dynamics Lifecycle Services. Pour plus d’informations, consultez [Importer une configuration de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). Sinon, vous pouvez [télécharger les configurations des états électroniques (ER) à partir du référentiel global du service de configuration](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).
- Si vous devez personnaliser les configurations ER fournies par Microsoft ou créer vos propres configurations ER, vous devez provisionner un environnement Regulatory Configuration Services (RCS). Pour plus d’informations sur l’utilisation de RCS, voir [Importer les configurations ER depuis RCS](../../fin-ops-core/dev-itpro/analytics/rcs-download-configurations.md).

Vous devez télécharger les versions suivantes (ou les versions ultérieures) des configurations :

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

> [!IMPORTANT]
> Vous devez configurer les composants du canal uniquement si vous utilisez Commerce version 10.0.28 ou antérieure. À partir de la version 10.0.29, tous les composants de canal de Commerce requis pour la France sont activés par défaut. Si vous utilisez la version 10.0.28 ou une version antérieure de Commerce et que vous migrez vers la version 10.0.29 ou une version ultérieure, vous devez suivre les étapes décrites dans [Migrer vers la version 10.0.29 ou ultérieure](./emea-fra-fi-deployment.md#migrate-to-commerce-version-10029-or-later).

Pour activer la fonctionnalité spécifique à la France, vous devez configurer les extensions des composants de canal. Pour plus d’informations, voir les [instructions de déploiement](./emea-fra-fi-deployment.md).

> [!NOTE]
> Cette version de la fonctionnalité Commerce pour la France est basée sur le [cadre de l’intégration fiscale](./fiscal-integration-for-retail-channel.md). Pour plus d’informations sur l’exemple de signature numérique hérité pour la France, voir [Instructions de déploiement de caisses enregistreuses pour la France (héritées)](./emea-fra-deployment.md). Pour obtenir des instructions sur la façon d’activer la fonctionnalité d’intégration fiscale pour la France dans les environnements existants qui utilisent l’exemple de signature numérique hérité, voir [Effectuer une migration depuis l’ancienne fonctionnalité Commerce pour la France](./emea-fra-fi-migration.md).

### <a name="enable-the-digital-signature-in-offline-mode"></a>Activer la signature numérique en mode hors connexion

Pour activer la signature numérique en mode hors connexion, vous devez suivre ces étapes après avoir activé le PDV sur un nouvel appareil.

1. Connectez-vous à POS.
1. Sur la page **Statut de la connexion à la base de données**, assurez-vous que la base de données hors connexion est entièrement synchronisée. Lorsque la valeur du champ **Téléchargements en attente** est **0** (zéro), la base de données est entièrement synchronisée.
1. Déconnectez-vous du PDV.
1. Attendez que la base de données hors connexion soit entièrement synchronisée.
1. Connectez-vous à POS.
1. Sur la page **Statut de la connexion à la base de données**, assurez-vous que la base de données hors connexion est entièrement synchronisée. Lorsque la valeur du champ **Transactions en attente dans la base de données hors connexion** est **0** (zéro), la base de données est entièrement synchronisée.
1. Redémarrer le PDV.

## <a name="compliance-checklist"></a>Liste de contrôle de conformité

Cette section décrit des scénarios de base que vous pouvez effectuer pour valider que votre environnement est correctement configuré afin qu’il soit conforme aux exigences de caisse enregistreuse pour la France. Ces scénarios peuvent être complétés en série, de sorte qu’ils constituent une liste de contrôle de conformité complète de bout en bout. Nous vous recommandons de commencer la validation avec une base de données propre, afin de pouvoir valider facilement les numéros séquentiels et les montants perpétuels.

1. [Préparation](#1-preparation)
1. [Vente de base](#2-basic-sale)
1. [Retour de base](#3-basic-return)
1. [Émettre une carte cadeau](#4-issue-gift-card)
1. [Commande client](#5-customer-order)
1. [Commande client hybride](#6-hybrid-customer-order)
1. [Vente en mode hors connexion](#7-sale-in-offline-mode)
1. [Transaction hors vente (dépense)](#8-non-sale-transaction-expense)
1. [Imprimer une copie du ticket de caisse](#9-print-receipt-copy)
1. [Événements d’audit](#10-audit-events)
1. [Clôturer l’équipe de travail et imprimer l’état Z](#11-close-shift-and-print-z-report)
1. [Restriction de durée de l’équipe de travail](#12-shift-duration-restriction)
1. [Traiter le journal du total général de la période](#13-process-period-grand-total-journal)
1. [Exporter et vérifier les archives fiscales](#14-export-and-verify-fiscal-archive)

### <a name="validation"></a>Validation

#### <a name="validate-a-sales-transaction"></a>Valider la transaction commerciale

Pour valider une transaction de vente signée numériquement une fois qu’elle est terminée, procédez comme suit.

1. Dans le PDV, vérifiez que tous les [champs spécifiques à la France](#configure-receipt-formats) du ticket de caisse, à l’exception des champs liés à une copie du ticket de caisse, sont imprimés et ont des valeurs correctes. Pour vérifier certains des champs, vous devez compléter l’étape suivante.
1. Dans Commerce Headquarters, procédez comme suit :

    1. Exécutez la tâche P pour télécharger les données de transaction de détail à Commerce headquarters.
    1. Ouvrez la page **Transactions du magasin**, et sélectionnez la transaction récemment complétée.
    1. Sur le raccourci **Opérations fiscales**, vérifiez qu’il existe une transaction fiscale dont le statut d’enregistrement est réussi.
    1. Vérifiez que le texte dans le champ **Réponse du registre fiscal** est au format JavaScript Object Notation (JSON) et contient les informations suivantes :

        - Signature numérique de la transaction
        - Chaîne utilisée pour la signature numérique de la transaction
        - Numéro séquentiel de transaction signé
        - Empreinte numérique du certificat utilisée pour la signature numérique
        - Algorithme de hachage
        - La version de l’algorithme de signature numérique, qui peut être utilisée ultérieurement pour vérifier la signature numérique

    1. Vous pouvez également sélectionner **Données étendues** et afficher des propriétés spécifiques de la transaction fiscale, telles que la signature, le numéro séquentiel, l’empreinte numérique du certificat et l’identificateur de l’algorithme de hachage.
    1. Vérifiez que le numéro séquentiel de la transaction signée est égal au numéro séquentiel de la transaction de vente signée précédente sur le même registre (s’il y a une transaction de vente signée précédente) plus 1. Ce numéro séquentiel doit également être imprimé dans le champ **Numéro séquentiel** du ticket de caisse.
    1. Vérifiez la chaîne utilisée pour la [signature numérique de la transaction](#digital-signing-of-sales-and-return-transactions). Validez les montants de la transaction, le numéro de registre et d’autres données. Vérifiez la signature précédente pour la même caisse enregistreuse.
    1. Vérifiez que le champ **Signature numérique** du ticket de caisse contient un extrait de la signature numérique de la transaction, et qu’il consiste en une concaténation des troisième, septième, treizième et dix-neuvième symboles de la signature.
    1. Notez le numéro séquentiel de la transaction signée et sa signature numérique, afin que vous puissiez utiliser ces informations pour une validation ultérieure de la prochaine transaction.

#### <a name="validate-a-shift"></a>Valider une équipe de travail

Pour valider une équipe de travail signée numériquement une fois qu’elle est clôturée, procédez comme suit.

1. Dans le PDV, vérifiez que tous les [champs spécifiques à la France](#x-and-z-reports) de l’état Z sont imprimés et ont des valeurs correctes. Pour vérifier certains des champs, vous devez compléter l’étape suivante.
1. Dans Commerce Headquarters, procédez comme suit :

    1. Exécutez la tâche P pour télécharger les données de transaction de détail à Commerce headquarters.
    1. Ouvrez la page **Équipes de travail** et sélectionnez l’équipe de travail récemment clôturée.
    1. Comparez les champs spécifiques à la France (c’est-à-dire **Ventes totales**, **Nombre total de retours**, **Total général**, **Total général perpétuel cumulé** et **Total général perpétuel cumulé (valeur absolue)**) avec les champs imprimés sur l’état Z.
    1. Sélectionnez **Transactions de taxes d’équipe de travail**, comparez les montants de TVA par taux de taxe avec les montants de TVA imprimés sur l’état Z, puis fermez la page **Transactions de taxes d’équipe de travail**.
    1. Sur la page **Équipes de travail**, sélectionnez **Auditer les événements**. L’événement d’audit qui a été enregistré lors de la clôture de l’équipe doit être affiché, et le champ **Chaîne de journal** doit contenir le numéro d’équipe.
    1. Sur le raccourci **Résultats de l’enregistrement fiscal**, vérifiez qu’il existe une transaction fiscale dont le statut d’enregistrement est réussi.
    1. Vérifiez que le texte dans le champ **Réponse du registre fiscal** est au format JSON et contient les informations suivantes :

        - Signature numérique de l’équipe de travail
        - Chaîne utilisée pour la signature numérique de l’équipe de travail
        - Numéro séquentiel de l’équipe de travail ayant signé
        - Empreinte numérique du certificat utilisée pour la signature numérique
        - Algorithme de hachage
        - La version de l’algorithme de signature numérique, qui peut être utilisée ultérieurement pour vérifier la signature numérique

    1. Vérifiez que le numéro séquentiel de l’équipe ayant signé est égal au numéro séquentiel de l’équipe clôturée précédente ayant signé sur le même registre (s’il y a une équipe clôturée précédente ayant signé) plus 1.
    1. Vérifiez la chaîne utilisée pour la [signature numérique de l’équipe de travail](#digital-signing-of-closed-shifts). Validez les montants de l’équipe de travail et d’autres données. Vérifiez la signature précédente pour la même caisse enregistreuse.
    1. Notez le numéro séquentiel de l’équipe ayant signé et sa signature numérique, afin que vous puissiez utiliser ces informations pour une validation ultérieure de la prochaine équipe.

#### <a name="validate-an-audit-event"></a>Valider un événement d’audit

Pour valider un événement d’audit signé numériquement, procédez comme suit.

1. Dans Commerce headquarters, exécutez la tâche P pour télécharger les données d’événement d’audit vers Commerce headquarters.
1. Ouvrez la page **Événements d’audit** et sélectionnez un événement d’audit. Vous pouvez utiliser les champs **Numéro de magasin**, **Numéro de registre**, **Type d’événement**, **Date**, et **Heure** pour trouver l’événement. Le champ **Chaîne de journal** contient la description de l’événement.
1. Sur le raccourci **Résultats de l’enregistrement fiscal**, vérifiez qu’il existe une transaction fiscale dont le statut d’enregistrement est réussi.
1. Vérifiez que le texte dans le champ **Réponse du registre fiscal** est au format JSON et contient les informations suivantes :

    - Signature numérique de l’événement
    - Chaîne utilisée pour la signature numérique de l’événement
    - Numéro séquentiel de l’événement signé
    - Empreinte numérique du certificat utilisée pour la signature numérique
    - Algorithme de hachage
    - La version de l’algorithme de signature numérique, qui peut être utilisée ultérieurement pour vérifier la signature numérique

1. Vérifiez que le numéro séquentiel de l’événement signé est égal au numéro séquentiel de l’événement précédent signé du même type de séquence d’événement sur le même registre (s’il y a un événement précédent signé) plus 1.

    > [!NOTE]
    > Seuls les événements d’audit [spécifiques à la France](#registration-of-audit-events) sont signés. Trois séquences distinctes d’événements d’audit signés numériquement sont conservées par registre. Les événements d’audit qui ne sont pas signés numériquement sont exclus de ces séquences.
    >
    > - Séquence des événements d’audit **Équipe de travail clôturée** qui sont enregistrés lorsque les équipes de travail sont clôturées
    > - Séquence des événements d’audit **Copie de ticket de caisse imprimée** qui sont enregistrés lors de l’impression des copies de ticket de caisse
    > - La séquence des autres événements d’audit signés

1. Vérifiez la chaîne utilisée pour la [signature numérique de l’événement](#digital-signing-of-events). Validez le code d’événement prédéfini, la description de l’événement et d’autres données. Vérifiez la signature précédente de l’événement du même type de séquence d’événements pour le même registre.
1. Notez le numéro séquentiel de l’événement signé et sa signature numérique, afin que vous puissiez utiliser ces informations pour une validation ultérieure du prochain événement.

### <a name="1-preparation"></a>1. Préparation

1. Dans Commerce Headquarters, procédez comme suit :

    1. [Configurer Commerce pour la France](#set-up-commerce-for-france).
    1. Exécutez les travaux de distribution appropriés ou la tâche **9999** (**Toutes les tâches**).

1. Dans le PDV, procédez comme suit :

    1. Connectez-vous au PDV, et ouvrez une nouvelle équipe.
    1. Ouvrez la page **Paramètres**.
    1. Sous **France**, dans la section **Certification NF 525**, sélectionnez **Voir les détails**.
    1. Dans la boîte de dialogue **Certification NF 525**, passez en revue le nom et la version du logiciel, la catégorie de certification et le numéro de certificat NF 525.
    1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments et payez le montant exact.
    1. Revenez à **Accueil**, et sélectionnez **Afficher le journal**.
    1. Sur la page **Journal des transactions**, sélectionnez la transaction de vente précédente et renvoyez-en un article. Payez le montant exact.
    1. Clôturez l’équipe de travail.
    1. [Validez les transactions](#validate-a-sales-transaction). Notez le numéro séquentiel de la dernière transaction signée (à savoir, la transaction de retour) et sa signature numérique, afin que vous puissiez utiliser ces informations pour une validation ultérieure de la prochaine transaction.
    1. [Valider l’équipe de travail](#validate-a-shift). Notez le numéro séquentiel de l’équipe ayant signé, sa signature numérique, son total général perpétuel cumulé et le total général perpétuel cumulé des valeurs absolues des ventes et des retours, afin que vous puissiez utiliser ces informations pour une validation ultérieure dans des scénarios ultérieurs.

### <a name="2-basic-sale"></a>2. Vente de base

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments et payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction).

### <a name="3-basic-return"></a>3. Retour de base

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez un élément, puis sélectionnez **Retourner le produit**. Sélectionnez ou spécifiez un code de motif selon vos besoins.
1. Payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction). Notez que les montants dans la chaîne utilisée pour la signature numérique de la transaction sont négatifs, mais le type de transaction est toujours **Vente**. Pour la signature numérique, les transactions de retour sont considérées comme des transactions de vente régulières. De même, le champ **Type de transaction** du ticket de caisse doit préciser **Vente**.

### <a name="4-issue-gift-card"></a>4. Émettre une carte cadeau

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, sélectionnez **Émettre une carte-cadeau**, puis précisez le numéro de la nouvelle carte cadeau et le montant à y ajouter.
1. Payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction). Notez que la transaction n’est pas signée numériquement. Aucune signature n’est imprimée sur le ticket de caisse.
1. Dans le PDV, sur la page **Transaction en cours**, ajoutez plusieurs éléments.
1. Sélectionnez **Émettre une carte-cadeau**, puis précisez le numéro de la nouvelle carte cadeau et le montant à y ajouter.
1. Payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction). Notez que le montant de la carte-cadeau est exclu du montant total de la transaction de vente, à la fois sur le ticket de caisse et dans les données de transaction qui ont été utilisées pour la signer numériquement.

### <a name="5-customer-order"></a>5. Commande client

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments.
1. Ajoutez un client à la transaction.
1. Sélectionnez **Créer une commande client**.
1. Sélectionnez **Prélever tout**, sélectionnez un magasin et une date, puis confirmez l’opération.
1. Payez le montant exact (c’est-à-dire l’acompte).
1. [Validez la transaction](#validate-a-sales-transaction). Notez que la transaction n’est pas signée numériquement. Aucune signature n’est imprimée sur le ticket de caisse.
1. Dans le PDV, sélectionnez **Rappeler la commande**, et recherchez la commande précédemment créée.
1. Sélectionnez **Prélever**, spécifiez les quantités prélevées, puis confirmez l’opération.
1. Payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction). Vérifiez que le montant total de la transaction de vente ne comprend que les articles prélevés. Le montant de l’acompte appliqué n’est pas exclu du montant total.

### <a name="6-hybrid-customer-order"></a>6. Commande client hybride

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments.
1. Ajoutez un client à la transaction.
1. Sélectionnez **Créer une commande client**.
1. Sélectionnez **Prélever tout**, sélectionnez un magasin et une date, puis confirmez l’opération.
1. Ajoutez un article, puis sélectionnez **Exécuter la sélection**.
1. Payez le montant exact (c’est-à-dire l’acompte), plus le montant de l’article marqué comme **Exécuter**.
1. [Validez la transaction](#validate-a-sales-transaction). Vérifiez que le ticket de caisse contient une signature numérique et que le montant total de la transaction de vente ne comprend que l’article à traiter.
1. Dans le PDV, sélectionnez **Rappeler la commande**, et recherchez la commande précédemment créée.
1. Sélectionnez **Prélever**, spécifiez les quantités prélevées, puis confirmez l’opération.
1. Payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction). Vérifiez que le montant total de la transaction de vente ne comprend que les articles prélevés. Le montant de l’acompte appliqué n’est pas exclu du montant total.

### <a name="7-sale-in-offline-mode"></a>7. Vente en mode hors connexion

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Utilisez l’opération **Statut de connexion à la base de données** pour déconnecter manuellement le PDV depuis Commerce Scale Unit et basculer le PDV en mode hors ligne.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments et payez le montant exact.
1. Utilisez l’opération **Statut de connexion à la base de données** pour connecter manuellement le PDV depuis Commerce Scale Unit et basculer le PDV en mode en ligne. Attendez que la synchronisation entre la base de données hors ligne et la base de données des canaux soit terminée.
1. [Validez la transaction](#validate-a-sales-transaction). Notez que la transaction est signée numériquement et que la séquence des signatures numériques n’est pas rompue.

### <a name="8-non-sale-transaction-expense"></a>8. Transaction hors vente (dépense)

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Exécutez l’opération **Comptes de dépenses**, sélectionnez un compte de dépenses, spécifiez le montant de la dépense et confirmez l’opération.
1. Payez le montant exact.
1. [Validez la transaction](#validate-a-sales-transaction). Notez que la transaction n’est pas signée numériquement. Aucune signature n’est imprimée sur le ticket de caisse.

### <a name="9-print-receipt-copy"></a>9. Imprimer une copie du ticket de caisse

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments et payez le montant exact.
1. Revenez à **Accueil**, sélectionnez **Afficher le journal**, puis sélectionnez la transaction de vente récemment conclue.
1. Sélectionnez **Afficher le reçu**, puis, dans l’aperçu du reçu, sélectionnez **Imprimer \> Imprimer**.
1. Vérifiez la copie imprimée du ticket de caisse. Notez la légende « Copie » sur le ticket de caisse. Vérifiez les données de la copie, telles que la valeur **Réimprimer le numéro** (elle devrait être **1**), la **Réimprimer la date** et **Réimprimer l’heure**, et l’extrait de la signature numérique de la copie.
1. Fermez l’aperçu du ticket de caisse.
1. [Validez l’événement d’audit de la copie du ticket de caisse](#validate-an-audit-event). L’événement d’audit est de type **Copie du ticket de caisse imprimé**. Vérifiez que le champ **Réimprimer la signature numérique** de la copie du ticket de caisse contient un extrait de la signature numérique de l’événement d’audit, et qu’il consiste en une concaténation des troisième, septième, treizième et dix-neuvième symboles de la signature.
1. Dans le PDV, sur la page **Journal des transactions**, sélectionnez la transaction commerciale récemment complétée. Sélectionnez **Afficher le reçu**, puis, dans l’aperçu du reçu, sélectionnez **Imprimer \> Imprimer**. Une deuxième copie du même ticket de caisse est imprimée.
1. Vérifiez la copie imprimée du ticket de caisse. Vérifiez que la valeur **Réimprimer le numéro** passe maintenant à **2**.
1. [Validez l’événement d’audit de la copie du ticket de caisse](#validate-an-audit-event). L’événement d’audit est de type **Copie du ticket de caisse imprimé**. Vérifiez que le numéro séquentiel de l’événement signé est égal au numéro séquentiel de l’événement de copie du ticket de caisse précédent plus 1. Vérifiez que la chaîne qui a été utilisée pour la [signature numérique de l’événement de copie du ticket de caisse](#digital-signing-of-receipt-copies) contient la signature de l’événement de copie de ticket de caisse précédent.

### <a name="10-audit-events"></a>10. Événements d’audit

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments.
1. Sélectionnez une ligne de transaction, puis sélectionnez **Annuler la ligne**.
1. Payez le montant exact.
1. Ajoutez plusieurs éléments à une nouvelle transaction.
1. Sélectionnez **Annuler la transaction**, et confirmez l’opération.
1. [Validez les événements d’audit](#validate-an-audit-event). L’un a le type **Élément annulé**, et l’autre a le type **Transaction annulée**.

### <a name="11-close-shift-and-print-z-report"></a>11. Clôturer l’équipe de travail et imprimer l’état Z

1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert.
1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments et payez le montant exact.
1. Revenez à **Accueil**, et sélectionnez **Afficher le journal**
1. Sur la page **Journal des transactions**, sélectionnez la transaction de vente précédente et renvoyez-en un article. Payez le montant exact.
1. Revenez à **Accueil**, et sélectionnez **Clôturer l’équipe**
1. [Valider l’équipe de travail](#validate-a-shift).

### <a name="12-shift-duration-restriction"></a>12. Restriction de durée de l’équipe de travail

1. Dans Commerce Headquarters, procédez comme suit :

    1. Ouvrez la page **Profils de fonctionnalité du PDV**.
    1. Veillez à ce que l’option **Appliquer la clôture quotidienne de l’équipe de travail** soit définie sur **Oui**.
    1. Définissez le champ **Heure de clôture de l’équipe** sur une heure qui est 20 minutes après l’heure actuelle.
    1. Définissez l’intervalle de clôture de l’équipe sur 10 minutes et sauvegardez l’enregistrement.
    1. Exécutez la tâche de distribution **1070**.

1. Dans le PDV, procédez comme suit :

    1. Connectez-vous au PDV et ouvrez un nouveau service s’il n’est pas encore ouvert. Vous devez commencer l’équipe plus de 10 minutes avant l’heure de clôture spécifiée.
    1. Sur la page **Transaction en cours**, ajoutez plusieurs éléments et payez le montant exact. Vous ne devriez pas recevoir d’erreur ou d’avertissement.
    1. Attendez que l’heure actuelle corresponde à l’heure de fermeture de l’équipe spécifiée moins cinq minutes.
    1. Sur la page **Transaction en cours**, ajoutez un élément. Vous devriez recevoir l’avertissement suivant : « Vous devez clôturer l’équipe à \<specified shift closing time\>. » Cependant, la ligne doit être ajoutée avec succès.
    1. Payez le montant exact. Vous devriez recevoir le même avertissement, mais la vente devrait être conclue avec succès.
    1. Sur la page **Transaction en cours**, ajoutez un élément. Vous devriez recevoir le même avertissement.
    1. Attendez que l’heure actuelle soit postérieure à l’heure de fermeture de l’équipe spécifiée.
    1. Essayez de payer le montant exact. Vous devriez recevoir l’erreur suivante : « La durée de l’équipe de travail dépasse la limite. Suspendez la transaction, fermez l’équipe de travail et ouvrez une nouvelle équipe de travail. » Le paiement ne devrait pas aboutir.
    1. Interrompez la transaction.
    1. Clôturez l’équipe de travail.
    1. Rappelez la transaction.
    1. Payez le montant exact. Vous ne devriez pas recevoir d’erreur ou d’avertissement.

### <a name="13-process-period-grand-total-journal"></a>13. Traiter le journal du total général de la période

1. Dans Commerce headquarters, exécutez la tâche P pour télécharger les données de vente au détail vers Commerce headquarters.
1. Créez et publiez tous les relevés de vente au détail pour la période fiscale.
1. Ouvrez la page **Journal du total général de la période**.
1. Créez un journal.
1. Dans le champ **Journal**, indiquez le numéro de journal, s’il n’est pas défini automatiquement.
1. Dans le champ **Numéro de magasin**, sélectionnez le numéro du magasin.
1. Si le journal est le premier journal du magasin sélectionné, vous devez sélectionner la date « fin » dans le champ **Date de fin**. Vous pouvez sélectionner n’importe quelle date d’une période fiscale, et les champs **Date de début** et **Date de fin** sont automatiquement définis sur le premier et le dernier jour de la période fiscale à laquelle appartient la date sélectionnée.

    Si le journal n’est pas le premier journal du magasin, les champs **Date de début** et **Date de fin** sont automatiquement définis sur le premier et le dernier jour de la période fiscale qui suit la dernière période fiscale pour laquelle un journal fermé existe.

1. Sélectionnez **Fonctions \> Calculer le journal**. La valeur **Statut** du journal doit passer sur **Calculé**.
1. Sélectionnez **Équipes de travail**, et vérifiez que les bonnes équipes de travail sont incluses dans le journal. En d’autres termes, vérifiez que toutes les équipes de travail qui ont été clôturées pendant la période du journal sont incluses. Fermez la page **Équipes de travail**.
1. Sur l’onglet **Montants**, vérifiez les totaux du journal. Vérifiez les champs **Montant total des ventes**, **Montant total des retours** et **Total général**. Vérifiez que les montants **Total général perpétuel** et **Total général perpétuel (valeur absolue)** sont égaux aux montants de la dernière équipe de travail clôturée incluse dans le journal.
1. Sélectionnez **Totaux de taxe**, et vérifiez les totaux de la période par taux de taxe.
1. Sélectionnez **Fonctions \> Clôturer le journal**. La valeur **Statut** du journal doit passer sur **Clôturé**, et le journal doit être signé numériquement. Vérifiez les détails de la signature numérique sur le raccourci **Détails de la signature**. Le champ **Données signées** contient la chaîne qui a été utilisée pour la [signature numérique du journal](#period-grand-total-journal). Validez les montants du journal et d’autres données. Vérifiez la signature du journal précédente pour le même magasin.

### <a name="14-export-and-verify-fiscal-archive"></a>14. Exporter et vérifier les archives fiscales

1. Dans Commerce headquarters, ouvrez la page **Journal du total général de la période** et sélectionnez un journal du total général de la période clôturée.
1. Sélectionnez **Archive \> Exporter l’archive**, spécifiez le nom du fichier d’exportation et confirmez l’opération. Vous devez également désactiver le bloqueur de fenêtres contextuelles du navigateur, afin que cette exportation puisse être effectuée.
1. Vérifiez que le fichier exporté est une archive zip contenant des fichiers XML et SIGN.
1. Pour vérifier l’archive fiscale exportée, suivez les étapes dans [Archives fiscales pour la France](./emea-fra-fiscal-archive.md#fiscal-archive-integrity-verification-tool).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
