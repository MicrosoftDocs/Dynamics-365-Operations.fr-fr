---
title: Ouvrir des données d’entité dans Excel et les mettre à jour à l’aide du module complémentaire Excel
description: Cette rubrique explique comment ouvrir des données d’entité dans Microsoft Excel, puis les étudier, les mettre à jour et les modifier à l’aide du module complémentaire Microsoft Dynamics Office pour Excel.
author: ChrisGarty
manager: AnnBe
ms.date: 04/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26d5f165648c1553745e3061cc89bcba42f9636a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688465"
---
# <a name="open-entity-data-in-excel-and-update-it-by-using-the-excel-add-in"></a>Ouvrir des données d’entité dans Excel et les mettre à jour à l’aide du module complémentaire Excel

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment ouvrir des données d’entité dans Microsoft Excel, puis les étudier, les mettre à jour et les modifier à l’aide du module complémentaire Microsoft Dynamics Office pour Excel. Pour ouvrir les données d’entité, vous pouvez commencer à partir d’Excel ou de Finance and Operations.

En ouvrant des données d’entité dans Excel, vous pouvez rapidement les étudier et les modifier à l’aide du module complémentaire pour Excel. Ce complément exige Microsoft Excel 2016.

> [!NOTE]
> Remarque : si votre location Microsoft Azure Active Directory (Azure AD) est configurée pour utiliser les services AD FS (Active Directory Federation Services), vous devez vous assurer que la mise à jour de mai 2016 pour Office a été appliquée, de sorte de pouvoir vous connecter correctement au module complémentaire Excel.

