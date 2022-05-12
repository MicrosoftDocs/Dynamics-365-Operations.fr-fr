---
title: Guide de localisation de l’e-commerce Dynamics 365 Commerce
description: Cette rubrique décrit comment localiser un site d’e-commerce Microsoft Dynamics 365 Commerce dans d’autres langues et configurer le site pour qu’il prenne en charge plusieurs canaux.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1e9d91036ceeb9161dc8ee903532b2cf3ca435e2
ms.sourcegitcommit: 26c726bd0b00935e3d2c31fdc5a3b2ae03a8a2b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661525"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Guide de localisation de l’e-commerce Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment localiser un site d’e-commerce Microsoft Dynamics 365 Commerce dans des langues supplémentaires et configurer le site pour prendre en charge plusieurs canaux, et couvre également les concepts et la terminologie liés au processus.

Les capacités d’e-commerce dans Dynamics 365 Commerce ont été conçues pour permettre des expériences en ligne qui peuvent être adaptées à des pays et des langues spécifiques, tout en permettant la réutilisation maximale des modèles, des pages, du contenu et des médias. Vous pouvez également créer un site de base, puis le développer sur de nouveaux marchés en ajoutant la prise en charge de pays et de langues supplémentaires au fil du temps.

## <a name="definitions"></a>Définitions

**Paramètres régionaux, identificateur de paramètres régionaux** : paramètre régional (également appelé identificateur de paramètres régionaux) définit une langue associée à un pays ou à une région. Par exemple, l’identificateur de paramètres régionaux « fr-ca » est associé au français canadien.

**Langue de base** : langue dans laquelle vous développez le contenu de votre site avant de l’exporter pour la localisation.

**Chaîne, boutique en ligne** : canal (également appelé boutique en ligne) définit les modes de paiement, les groupes de prix, les hiérarchies de produits, les assortiments et les produits pour une vitrine d’e-commerce en ligne.

## <a name="concepts"></a>Concepts

### <a name="url-driven-experience"></a>Expérience basée sur l’URL

Les sites d’e-commerce Dynamics 365 Commerce offrent aux clients des expériences uniques commercialisées et localisées via des canaux et des identificateurs de paramètres régionaux. Les canaux définissent les produits, les catégories, les devises et les modes de paiement uniques pour un marché, et les identificateurs de paramètres régionaux déterminent la langue du contenu que les clients voient. Un site d’e-commerce utilise des URL pour différencier les expériences commercialisées et localisées. Les URL de site pour ces expériences uniques de canaux et de paramètres régionaux sont définies pour un site sur la page **Paramètres du site \> Canaux** dans le générateur de site Dynamics 365 Commerce.

Dans le générateur de site, une URL est une combinaison d’un domaine et d’un chemin d’accès qui définit le point d’entrée pour une combinaison unique d’un canal et d’un paramètre régional. Dans l’exemple suivant, une boutique en ligne fictive appelée Fabrikam Inc. définit quatre combinaisons uniques d’un canal et d’un paramètre régional, et mappe chaque combinaison à une URL unique qui fournit du contenu aux clients.

| Domaine                     |  Chemin d’accès      | Canal       |   Paramètres régionaux     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Boutique en ligne étendue Fabrikam | fr  |
| `https://fabrikam.com` | /es    | Boutique en ligne étendue Fabrikam | es     |
| `https://fabrikam.ca`  | /      | Magasin en ligne Contoso    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Magasin en ligne Contoso    | en-ca  |

#### <a name="domain"></a>Domaine

Les domaines sont établis quand vous configurez votre site d’e-commerce dans Microsoft Dynamics Lifecycle Services (LCS). Une fois votre environnement d’e-commerce mis en service, vous pouvez ajouter d’autres domaines en ouvrant une demande de service. Pour plus d’informations sur la configuration de domaines pour votre site d’e-commerce, voir [Domaines dans Dynamics 365 Commerce](domains-commerce.md).

