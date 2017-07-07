---
title: "Configurer les mises en page d'écran pour le PDV"
description: "Cette rubrique fournit des informations sur les mises en page de l'écran pour le point de vente (PDV) Microsoft Dynamics 365 for Retail utilisées."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 9f7f46c1bae5bac6eefa0b8c70b079cab76aa8b6
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Configurer les mises en page d'écran pour le PDV

[!include[banner](includes/banner.md)]


Cette rubrique fournit des informations sur les mises en page de l'écran pour le point de vente (PDV) Microsoft Dynamics 365 for Retail utilisées.

L'interface utilisateur Microsoft Dynamics 365 for Retail - Point de vente au détail (PDV) peut être configurée avec une combinaison de profils visuels et des mises en page de l'écran, affectés aux magasins, aux registres et/ou aux utilisateurs.

## <a name="visual-profile"></a>Profil visuel
Les profils visuels sont affectés aux registres et permettent de spécifier les éléments visuels qui sont spécifiques aux registres et qui sont partagés par plusieurs utilisateurs. Tout utilisateur qui se connecte au registre a les mêmes thème, couleurs et images. 

**Numéro de profil** - Le numéro de profil est l'identificateur unique du profil visuel. 

**Description** - La description vous permet de spécifier un nom significatif qui permet d'identifier le profil correct pour votre cas.

**Thème** - Les utilisateurs peuvent choisir entre les thèmes d'application Clair ou Foncé. Ces paramètres concernent la couleur de police et d'arrière-plan dans l'application.

**Couleur d'accentuation** - La couleur d'accentuation est utilisée dans le PDV pour différencier ou mettre en évidence certains éléments visuels tels que des vignettes, des boutons de commande ou des liens hypertextes. Ces éléments sont généralement actionnables.

**Couleur d'en-tête** - La couleur d'en-tête permet à l'utilisateur denfigurer la couleur de l'en-tête de page pour répondre aux besoins de marquage du détaillant. Cette fonction est disponible uniquement dans Dynamics 365 for Retail version 1611.

**Arrière-plan de connexion** - Les utilisateurs peuvent spécifier une image d'arrière-plan pour l'écran de connexion. La taille du fichier des images d'arrière-plan devrait être aussi petite que possible, car le stockage et le chargement de fichiers volumineux peuvent avoir un impact sur le comportement et les performances de l'application.

**Arrière-plan d'application** - Le PDV peut également utiliser une image comme arrière-plan affichée dans l'application à la place de la couleur de thème unie. Comme pour l'arrière-plan de connexion, il est recommandé de conserver une taille de fichier aussi réduite que possible.

## <a name="screen-layouts"></a>Mises en page de l'écran
La configuration de la mise en page de l'écran détermine les actions, le contenu et le placement des contrôles de l'interface utilisateur dans l'écran d'accueil et l'écran de transaction du PDV. 

**Écran d'accueil** - dans la plupart des cas, l'écran d'accueil est la page que les utilisateurs voient lorsqu'ils se connectent la première fois au PDV. L'écran d'accueil peut correspondre à une image de marque et des groupes de boutons qui permettent d'accéder aux opérations de PDV. Généralement, les opérations qui ne sont pas spécifiques à la transaction actuelle sont placées ici. 

**Écran de transaction** - L'écran de transaction est l'écran principal dans le PDV pour traiter les transactions de vente et les commandes. L'écran de transaction peut être configuré à l'aide du concepteur de mise en page de l'écran. 

**Écran d'accueil par défaut** - Certains détaillants préfèrent que le caissier accèdent directement à l'écran de transaction après s'être connecté. Le paramètre de l'écran d'accueil par défaut permet aux utilisateurs de définir cette procédure pour chaque mise en page de l'écran.

### <a name="assignment"></a>Affectation

Les mises en page de l'écran peuvent être affectées au magasin, au registre ou à l'utilisateur. L'affectation d'utilisateur remplace l'affectation de registre et de magasin, et l'affectation de registre remplace l'affectation de magasin. Dans un scénario unique où tous les utilisateurs utilisent la même mise en page, quel que soit le registre ou le rôle, la mise en page de l'écran peut être paramétrée uniquement au niveau du magasin. En raison de certains registres ou utilisateurs qui nécessitent des mises en page spécialisées, elles peuvent être affectées en conséquence.

### <a name="layout-sizes"></a>Tailles de mise en page