Pour en savoir plus sur l’utilisation du module complémentaire Excel, consultez la courte vidéo [Créer un modèle Excel pour les modèles d’en-tête et de ligne dans Dynamics 365 for Finance and Operations](https://youtu.be/RTicLb-6dbI).

## <a name="open-entity-data-in-excel-when-you-start-from-finance-and-operations"></a>Ouvrir les données d’entité dans Excel au démarrage à partir de Finance and Operations
1. Sur une page de Finance and Operations, sélectionnez **Ouvrir dans Microsoft Office**.

    Si la source de données racine (tableau) de la page est identique à la source de données racine pour toutes les entités, les options par défaut **Ouvrir dans Excel** sont générées pour la page. Les options **Ouvrir dans Excel** se trouvent dans les pages fréquemment utilisées, telles que **Tous les fournisseurs** et **Tous les clients**.
 
2. Cliquez sur l’option **Ouvrir dans Excel** et ouvrez le classeur généré. Ce classeur dispose des informations de liaison pour l’entité, d’un pointeur vers votre environnement, et d’un pointeur vers le module complémentaire Excel.
3. Dans Excel, cliquez sur **Activer la modification** pour permettre l’exécution du module complémentaire Excel. Le module complémentaire Excel s’exécute dans un volet à droite de la fenêtre Excel.
4. Si vous exécutez le module complémentaire Excel pour la première fois, cliquez sur **Faire confiance à ce module complémentaire**.
5. Si vous êtes invité à vous connecter, cliquez sur **Connexion** et connectez-vous à l’aide des mêmes informations d’identification que pour Finance and Operations. Le module complémentaire Excel utilise un contexte de connexion antérieur issu d’Internet Explorer et vous connecte automatiquement si c’est possible. Par conséquent, vérifiez le nom d’utilisateur dans le coin supérieur droit du module complémentaire Excel.

Le module complémentaire Excel lit automatiquement les données de l’entité sélectionnée. Notez qu’il n’existe aucune donnée dans le classeur tant que le module complémentaire Excel n’en a pas lue.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Ouvrir les données d’entité dans Excel au démarrage à partir d’Excel
1. Dans Excel, sous l’onglet **Insertion**, dans le groupe **Compléments**, cliquez sur **Store** pour ouvrir le magasin Office.
2. Dans le magasin Office, recherchez le mot clé **Dynamics** et cliquez sur **Ajouter** en regard de **Microsoft Dynamics Office Add-in** (le complément Excel).
3. Si vous exécutez le module complémentaire Excel pour la première fois, cliquez sur **Faire confiance à ce module complémentaire** pour permettre l’exécution du complément Excel. Le module complémentaire Excel s’exécute dans un volet à droite de la fenêtre Excel.
4. Cliquez sur **Ajouter des informations sur le serveur** pour ouvrir le volet **Options**.
5. Dans votre navigateur, copiez l’URL de votre instance Finance and Operations cible, collez-la dans le champ **URL du serveur**, puis supprimez tout ce qui suit le nom de l’hôte. L’URL obtenue doit comporter juste le nom d’hôte.

    Par exemple, si l’URL est `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, supprimez tout excepté `https://xxx.dynamics.com`.

6. Cliquez sur **OK**, puis cliquez sur **Oui** pour confirmer la modification. Le complément Excel redémarre et charge les métadonnées.

    Le bouton **Conception** est désormais disponible. Si le complément Excel comporte un bouton **Charger les applets**, vous n’êtes probablement pas connecté sous le bon compte d’utilisateur. Pour plus d’informations, voir « Le bouton Charger les applets s’affiche » dans la section [Dépannage](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in#troubleshooting) de cette rubrique.

7. Sélectionnez **Design**. Le complément Excel récupère les métadonnées d’entité.
8. Sélectionnez **Ajouter une table**. La liste des entités apparaît. Les entités sont répertoriées dans le format « Nom - Étiquette ».
9. Sélectionnez une entité dans la liste, telle que **Client - Clients**, puis cliquez sur **Suivant**.
10. Pour ajouter un champ à partir de la liste **Champs disponibles** à la liste **Champs sélectionnés**, cliquez sur le champ, puis cliquez sur **Ajouter**. Sinon, double-cliquez sur le champ dans la liste **Champs disponibles**.
11. Après avoir ajouté les champs souhaités à la liste **Champs sélectionnés**, vérifiez que le curseur est à l’emplacement correct dans la feuille de calcul (par exemple, la cellule A1), puis cliquez sur **Terminé**. Ensuite, cliquez sur **Terminé** pour quitter le concepteur.
12. Cliquez sur **Actualiser** pour extraire un jeu de données.

## <a name="view-and-update-entity-data-in-excel"></a>Afficher et mettre à jour des données d’entité dans Excel
Après que le complément Excel a lu les données d’entité dans le classeur, vous pouvez mettre à jour les données à tout moment en cliquant sur **Actualiser** dans le complément Excel.

## <a name="edit-entity-data-in-excel"></a>Modifier des données d’entité dans Excel
Vous pouvez modifier les données d’entité selon vos besoins, puis les publier en cliquant sur **Publier** dans le complément Excel. Pour modifier un enregistrement, sélectionnez une cellule de la feuille de calcul, puis modifiez sa valeur. Pour ajouter un nouvel enregistrement, suivez l’une des étapes suivantes :

- Cliquez n’importe où dans la table des sources de données, puis sur **Nouveau** dans le complément Excel.
- Cliquez n’importe où dans la dernière ligne de la table des sources de données, puis appuyez sur la touche Tabulation jusqu’à ce que le curseur sorte de la dernière colonne de cette ligne et crée une nouvelle ligne.
- Cliquez n’importe où sur la ligne immédiatement en dessous de la table des sources de données, et entrez des données dans une cellule. Lorsque vous déplacez le focus hors de cette cellule, la table se développe pour inclure la nouvelle ligne.
- Pour les liaisons de champ d’enregistrements d’en-tête, cliquez sur l’un des champs, puis cliquez sur **Nouveau** dans le module complémentaire Excel.

Notez qu’un enregistrement peut être créé uniquement si toutes les clés et tous les champs obligatoires sont liés dans la feuille de calcul, ou si des valeurs par défaut sont exécutées à l’aide de la condition de filtre.

Pour supprimer un enregistrement, suivez l’une des étapes suivantes :

- Cliquez avec le bouton droit sur le numéro de ligne en regard de la ligne de la feuille de calcul à supprimer, puis cliquez sur **Supprimer**.
- Cliquez n’importe où sur le numéro de ligne en regard de la ligne de la feuille de calcul à supprimer, puis cliquez sur **Supprimer** &gt; **Lignes de table**.

Si des sources de données ont été ajoutées comme liées, l’en-tête est publié avant les lignes. S’il existe des dépendances entre d’autres sources de données, vous pouvez modifier l’ordre de publication par défaut. Pour modifier l’ordre de publication, dans le module complémentaire Excel, cliquez sur le bouton **Options** (le symbole de vitesse), puis, dans l’organisateur **Connecteur de données**, sélectionnez **Configurer un ordre de publication**.

## <a name="add-or-remove-columns"></a>Ajouter ou supprimer des colonnes
Vous pouvez utiliser le concepteur pour ajuster les colonnes qui sont automatiquement ajoutées à la feuille de calcul.

> [!NOTE]
> Si le bouton **Configuration** n’apparaît pas en dessous du bouton **Filtre** dans le module complémentaire Excel, vous devez activer le concepteur de données source. Sélectionnez le bouton **Options** (le symbole de vitesse), puis activez la case à cocher **Activer la configuration**.

1. Cliquez sur **Configuration** dans le module complémentaire Excel. Toutes les sources de données sont répertoriées.
2. À côté de la source de données, cliquez sur le bouton **Modifier** (le symbole du crayon).
3. Dans la liste des **Champs sélectionnés** modifiez la liste des champs selon vos besoins :

    - Pour ajouter un champ à partir de la liste **Champs disponibles** à la liste **Champs sélectionnés**, cliquez sur le champ, puis cliquez sur **Ajouter**. Sinon, double-cliquez sur le champ dans la liste **Champs disponibles**.
    - Pour supprimer un champ de la liste **Champs sélectionnés**, cliquez sur le champ, puis cliquez sur **Supprimer**. Sinon, double-cliquez sur le champ.
    - Pour modifier l’ordre des champs, dans la liste **Champs sélectionnés**, sélectionnez un champ, puis cliquez sur **Haut** ou **Bas**.

4. Pour appliquer les modifications à la source de données, cliquez sur **Mettre à jour**. Ensuite, cliquez sur **Terminé** pour quitter le concepteur.
5. Si vous avez ajouté un champ (colonne), cliquez sur **Actualiser** pour extraire un jeu de données mis à jour.

## <a name="copy-environment-data"></a>Copier les données de l’environnement

Les données qui sont lues dans le classeur à partir d’un environnement peuvent être copiées vers un autre environnement. Toutefois, vous ne pouvez pas uniquement modifier l’URL de connexion, car le cache de données dans le classeur continuera à traiter les données comme des données existantes. Au lieu de cela, vous devez utiliser la fonctionnalité Copier les données de l’environnement pour publier des données dans un nouvel environnement comme de nouvelles données.

1. Sélectionnez le bouton **Imprimer** (le symbole de vitesse), puis, dans l’organisateur **Connecteur de données**, sélectionnez **Copier les données de l’environnement**. 
2. Indiquez l’URL du serveur pour le nouvel environnement. 
3. Cliquez sur **OK**, puis cliquez sur **Oui** pour confirmer l’action. Le complément Excel est relancé et se connecte au nouvel environnement. Toutes les données existantes du classeur sont traitées comme des nouvelles données.

    Une fois que le complément Excel a redémarré, une zone de message indique que le classeur est en mode Copie de l’environnement.

4. Pour copier des données dans le nouvel environnement comme de nouvelles données, sélectionnez **Publier**. Pour annuler l’opération de copie dans l’environnement et examiner les données existantes dans le nouvel environnement, sélectionnez **Actualiser**.

## <a name="troubleshooting"></a>Dépannage
Il existe quelques problèmes pouvant être résolus en quelques pas.

- **Le bouton Charger les applets s’affiche** – Si le complément Excel comporte un bouton **Charger les applets** après la connexion, vous n’êtes probablement pas connecté sous le bon compte d’utilisateur. Pour résoudre ce problème, vérifiez que le nom d’utilisateur approprié s’affiche dans le coin supérieur droit du complément Excel. Si un nom d’utilisateur incorrect s’affiche, cliquez dessus, déconnectez-vous et reconnectez-vous.
- **Vous recevez un message « Interdit »** – Si vous recevez un message « Interdit » alors que le complément Excel charge les métadonnées, le compte qui est connecté dans le complément Excel ne dispose pas de l’autorisation d’utilisation du service, de l’instance ou de la base de données cible. Pour résoudre ce problème, vérifiez que le nom d’utilisateur approprié s’affiche dans le coin supérieur droit du complément Excel. Si un nom d’utilisateur incorrect s’affiche, cliquez dessus, déconnectez-vous et reconnectez-vous.
- **Une page web vide s’affiche au-dessus d’Excel** – Si une page web vide s’affiche lors du processus de connexion, le compte nécessite AD FS, mais la version d’Excel qui exécute le complément n’est pas assez récente pour charger la boîte de dialogue de connexion. Pour résoudre ce problème, mettez à jour la version d’Excel que vous utilisez. Pour mettre à jour la version d’Excel lorsque vous êtes dans une entreprise se trouvant dans un canal différé, utilisez l’[Outil de déploiement Office](https://technet.microsoft.com/library/jj219422.aspx) pour [passer du canal différé au canal actuel](https://technet.microsoft.com/library/mt455210.aspx).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]