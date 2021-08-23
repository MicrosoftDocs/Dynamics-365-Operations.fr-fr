---
title: Aperçu de l'impôt indien déduit à la source (TDS)
description: Cette rubrique fournit des informations détaillées sur l'impôt indien déduit à la source (TDS). La documentation TDS couvre la fonctionnalité de cette capacité.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b55e6aa5f56090ca14836894e9e51232ab63dce1ef33255b8eac1170404190c9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723770"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Aperçu de l'impôt indien déduit à la source (TDS)

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations détaillées sur l'impôt indien déduit à la source (TDS).

La documentation TDS couvre la fonctionnalité de cette capacité. Il explique également comment effectuer la configuration de base pour TDS, calculer TDS sur les transactions, terminer le processus de règlement TDS, enregistrer les numéros de certificat TDS et générer des requêtes TDS, des relevés TDS et des certificats TDS. La documentation comprend les rubriques suivantes :

- [Paramétrage de base pour TDS](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [Concepteur de formule et fonctionnalité de limite de seuil utilisées pour le calcul TDS](apac-ind-TDS-Formula-designer.md)
- [Calcul du TDS sur les factures, les paiements, les billets à ordre et les transactions intersociétés](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [Processus de règlement périodique de TDS et règlement des montants TDS aux fournisseurs de l'autorité TDS](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [Enregistrement et mise à jour des numéros et dates des certificats TDS](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Introduction à TDS

Conformément à la loi de 1961 sur l'impôt sur le revenu, l'impôt sur le revenu est déduit à la source par le bénéficiaire du service au moment du paiement anticipé ou de la comptabilisation du crédit, selon la première éventualité. La personne qui effectue le paiement doit déduire le montant de la taxe et ne payer que le solde net au fournisseur du service. Le TDS est appliqué aux services que le gouvernement spécifie, et la taxe est déduite en utilisant les taux que le gouvernement spécifie pour une période. Le taux de déduction est basé sur le statut de l'entité qui reçoit le paiement ou fournit le service. Les statuts comprennent **Individuel**, **Famille indivise hindoue** (**HUF**), **Compagnie**, **Entreprise**, **Association de personnes** (**AOP**), **Corps d'individus** (**BOI**) et **Autorité locale**.

Les sections suivantes répertorient les services sur lesquels TDS est appliqué, comme spécifié par le gouvernement indien.

**Résidents**

- Revenus de salaires (en vertu de l'article 192)
- Revenu des intérêts sur les titres (en vertu de l'article 193)
- Revenus des dividendes (en vertu de l'article 194)
- Revenus des intérêts (en vertu de l'article 194A)
- Revenus de loteries ou de puzzles (en vertu de l'article 194B)
- Gains courses hippiques, etc. (en vertu de l'article 194BB)
- Entrepreneurs et sous-traitants (en vertu de l'article 194C)
- Commission des assurances (en vertu de l'article 194D)
- Revenu des dépôts dans le cadre du régime d'épargne national (en vertu de l'article 194EE)
- Revenu provenant d'un fonds commun de placement ou d'une UTI (en vertu de l'article 194F)
- Commission, rémunération, prix, etc., en vente ou à la loterie (en vertu de l'article 194G)
- Paiement de la commission ou du courtage (en vertu de l'article 194H)
- Loyer (en vertu de l'article 194I)
- Service professionnel (en vertu de l'article 194J)
- Revenus des unités (en vertu de l'article 194K)
- Paiement d'une indemnité lors de l'acquisition de certains biens immobiliers (en vertu de l'article 194LA)

**Non résidents**

- Paiements aux sportifs non résidents ou à une association sportive (en vertu de l'article 194E)
- Autres sommes (en vertu de l'article 195)
- Revenu relatif aux unités de non-résidents (en vertu de l'article 196A)

    - Revenu provenant d'obligations en devises ou d'actions d'une société indienne (en vertu de l'article 196C)
    - Revenus des investisseurs institutionnels étrangers provenant de titres (en vertu de l'article 196D)
    - Salaire et tous les autres revenus positifs sous n'importe quelle rubrique sur le revenu (article 192)
    - Intérêts sur les valeurs mobilières (article 193)
    - Intérêts autres que les intérêts sur les valeurs mobilières (article 194A)
    - Paiements aux prestataires et sous-traitants (Article 194C)
    - Gains de loterie ou de mots croisés (article 194B)
    - Gains courses hippiques, etc. (Article 194BB)
    - Commission des assurances couvrant tous les paiements pour l'acquisition des activités d'assurance (article 194D)
    - Tout intérêt autre que l'intérêt sur les titres payables à des non-résidents n'étant pas une société ou à une société étrangère (article 195)
    - Paiement à un sportif non-résident, y compris un athlète ou une association ou institution sportive. En cas de sportif non-résident, les paiements au titre des publicités ainsi que des articles sur tout jeu/sport en Inde dans les journaux, magazines, etc. Est inclus (article 194E)
    - Paiement au titre des dépôts sous NSS \[Régime national d'épargne\] (Article 194EE)
    - Paiement au titre du rachat de parts par un fonds commun de placement ou UTI (article 194F)
    - Paiement de la commission ou du courtage (Article 194H)
    - Paiement du loyer (article 194I)
    - Paiement d'honoraires pour services professionnels ou techniques (article 194J)
    - Commission à Stockiest, distributeurs, acheteurs et vendeurs de billets de loterie, y compris la rémunération ou le prix sur ces billets (article 194G)
    - Revenu provenant de parts achetées en devises ou gain en capital à long terme découlant du transfert de ces parts achetées en monnaie étrangère (chapitre 196B)
    - Paiement de tout revenu à des non-résidents au titre des intérêts ou des dividendes sur les obligations et les actions (article 196C)

Le TDS est calculé sur les achats, les ventes, les retours sur ventes, les notes de crédit, les acquisitions d'immobilisations, les paiements anticipés, les paiements anticipés, les billets à ordre, la taxe de travaux et les transactions intersociétés.

> [!NOTE]
> Dans le scénario fiscal indien actuel, le TDS n'est pas calculé sur les transactions de vente. Cependant, le système comprend une disposition pour calculer le TDS récupérable sur les transactions de vente, en particulier pour les transactions intersociétés.

Le calcul de TDS prend toujours en compte le seuil et le seuil d'exception définis pour le composant TDS.

Le processus de règlement périodique de TDS doit être exécuté et les paiements TDS doivent être réglés aux fournisseurs autorisés de TDS.

Les numéros et dates des certificats TDS reçus des fournisseurs ou des clients peuvent être enregistrés et mis à jour. De plus, les relevés trimestriels du formulaire 26Q et du formulaire 27Q, ainsi que le certificat du formulaire 16A pour TDS, peuvent être générés dans Finance.

## <a name="setting-up-and-working-with-tds"></a>Configuration et utilisation de TDS

Voici un aperçu du processus de configuration et d'utilisation de TDS :

1. **Paramétrage TDS :**

    - Paramétrage :

        - Dans Paramètres de Comptabilité, activez les paramètres liés à TDS.
        - Dans Paramètres de Comptabilité, configurez la souche de numéros pour les paiements de retenue à la source.
        - Définition des paramètres dans Comptabilité client et Comptabilité fournisseur.

    - Paramétrage de base :

        - Configurez les numéros d'enregistrement TDS pour une entreprise, des clients et des fournisseurs.
        - Paramétrer des groupes de composants TDS.
        - Configurez les composants TDS, associez-leur des groupes de composants TDS et définissez leur seuil et leur seuil d'exception.
        - Configurez les autorités TDS.
        - Paramétrez des périodes de règlement TDS.
        - Configurez les codes de taxe TDS et associez-leur des composants TDS.
        - Configurez les groupes de taxes TDS et associez-leur des codes de taxe TDS.
        - Dans le concepteur de formules, définissez une formule pour calculer TDS pour un groupe TDS.
        - Enregistrez les numéros de certificat de concession TDS.

    - Comptes généraux et configuration de la société :

        - Configurez la comptabilité fournisseur et comptabilité client TDS.
        - Configurez une déduction fiscale et un numéro de compte de recouvrement (TAN) et une catégorie de type de déducteur pour l'entreprise.

    - Autre configuration :

        - Configurez un calendrier de paiement qui inclut l'allocation TDS.
        - Paramétrer un type de frais de paiement pour les paiements TDS.
        - Configurez des informations sur les groupes TDS, les numéros de compte permanents (PAN) et les TAN pour les fournisseurs et les clients.

2. **Calcul de TDS dans les transactions :**

    - Factures et paiements
    - Billets à ordre
    - Paiements anticipés
    - Acomptes

3. **Règlement TDS :**

    - Processus de règlement périodique de TDS
    - Règlement des paiements TDS aux fournisseurs de l'autorité TDS et génération d'un challan TDS

4. **Demandes de renseignements, déclarations et certificat TDS :**

    - Enregistrez et mettez à jour des numéros et dates des certificats TDS.
    - Générez une demande TDS et une demande TDS validée.
    - Générez les relevés trimestriels des formulaires 27A, 26Q et 27Q TDS et e-TDS.
    - Générez un certificat de l'écran 16A.
