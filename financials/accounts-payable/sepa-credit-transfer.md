---
title: Vue d&quot;ensemble des virements SEPA
description: "Cet articles associées des informations générales sur ISO 20022 transferts de crédit, notamment les transferts de crédit de (SEPA) de l&quot;Espace unique de paiement en euros et tous les autres paiements électroniques pour les fournisseurs. Un virement SEPA est un type spécifique de paiement en euros d&quot;une société ou personne à une société ou une autre personne. La rubrique décrit également comment configurer et envoyer un fichier de virement de crédit."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>Vue d'ensemble des virements SEPA

Cet articles associées des informations générales sur ISO 20022 transferts de crédit, notamment les transferts de crédit de (SEPA) de l'Espace unique de paiement en euros et tous les autres paiements électroniques pour les fournisseurs. Un virement SEPA est un type spécifique de paiement en euros d'une société ou personne à une société ou une autre personne. La rubrique décrit également comment configurer et envoyer un fichier de virement de crédit.

## <a name="what-is-a-credit-transfer-message"></a>Quel est un message de transfert de crédit ?
Message de transfert de crédit est une demande qu'une partie initialisante (la société) soumet aux fonds de mouvement de son propre compte à un créditeur. Plusieurs pays/région spécifique et les implémentations banque spécifiques du crédit transfèrent des messages. Certains d'entre elles sont utilisés au sein d'une pays/région, et les autres sont les normes devenants. Une norme bien été établie globale est ISO 20022 et les messages d'initiation, tels que le transfert de crédit. L'illustration suivante présente les relations et la couverture pour les messages sélectionnés de transfert de crédit. 
messages\[/caption\]de transfert de crédit d'](./media/credit-transfer.jpg) de tansfer de crédit d'![ 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Quels sont des paiements ISO 20022 et SEPA ?
L'Espace unique de paiement en euro (SEPA) est défini par la Commission européenne et stipule que tous les paiements électroniques sont considérés comme locaux, quel que soit le pays/la région où la personne, l'entreprise ou l'organisation et la banque sont localisées. Il n'existe aucune différence entre les paiements nationaux et les paiements transfrontaliers. Le SEPA comprend 28 États membres de l'Union européenne (EU), ainsi que l'Islande, le Liechtenstein, la Norvège, la Suisse, le Monaco, et le San Marino. Le SEPA permet de former un marché unique pour les transactions de paiement dans l'Espace économique européen. Enfin, le SEPA est supposé réduire le nombre de formats de paiement pour les banques, les entreprises et les personnes. La Commission européenne a établi les fondements légaux des paiements SEPA dans la Directive sur les Services de Paiement (PSD, Payment Services Directive). Le Conseil européen des paiements (EPC) assure le fonctionnement du SEPA par les activités suivantes :

-   il fixe les normes pour les paiements électroniques SEPA à l'aide du format XML ISO 20022 Schéma universel de messages pour l'industrie financière ;
-   il établit les règles et les instructions relatives sur la gestion des paiements en euro.

L'EPC, qui est constitué de banques européennes, développe les infrastructures commerciales et techniques pour les instruments de paiement SEPA. Trois types de paiements SEPA sont utilisés :

-   les virements ;
-   les prélèvements.
-   Cartes

## <a name="what-is-a-sepa-credit-transfer"></a>Qu'est-ce qu'un virement SEPA ?
Le virement SEPA est un paiement d'une société ou d'une personne à une société ou une autre personne. Les paiements doivent être en euro, et doivent inclure le numéro de compte international (IBAN) et le code d'identificateur de la banque (BIC, Bank Identifier Code) pour les deux parties. (Le BIC (également appelé société pour le code SWIFT \[\] Inter-bank Financial Telecommunication). mondiale En outre, les coûts des transactions doivent être partagés entre les deux parties. Les virements bancaires qui surviennent entre les pièces doivent utiliser des fichiers XML conformes aux normes de traitement des paiements ISO 20022 et au format XML, tels qu'ils sont spécifiés par le CEP.

## <a name="how-is-a-credit-transfer-implemented"></a>Procédure d'attribution d'un transfert de crédit est implémenté ?
Le format de paiement de transfert de crédit pour les pays européens est implémenté à l'aide de (ER) et des fonctionnalités de déclarations électroniques de modes de paiement dans Dynamics 365 pour les opérations. Certains formats de transfert de crédit qui sont toujours utilisés dans d'autres régions utilisent la zone de paiement fournisseur. Parmi nombreux autres formats, il existe des douze ISO 20022 formats de fichier de transfert de crédit disponibles. Ces formats d'exportation sont conformes à la norme SEPA ISO XML 20022. Ils sont utilisés pour générer les transferts de paiement non en euros pour les pays/régions où ils sont utilisés et l'euro paiements comme spécifié dans la version 8,2 du règlement de programme de virement SEPA que l'EPC lance. Avant de pouvoir mettre en œuvre les transferts de crédit, vous devez contacter votre banque pour obtenir le logiciel requis afin de télécharger les fichiers bancaires électroniques. Vous pouvez utiliser ce logiciel pour transférer les fichiers XML contenant les ordres de paiement à votre banque.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Le transfert de crédit formate actuellement pris en charge dans Dynamics 365 pour les opérations ?
Vous devez toujours accéder à la bibliothèque partagée d'immobilisation dans des services (LCS) de Microsoft Dynamics Lifecycle et afficher la liste la plus à jour de fichiers disponibles avoir un type d'immobilisation dont ** configuration de GER **. Des que section suivante, « que je dois paramétrer ?  », fournit un lien vers une rubrique qui illustre la création d'un référentiel de lettres de crédit pour réviser les configurations disponibles et configurations sélectionnées par importation.

## <a name="what-do-i-have-to-set-up"></a>Que dois-je paramétrer ?
-   Avant de créer des fichiers de transfert de crédit, au moins une configuration active de transfert de crédit doit être importées dans vos configurations d'ER. Pour obtenir des instructions, voir [des configurations électroniques de génération d'états de téléchargement de Lifecycle Services] (https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Lorsque vous configurez les modes de paiement Achats, sélectionnez ** génération d'états électronique générique ** la case à cocher, puis sélectionnez le format approprié de transfert de crédit (par exemple, ** transfert de crédit ISO 20022 (AT) **) comme configuration de format d'exportation.
-   Vous devez également paramétrer l'entité juridique et les informations de compte bancaire dans Dynamics 365 pour les opérations.
-   Les numéros de compte bancaire, l'IBANs, les codes SWIFT (BICs) ou d'autres ID sont nécessaires afin de créer des paiements valides de transfert de crédit. Par conséquent, vous devez les paramétrer pour le compte bancaire fournisseur et le compte bancaire pour l'organisation qui demande le transfert.
-   Les informations supplémentaires peuvent être demandées, comme les numéros de (VAT) de taxe sur la valeur ajoutée pour les parties qui sont mentionnées au message de transfert de crédit. Ces informations doivent être paramétrée pour les fournisseurs et pour l'entité juridique lorsqu'elle vous a demandé.
-   Certains modes de paiement Achats, la plupart ISO 20022 ont basé des modes de paiement, peuvent nécessiter un paramétrage supplémentaire pour ** des codes de format de paiement **, comme ** type de service ** = ** SLEV **. Ces codes sont utilisés comme référence supplémentaires pour les transactions de paiement de le processus de paiement. Les valeurs par défaut des codes de paiement, comme ** objectif de catégorie **, ** porteur de frais **, ** instrument local ** et ** service de niveau ** peuvent être définies dans deux emplacements. Le premier lieu est ** en-tête de journal des paiements des achats ** et le second est ** des méthodes d'Achats pour les paiements **. En cas de création des lignes de journal des paiements, des éléments de code paiement définis sous l'en-tête de journal des paiements sont transférés vers une ligne de journal, si l'ensemble, les valeurs des modes de paiement sont utilisés.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Quels paramètres sont disponibles pour générer des paiements de transfert de crédit ?
La liste des paramètres spécifiques dépend du format de transfert de crédit. Le tableau suivant indique les paramètres disponibles lorsque vous générez un fichier de virement de crédit ISO 20022 pour l'Allemagne dans un journal des paiements fournisseur. Grâce à les options disponibles dans ** exécution en arrière-plan ** l'onglet, vous pouvez exécuter la génération de paiement par lots.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Champ</th>
<th>description ;</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Réservation de traitement par lots</td>
<td>Activez cette case à cocher pour inclure la balise de réservation de traitement par lots dans le fichier XML.</td>
</tr>
<tr class="even">
<td>Date de traitement</td>
<td>Entrez la date à laquelle la banque doit traiter les paiements.</td>
</tr>
<tr class="odd">
<td>Format</td>
<td>Sélectionnez le format des informations de remise, selon les exigences de votre pays/région ou de votre banque :
<ul>
<li><strong>Strd</strong> – Sélectionnez cette option pour utiliser le format structuré lorsqu'une ligne de paiement est réglée par rapport à une facture. Cette option n'est pas disponible pour le pays/formats d'exportation région spécifiques à la France, l'Allemagne, ou les Pays-Bas.</li>
<li><strong>Ustrd</strong> – Sélectionnez cette option pour utiliser le format non structuré lorsque le paiement est réglée par rapport à plusieurs factures. Les numéros de facture pour les factures réglées sont concaténés et utilisés comme informations de remise. {{Conformément:In_compliance_with}} À ISO 20022 instructions, des informations non structurée de remise sont limitées à 140 caractères.</li>
</ul></td>
</tr>
<tr class="even">
<td>Nombre de factures</td>
<td>Entrez le nombre de factures des lesquelles <strong>Avis de paiement</strong> le de l'état.</td>
</tr>
<tr class="odd">
<td>Souche de N°</td>
<td>Entrez un numéro de souche pour identifier le fichier. Le numéro de souche apparaît dans <strong>Note de participation</strong> l'état.</td>
</tr>
<tr class="even">
<td>Imprimer une note de participation</td>
<td>Activez cette case à cocher pour imprimer l'état <strong>Note de participation</strong>.</td>
</tr>
<tr class="odd">
<td>Imprimer l'état de contrôle</td>
<td>Activez cette case à cocher pour imprimer un état contenant les informations de paiement.</td>
</tr>
<tr class="even">
<td>Imprimer la lettre explicative</td>
<td>Activez cette case à cocher pour imprimer l'état <strong>Avis de paiement</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>Que sont les codes IBAN et BIC ?
Numéro de compte bancaire international (IBAN) et le code bancaire (BIC) d'identification permettent d'identifier les comptes dans plusieurs pays/régions dans le monde. Notamment les 34 pays/régions SEPA. Entrez le BIC dans ** code SWIFT ** le champ et l'IBAN dans ** IBAN ** le champ. Pour le compte bancaire du créditeur et le compte bancaire du client, ces champs sont situés sous ** identification supplémentaire ** l'organisateur d'** compte bancaire ** l'onglet ** des comptes bancaires ** de la page. L'utilisation du BIC pour les paiements SEPA n'est plus appliquée.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Comment puis-je communiquer un fichier de paiement à la banque ?
Lorsque vous générez des paiements, le fichier de paiement est généré, et vous êtes invité à l'enregistrer de votre navigateur Web sur chaque emplacement disponible. L'étape suivante consiste à envoyer le fichier XML à votre banque. Ce processus varie d'une banque à l'autre. Suivez les instructions de votre banque pour envoyer les fichiers à la banque aux fins de traitement.


