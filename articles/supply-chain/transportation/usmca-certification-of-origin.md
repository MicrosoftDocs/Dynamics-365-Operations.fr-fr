---
title: Certification d'origine USMCA
description: Cette fonctionnalité vous permet d'imprimer les documents de certification d'origine requis par l'Accord États-Unis-Mexique-Canada (USMCA).
author: Henrikan
manager: tfehr
ms.date: 10/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: de0917f6734d81248f8aa588bd0c5dec7d056219
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006414"
---
# <a name="usmca-certification-of-origin"></a>Certification d'origine USMCA

[!include [banner](../includes/banner.md)]

Cette fonctionnalité vous permet d'imprimer les documents de certification d'origine requis par l'Accord États-Unis-Mexique-Canada (USMCA).

Le *Document de certification d'origine USMCA* contient les éléments de données minimum requis pour la déclaration. Certains éléments de données peuvent être préremplis avant l'impression tandis que d'autres doivent être remplis manuellement après l'impression. Pour bénéficier d'un traitement tarifaire préférentiel, le document doit être rempli et en possession de l'importateur au moment de la déclaration. Le document peut être rempli par l'importateur, l'exportateur ou le producteur.

Vous pouvez imprimer le document pour un seul envoi à partir de la page de liste **Toutes les expéditions** ou depuis la page **Détails de l'expédition**.

Le document n'est accessible que lorsque le pays de l'adresse principale de l'entité juridique est les États-Unis.

En fonction de la sélection d'impression du document, le document peut être prérempli avec les données de votre système. Il est possible de modifier ou d'ajouter des données au document imprimé en exportant le document imprimé dans un format modifiable, tel que Microsoft Word. Après l'exportation, vous pouvez appliquer les modifications requises avant qu'une déclaration ne soit faite.

## <a name="turn-on-the-usmca-feature"></a>Activer la fonctionnalité USMCA

Avant de pouvoir utiliser la fonctionnalité USMCA, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Vidéos sur la gestion du transport*
- **Nom de la fonctionnalité :** *Document de certification d'origine USMCA*

## <a name="document-content"></a>Contenu du document

La certification USMCA du document d'origine contient les éléments de données suivants :

- Éléments d'adresse
- Rôle du certificateur
- Expédition unique
- Factures
- Période globale
- Détails de l'article
- Signature du certificateur
- Nombre de pages

Pour plus d'informations sur chacun de ces éléments et sur la manière dont leurs valeurs sont trouvées, consultez les sections restantes de cette rubrique.

## <a name="print-a-usmca-certification-of-origin-document"></a>Imprimer le document de certification d'origine USMCA

Pour imprimer un document de certification d'origine USMCA pour un envoi, procédez comme suit :