Cette fonction s'applique uniquement dans Dynamics 365 for Retail version 1611. Parce que dans de nombreux cas, les mises en page peuvent être utilisées sur plusieurs tailles d'écran et résolutions, les utilisateurs peuvent configurer leur mise en page et leur contenu pour chacun. L'application de PDV choisira automatiquement la taille de disposition la plus proche pour l'appareil au moment du démarrage. Une mise en page de l'écran peut également contenir des configurations pour les périphériques complets et compacts. Cette configuration permet à un utilisateur d'être affecté à une disposition d'écran unique qui fonctionnera selon différentes tailles et facteurs de forme au sein du magasin. 

**Modern POS - Complet** - Les mises en page complètes sont généralement utilisées pour des écrans plus grands tels que des moniteurs ou des tablettes PC. Les utilisateurs peuvent choisir les éléments de l'IU à inclure, déterminer leur taille et emplacement, et configurer leurs propriétés détaillées. Les mises en page complètes prennent en charge les configurations Portrait et Paysage. 

**Modern POS - Compact** - Les mises en page compactes sont généralement recommandées pour les téléphones ou les petites tablettes. Les possibilités de conception sont limitées pour les périphériques compacts. Les utilisateurs peuvent configurer les colonnes et les champs pour les volets Ticket de caisse et Totaux.

### <a name="screen-layout-designer"></a>Concepteur de mise en page de l'écran

Chaque taille de mise en page dans une mise en page de l'écran doit être configurée à l'aide du concepteur de mise en page de l'écran. Le concepteur permet aux utilisateurs de spécifier et de configurer les éléments de l'IU de l'écran de transaction. Le concepteur de mise en page de l'écran utilise ClickOnce pour télécharger, installer et lancer la dernière version de l'application chaque fois que l'utilisateur y accède. Veillez à vérifier les besoins du navigateur pour l'utilisation de ClickOnce- certains navigateurs, tels que chrome, nécessitent des extensions. 

**Pavé numérique** - Le pavé numérique est le mode de saisie utilisateur principal dans l'écran de transaction du PDV. Il peut être configuré pour afficher l'intégralité du pavé sur l'écran, idéal pour les écrans tactiles, ou seulement le champ de saisie, qui peut être utilisé avec un clavier physique. Les paramètres du pavé numérique sont disponibles dans la mise en page complète uniquement. Dans Dynamics 365 for Retail version 1611, les mises en page compactes ont toujours le bloc-notes complet disponible à partir de l'écran Transaction.

**Volet des totaux** - Le volet des totaux peut être configuré dans une ou deux colonnes pour afficher les champs tels que le nombre de lignes, le montant de la remise, les frais, le sous-total et les taxes. Dans Dynamics 365 for Retail version 1611, les mises en page compactes ne prennent en charge qu'une seule colonne de totaux. 

**Ticket de caisse** - Le volet Ticket de caisse contient les lignes de vente, les lignes de paiement, puis les informations de livraison pour les produits et services traités dans le PDV. Les utilisateurs peuvent spécifier les colonnes, les largeurs et le positionnement. Dans les mises en page compactes dans Dynamics 365 for Retail version 1611, vous pouvez également configurer des informations supplémentaires qui figurent dans la ligne sous la ligne principale. 

**Carte du client** - La carte du client affiche les informations relatives au client actuellement associé à la transaction. La carte du client peut être configurée pour masquer ou afficher des informations supplémentaires. 

**Contrôle Onglet** - Le contrôle Onglet peut être placé dans la mise en page de l'écran, et les autres contrôles tels que le pavé numérique, la carte du client ou les groupes de boutons peuvent être placés dans l'onglet. Le contrôle Onglet est un conteneur qui aide les utilisateurs à contenir plus de contenu dans l'écran. Le contrôle Onglet est disponible uniquement pour les mises en page complètes. 

**Image** - Le contrôle Image peut être utilisée pour afficher le logo de magasin ou une autre image de marque dans l'écran de transaction. Le contrôle Image est disponible uniquement pour les mises en page complètes. 

**Produits recommandés** - Si configuré pour l'environnement, le contrôle Produits recommandés affichera les suggestions de produits basées sur Machine Learning. Le contrôle Produits recommandés est disponible uniquement pour les mises en page complètes dans Dynamics 365 for Retail version 1611. **Contrôle personnalisé **- Le contrôle personnalisé agit comme un espace réservé dans la mise en page de l'écran pour permettre aux utilisateurs de réserver de l'espace pour un contenu personnalisé. Le contrôle Personnalisé est disponible uniquement pour les mises en page complètes.

<a name="see-also"></a>Voir également :
--------

[Installer le concepteur de mise en page de Retail POS](install-pos-layout-designer.md)




