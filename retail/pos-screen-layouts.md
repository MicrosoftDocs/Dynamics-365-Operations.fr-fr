---
title: "Configuration des mises en page de l&quot;écran du PDV"
description: "Cette rubrique fournit des informations sur les mises en page de l&quot;écran pour Microsoft Dynamics 365 pour les opérations - expériences de Retail (POS) du point de vente."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Configuration des mises en page de l'écran du PDV

Cette rubrique fournit des informations sur les mises en page de l'écran pour Microsoft Dynamics 365 pour les opérations - expériences de Retail (POS) du point de vente.

Microsoft Dynamics 365 pour les opérations - L'interface utilisateur de Retail (POS) de point de vente peut être configurée avec une combinaison des profils et les mises en page de l'écran visuels, affectée aux magasins, aux registres, et/ou les utilisateurs.

## <a name="visual-profile"></a>Profil visuel
Les profils visuels sont affectés à des registres et pour spécifier les éléments visuels qui sont - spécifiques et sont partagés par plusieurs utilisateurs. Tout utilisateur qui enregistre dans le registre a le même thème, couleurs, et images. ** Numéro de profil ** - Numéro de profil est l'identificateur unique pour le profil visuel. ** La description ** - Description vous permet de spécifier un nom significatif qui permet d'identifier le profil correct pour votre cas. ** Le thème ** - Les utilisateurs peuvent choisir entre les thèmes légers ou foncés d'application. Ces paramètres concernent police et Couleurs le parcours dans l'application. ** La couleur de vue ** - La couleur de vue est utilisée dans le système POS pour différencier ou certains éléments mettre en surbrillance visuels tels que des vignettes, les boutons de commande, ou des liens hypertextes. Ces éléments sont généralement déductibles. ** La couleur d'en-tête ** - La couleur d'en-tête permet à l'utilisateur pour configurer la couleur de l'en-tête de page pour répondre aux besoins de marquage à chaud du détaillant. Cette fonction est disponible uniquement dans Dynamics 365 pour la version 1611 d'opérations. ** Les milieux de connexion ** - Les utilisateurs peuvent spécifier une image d'arrière-plan pour l'écran de connexion. Volume de fichier des fonds d'image doit être aussi réduit que possible, car enregistrer et charger des fichiers peuvent avoir un impact sur le comportement et les performances de l'application. ** Le fond d'application ** - Le PDV peut également utiliser une image comme fond affichée dans l'application à la place de la couleur solide de thème. Comme pour les milieux de connexion, il est recommandé pour que le volume de fichier et minimal que possible.

## <a name="screen-layouts"></a>Mises en page de l'écran
Configuration de mise en page de l'écran détermine les actions, le contenu, et le placement des contrôles d'IU dans l'écran d'accueil du PDV et l'écran de transaction. ** L'écran de bienvenue ** - dans la plupart des cas, l'écran de bienvenue est la page que les utilisateurs verront lorsqu'ils enregistrent d'abord dans le système POS. L'écran d'accueil peut correspondre à une image de marquer et des groupes de boutons qui permettent d'accéder aux opérations de PDV. Généralement, les opérations qui ne sont pas spécifiques à la transaction actuelle sont placées ici. ** L'écran de transaction ** - L'écran de transaction est l'écran principal dans POS pour traiter les transactions de vente et des commandes. L'écran de transaction peut être configuré à l'aide de le concepteur de mise en page de l'écran. ** L'écran par défaut de début ** - Certains détaillants préfèrent que le caissier accèdent directement dans l'écran de transaction après avoir connecté. Le paramètre par défaut d'écran de début permet aux utilisateurs de définir cette procédure pour chaque mise en page de l'écran.

### <a name="assignment"></a>Affectation

Les mises en page de l'écran peuvent être affectées au magasin, dans le Registre, ou de l'utilisateur. L'affectation d'utilisateur remplace l'affectation de registre et de magasin, et l'affectation de registre remplace l'affectation de magasin. Dans un scénario unique où tous les utilisateurs utilisent la même mise en page quel que soit le Registre ou du rôle, la mise en page de l'écran peut être paramétrée uniquement au magasin. En raison de les registres certains utilisateurs ou nécessitent des mises en page spécialisées, ils peuvent être affectés en conséquence.

### <a name="layout-sizes"></a>Tailles de mise en page

