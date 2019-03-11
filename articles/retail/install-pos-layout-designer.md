---
title: Installer le concepteur de mise en page du Point de vente au détail (PDV)
description: Vous pouvez utiliser le concepteur en un seul clic pour concevoir différentes mises en page Retail Modern POS (MPOS) et PDV Cloud, en mode paysage ou en mode portrait, pour les magasins, les caisses enregistreuses, les caissiers, et les responsables.
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7fc5b48b71816b662f016f4a2d909526da0595f4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "327640"
---
# <a name="install-the-retail-point-of-sale-pos-layout-designer"></a>Installer le concepteur de mise en page du Point de vente au détail (PDV)

[!include [banner](includes/banner.md)]

Vous pouvez utiliser le concepteur en un seul clic pour concevoir différentes mises en page Retail Modern POS (MPOS) et PDV Cloud, en mode paysage ou en mode portrait, pour les magasins, les caisses enregistreuses, les caissiers, et les responsables.

Le l'interface de conception graphique de MPOS ou PDV Cloud est contrôlée par la disposition du tiroir-caisse. Une mise en page contrôle la disposition de divers objets. Par exemple, la mise en page du total, la mise en page du groupe d'articles, la mise en page du client, la mise en page des paiements et la mise en page de plusieurs boutons de menu. Les mises en page incluent également l'apparence globale de l'interface de vente présentée aux travailleurs.

## <a name="install-the-one-click-designer"></a>Installer le concepteur en un seul clic

1. Dans Microsoft Dynamics 365 for Retail, utilisez le menu dans le volet supérieur gauche pour accéder à **Vente au détail** **et commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **PDV** &gt; **Mises en page de l'écran**.
2. Sélectionnez n'importe quelle mise en page ayant un type d'application **Modern POS pour Windows** ou **PDV Cloud**, puis cliquez **Concepteur de mise en page**.
3. Dans la barre de Notification qui apparaît au bas de la fenêtre d'Internet Explorer, cliquez sur **Ouvrir** pour installer le concepteur en un seul clic. (La barre de notification peut apparaître dans un emplacement différent dans d'autres navigateurs.)
4. Dans la zone de message **Exécution d'application - Avertissement de sécurité** qui s'affiche, cliquez sur **Exécuter** pour installer l'hôte du concepteur Retail. Un indicateur de progression indique la progression de l'installation.
5. Une fois l'installation terminée, sur la page **Connexion**, entrez votre nom d'utilisateur et votre mot de passe Microsoft Dynamics 365 for Retail, puis cliquez sur **Connexion** pour démarrer le concepteur.
6. Une fois que vos informations d'identification sont validées et que le concepteur démarre, vous pouvez concevoir votre propre mise en page ou modifier la mise en page existante.

    [![Mise en page dans le concepteur en un seul clic](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Résolution des problèmes d'installation du concepteur de mise en page

- Lorsque vous cliquez sur **Concepteur**, l'invite de téléchargement (ou d'exécution) du programme d'installation ne s'affiche pas, ou vos paramètres de sécurité actuels ne permettent pas de télécharger le fichier. 

    **Solutions :**

    - Dans Internet Explorer, assurez-vous que le bloqueur de fenêtres publicitaires est désactivé pour ce site. Cliquez sur **Paramètres** &gt; **Options** &gt; **Confidentialité** &gt; **Rechercher le bloqueur de fenêtres publicitaires**, et modifiez le paramètre, si une modification est requise.
    - Dans Internet Explorer, ajoutez l'URL Dynamics 365 for Retail à vos sites de confiance. Cliquez sur **Paramètres** &gt; **Options** &gt; **Sécurité** &gt; **Sites de confiance** &gt; **Sites** &gt; **Ajouter**.

- Le programme ne démarre pas, et vous recevez l'instruction de contacter le fournisseur.

    **Solution :** Dans Internet Explorer, ajoutez l'URL Dynamics 365 for Retail à vos sites de confiance. Cliquez sur **Paramètre** &gt; **Options** &gt; **Sécurité** &gt; **Sites de confiance** &gt; **Sites** &gt; **Ajouter**.

**Problème connu :** Le concepteur ne fonctionne pas correctement dans les navigateurs Google Chrome et Mozilla Firefox. Nous œuvrons à corriger ce problème.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer, télécharger, installer et activer Retail Modern POS](retail-modern-pos-device-activation.md)