1. Effectuez l’une des opérations suivantes :
    - Aller à **Gestion du transport > Expéditions > Toutes les expéditions** et sélectionnez l'expédition pour laquelle vous souhaitez imprimer le document.
    - Ouvrez la page **Détails de l'expédition** de l'expédition pour laquelle vous souhaitez imprimer le document (il existe plusieurs façons de s'y rendre, notamment à partir de la page **Toutes les expéditions**).
1. Dans le volet Actions, ouvrez l'onglet **Expéditions** et, à partir du groupe **Impression**, sélectionnez **Certificat d'origine USMCA**.
1. La boîte de dialogue **Certificat ou origine** s'ouvre. Définissez les paramètres décrits dans les sous-sections suivantes, puis sélectionnez **OK** pour générer le document.
1. Un aperçu du document s'ouvre. Utilisez les commandes fournies dans le volet Actions pour imprimer ou exporter le document selon vos besoins.

### <a name="certifying-party"></a>Tiers certificateur

Utilisez la liste déroulante **Certificateur** pour identifier le type de partie qui imprime le document. Indiquez si le certificateur est *Exportateur*, *Exportateur et producteur*, *Producteur*, ou *Importateur* ; ou laissez ce champ vide si le certificateur n'est aucun de ceux-ci. L'option que vous sélectionnez détermine ce qui est imprimé dans les sections d'adresse du document.

Le **Certificateur** que vous choisissez sera inclus dans le document imprimé.

Le document peut être imprimé pour les expéditions entrantes et sortantes. Sélectionnez *Importateur* comme **Certificateur** pour les expéditions entrantes uniquement.

Le tableau suivant décrit les types d'informations inclus dans le document en fonction du **Certificateur** que vous choisissez.

| Certificateur | Description |
|---|---|
| *\[Blanc\]* | Ajoute les détails suivants au document :<ul><li>**Détails du certificateur** : Utilise les coordonnées de l'entrepôt d'expédition, le cas échéant ; sinon, il utilise l'adresse du site d'expédition, si disponible ; sinon, il utilise l'adresse de l'entité juridique (société) sélectionnée dans Supply Chain Management.</li><li>**Détails de l'exportateur** : Vide</li><li>**Détails du producteur** : Vide</li><li>**Détails de l'importateur** : Vide</li><ul>|
| *Exportateur* | Ajoute les détails suivants au document :<ul><li>**Détails du certificateur** : Utilise les coordonnées de l'entrepôt d'expédition, le cas échéant ; sinon, il utilise l'adresse du site d'expédition, si disponible ; sinon, il utilise l'adresse de l'entité juridique (société) sélectionnée dans Supply Chain Management.</li><li>**Détails de l'exportateur** : Utilise les coordonnées de l'entité juridique.</li><li>**Détails du producteur** : Vide</li><li>**Détails de l'importateur** : Utilise le compte de facturation pour la commande client associée.</li><ul>|
| *Exportateur et producteur* | Ajoute les détails suivants au document :<ul><li>**Détails du certificateur** : Utilise les coordonnées de l'entrepôt d'expédition, le cas échéant ; sinon, il utilise l'adresse du site d'expédition, si disponible ; sinon, il utilise l'adresse de l'entité juridique (société) sélectionnée dans Supply Chain Management.</li><li>**Détails de l'exportateur** : Utilise les coordonnées de l'entité juridique.</li><li>**Détails du producteur** : Utilise les coordonnées de l'entité juridique.</li><li>**Détails de l'importateur** : Utilise le compte de facturation pour la commande client associée.</li><ul>|
| *Importateur* | Ajoute les détails suivants au document :<ul><li>**Détails du certificateur** : Utilise les coordonnées de l'entrepôt d'expédition, le cas échéant ; sinon, il utilise l'adresse du site d'expédition, si disponible ; sinon, il utilise l'adresse de l'entité juridique (société) sélectionnée dans Supply Chain Management.</li><li>**Détails de l'exportateur** : Vide</li><li>**Détails du producteur** : Vide</li><li>**Détails de l'importateur** : Utilise les coordonnées de l'entité juridique.</li><ul>|
| *Producteur* | Ajoute les détails suivants au document :<ul><li>**Détails du certificateur** : Utilise les coordonnées de l'entrepôt d'expédition, le cas échéant ; sinon, il utilise l'adresse du site d'expédition, si disponible ; sinon, il utilise l'adresse de l'entité juridique (société) sélectionnée dans Supply Chain Management.</li><li>**Détails de l'exportateur** : Vide</li><li>**Détails du producteur** : Utilise les coordonnées de l'entité juridique.</li><li>**Détails de l'importateur** : Vide</li><ul>|

### <a name="has-various-producers"></a>A plusieurs producteurs

La liste déroulante **Certificateur** contrôle le texte à utiliser pour les détails du producteur dans le document. Choisissez l'une des méthodes suivantes :

- *Divers producteurs* : Imprime le texte « Divers » dans les détails du producteur.
- *Disponible sur demande* : Imprime le texte « Disponible sur demande par les autorités importatrices » dans les coordonnées du producteur.

Quand le **Certificateur** est défini sur *Exportateur et producteur* ou *Producteur*, et que paramètre **Dispose de divers producteurs** est annulé et les détails de l'adresse du producteur seront les mêmes que ceux du certificateur.

### <a name="blanket-period"></a>Période globale

Utilisez les paramètres **Période de couverture à partir du** et **Période de couverture jusqu'au** pour établir une période globale, pendant laquelle le document couvrira plusieurs envois de marchandises identiques, même si le document est imprimé pour un seul envoi. Vous pouvez définir les dates de la période de couverture sans aucune contrainte, et elles seront ajoutées au document. Vous pouvez également laisser ces paramètres vides ou les définir dans le passé.

### <a name="is-single-shipment"></a>Expédition unique

Dans la boîte de dialogue **Certificat d'origine**, définissez **Expédition unique** sur l'un des éléments suivants :

- *Oui* : Ajoute « Expédition unique : Oui » à côté du numéro de facture.
- *Non* : N'ajoute rien.

## <a name="other-information-included-in-the-document"></a>Autres informations incluses dans le document

En plus des éléments facultatifs que vous sélectionnez à l'aide de la boîte de dialogue **Certificat ou origine**, le document de certification d'origine de l'USMCA comprendra les informations et les champs personnalisés résumés dans les sous-sections suivantes. Certaines de ces informations doivent être saisies manuellement après avoir généré le document.

### <a name="invoice-number"></a>Numéro de facture

Les ID des factures client liées aux expéditions sont imprimés sur le document quelle que soit la période globale. Les numéros de facture sont imprimés que **Expédition unique** soit sélectionné ou non.

### <a name="item-details"></a>Détails de l'article

Le document fournit plusieurs sections qui répertorient les détails des articles spécifiques, à savoir :

- **Numéro SKU** : Imprime le numéro d'article du produit lancé.

- **Description** : Imprime la description ou le nom du produit lancé. S'il existe une description dans la langue de l'utilisateur, celle-ci est imprimée. S'il n'existe aucune description de ce type, le nom dans la langue de l'utilisateur est imprimé. Si ce nom n'existe pas, le nom de l'article est imprimé.

- **Classement douanière du Système harmonisé (SH)**  : Imprime le barème douanier harmonisé associé au produit. Vous pouvez configurer ces barèmes en accédant à **Gestion des transports \> Configurer \> Norme de transport \> Barèmes douaniers harmonisés**.

- **Critère d'origine :** Vous devez saisir manuellement les données dans cette section la première fois que vous publiez le document.

- **Pays d'origine :** Imprime le pays d'origine que vous appliquez en accédant à **Gestion des informations produit \> Configurer \> Conformité des produits \> Pays d'origine** (voir également [Pays d'origine](../pim/country-of-origin.md)). Le code ISO du pays d'origine est imprimé en fonction du pays/de la région de destination dans l'adresse d'expédition de l'envoi et l'article. Si aucune donnée sur le pays d'origine n'a été configurée, cette valeur revient au paramètre trouvé dans **Produit commercialisé \> Commerce extérieur \> Origine**. Si aucune donnée sur le pays d'origine n'est trouvée, vous devez saisir manuellement le pays d'origine après avoir généré le document.

### <a name="certifier-signature-and-date"></a>Signature et date du certificateur

Vous devez le saisir manuellement après avoir généré le document.

### <a name="consists-of-number-of-pages"></a>Se compose d'un nombre de pages

L'utilisateur qui signe la certification doit saisir manuellement le nombre de pages (pour vérification) après avoir généré le document.

### <a name="page-numbers"></a>Numéros de page

Page actuelle et nombre de pages imprimées au bas du document.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]