---
title: Configurer la Facturation électronique dans Regulatory Configuration Services (RCS)
description: Cette rubrique explique comment configurer la Facturation électronique dans Dynamics 365 Regulatory Configuration Services (RCS).
author: gionoder
ms.date: 05/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6c1d309744c4c8dd0d17f5259551d31c257ede61
ms.sourcegitcommit: 633d51834d7d29b745824924315a3898dc471f1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6075141"
---
# <a name="configure-electronic-invoicing-in-regulatory-configuration-services-rcs"></a>Configurer la Facturation électronique dans Regulatory Configuration Services (RCS)

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les fonctionnalités de configuration de la Facturation électronique dans Dynamics 365 Regulatory Configuration Services (RCS).

C’est grâce aux capacités de configuration que la Facturation électronique vous aide à répondre aux exigences commerciales et réglementaires des factures électroniques sans avoir à effectuer de codage. Et dans les scénarios où les factures électroniques doivent être approuvées électroniquement par un service Web, les capacités de configuration vous aident également à répondre aux exigences d’échange de messages avec un service Web, sans faire de code.

## <a name="electronic-reporting"></a>Gestion des états électroniques

La Gestion des états électroniques (ER) prend en charge la Facturation électronique.

Le mappage et les formats du modèle de données sont des composants configurables qui sont créés et gérés via la Gestion des états électroniques et sont utilisés dans la Facturation électronique. Le concepteur de format ER est l’outil pour créer et mettre à jour des formats de fichiers. Il est utilisé pour configurer les fonctionnalités de facturation électronique.