#### <a name="path"></a>Chemin d’accès

- Un chemin d’accès est une chaîne arbitraire qui, en combinaison avec le domaine, est mappée à une combinaison unique d’un canal et d’un environnement local. Dans l’exemple précédent, la chaîne utilisée comme chemin d’accès correspond à l’identificateur de paramètres régionaux auquel le chemin d’accès est mappé. Cependant, vous pouvez utiliser une approche différente.
- Une combinaison d’un canal et d’un paramètre régional peut être mappée à un domaine et à un chemin d’accès vide ("/"). Dans l’exemple précédent, les clients qui visitent `https://fabrikam.ca/` obtiendront les produits et les assortiments pour le marché canadien en français canadien.
- Le générateur de site de commerce vous empêche de créer des combinaisons en double d’un domaine et d’un chemin d’accès. Cependant, vous pouvez mapper des combinaisons en double d’un canal et d’un environnement local à une combinaison différente d’un domaine et d’un chemin d’accès.

#### <a name="channel"></a>Canal

- Les canaux (également appelés boutiques en ligne) définissent les modes de paiement, les groupes de prix, les hiérarchies de produits, les assortiments et les produits pour une vitrine d’e-commerce en ligne.
- Les canaux sont définis, configurés et publiés dans Dynamics 365 Commerce headquarters.
- Le générateur de site peut détecter les magasins en ligne qui ont été configurés dans Commerce headquarters et qui sont disponibles pour être mappés sur un site.

Pour plus d’informations sur les canaux, voir [Vue d’ensemble des canaux](channels-overview.md). Pour plus d’informations sur la configuration d’un canal en ligne, voir [Configurer un canal en ligne](channel-setup-online.md).

#### <a name="locale"></a>Paramètres régionaux

- Les paramètres régionaux sont l’identificateur réel utilisé quand vous transférez des fichiers XLIFF (XML Localization Interchange File Format) pour la localisation. Les paramètres régionaux sont définis et publiés pour chaque canal de Commerce headquarters. Pour plus d’informations sur la configuration des langues et des canaux dans le générateur de site, consultez la section suivante.
- Le même paramètre régional peut être mappé sur plusieurs canaux. De cette manière, une langue commune peut être proposée sur plusieurs marchés.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Configurez les langues et les canaux de votre site e-commerce

Tous les sites d’e-commerce Dynamics 365 Commerce sont configurés de manière prédéfinie pour utiliser un seul canal en ligne et une seule langue, que vous commenciez avec le site de démonstration Fabrikam ou que vous créiez un site à partir de zéro.

Dans cette configuration, les clients et les partenaires développent généralement tous les actifs qui seront utilisés dans différents pays et langues. Ces actifs comprennent des modèles, des pages, des fragments, du contenu et des médias. Tout le contenu du site est développé dans la première langue que vous avez sélectionnée pour votre site, ou si vous utilisez le site de démonstration Fabrikam, le contenu du site sera développé en anglais.

![Site d’e-commerce Dynamics 365 Commerce prédéfini](media/loc-guide-1.png)

