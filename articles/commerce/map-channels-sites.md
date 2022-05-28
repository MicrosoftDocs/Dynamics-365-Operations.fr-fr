---
title: Mettre les canaux en correspondance avec les sites d’e-commerce
description: Cette rubrique décrit certains des scénarios de mappage de canaux les plus courants dans Microsoft Dynamics 365 Commerce qui peut être extrapolé pour la plupart des autres besoins de l'entreprise.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8ce272d63b4a37f99661333a02434708205ea19a
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743588"
---
# <a name="map-channels-to-e-commerce-sites"></a>Mettre les canaux en correspondance avec les sites d’e-commerce

Cette rubrique décrit certains des scénarios de mappage de canaux les plus courants dans Microsoft Dynamics 365 Commerce qui peut être extrapolé pour la plupart des autres besoins de l'entreprise.

Dynamics 365 Commerce prend en charge de nombreux scénarios d'entreprise pour le mappage des [canaux en ligne](#channels) qui ont un ensemble configuré de produits, de prix et de remises aux expériences de [site e-commerce](#e-commerce-sites) pour les clients.

Cette rubrique couvre les scénarios suivants :

- **Un canal monolingue qui offre une expérience de site e-commerce unique.** Par exemple, ce scénario peut impliquer un site de marque unique configuré pour le marché anglais américain.
- **Un canal multilingue qui offre une expérience de site localisé unique.** Par exemple, ce scénario peut impliquer un site de marque unique configuré pour le Canada avec une prise en charge en français et en anglais. Dans ce scénario, les utilisateurs qui sélectionnent différentes langues bénéficient de la même expérience de site, mais celle-ci est localisée dans la langue sélectionnée par chaque utilisateur.
- **Un canal multilingue qui offre une expérience de site différente par langue.** Par exemple, ce scénario peut impliquer un site de marque unique configuré pour le Canada avec une prise en charge en français et en anglais. Dans ce scénario, il existe une expérience de site unique pour chaque langue.
- **Plusieurs canaux (unilingues et/ou multilingues) qui ont une seule expérience de site localisée.** Par exemple, ce scénario peut impliquer un site de marque unique configuré pour l'Australie et la Nouvelle Zélande. Dans ce scénario, les deux pays partagent la même expérience de site en anglais, mais chaque pays est configuré avec des produits, des devises, des prix, des remises et des modes d'expédition différents.
- **Plusieurs canaux (unilingues et/ou multilingues) qui ont une expérience de site différente par canal.** Par exemple, ce scénario peut impliquer un site de marque unique configuré pour l'Australie, le Canada et l'Allemagne dans plusieurs langues. Dans ce scénario, chaque pays a une expérience de site unique qui est configurée avec des produits, des devises, des prix, des remises et des modes d'expédition différents.

## <a name="channels"></a>Canaux

Un canal (également appelé boutique en ligne ou canal en ligne) représente une vitrine de commerce électronique en ligne utilisée pour cartographier les produits, les prix, les remises, les langues, les modes de paiement, les modes de livraison, les centres de distribution et d'autres aspects de l'expérience en ligne qui sera disponible pour vos clients e-commerçants. Les canaux sont créés et gérés dans Commerce Headquarters et mappés à une seule [entité légale](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). L'entité juridique est généralement basée dans un seul pays qui exige une déclaration fiscale pour le canal et peut être configurée avec une seule devise.

Pour plus d’informations sur les canaux, voir [Vue d’ensemble des canaux](channels-overview.md). Pour plus d’informations sur la création d’un canal en ligne, voir [Configurer un canal en ligne](channel-setup-online.md).

L'exemple d'illustration suivant de Commerce Headquarters montre les canaux en ligne par défaut qui sont déployés avec Dynamics 365 Commerce si l'option de données de démonstration est sélectionnée.