Cette fonction s'applique uniquement à Dynamics 365 pour la version 1611 d'opérations. Comme les mises en page de l'écran peuvent être utilisées dans de nombreux cas dans les tailles et les résolutions d'écran multiples, les utilisateurs peuvent configurer leur mise en page et contenu pour chacun. L'application du PDV choisira automatiquement la taille de mise en page la plus proche du périphérique au moment de le démarrage. Une mise en page de l'écran peut également contenir des configurations pour les périphériques complets et compacts. Cette configuration permet à un utilisateur d'affecter à une mise en page de l'écran unique qui travaillera effectués sur différentes tailles et facteurs d'écran dans le magasin. ** Le Modern POS - complet ** - des dispositions complètes sont généralement recommandé utilisé pour les plus importants affiche comme les moniteurs ou des tablettes de PC. Les utilisateurs peuvent choisir les éléments de l'IU à inclure, déterminent leur taille et emplacement, et configurer leurs propriétés détaillées. Les mises en page complètes prennent en charge les configurations Portrait et Paysage. ** Le Modern POS - contrat ** - Les mises en page compactes sont généralement recommandé utilisé pour des téléphones ou les petites tablettes. Les possibilités de conception sont limitées pour les périphériques compacts. Les utilisateurs peuvent configurer les colonnes et les champs pour la réception et les volets des totaux.

### <a name="screen-layout-designer"></a>Concepteur de mise en page de l'écran

Chaque taille de mise en page dans une mise en page de l'écran doit être configurée à l'aide de le concepteur de mise en page de l'écran. Le concepteur permet aux utilisateurs de spécifier et de configurer les éléments de l'IU de l'écran de transaction. Le concepteur de mise en page de l'écran utilise ClickOnce pour télécharger, l'installation, et lancer la dernière version de l'application à chaque fois les accès utilisateur il. Veillez à vérifier les besoins du navigateur pour l'utilisation de ClickOnce- certains navigateurs, tels que chrome, nécessitent des extensions. ** La sécurité de numéro ** - La sécurité de numéro est l'entrée principale d'utilisateur de la transaction POS. Elle peut être configurée pour afficher le clavier à l'écran complète, qui est idéale des écrans tactiles, ou le champ d'entrée, qui peut être utilisé avec un clavier physique. Les paramètres de sécurité de numéros sont disponibles dans la mise en page complète uniquement. Dans Dynamics 365 pour la version 1611 d'opérations, des mises en page compactes ont toujours la protection complète de numéro disponible dans l'écran de transaction. ** Le volet des totaux ** - le panneau de totaux peut être configuré dans d'un ou deux colonnes dans les champs d'afficher comme la ligne nombre, montant de remise, frais, sous-total, et taxe. Dans Dynamics 365 pour la version 1611 d'opérations, des mises en page compactes prennent en charge qu'une seule colonne de totaux. ** Réception ** - ** ** le panneau de réception contient les lignes de vente, les lignes de paiement, puis les informations de livraison pour les produits et services traités dans POS. Les utilisateurs peuvent spécifier des colonnes, des largeurs, et le positionnement dans le temps. Dans les mises en page compactes dans Dynamics 365 pour la version 1611 d'opérations, vous pouvez également configurer des informations supplémentaires qui figurent dans la ligne sous la ligne principale. ** Carte de client ** - L'affiche des informations de carte de client faisant partie du client actuellement associé à la transaction. La carte de client peut être configurée pour masquer ou des informations supplémentaires d'affiche. ** Le contrôle de l'onglet ** - Le contrôle de l'onglet peut être placé dans la mise en page de l'écran, et les autres contrôles tels que le bloc de numéro, la carte client, ou les groupes de boutons peuvent être placés dans l'onglet. Le contrôle de l'onglet est un conteneur qui aide les utilisateurs correspondent plus de contenu dans l'écran. Le contrôle de l'onglet est disponible uniquement pour les mises en page complètes. ** Image ** - Le contrôle d'image peut être utilisée pour afficher le logo de magasin ou autre image de marquer dans l'écran de transaction. Le contrôle de l'image n'est disponible que pour les mises en page complètes. ** Produits recommandés ** - Si configuré pour l'environnement, le contrôle recommandé de produits apprentissage de machine des suggestions de produit d'afficher sur. Le contrôle recommandé de produit est disponible uniquement pour les mises en page complètes dans Dynamics 365 pour la version 1611 d'opérations. ** Le contrôle personnalisé ** - Le contrôle personnalisé sert d'espace réservé dans la mise en page de l'écran permet aux utilisateurs de l'espace de réserves pour le contenu personnalisé. Le contrôle personnalisé est disponible uniquement pour les mises en page complètes.

<a name="see-also"></a>Voir également :
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)


