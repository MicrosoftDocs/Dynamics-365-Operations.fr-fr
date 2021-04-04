---
title: Recherche étendue de format d’état électronique (ER)
description: Cette rubrique décrit comment une référence de format ER peut être configurée dans la recherche de format ER lorsque le format requis est stocké dans le référentiel global.
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 9062cea14ddfd27d88ce5bcecee75f9b2f8b542c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561852"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>Autoriser les utilisateurs à configurer une référence de format ER en demandant un format à partir du référentiel global

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser le cadre [État électronique](general-electronic-reporting.md) (ER) pour configurer des [formats](general-electronic-reporting.md#FormatComponentOutbound) pour les documents sortants conformes aux obligations légales de différents pays/régions. Vous pouvez également utiliser le cadre ER pour configurer des [formats](general-electronic-reporting.md#FormatComponentInbound) pour analyser les documents entrants et utiliser les informations de ces documents pour ajouter ou mettre à jour les données d’application. Chacun de ces formats peut être utilisé dans votre instance Dynamics 365 Finance pour la gestion des documents commerciaux entrants ou sortants dans le cadre d’un certain processus commercial.

Habituellement, vous devez spécifier le format ER à utiliser dans un processus commercial donné. Pour ce faire, sélectionnez un format ER unique dans un champ de recherche configuré dans le cadre de paramètres spécifiques au processus commercial. Ces champs de recherche sont généralement implémentés à l’aide de l’API appropriée du cadre ER. Pour plus d’informations, voir [API du framework ER - code pour afficher une recherche de mappage de format](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

Par exemple, lorsque vous configurez les [paramètres de commerce extérieur](https://docs.microsoft.com/dynamics365/finance/localizations/emea-intrastat#set-up-foreign-trade-parameters), vous devez configurer les références aux formats ER individuels qui seront utilisés pour générer la déclaration Intrastat et le rapport de contrôle de la déclaration Intrastat. Les captures d’écran ci-dessous montrent à quoi ressemble le champ de recherche des formats ER dans la page **Paramètres de commerce extérieur**.

Si l’instance Finance actuelle ne contient aucun format ER lié au processus commercial Intrastat, ce champ de recherche sera vide.

[![Page Paramètres de commerce extérieur](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Si l’instance Finance actuelle ne contient aucun format ER lié au processus commercial Intrastat, ce champ de recherche présentera les formats ER.

[![Page Paramètres de commerce extérieur](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

Cette recherche ne propose que les formats ER qui ont déjà été importés dans l’instance Finance actuelle. Pour [importer](./tasks/er-import-configuration-lifecycle-services.md) des solutions ER vers l’instance Finance actuelle, vous devez disposer des autorisations pour exécuter la fonction appropriée du cadre ER qui prend en charge le [cycle de la vie ](general-electronic-reporting-manage-configuration-lifecycle.md)des solutions ER contenant les formats ER.

À partir de la version Finance 10.0.9 (version d’avril 2020), l’interface utilisateur de la recherche de format ER implémentée à l’aide de l’API du cadre ER a été étendue. Vous pouvez toujours sélectionner les formats ER existants, qui sont sur l’organisateur **Sélectionner la configuration du format**. En plus, la recherche étendue offre une nouvelle option pour rechercher dans le référentiel global (GR) des formats ER spécifiques. Tous les formats ER du GR sont proposés sur l’organisateur **Importer depuis le référentiel global**.

[![Page Paramètres de commerce extérieur](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

Similairement à l’organisateur **Sélectionner la configuration du format**, l’organisateur **Importer depuis le référentiel global** affiche uniquement les formats ER applicables au processus commercial pour lequel un format ER est sélectionné dans ce champ de recherche. Dans cet exemple, il s’agit de la génération de la déclaration Intrastat. Le format ER est applicable à l’entreprise à laquelle l’utilisateur est actuellement connecté, selon le contexte du pays de l’entreprise.

Lorsque vous sélectionnez un format ER sur l’organisateur **Importer depuis le référentiel global**, la [configuration](general-electronic-reporting.md#Configuration) du format ER sélectionné est importée du GR vers l’instance Finance actuelle.

[![Page Paramètres de commerce extérieur](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Ensuite, si l’importation se termine avec succès, la référence au format ER importé est stockée dans ce champ de recherche. Lorsque vous accédez au GR pour la première fois, vous devez suivre le lien fourni pour vous inscrire au [Regulatory Configuration Service](https://aka.ms/rcs) (RCS) qui est utilisé pour gérer l’accès au stockage GR.

[![Page Paramètres de commerce extérieur](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Par défaut, l’organisateur **Importer depuis le référentiel global** présente la liste des formats ER depuis le stockage temporaire qui est automatiquement créé en fonction du contenu GR pour des améliorations de performances. Cela se produit lorsque l’organisateur **Importer depuis le référentiel global** est ouvert la première fois, ce qui peut prendre plusieurs secondes.

Si vous ne voyez pas le format ER requis dans l’organisateur **Importer depuis le référentiel global**, mais vous êtes sûr que ce format ER est stocké dans le GR, sélectionnez l’option **Synchroniser**. Cette option mettra à jour le stockage temporaire et le synchronisera avec le contenu actuel du GR.

## <a name="feature-activation"></a>Activation des fonctionnalités

La disponibilité de cette fonctionnalité est contrôlée par la fonctionnalité **Recherche étendue des configurations de format ER permettant de consulter le référentiel global** dans la **Gestion des fonctionnalités**. Cette fonctionnalité est activée par défaut.

[![Page Gestion des fonctions](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Considérations de sécurité

Le privilège **Gérer les référentiels de configuration** (**ERMaintainSolutionRepositories**) contrôle l’accès au GR pour un utilisateur lançant la recherche de format ER avec l’’organisateur **Importer depuis le référentiel global** activé. Pour permettre aux utilisateurs d’accéder au contenu GR à partir des recherches au format ER, vous devez modifier les paramètres de sécurité en accordant le privilège **ERMaintainSolutionRepositories** aux utilisateurs soit directement, soit en utilisant des rôles et des tâches déjà attribués.

La capture d’écran suivante montre comment ce privilège peut être accordé aux utilisateurs affectés au rôle **Comptable**. Ce rôle autorise les utilisateurs à configurer les paramètres de commerce extérieur et de définir des références aux formats ER dans les champs **Mappage de format de fichier** et **Mappage de format de rapport** sur la page **Paramètres de commerce extérieur**.

[![Page Configuration de sécurité](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Limites

L’accès au GR dans la recherche de format ER n’est actuellement pris en charge que pour la sélection des formats ER utilisés pour générer des documents sortants.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>Pourquoi ne puis-je pas accéder au référentiel global à partir de la recherche au format ER ?

Si vous avez activé la fonction **Recherche étendue des configurations de format ER permettant de consulter le référentiel global** dans la page **Gestion des fonctionnalités**, mais les utilisateurs ne peuvent pas voir les formats ER sur l’organisateur **Importer depuis le référentiel global** et l’option **Synchroniser** est visible mais désactivée, assurez-vous que le privilège **Gérer les référentiels de configuration** (**ERMaintainSolutionRepositories**) a été accordé à l’utilisateur. Contactez votre administrateur système pour obtenir ce privilège.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des états électroniques](general-electronic-reporting.md)
- [AP du cadre des états électroniques (ER)](er-apis-app73.md)
- [Gérer le cycle de vie des configurations des états électroniques (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]