> [!NOTE]
> Vous pouvez configurer le site de démonstration Fabrikam pour une langue supplémentaire afin que le développement de contenu puisse être effectué dans cette langue. Pour plus d’informations sur l’ajout d’une nouvelle langue à un site et à un canal, consultez la section [Configurer une langue supplémentaire pour votre site](#configure-an-additional-language-for-your-site) plus loin dans cette rubrique.

Cependant, le système de gestion de contenu (CMS) et le modèle de page pour les sites d’e-commerce Dynamics 365 Commerce ont été conçus pour permettre l’expansion vers de nouveaux marchés et régions. Par conséquent, via un seul site d’e-commerce, vous pouvez gérer les actifs d’une boutique en ligne couvrant plusieurs marchés et langues.

![Site d’e-commerce Dynamics 365 Commerce couvrant plusieurs marchés et langues](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>Configurer une langue supplémentaire pour votre site

Le processus de configuration d’une nouvelle langue pour un site d’e-commerce comporte trois étapes.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>Étape 1 : Ajoutez la langue à votre canal (boutique en ligne) dans Commerce headquarters

1. Dans Commerce headquarters, accédez au canal auquel vous souhaitez ajouter la nouvelle langue. Pour trouver la liste des canaux configurés dans Commerce headquarters, accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.
1. Ouvrez la boutique en ligne associée à votre site en sélectionnant sa valeur **ID de canal de vente au détail**. Vous pouvez vérifier la boutique en ligne associée à votre site en ouvrant la page de configuration du site **Canaux** dans le générateur de site Commerce et en regardant le nom de la boutique en ligne dans la colonne **Canaux**. 
1. Dans l’organisateur **Langues**, sélectionnez **Ajouter**. Dans le champ **Langue**, sélectionnez le code de paramètres régionaux pour la nouvelle langue. Sélectionnez ensuite **Enregistrer**.
1. Accédez à **Retail et Commerce \> Informatique Retail et Commerce \> Programme de distribution**, et exécutez la tâche **Configuration de canal 1070**. Quand le travail est terminé, vous pouvez passer à l’étape 2 et ajouter la langue à un canal pour votre site dans le générateur de site.

![Raccourci Langues d’une boutique en ligne dans Commerce headquarters](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>Étape 2 : Ajouter la langue à un canal dans le générateur de site

Pour ajouter une langue à un canal dans le générateur de site, procédez comme suit.

1. Dans le générateur de site Commerce, ouvrez votre site, puis ouvrez la page **Canaux** dans les paramètres du site.
1. Sélectionnez le nom du canal auquel ajouter la langue.
1. Dans le volet droit, sélectionnez **Ajouter un paramètre régional**.
1. Dans la boîte de dialogue **Ajouter un paramètre régional**, sous **Ajouter un paramètre régional**, sélectionnez les paramètres régionaux pour la langue précédemment ajoutée au canal dans Commerce headquarters.
1. Sélectionnez le domaine et le chemin d’accès que les clients demanderont pour afficher votre site dans ce canal et cette langue.
1. Si vous souhaitez que la langue soit la langue par défaut pour l’affichage, la création et la mise à jour des pages et des fragments du générateur de site, cochez la case **Utiliser comme langue de canal de création par défaut**. 
    > [!NOTE]
    > Ce paramètre affecte uniquement le générateur de site. Cela n’influence pas l’expérience du site publié pour vos clients.
1. Cliquez sur **OK**.
1. Sélectionnez **Enregistrer et publier**.

#### <a name="step-3-localize-your-site-content"></a>Étape 3 : Localisez le contenu de votre site

Quand vous revenez à la vue **Pages** dans le générateur de site Commerce, la nouvelle langue sera disponible dans le sélecteur de canaux et de paramètres régionaux en haut à droite. Vous pouvez désormais créer des versions localisées des pages dans votre langue de base.

Le processus de localisation du contenu de vos pages et fragments est décrit dans la section [Localiser le contenu du site d’e-commerce](#localize-e-commerce-site-content) plus loin dans cette rubrique.

### <a name="configure-a-new-channel-for-your-site"></a>Configurer un nouveau canal pour votre site

Les sites d’e-commerce Dynamics 365 Commerce peuvent proposer des expériences définies sur plusieurs canaux en ligne configurés au Commerce headquarters. Un site utilise plusieurs canaux pour montrer aux clients une configuration unique de modes de paiement, de groupes de prix, de hiérarchies de produits, d’assortiments et d’un ensemble de produits. Un canal est généralement utilisé pour configurer ces dimensions afin de répondre aux exigences et aux préférences de l’expérience associée à chaque pays. Cependant, cette approche est une décision commerciale que le client prend. Ce n’est pas une exigence.

Les conditions préalables et les tâches associées à la configuration d’un canal (boutique en ligne) sortent du cadre de ce document. Pour plus d’informations sur la configuration d’un canal en ligne dans Commerce headquarters, voir [Principes de base de configuration de canal](channels-overview.md#channel-setup-basics). Pour plus d’informations sur les étapes et les exigences spécifiques aux canaux en ligne, voir [Configurer un canal en ligne](channel-setup-online.md).

Pour ajouter un canal à votre site dans le générateur de site, procédez comme suit.

1. Dans le générateur de site de Commerce, accédez à **Paramètres de site \> Canaux**. 
1. Sélectionnez **Ajouter un canal**.
1. Dans la boîte de dialogue **Ajouter un canal** sous **Canal**, sélectionnez le canal à ajouter. 
    > [!NOTE]
    > Vous ne pouvez ajouter que des canaux qui n’ont pas encore été ajoutées à votre site.
1. Sélectionnez les paramètres régionaux par défaut pour le canal. Si vous ajoutez de nouvelles langues au canal, vous pouvez changer la langue par défaut pour l’une d’entre elles.
1. Spécifiez le domaine et le chemin d’accès qui constitueront l’URL qui diffuse le contenu et les expériences pour cette combinaison d’un canal et d’une langue.
1. Cliquez sur **OK**.
1. Sélectionnez **Enregistrer et publier**.

## <a name="localize-e-commerce-site-content"></a>Localiser le contenu du site d’e-commerce

### <a name="xliff-basics"></a>Principes de base de XLIFF

XLIFF est un format de fichier standard du secteur d’activité pour transmettre du contenu localisable entre les outils de gestion de contenu. Le générateur de sites de commerce utilise le format de fichier XLIFF pour exporter le contenu des métadonnées de page, de fragment et d’image afin qu’il puisse être localisé et réimporté.

Les clients Microsoft Dynamics travaillent généralement avec des fournisseurs de localisation tiers tels que [Translated.com](https://translated.com/welcome) pour traduire leurs fichiers XLIFF dans les langues dont ils ont besoin.

### <a name="localize-assets-in-site-builder"></a>Localiser les actifs dans le générateur de site

Les actifs de site d’e-commerce suivants peuvent être localisés dans le créateur de site :

- Pages
- Fragments
- Actifs médias
- Modules

Toutes les nouvelles pages, fragments et actifs multimédias sont créés dans le contexte du canal et de la langue actuellement sélectionnés dans le sélecteur de canaux et de paramètres régionaux. Cette langue est généralement votre "langue de base", à condition que vous n’ayez pas configuré de langues ou de canaux supplémentaires. Sur les sites où plusieurs canaux et langues sont configurés, la "langue de base" est définie par le canal et les paramètres régionaux que vous avez définis par défaut sur la page **Canaux** dans les paramètres du site.

Les étapes de localisation du contenu des pages, des fragments et des ressources multimédias sont similaires. Les exceptions et les différences seront soulignées dans les sections qui suivent. Cependant, les étapes de localisation du contenu du module diffèrent. Pour plus d’informations, voir la section [Localisation de modules](#localize-modules) plus loin dans cette rubrique.

#### <a name="step-1-export-an-xliff-file"></a>Étape 1 : Exporter un fichier XLIFF

Pour exporter un fichier XLIFF pour une page, un fragment ou une image dans le générateur de site, procédez comme suit.

1. Ouvrez l’actif pour lequel vous souhaitez exporter le contenu de la langue de base, afin qu’il puisse être localisé.
1. Dans la barre de commandes, sélectionnez **Localisation \> Exporter XLIFF**.
    > [!NOTE]
    > L’option **Localisation** n’est visible que quand l’actif est dans un état **Modifier**.

Un fichier XLIFF nommé **\<assetname\>.xlf** sera téléchargé dans le dossier de téléchargement de votre navigateur. Ce fichier XLIFF est spécifique à la ressource que vous localisez. Vous exporterez un fichier XLIFF pour chaque ressource que vous souhaitez localiser.

#### <a name="step-2-localize-the-xliff-file"></a>Étape 2 : Localiser le fichier XLIFF

Dans la plupart des cas, vous travaillerez avec un fournisseur de localisation pour traduire vos fichiers XLIFF. Toutefois, si vous localisez des ressources en interne ou si vous souhaitez simplement tester le processus de localisation, vous devez apporter les modifications suivantes à un fichier XLIFF :

- Ajoutez un attribut de langue cible à l’élément /xliff/file et définissez la valeur sur l’identificateur de paramètres régionaux de la langue vers laquelle vous localisez. 
    > [!NOTE]
    > Cet identificateur de paramètres régionaux doit correspondre à l’identificateur de paramètres régionaux da la page **Canaux** dans les paramètres du site.
- Pour chaque élément //source, ajoutez un frère d’élément cible où la valeur de texte est la version localisée du contenu de cet élément source.

Pour plus d’informations sur le schéma qui régit les fichiers XLIFF, consultez la [Spécification XLIFF 1.2](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Pour localiser une ressource dans plusieurs langues, vous devez créer un fichier XLIFF localisé pour chacune de ces langues.

#### <a name="step-3-import-the-localized-xliff-file"></a>Étape 3 : Importer le fichier XLIFF localisé

Pour importer un fichier XLIFF pour une ressource, procédez comme suit.

1. Dans le générateur de site Commerce, ouvrez la ressource pour laquelle vous souhaitez importer un fichier XLIFF.
1. Dans le sélecteur de canal et de paramètres régionaux en haut à droite, sélectionnez le canal et la langue pour lesquelles vous importez du contenu localisé.
1. Dans la barre de commandes, sélectionnez **Localisation \> Importer XLIFF**. Ensuite, recherchez et sélectionnez le fichier XLIFF localisé pour la ressource et la langue sélectionnées.

Une fois le fichier XLIFF importé avec succès, une "variante" de la page, du fragment ou de l’actif est créée. À partir de ce moment, toutes les modifications apportées à la variante localisée n’affecteront que cette variante. Ils n’affecteront pas l’actif de base dont la variante est dérivée. De même, les modifications apportées à l’actif de base n’affecteront pas la variante de cet actif. 

Cependant, dans le cas des pages, vous pouvez apporter des modifications aux variantes en modifiant le modèle ou la mise en page auxquels ces pages sont liées. De même, les modifications apportées à un fragment affecteront toutes les pages qui dépendent de cette variante.

### <a name="images"></a>Images

Les images peuvent être rendues dans une variante de page ou de module uniquement si les métadonnées de contenu associées à ces images sont localisées. Actuellement, les métadonnées suivantes d’un élément multimédia sont localisables :

- Texte de remplacement
- Description
- Titre

Actuellement, vous ne pouvez pas localiser le binaire d’un élément numérique tel qu’une image ou une vidéo. L’équipe de produit Dynamics 365 Commerce travaille actuellement sur cette capacité.

### <a name="localize-modules"></a>Localiser des modules

Les chaînes rendues dans le cadre du module lui-même (par exemple, "Précédent" et "Suivant" dans un module carrousel) sont localisées séparément du contenu du module. Pour obtenir des instructions, voir [Localiser un module](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Glossaire sur le modèle de page](page-elements-overview.md)

[Partage intercanal](cross-channel-sharing.md)

[Localiser un module](e-commerce-extensibility/localize-module.md)

[Fichier de définition de module](e-commerce-extensibility/module-definition-file.md)

[Localiser les ressources d’extension et les fichiers de libellés Commerce](dev-itpro/extension-resource-localization.md)

[Globaliser les modules avec la classe CultureInfoFormatter](e-commerce-extensibility/globalize-modules.md)

[Paramètres de l’application : Thèmes](e-commerce-extensibility/app-settings.md#themes-section)