Pour plus de détails, voir [Vue d’ensemble des États électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Fonctionnalités de facturation électronique

Les fonctionnalités de facturation électronique sont responsables de la génération de factures électroniques via la Facturation électronique. Elles encapsulent les règles de configuration et les utilisent pour traiter les données que Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management envoient à la Facturation électronique et aux factures électroniques.

Les fonctionnalités prennent également en charge les scénarios dans lesquels la conformité aux spécifications de format de fichier est requise et la sortie est un fichier électronique autonome. Dans la plupart des cas, les spécifications de format de fichier sont publiées par l’administration fiscale.

Enfin, les fonctionnalités prennent en charge l’échange de messages avec des services Web externes qui sont hébergés par l’administration fiscale ou par une partie accréditée, et les demandes d’autorisation ou un tampon d’approbation dans la facture électronique.

### <a name="availability-of-electronic-invoicing-features"></a>Disponibilité des fonctionnalités de facturation électronique

La disponibilité des fonctionnalités de facturation électronique dépend du pays ou de la région. Bien que certaines fonctionnalités soient généralement disponibles, d’autres sont en version préliminaire.

#### <a name="generally-available-features"></a>Fonctionnalités en disponibilité générale

Le tableau suivant présente les fonctionnalités de facturation électronique actuellement en disponibilité générale.

| Pays/région | Nom de la fonction                         | Document commercial |
|----------------|--------------------------------------|-------------------|
| Égypte          | Facture électronique pour l’Égypte (EG) | Factures de vente et factures projet |

#### <a name="preview-features"></a>Fonctionnalités d'aperçu

Le tableau suivant présente les fonctionnalités de facturation électronique actuellement en version préliminaire.

| Pays/région | Nom de la fonction                         | Document commercial |
|----------------|--------------------------------------|-------------------|
| Autriche        | Factures électroniques autrichiennes (AT)    | Factures de vente et factures projet |
| Belgique        | Facture électronique belge (BE)      | Factures de vente et factures projet |
| Brésil         | NF-e (BR) pour le Brésil                  | Modèle de document fiscal 55, lettres de correction, annulations et rejets |
| Brésil         | NFS-e ABRASF Curitiba (BR) pour le Brésil | Documents fiscaux du service |
| Danemark        | Facture électronique danoise (DK)       | Factures de vente et factures projet |
| Estonie        | Facture électronique estonienne (EE)     | Factures de vente et factures projet |
| Finlande        | Facture électronique finlandaise (DK)      | Factures de vente et factures projet |
| France         | Facture électronique française (FR)       | Factures de vente et factures projet |
| Allemagne        | Facture électronique allemande (DE)       | Factures de vente et factures projet |
| Italie          | FatturaPA (IT)                       | Factures de vente et factures projet |
| Mexique         | CFDI mexicain (MX)                    | Factures de vente, bons de livraison, transferts d’inventaire, compléments de paiement et annulations |
| Pays-Bas    | Facture électronique néerlandaise (NL)        | Factures de vente et factures projet |
| Norvège         | Facture électronique norvégienne (NO)    | Factures de vente et factures projet |
| Espagne          | Facture électronique espagnole (ES)      | Factures de vente et factures projet |
| Europe         | Facture électronique PEPPOL            | Factures de vente et factures projet PEPPOL |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Composants configurables des fonctionnalités de facturation électronique

Les fonctionnalités de facturation électronique se composent des groupes suivants de composants configurables :

- **Formats** – Les formats vous permettent de configurer ce que la Facturation électronique doit générer lorsqu’un document électronique devient une facture électronique. Les formats incluent la configuration de format de la facture électronique et des fichiers et messages utilisés pour soumettre des demandes et recevoir des réponses lorsqu’une communication avec un service Web externe est requise.
- **Actions** – Les actions vous permettent de configurer la manière dont la Facturation électronique génère la transformation d’un document électronique que Finance et Supply Chain Management a soumis dans une facture électronique.
- **Règles d’applicabilité** – Les règles d’applicabilité vous permettent de configurer le contexte que la Facturation électronique doit prendre en compte pour traiter une fonction de facturation électronique.
- **Variables** – Les variables vous permettent de configurer le support pour la construction de la logique de configuration. Les variables peuvent fonctionner comme entrée de valeurs pour effectuer une action spécifique. Elles peuvent aussi fonctionner comme un échange de valeurs entre Finance et Supply Chain Management et la Facturation électronique.
- **Mappage du modèle de document électronique** – Le mappage du modèle de document électronique vous permet de configurer le mappage du modèle ER. Le mappage de modèle définit le mappage des données de la facture abstraite qui est intégré dans la Facturation électronique lorsque des documents électroniques sont soumis.
- **Modèle de contexte de facture** – Le modèle de contexte de facture vous permet de configurer le modèle de contexte de facture ER et de définir le contexte d’une fonction de facturation électronique.
- **Types de réponse** – Les types de réponse vous permettent de configurer ce que la Facturation électronique doit mettre à jour dans Finance et Supply Chain Management suite au traitement des factures électroniques.

### <a name="formats"></a>Formats

Les listes suivantes présentent les configurations de format ER disponibles pour les fonctionnalités de facturation électronique.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Factures électroniques autrichiennes (AT) : factures de vente et de projet pour l’Autriche

- Facture client OIOUBL
- Facture de projet OIOUBL
- Avoir sur vente OIOUBL
- Avoir sur projet OIOUBL

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Facture électronique belge (BE) : factures de vente et de projet pour la Belgique

- Facture client UBL BE
- Facture de projet UBL BE
- Avoir de projet UBL BE
- Avoir sur vente UBL BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>NF-e (BR) pour le Brésil : NF-e Federal (Brésil)

- Format d’exportation de l’envoi NFe (BR)
- Format d’exportation de lettre de correction NF-e (BR)
- Format d’exportation de l’annulation NFe (BR)
- Format d’exportation de la suppression NF-e (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>NFS-e pour le Brésil (BR) : NFS-e ABRASF Curitiba city

- NFS-e ABRASF Curitiba (BR)
- NFS-e ABRASF Inquire Curitiba (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Facture électronique danoise (DK) : factures de vente et de projet pour le Danemark

- Facture client OIOUBL
- Facture de projet OIOUBL
- Avoir sur vente OIOUBL
- Avoir sur projet OIOUBL

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Facture électronique néerlandaise (NL) : factures de vente et de projet pour les Pays-Bas

- Facture client UBL NL
- Facture de projet UBL NL
- Avoir de projet UBL NL
- Avoir sur vente UBL NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Facture électronique pour l’Égypte (EG) : factures client et de projet pour l’Égypte

- Facture client (EG) (facturation)
- Facture de projet (EG) (facturation)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Facture électronique estonienne (EE) : factures client et de projet pour l’Estonie

- Facture client (EE)
- Facture de projet (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Facture électronique finlandaise (FI) : factures client et de projet pour la Finlande

- Facture client (FI)
- Facture de projet (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Facture électronique française (FR) : factures client et de projet pour la France

- Facture client UBL FR
- Facture de projet UBL FR
- Avoir de projet UBL FR
- Avoir sur vente UBL FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Facture électronique allemande (DE) : factures client et de projet pour l’Allemagne

- Facture client (DE)
- Facture de projet (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Facture électronique italienne (IT) : factures client et de projet pour l’Italie

- Facture client (IT)
- Facture de projet (IT)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>CFDI mexicain (MX) : CFDI pour le Mexique

- Format de facture CFDI (MX)
- Bon de livraison CFDI (MX)
- Transfert de stock CFDI (MX)
- Format de paiement CFDI (MX)
- Format d’annulation de facture CFDI (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Facture électronique norvégienne (NO) : factures client et de projet pour la Norvège

- Facture client OIOUBL
- Facture de projet OIOUBL
- Avoir sur vente OIOUBL
- Avoir sur projet OIOUBL

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>Facture électronique PEPPOL : factures client et de projet PEPPOL

- Facture client PEPPOL
- Facture de projet PEPPOL
- Avoir sur vente PEPPOL
- Avoir sur projet PEPPOL

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Facture électronique espagnole (ES) : factures client et de projet pour l’Espagne

- Facture client (ES)
- Facture de projet (ES)

En plus des configurations de format d’états électroniques disponibles par défaut pour une utilisation avec le service de facturation électronique, vous pouvez également créer vos propres configurations de format d’états électroniques. Cependant, les configurations de format créées pour être utilisées avec les fonctionnalités de facturation électronique ne prennent pas en charge la référence directe aux tables de Finance ou de Supply Chain Management ou aux métadonnées correspondantes. Seules les références au mappage de modèles d’états électroniques sont prises en charge.

### <a name="actions"></a>Actions

Le tableau suivant répertorie les actions disponibles et indique si elles sont actuellement disponibles ou toujours en version préliminaire.

| Action                                        | Description                                                                  | Disponibilité         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Transformer le document                            | Exécutez le format de rapport électronique pour transformer le document.                   | Disponibilité générale  |
| Signer le document XML                             | Signez des documents xml avec une signature numérique.                                   | En mode aperçu           |
| Signer un document JSON pour l’administration fiscale égyptienne | Signez les documents json avec une signature numérique pour l’administration fiscale égyptienne.       | Disponibilité générale  |
| Intégration avec le service ETA égyptien           | Communiquez avec l’administration fiscale égyptienne.                                     | Disponibilité générale  |
| Appeler le service SEFAZ brésilien                  | Intégration avec le service brésilien SEFAZ pour la soumission de documents fiscaux.       | En mode aperçu           |
| Appeler le service PAC mexicain                      | Intégration avec le service PAC mexicain pour la soumission CFDI.                      | En mode aperçu           |
| Réponse du processus                              | Analysez la réponse reçue de l’appel de service Web.                     | Disponibilité générale  |
| Utiliser MS Power Automate                         | Intégrer avec le flux intégré à Microsoft Power Automate.                       | En mode aperçu           |

### <a name="applicability-rules"></a>Règles d'applicabilité

Les règles d'applicabilité sont des clauses configurables qui sont définies au niveau de la fonctionnalité Facturation électronique. Les règles sont configurées pour fournir un contexte d'exécution des fonctionnalités de facturation électronique via l'ensemble de fonctionnalités de la Facturation électronique.

Lorsqu'un document commercial de Finance ou Supply Chain Management est soumis à la facturation électronique, le document commercial ne comporte pas de référence explicite permettant à l'ensemble de fonctionnalités de Facturation électronique d'appeler une fonction de facturation électronique particulière pour traiter l'envoi.

Néanmoins, lorsqu'il est correctement configuré, le document commercial contient les éléments nécessaires qui permettent à la facturation électronique de déterminer quelle fonction de facturation électronique doit être sélectionnée, puis de générer la facture électronique.

Les règles d'applicabilité permettent à l'ensemble de fonctionnalités de la Facturation électronique de trouver les fonctionnalités de facturation électronique exactes qui doivent être utilisées pour traiter l'envoi. Cela se fait en faisant correspondre le contenu du document commercial envoyé avec les clauses des règles d'applicabilité.

Par exemple, deux fonctionnalités de facturation électronique avec des règles d'applicabilité associées sont déployées dans l'ensemble de fonctionnalités de la Facturation électronique.

| Fonction de facturation électronique | Règles d'applicabilité        |
|------------------------------|--------------------------- |
| A                            | <p>Pays = BR</p><p>et</p><p>Entité juridique = BRMF</p>  |
| o                            | <p>Pays = MX</p><p>et</p><p>Entité juridique = MXMF</p>  |

Si un document commercial de Finance ou Supply Chain Management est envoyé à l'ensemble de fonctionnalités de Facturation électronique, le document commercial contient les attributs suivants renseignés comme suit :

- Pays = BR
- Entité juridique = BRMF

L'ensemble de fonctionnalités de Facturation électronique sélectionnera la fonction de facturation électronique **A** pour traiter l'envoi et générer la facture électronique.

De la même manière, si le document commercial contient :

- Pays = MX
- Entité juridique = MXMF

La fonction de facturation électronique **B** est sélectionné pour générer la facture électronique.

La configuration des règles d'applicabilité ne peut pas être ambiguë. Cela signifie que deux ou plusieurs fonctionnalités de facturation électronique ne peuvent pas avoir les mêmes clauses, sinon cela n'entraînera aucune sélection. En cas de doublons de fonctionnalités de facturation électronique, pour éviter toute ambiguïté, utilisez des clauses supplémentaires pour permettre à l'ensemble de fonctionnalités de Facturation électronique de faire la distinction entre les deux fonctionnalités de facturation électronique.

Par exemple, prenons la fonction de facturation électronique **C**. Cette fonction est une copie de la fonction de facturation électronique **A**.

| Fonction de facturation électronique | Règles d'applicabilité        |
|------------------------------|--------------------------- |
| A                            | <p>Pays = BR</p><p>et</p><p>Entité juridique = BRMF</p>  |
| C                            | <p>Pays = BR</p><p>et</p><p>Entité juridique = BRMF</p>  |

Dans cet exemple, la fonction **C** se trouve devant un envoi de document commercial contenant les éléments suivants :

- Pays = BR
- Entité juridique = BRMF

La fonctionnalité de Facturation électronique ne peut pas distinguer quelle fonction de facturation électronique doit être utilisée pour traiter l'envoi, car les envois contiennent exactement les mêmes clauses.

Pour créer une distinction entre les deux fonctions via les règles d'applicabilité, une nouvelle clause doit être ajoutée à l'une des fonctions pour permettre à l'ensemble de fonctionnalités de Facturation électronique de sélectionner la fonction de facturation électronique appropriée.

| Fonction de facturation électronique | Règles d'applicabilité        |
|------------------------------|--------------------------- |
| A                            | <p>Pays = BR</p><p>et</p><p>Entité juridique = BRMF</p>  |
| C                            | <p>Pays = BR</p><p>et</p><p>Entité juridique = BRMF</p><p>et</p><p>Modèle = 55</p>  |

Pour prendre en charge la création de clauses plus complexes, les ressources suivantes sont disponibles :

Opérateurs logiques :
- And
- Ou

Types d'opérateurs :
- Equal
- Not equal
- Greater than
- Less than
- Supérieur ou égal à
- Inférieur ou égal à
- Contains
- Commence par

Types de données :
- Chaîne
- Nombre
- Booléen
- Date
- UUID

Capacité de regrouper et de dissocier des clauses.
L'exemple ressemble à ceci :

| Fonction de facturation électronique | Règles d'applicabilité        |
|------------------------------|--------------------------- |
| C                            | <p>Pays = BR</p><p>et</p><p>(Entité juridique = BRMF</p><p>ou</p><p>Modèle = 55)</p>  |


## <a name="configuration-providers"></a>Fournisseurs de configuration

Les fournisseurs de configuration fournissent les fonctionnalités de facturation électronique et leurs composants ER, tels que le mappage du modèle, la configuration du format et le modèle de contexte. Ils publient les fonctionnalités de facturation électronique et les composants ER dans le référentiel global associé. De là, d’autres organisations peuvent les télécharger.

Avant de configurer les fonctionnalités de facturation électronique via RCS, vous devez configurer votre propre organisation en tant que fournisseur de configuration dans le module **Rapports électroniques**. Pour plus d’informations sur la définition d’un fournisseur de configuration sur **Actif**, voir [Créer des fournisseurs de configuration et les marquer comme actifs](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>Affichage des fonctionnalités de facturation électronique dans le référentiel global

Pour parcourir les fonctionnalités de facturation électronique disponibles dans le référentiel global pour un fournisseur de configuration spécifique, synchronisez l’instance RCS de votre organisation. Une fois la synchronisation terminée, la liste des fonctionnalités de facturation électronique disponibles est mise à jour.

## <a name="importing-electronic-invoicing-features"></a>Importation des fonctionnalités de facturation électronique

Avant d’utiliser ou de configurer les fonctionnalités de facturation électronique, vous devez les importer dans l’instance RCS de votre organisation. L’opération d’importation crée une copie locale des fonctionnalités et copie tous les artefacts ER utilisés par les fonctionnalités (par exemple, les configurations de format et les configurations de modèle) dans l’instance RCS de votre organisation.

Vous pouvez importer les fonctionnalités de facturation électronique à partir de n’importe quel fournisseur de configuration.

## <a name="creating-electronic-invoicing-features"></a>Création des fonctionnalités de facturation électronique

Vous pouvez créer une fonctionnalité de facturation électronique à partir de zéro ou la dériver d’une autre fonctionnalité de facturation électronique.

Lorsque vous créez une fonctionnalité de facturation électronique à partir de zéro, vous devez ajouter manuellement les composants ER (par exemple, les configurations de version de fonctionnalité et d’autres configurations, telles que la configuration de la version de fonctionnalité et la configuration de l’application). Lorsque vous créez une fonctionnalité en la dérivant d’une autre, la nouvelle fonctionnalité hérite de toutes les configurations de l’original. 

## <a name="electronic-invoicing-feature-version"></a>Version de la fonctionnalité de facturation électronique

Les fonctionnalités de facturation électronique font l’objet d’une version. Lorsqu’une nouvelle version est créée, le numéro de version est automatiquement incrémenté. Une date « effective à partir de » peut être définie pour la nouvelle version.

Les versions des fonctionnalités de facturation électronique suivent un cycle de vie qui a jusqu’à trois statuts :

- **Brouillon** – Si une version de fonctionnalité est dans cet état, vous pouvez modifier ses attributs de configuration et n’importe lequel de ses artefacts (par exemple, les configurations de format de fichier).
- **Complète** – Si une version de fonctionnalité est dans cet état, elle a été publiée dans le référentiel global associé à votre organisation. Vous ne pouvez plus modifier la version de la fonctionnalité ou l’un des composants ER.
- **Publié** – Si une version de fonctionnalité est dans ce statut, elle a été publiée dans la Facturation électronique. Vous ne pouvez plus modifier la version de la fonctionnalité ou l’un des composants ER.

### <a name="feature-configurations"></a>Configurations de la fonctionnalité

Les configurations de fonctionnalités contiennent toutes les configurations de format ER utilisées par les fonctionnalités de facturation électronique. Tous les fichiers électroniques qu’une fonctionnalité de facturation électronique utilise pendant le traitement proviennent des configurations de format qui ont été ajoutées aux configurations de cette fonctionnalité.

À partir des configurations de fonctionnalités, vous pouvez accéder au concepteur de format ER, qui est l’outil ER utilisé pour créer des configurations de format.

### <a name="feature-setup"></a>Paramétrage de fonctionnalité

Les configurations de fonctionnalités sont utilisées en combinaison avec les configurations de fonctionnalités. Chaque configuration de fonctionnalité encapsule un ensemble d’actions, de règles d’applicabilité et de variables qui fournissent le comportement attendu afin qu’une fonctionnalité de facturation électronique puisse répondre à une exigence spécifique de la facture électronique.

### <a name="application-setup"></a>Configuration de l’application

La configuration de l’application doit être associée à une application connectée précédemment créée.

Grâce à la configuration de l’application, vous pouvez configurer la partie d’une fonctionnalité de facturation électronique qui doit être effectuée dans Finance et Supply Chain Management. Au moins trois composants configurables sont obligatoires, quelle que soit la fonctionnalité de facturation électronique :

- **Nom de la table** – L’entité de Finance et Supply Chain Management qui détient les factures validées et sur laquelle repose la fonctionnalité de facturation électronique.
- **Contexte** – Le nom du modèle de contexte de facture configuré via ER.
- **Mappage de document commercial** – Le nom du modèle de mappage de facture configuré via ER.

> [!IMPORTANT]
> La configuration saisie dans la configuration de l’application peut être affichée dans Finance et Supply Chain Management. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**. Sur l’onglet **Document électronique**, sélectionnez **Déployer**, puis l’option **Application connectée**.

### <a name="deploying-feature-versions"></a>Déployer des versions de fonctionnalités

Dans RCS, vous devez utiliser la commande **Déployer** pour cibler-publier une version de la fonctionnalité de facturation électronique. Sélectionnez **Déployer**, puis sélectionnez l’une des options suivantes pour définir la cible du déploiement : 

- **Environnement de service** – Lorsque la cible du déploiement est l’environnement de service, la version de la fonction de facturation électronique est publiée dans l’environnement de service. La Facturation électronique est alors prête à recevoir et à traiter les documents électroniques envoyés par Finance et Supply Chain Management.
- **Application connectée** – Lorsque la cible du déploiement est l’application connectée, la configuration fournie par le programme d’installation de l’application est écrite dans l’instance Finance et Supply Chain Management qui lui était précédemment associée.

Seules les versions des fonctionnalités de facturation électronique dont le statut est **Terminé** peuvent être déployées dans un environnement de service ou une application connectée.

### <a name="removing-feature-versions"></a>Suppression des versions de fonctionnalités

Dans RCS, vous devez utiliser la commande **Annuler le déploiement** pour supprimer une version spécifique de la fonction de facturation électronique d’un environnement de service dans la Facturation électronique.

> [!IMPORTANT]
> La commande **Annuler le déploiement** ne fonctionne que dans les environnements de service. Elle ne supprime pas les versions des fonctionnalités de facturation électronique des applications connectées.

### <a name="rebasing-electronic-invoicing-features"></a>Redéfinition de la base des fonctionnalités de facturation électronique

Lorsqu’une fonctionnalité de facturation électronique est dérivée d’une autre, la commande **Redéfinir** met à jour la fonctionnalité dérivée avec les modifications qui ont été introduites dans la fonctionnalité d’origine.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Émettre des factures électroniques dans Finance et Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