![Canaux de données de démonstration par défaut dans Commerce Headquarters.](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>Sites e-commerce

Un site e-commerce contient un ensemble de pages de site que les clients utilisent pour naviguer et faire des achats. Les sites e-commerce sont gérés dans le générateur de site Commerce.

Pour plus d'informations sur la création et la gestion de sites dans le générateur de site, consultez [Présentation du site e-commerce](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Scénarios de mappage de canaux courants

Dynamics 365 Commerce prend en charge un large éventail de scénarios de mappage de canaux. Les scénarios de mappage de canaux qui suivent ne sont qu'un sous-ensemble de tous les scénarios de mappage de canaux possibles. Ils sont conçus comme un guide pour vous aider à planifier tous les scénarios commerciaux uniques que vous avez. Le magasin d'articles de sport fictif Adventure Works qui est inclus avec les données de démonstration Dynamics 365 Commerce est utilisé comme exemple pour chaque scénario.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Un canal monolingue qui offre une expérience de site e-commerce unique

Dans le scénario le plus simple, un seul canal a une seule langue pour vendre sur un seul marché. Un exemple de ce scénario est une boutique en ligne Adventure Works configurée pour le marché anglais américain uniquement.

L'exemple d'illustration suivant montre une configuration de canal dans Commerce Headquarters. Dans cette configuration, le canal en ligne ne prend en charge qu'une seule langue (**en-us**), une devise unique (**USD**) et une seule entité commerciale (**usrt**) utilisée pour la déclaration fiscale.

![Entité juridique, devise et valeurs linguistiques pour la boutique en ligne Adventure Works mises en évidence dans Commerce Headquarters.](media/channel-mapping-3.png)

Le canal en ligne unique peut être mappé à un seul site e-commerce dans le créateur de site. Pour plus d'informations sur la création d'un nouveau site et sa mise en correspondance avec un canal, consultez la section [Mapper un canal sur un site dans le générateur de site](#map-a-channel-to-a-site-in-site-builder) de cette rubrique.

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Un canal multilingue qui offre une expérience de site localisé unique

Dans ce scénario, un seul canal prend en charge plusieurs langues. Par conséquent, les noms, les descriptions et les attributs des produits peuvent être localisés dans Commerce Headquarters. Pour fournir une expérience de site localisée complète, le contenu marketing du site peut également être localisé dans le générateur de site Commerce.

La limite de ce scénario est qu'un seul canal peut être configuré avec une seule devise, une seule entité juridique et un seul ensemble de produits et de prix. Cette configuration fonctionne mieux pour les pays qui ont une seule devise et plusieurs langues (par exemple, le Canada, qui a les langues anglaise et française), une seule entité juridique et un seul ensemble de produits et de prix.

Chaque langue d'un canal peut être configurée avec son propre nom de domaine. Par exemple, le domaine `www.adventure-works.ca` peut être configuré pour la version anglaise du Canada, et le domaine `www.adventure-works-fr.ca` peut être configuré pour la version française du Canada. Alternativement, différentes langues dans un canal peuvent être configurées dans un seul domaine, puis un chemin différent peut être utilisé pour chaque langue. Par exemple, le domaine `www.adventure-works.ca` peut être configuré pour la version anglaise du Canada, alors le chemin `www.adventure-works.ca/fr` peut être utilisé pour la version française du Canada. [Détection géographique](geo-detection-redirection.md) peut également être activé pour rediriger automatiquement un utilisateur vers le bon site, en fonction de l'emplacement de l'utilisateur.

Pour plus d'informations sur la façon d'autoriser les clients à basculer manuellement entre les langues, consultez la section [Ajouter et configurer le module de sélection de site](#add-and-configure-the-site-picker-module) de cette rubrique. Pour plus d'informations sur la personnalisation des pages et des fragments localisés, consultez la section [Gérer le contenu du site qui a plusieurs canaux et langues](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Un canal multilingue qui offre une expérience de site différente par langue

Vous préférerez peut-être un scénario dans lequel un seul canal prend en charge plusieurs langues, mais une expérience de site complètement différente est rendue pour chaque langue. La méthode recommandée pour mettre en œuvre ce scénario consiste à utiliser des [variantes de pages](#implement-page-variants-for-each-language) sur un seul site.

Une autre méthode consiste à créer un nouveau site e-commerce pour chaque langue dans le créateur de site, puis à mapper chaque site sur un seul canal en ligne et une seule langue. Le résultat sera un canal en ligne unique mappé sur plusieurs sites de commerce électronique, un pour chaque langue. Cette méthode multisite nécessite des ressources de gestion supplémentaires, car il y aura plus d'un site à gérer dans le générateur de site.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Plusieurs canaux (unilingues et/ou multilingues) qui ont une seule expérience de site localisée

Un site de marque peut nécessiter plusieurs canaux en ligne par région pour prendre en charge une devise, un ensemble de produits et un ensemble de prix différents pour chaque canal sur un même site. Par exemple, le site Adventure Works peut avoir un canal en ligne pour le marché canadien en plusieurs langues, un canal pour le marché américain en une langue et un canal pour le marché allemand en une langue. Dans ce scénario, chaque canal en ligne sera configuré pour une entité juridique spécifique à une région, et il peut avoir le même ensemble de produits que les autres canaux, un sous-ensemble de ces produits ou un ensemble de produits différent. Chaque canal aura également ses propres prix dans la devise régionale, les taxes, les remises et les modes d'expédition.

Dans ce scénario, chaque marché peut être configuré avec ses propres noms de domaine. Par exemple, le domaine `www.adventure-works.com` peut être configuré pour le marché américain, et le domaine `www.adventure-works.de` peut être configuré pour le marché allemand. Alternativement, chaque marché peut être configuré pour utiliser un chemin différent. Par exemple, le domaine `www.adventure-works.com` peut être configuré pour le marché américain, alors le chemin `www.adventure-works.com/de` peut être utilisé pour le marché allemand. [Détection géographique](geo-detection-redirection.md) peut également être activé pour rediriger automatiquement les utilisateurs vers le bon site, en fonction de leur région.

Vous pouvez également souhaiter que votre site fournisse une liste déroulante permettant aux utilisateurs de basculer manuellement vers un marché spécifique. Pour plus d’informations, voir la section [Ajouter et configurer le module de sélection de site](#add-and-configure-the-site-picker-module) située plus loin dans cette rubrique.

Pour plus d'informations sur la configuration de plusieurs canaux sur un même site, consultez la section [Configurer plusieurs canaux sur un site e-commerce](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Plusieurs canaux (unilingues et/ou multilingues) qui ont une expérience de site différente par canal

Vous souhaiterez peut-être disposer de plusieurs canaux pour une seule marque dans différentes régions, et vous souhaiterez peut-être que chaque région ait une expérience de site différente. Il existe deux méthodes pour mettre en œuvre ce scénario :

- Utilisez les [variantes de page](#implement-page-variants-for-each-language).
- Configurez un site différent pour chaque canal en ligne dans le créateur de site, puis associez chaque site à un canal en ligne et à une langue différents. Cette méthode multisite nécessite des ressources de gestion supplémentaires, car il y aura plusieurs sites à gérer dans le générateur de site.

## <a name="cross-channel-sharing"></a>Partage intercanal

Le partage intercanal est utile lorsque plusieurs canaux d’un même site peuvent partager du contenu. Par exemple, un détaillant qui possède plusieurs marques et vitrines regroupées dans un même site peut partager du contenu entre certaines ou toutes les vitrines. Le contenu partagé peut inclure des pages pour les conditions générales, les conditions de paiement, les modes d’expédition et les questions fréquentes (FAQ). Pour plus d'informations, voir [Activer et utiliser le partage inter-canal](cross-channel-sharing.md).

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Mapper un canal sur un site dans le créateur de site

Il existe plusieurs méthodes pour créer et configurer des sites afin d'utiliser différents canaux en ligne.

### <a name="create-a-new-site"></a>Créer un site

Vous pouvez créer un tout nouveau site dans le créateur de site en accédant à la page **Sites** et en sélectionnant **Nouveau site**. Puis, dans la boîte de dialogue **Nouveau site** qui s'affiche, vous pouvez sélectionner le canal en ligne et la langue par défaut pour le site, comme illustré dans l'exemple suivant.

![Création d'un nouveau canal dans le générateur de site](media/channel-mapping-4.png)

Le site que vous créez de cette manière sera vide et n'inclura aucune page de site (par exemple, une page d'accueil, des pages de catégories et des pages de produits).

Pour plus d’informations, voir [Créer un site d’e-commerce](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Créer un nouveau site à l'aide de l'opération de copie de site

Au lieu de créer un tout nouveau site vide comme décrit dans la section précédente, une meilleure pratique consiste à commencer par une copie de l'un des sites de démarrage fournis dans la bibliothèque du module Commerce, comme le site Fabrikam ou Adventure Works.

Pour copier un site existant, accédez à la page de liste **Sites** dans le générateur de site, puis sélectionnez **Copier le site**. Puis, dans la boîte de dialogue **Copier le site** qui s'affiche, vous pouvez sélectionner le site source et spécifier le nom du site de destination.

À ce stade, vous ne pouvez pas encore sélectionner le canal en ligne et la langue par défaut pour le site. Cependant, vous pouvez configurer ces propriétés une fois l'opération de copie de site terminée. Lorsque vous sélectionnez le site pour la première fois sur la page de liste **Sites** dans le générateur de site, la boîte de dialogue **Configurer votre site** apparaît, dans laquelle vous pouvez sélectionner le canal et la langue par défaut.

Pour plus d’informations sur l'opération de copie d'un site, voir [Création d’un site e-commerce](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Gérer un canal de site existant

Une fois qu'un site a été configuré avec un canal, vous pouvez gérer et mettre à jour le canal à partir du site sélectionné dans le générateur de site via **Paramètres du site \> Canaux**, comme illustré dans l'exemple suivant.

![Gestion du mappage des canaux dans le générateur de site.](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Prise en charge de plusieurs sites dans un seul client

De nombreux sites de marque peuvent coexister dans un même client. L'exemple d'illustration suivant montre trois sites de marque différents (Adventure Works, Adventure Works Business et Fabrikam), chacun étant mappé à un canal en ligne unique différent.

![Liste des sites dans le générateur de site.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Configurer un seul nom de domaine avec des chemins pour plusieurs sites

Un seul nom de domaine peut être utilisé pour plusieurs sites, et les chemins peuvent ensuite être utilisés pour séparer les sites ou les langues. Par exemple, le domaine `www.mycompany.com` est configuré pour deux sites de commerce électronique différents : un pour Fabrikam et un pour Adventure Works. Dans ce cas, le chemin par défaut (`www.mycompany.com`), également appelé chemin vide, peut être utilisé pour le site Fabrikam, et un autre chemin (par exemple,`www.mycompany.com/adventureworks`) peut être utilisé pour le site Adventure Works. Une autre option consiste à utiliser un chemin personnalisé (par exemple, `www.mycompany.com/fabrikam`) au lieu du chemin par défaut pour le site Fabrikam également.

Alternativement, un nom de domaine différent peut être utilisé pour chaque site (par exemple, `www.adventure-works.com` et `www.fabrikam.com`). Les chemins peuvent ensuite être utilisés pour différentes langues ou régions (par exemple, `www.adventure-works.com/fr-ca` pour le Canada français).

## <a name="configure-multiple-languages-on-a-site"></a>Configurer plusieurs langues sur un site

Les langues peuvent être configurées pour le site e-commerce dans le générateur de site via **Paramètres du site \> Canaux**. Dans l'exemple d'illustration suivant, chaque langue a été configurée en utilisant les paramètres régionaux pour le chemin, de sorte que chaque langue possède une URL unique.

![Plusieurs langues configurées sur un site.](media/channel-mapping-10.png)

Pour ajouter une nouvelle langue de chaîne, accédez à **Paramètres du site \> Canaux**, et sélectionnez le lien de la chaîne. Dans le volet qui apparaît à droite, sélectionnez **Ajouter un paramètre régional** pour sélectionner le canal et les paramètres régionaux que vous souhaitez ajouter. Spécifiez ensuite le chemin à utiliser pour le canal sélectionné.

### <a name="add-and-configure-the-site-picker-module"></a>Ajouter et configurer le module de sélection de site

Après avoir configuré un site avec plusieurs langues et/ou canaux, vous souhaiterez peut-être ajouter un sélecteur de langue à l'en-tête de la page du site, afin que les utilisateurs puissent sélectionner manuellement leur langue ou leur pays. Le [module d'en-tête](author-header-module.md) de la bibliothèque de modules a un support intégré pour que les utilisateurs sélectionnent une langue en utilisant le [module de sélection de site](site-selector.md). Le module de sélection de site peut être ajouté au module d'en-tête dans le fragment d'en-tête.

Pour plus d’informations sur le mode d'ajout et de configuration du module de sélection de site, consultez la section [Ajouter et configurer le module de sélection de site](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Implémenter des variantes de page pour chaque langue

Dans ce scénario, il n'y a qu'un seul canal, mais il existe plusieurs langues. Vous pouvez modifier l'apparence d'une page en fonction de la langue sélectionnée en créant une variante de page pour celle-ci. Vous pouvez ensuite ajouter du contenu localisé à la variante.

Lorsqu'une page est ouverte dans le générateur de site et que vous sélectionnez le lien en haut à droite qui affiche le canal et la langue actuels, un sélecteur de canal et de langue apparaît, comme illustré dans l'exemple suivant. Si vous souhaitez remplacer la page pour la langue actuelle, sélectionnez un autre paramètre régional, puis sélectionnez **Modifier**. Vous pouvez également changer de chaîne si vous [gérez un site qui a plusieurs canaux et langues](#manage-site-content-that has-multiple-channels-and-languages).

![Changer la langue d'une page dans le générateur de site.](media/channel-mapping-14.png)

Si la variante de la page ou du fragment sélectionné n'a pas encore été créée, vous recevez un message d'avertissement, comme illustré dans l'exemple suivant. Dans ce cas, sélectionnez le lien **Créer une variante de page** dans le texte du message. La boîte de dialogue qui s'affiche propose des options qui vous permettent de commencer avec une copie d'une variante existante ou de créer une toute nouvelle page à partir d'un modèle.

![Invite à créer une variante de page dans le générateur de site](media/channel-mapping-16.png)

Si vous ne créez pas de variante, la page d'origine est rendue et affiche la langue appropriée pour les chaînes de module et les informations sur les produits de Commerce Headquarters. Toutefois, si un texte tel qu'un titre de page ou un autre contenu marketing a été spécifié directement dans les modules de page par défaut, les chaînes de ce texte resteront dans la langue d'origine.

Au lieu de créer manuellement chaque page et fragment, vous pouvez exporter chaque page et fragment vers un fichier XLIFF (XML Localization Interchange File Format) qui peut ensuite être envoyé pour localisation. Une fois que chaque XLIFF a été localisé, il peut être importé en tant que variante de page localisée. Pour exporter un fichier XLIFF à partir d'une page ou d'un fragment dans le générateur de site, ou pour importer un fichier XLIFF dans une page ou un fragment, sélectionnez **Localisation** sur la barre de commandes. Sélectionnez ensuite soit **Exporter XLIFF** ou alors **Importer XLIFF**, comme illustré dans l'exemple suivant.

![Importer ou exporter une page ou un fragment au format XLIFF.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Gérer le contenu du site qui a plusieurs canaux et langues

Un site qui a plusieurs canaux et/ou langues stocke une variante unique de chaque page et fragment pour chaque combinaison d'un canal et d'une langue. Ce comportement permet aux variantes de page de contenir des données localisées, mais vous donne également la possibilité de modifier l'apparence d'une page pour une variante spécifique.

Pour plus d'informations sur l'utilisation des variantes de page, consultez la section [Implémenter des variantes de page pour chaque langue](#implement-page-variants-for-each-language) de cette rubrique.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Configurer plusieurs canaux sur un site e-commerce

Vous pouvez ajouter des canaux à un site e-commerce dans le créateur de site en accédant à **Paramètres du site \> Canaux** et en sélectionnant **Ajouter une chaîne**. Ensuite, dans la boîte de dialogue **Ajouter un canal** qui apparaît, vous pouvez sélectionner le canal en ligne et les paramètres régionaux par défaut.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des canaux](channels-overview.md)

[Paramétrer un canal en ligne](channel-setup-online.md)

[Vue d’ensemble des organisations et des hiérarchies d’organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Configurer la géodétection et la redirection](geo-detection-redirection.md)

[Activer et utiliser le partage intercanal](cross-channel-sharing.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Copier un site d’e-commerce](copy-ecommerce-site.md)

[Module de sélection de site](site-selector.md)
