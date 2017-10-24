---
title: "Paramétrer et gérer des images pour Retail Modern POS"
description: "Cet article décrit les étapes impliquées dans le paramétrage et la gestion des images pour les différentes entités qui apparaissent dans Retail Modern POS (MPOS)."
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 52851
ms.assetid: 5c21385e-64e0-4091-98fa-6a662eb33010
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2ec39137bcc68bd7d9b71f6798474e88fb89fd1e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-and-manage-images-for-retail-modern-pos"></a>Paramétrer et gérer des images pour Retail Modern POS

[!include[banner](includes/banner.md)]


Cet article décrit les étapes impliquées dans le paramétrage et la gestion des images pour les différentes entités qui apparaissent dans Retail Modern POS (MPOS).

<a name="setting-up-the-media-base-url-and-defining-media-templates-to-configure-the-format-for-image-urls"></a>Paramétrage de l'URL de base de média et définition des modèles de média pour configurer le format des URL d'image
-------------------------------------------------------------------------------------------------

Les images qui apparaissent dans Retail Modern POS (MPOS) doivent être hébergées en externe, hors de Microsoft Dynamics 365 for Retail. Généralement, elles sont hébergées dans un système de gestion de contenu, un réseau de diffusion de contenu (CDN), ou un serveur multimédia. MPOS ensuite extrait et affiche les images pour les entités appropriées, telles que des produits et des catalogues, en accédant à l'URL cible. Pour extraire les images hébergées en externe, MPOS nécessite le format URL approprié pour les images. Vous pouvez configurer le format d'URL requis pour les images en paramétrant la valeur de l'**URL de base de support** dans le profil de canal et en utilisant la fonctionnalité **Définir modèle de média** pour chaque entité. Vous pouvez également remplacer le format standard URL pour un sous-ensemble d'entités à l'aide de la fonction **Modifier dans Excel**. **Remarque importante :** dans la version actuelle de Dynamics 365 for Retail, vous ne pouvez plus paramétrer le format d'URL à l'aide de l'attribut XML **Image** pour MPOS dans le groupe d'attributs **Par défaut** pour les entités. Si vous êtes familiarisé avec Microsoft Dynamics AX 2012 R3 et que vous utilisez maintenant la version actuelle de Dynamics 365 for Retail, vérifiez que vous utilisez toujours la nouvelle fonctionnalité **Définir modèle de média** pour paramétrer des images. N'utilisez pas ou ne modifiez pas l'attribut **Image** dans le groupe d'attributs **par défaut** pour les entités, notamment les produits. Les modifications effectuées directement dans le groupe d'attributs **par défaut** pour les images ne seront pas répercutées. Cette option sera désactivée dans la prochaine version. Dans les procédures suivantes, des images sont paramétrés pour l'entité de catalogue à titre d'exemple. Ces procédures aideront à garantir que le chemin d'accès de destination de l'image correct est défini implicitement pour toutes les images du catalogue qui utilisent un chemin d'accès commun. Par exemple, si vous avez paramétré un serveur multimédia ou un CDN en externe, et que vous souhaitez voir les images apparaître dans MPOS pour un magasin donné, la fonctionnalité **Définir modèle de média** vous permet de définir le chemin d'accès dans lequel MPOS peut rechercher et récupérer les images. **Remarque :** pour cet exemple de données de démonstration, le serveur multimédia est déployé sur le serveur Retail. Toutefois, il peut être n'importe où à l'extérieur de Dynamics 365 for Retail.

### <a name="set-up-the-media-base-url-for-a-channel"></a>Paramétrer l'URL de base de support pour un canal

1.  Ouvrez le portail du siège Dynamics 365 for Retail.
2.  Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Profils du canal**. [![channel-profile1](./media/channel-profile1.png)](./media/channel-profile1.png)
3.  Dans le profil de canal que votre magasin utilise pour MPOS, mettez à jour le champ **URL de base de support** avec l'URL de base de votre serveur multimédia ou CDN. L'URL de base est la première partie de l'URL qui est partagée par tous les fichiers d'image de différentes entités.[![channel-profile2](./media/channel-profile2.png)](./media/channel-profile2.png)

### <a name="define-the-media-template-for-an-entity"></a>Définissez le modèle de média d'une entité

1.  Cliquez sur **Vente au détail** &gt; **Gestion des catalogues** &gt; **Images de catalogue**.
2.  Dans la page **Images de catalogue**, dans le Volet Actions, cliquez sur **Définir modèle de média**. Dans la boîte de dialogue **Définir modèle de média**, dans le champ **Entité**, **Catalogue** doit être sélectionné par défaut.
3.  Dans l'organisateur **Chemin d'accès de média**, entrez le chemin restant de l'emplacement d'image. Le chemin d'accès de média prend en charge **LanguageID** comme variable. Par exemple, pour les données de démonstration, vous pouvez créer un dossier **Catalogues** pour toutes les image de catalogue sous l'URL de base de support pour votre serveur multimédia (https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer). Vous pouvez ensuite avoir un dossier pour chaque langue (par ex., en-US ou fr-FR) et copier les images appropriées sous chaque dossier. Si vous n'avez pas différentes images pour les différentes langues, vous pouvez omettre la variable **LanguageID** de votre arborescence et pointer directement sur le dossier Catalogues qui contient les images du catalogue. **Remarque :** la version actuelle de Dynamics 365 for Retail prend en charge le jeton **{LanguageId}** pour les entités Catalogue, Produit et Catégorie. (Le jeton **{LanguageID}** n'est pas pris en charge pour les entités Client et Collaborateur, selon la norme existante effective depuis Microsoft Dynamics AX 6.x).
4.  Pour les images, le format du nom de fichier est codé de manière irréversible dans le nom du catalogue et ne peut pas être modifié. Renommez, par conséquent, les images afin qu'elles aient des noms de catalogue appropriés, pour aider à garantir que MPOS les gère correctement.
5.  Dans le champ **Extension de fichier**, sélectionnez l'extension de nom de fichier prévue, selon le type d'image que vous avez. Par exemple, pour les données de démonstration, les images de catalogue sont définies sur l'extension .jpg. (Les fichiers image sont également renommés afin qu'ils aient des noms de catalogue.)
6.  Cliquez sur **OK**.
7.  Pour contrôler que le modèle de média pour les images a été correctement enregistré, dans la page **Images de catalogue**, cliquez sur **Définir modèle de média** de nouveau. Pour valider le modèle sans fermer la boîte de dialogue **Définir modèle de média**, vous pouvez utiliser l'organisateur **Générer des URL d'image pour Excel**. Activez l'apparence de l'URL d'image, et vérifiez que l'URL est conforme au standard du modèle qui a été précédemment cité. La boîte de dialogue **Définir modèle de média** a maintenant défini le chemin d'accès à l'image implicitement pour toutes les images du catalogue qui utilisent ce chemin d'accès commun à l'URL. Ce chemin d'accès à l'URL s'applique à toutes les images du catalogue sauf si elles sont remplacées. La première partie du chemin d'image est extraite de l'URL de base de support que vous avez définie dans le profil de canal. La partie restante du chemin d'accès est extraite du chemin d'accès que vous avez défini dans le modèle de média. Les deux parties sont concaténées pour fournir l'URL complète de l'emplacement d'image. Par exemple, un catalogue dans les données de démonstration s'appelle Fabrikam Base Catalog. Par conséquent, le nom de l'image doit être Fabrikam Base Catalog.jpg pour qu'il utilise le nom du catalogue et l'extension du nom de fichier .jpg configurée dans le modèle. Dans ce cas, après concaténation, l'URL est https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg.
8.  Exécutez les tâches de synchronisation pour pousser le nouveau modèle dans la base de données de canal, de sorte que MPOS puisse utiliser le modèle pour accéder aux images.
9.  Pour mettre à jour le modèle de média pour les images du catalogue côté canal, veillez à l'exécution de la **Tâche de catalogue 1150** à partir de **IT de vente au détail** &gt; **Programme de distribution**.[![catalog1](./media/catalog1.png)](./media/catalog1.png)

## <a name="previewing-an-image-from-the-entity-level"></a>Afficher l'aperçu d'une image à partir du niveau d'entité
1.  Dans la page de l'article d'entité dans HQ, vous pouvez prévisualiser l'image qui utilise l'URL d'image dérivée du modèle de média. Pour cet exemple, accédez au catalogue approprié, puis, dans le Volet Actions, cliquez sur **Supports** &gt; **Images**. Utilisez la liste déroulante pour sélectionner différents magasins qui peuvent avoir divers profils de canal.
2.  Pour modifier ou supprimer le modèle de média implicite, vous devez revenir à la boîte de dialogue **Définir modèle de média** de la page **Images du catalogue**.
3.  Vous pouvez utiliser les boutons **Ajouter** et **Supprimer** pour modifier manuellement le chemin d'accès basé sur le modèle implicite et utilisé pour une image spécifique. Pour plus d'informations, voir la section « Remplacement du modèle de média pour les articles d'entité » ultérieurement dans cet article.
4.  Après avoir terminé de prévisualiser une image et d'apporter les modifications nécessaires, démarrez l'instance de MPOS pour le magasin approprié, et vérifiez si les images du catalogue sont affichées.[![catalog4](./media/catalog4.png)](./media/catalog4.png)

**Remarque :** vous pouvez utiliser la même procédure pour les cinq entités qui sont prises en charge : Collaborateur, Client, Catalogue, Catégorie et Produits. « Produits du catalogue » (produits définis au niveau du catalogue) et « Produits du canal » (produits définis au niveau du canal) utilisent le modèle de média défini pour l'entité Produits. Pour le modèle de média Produits, vous pouvez sélectionner le nombre d'images de produit à afficher par produit. Vous pouvez également définir l'image par défaut pour un produit donné. De cette manière, vous pouvez empêcher les images vides dans MPOS et aider à contrôler quelle image est utilisée comme image par défaut pour un article. Dans l'exemple suivant, chaque produit a cinq images, et la première image est définie comme image par défaut. Les variantes de produits sont traitées la même manière que les produits principaux. Le nom du fichier image doit être basé sur le numéro de produit. Certains caractères sont également échappés lorsque le nom de fichier est généré. Par conséquent, il est bon de vérifier le nom de fichier à l'aide de la section **Générer des URL d'image pour Excel**. [![prods](./media/prods.png)](./media/prods.png)  

## <a name="synchronization-jobs-to-send-a-media-template-to-the-channel-side"></a>Tâches de synchronisation pour envoyer un modèle de média du côté du canal
Pour les cinq entités prises en charge (Collaborateur, Client, Catalogue, Catégorie et Produits), chaque fois que vous mettez à jour la boîte de dialogue **Définir modèle de média**  pour paramétrer une image, assurez-vous que vous exécutez la tâche de catalogue (1150) à partir de **IT de vente au détail** &gt; **Programme de distribution**. Cette tâche permettra au modèle de média mis à jour d'être synchronisé sur le canal et utilisé par MPOS. Exécutez la Tâche de catalogue (1150) après avoir effectué les modifications suivantes :

-   Vous mettez à jour le modèle de média pour les images du catalogue à partir de **Images du catalogue** &gt; **Définir modèle de média**.
-   Vous mettez à jour le modèle de média pour les images des employés à partir de **Images des employés** &gt; **Définir modèle de média**.
-   Vous mettez à jour le modèle de média pour les images des clients à partir de **Images des clients** &gt; **Définir modèle de média**.
-   Vous mettez à jour le modèle de média pour les images de produits à partir de **Images des produits** &gt; **Définir modèle de média**.
-   Vous mettez à jour le modèle de média pour les images des catégories à partir de **Images des catégories** &gt; **Définir modèle de média**. Vous devez également publier le canal.

## <a name="overwriting-the-media-template-for-entity-items"></a>Remplacement du modèle de média pour les articles d'entité
Comme vous l'avez appris dans la section précédente, le modèle de média d'une entité donnée prend en charge un seul chemin d'accès commun. Ce chemin d'accès est basé sur l'URL de base de support configurée et sur le chemin d'accès au support défini. Toutefois, dans de nombreux cas, un détaillant souhaite pouvoir utiliser les images de différentes sources pour un sous-ensemble d'articles dans une entité. Par exemple, un magasin utilise le serveur multimédia auto-hébergé pour un ensemble d'images de catalogue mais utilise les URL CDN pour un autre ensemble. Pour remplacer les URL des images basées sur un modèle de média pour les images d'une entité au niveau de l'entité, vous pouvez utiliser la fonction Modifier dans Excel et la fonctionnalité de modification manuelle de la page **Aperçu**.

### <a name="overwrite-by-using-edit-in-excel"></a>Remplacer à l'aide de Modifier dans Excel

1.  Cliquez sur **Vente au détail** &gt; **Gestion des catalogues** &gt; **Images de catalogue**.
2.  Dans la page **Images de catalogue**, cliquez sur **Définir modèle de média**. Dans la boîte de dialogue **Définir modèle de média**, dans le champ **Entité**, **Catalogue** doit être sélectionné.
3.  Dans l'organisateur **Chemin d'accès de média**, notez l'emplacement de l'image.
4.  Dans l'organisateur **Générer des URL d'image pour Excel**, cliquez sur **Générer**. **Important :** dès que le modèle de média est modifié, vous devez cliquer sur **Générer** pour pouvoir utiliser la fonctionnalité Modifier dans Excel. [![excel1](./media/excel1.jpg)](./media/excel1.jpg) Vous voyez désormais s'afficher un aperçu des URL d'image qui ont été générées selon le dernier modèle de média enregistré. [![excel2](./media/excel2.png)](./media/excel2.png) **Remarque :** les URL générées pour Excel utilisent le chemin d'accès et les conventions du modèle de support défini. Ces conventions incluent des conventions pour les noms de fichier. Vous devez normalement avoir paramétré les images physiques en dehors de Dynamics 365 for Retail, et les images peuvent être récupérées à partir des URL qui sont dérivées du modèle de média défini précédemment. Vous pouvez remplacer ces URL dérivés à l'aide de la fonctionnalité Modifier dans Excel.
5.  Cliquez sur **Modifier dans Excel**.
6.  Une fois la feuille de calcul Microsoft Excel ouverte, cliquez sur **Activer la modification** lorsque vous y êtes invité.
7.  Lorsque vous y êtes invité, cliquez sur **Faire confiance à ce complément** dans le volet droit et attendez que le complément ait terminé l'installation. [![Faire confiance à ce complément](./media/excel4.jpg)](./media/excel4.jpg)
8.  Si vous êtes invité à vous connecter, entrez les informations d'identification que vous avez utilisées pour vous connecter dans HQ. [![Invite de connexion](./media/excel5.png)](./media/excel5.png)
9.  Après vous être connecté, vous devez pouvoir afficher la liste des URL d'image pour les différentes rubriques de catalogue.
10. Vous modifiez, ajoutez et supprimez des URL d'image pour divers articles d'entité.
11. Pour toutes les entités à l'exception des Produits, vous pouvez remplacer les URL d'image. Modifiez l'URL d'image existante, afin qu'il utilise la nouvelle URL de destination de l'image, et mettez à jour le nom de fichier avec le nouveau nom de fichier d'image. Le nom du fichier doit être unique pour garantir que l'enregistrement est unique. [![Remplacer les URL d'image dans Excel](./media/excel6.jpg)](./media/excel6.jpg) **Remarque :** lorsque vous remplacez des URL d'image pour les entités de Produits à l'aide de la fonctionnalité Modifier dans Excel ou de la page d'article d'entité, MPOS affiche toujours toutes les URL d'image du modèle du support accompagnées des URL d'image remplacées.
12. Après avoir terminé d'apporter les modifications, cliquez sur **Publier dans Excel** pour créer une nouvelle entrée d'association explicite.
13. Retourner à HQ, puis cliquez sur **OK**.
14. Exécutez les tâches appropriées de synchronisation pour l'entité, puis activez l'aperçu dans la page d'entité ou dans MPOS.

#### <a name="creating-new-records"></a>Création d'enregistrements

Vous pouvez créer des enregistrements dans Excel. Toutefois, veillez à fournir les informations appropriées. Par exemple, pour créer une entrée pour un catalogue, veillez à ce que l'ID du catalogue et le nom du catalogue soient corrects, et fournissez également un nom de fichier unique. Le nom de fichier unique est très important, car l'unicité des enregistrements dans Excel est validée lors de la validation. D'abord, copiez les détails du catalogue pour lequel vous souhaitez créer un enregistrement, puis copiez l'enregistrement. Vous devez seulement mettre à jour le nom du fichier et l'URL, car le reste des informations sera identique. Pour créer des enregistrements pour des articles d'entité de Produit, vous utilisez la même procédure de base. À partir de la feuille de calcul Excel, copiez un enregistrement existant pour le produit pour lequel vous créez un enregistrement, puis remplacez l'URL et le nom du fichier d'image. Vérifiez que le nom de fichier est unique.

#### <a name="deleting-an-existing-record"></a>Suppression d'un enregistrement existant.

Seuls les enregistrements d'URL d'image remplacés peuvent être supprimés. Une fois qu'une image est supprimée et que la synchronisation est terminée, l'image n'apparaît plus dans la page **Aperçu** ou dans MPOS. Les enregistrements d'URL d'image qui sont dérivés du modèle de média ne peuvent pas être supprimés, car ces enregistrements sont toujours dérivés du modèle de média à chaque fois.

### <a name="overwrite-from-the-entity-level-preview-page"></a>Remplacer à partir de la page d'aperçu au niveau de l'entité

Pour toutes les entités à l'exception des Produits, vous pouvez remplacer l'URL d'image pour un article d'entité donnée au niveau de l'article d'entité à partir de la page **Aperçu**. Pour les Produits, vous pouvez utiliser la page d'entité « Produits du catalogue ». Cet exemple décrit la manière de remplacer une image de catalogue.

1.  Cliquez sur **Catalogues** &gt; **Supports** &gt; **Images**, puis sélectionnez l'image de catalogue à mettre à jour.
2.  Cliquez sur **Ajouter**, puis entrez l'URL d'image pour remplacer l'URL du modèle de média.
3.  Si vous souhaitez que cette image s'affiche dans MPOS pour le catalogue, vous pouvez la définir comme image par défaut.
4.  Cliquez sur **OK**. L'URL d'image est mise à jour avec cette image de catalogue, puis un aperçu s'affiche. [![preview3](./media/preview3.png)](./media/preview3.png)
5.  Vous pouvez également afficher l'aperçu d'image pour toutes les URL d'image remplacées dans la page de galerie **Images de catalogue**.

**[![preview-4](./media/preview-4.png)](./media/preview-4.png)Remarque :** actuellement, la galerie n'affiche pas les aperçus d'image pour les URL d'image de modèle de média. Pour les entités Catalogue, Collaborateur, Client, et Catégorie, si l'utilisateur fournit explicitement une URL via cette page, il est recommandé d'indiquer quelle est l'image par défaut, car les clients du serveur Retail n'indiquent qu'une seule image par Catalogue, Client, Collaborateur et Catégorie. Si l'utilisateur ne spécifie pas une image par défaut, le système détermine l'image par défaut et l'envoie à l'appelant du service Retail (MPOS ou commerce électronique).

### <a name="overwrite-the-image-url-for-catalog-product-images-from-the-preview-page"></a>Remplacer l'URL d'image pour les images de produits du catalogue à partir de la page Aperçu

Pour remplacer les URL d'image pour les images de produits du catalogue, vous devez utiliser la page **Aperçu**. Vous ne pouvez pas utiliser la fonctionnalité Modifier dans Excel.

1.  Pour remplacer les images des produits au niveau d'un catalogue, sélectionnez un catalogue, puis sélectionnez le produit pour lequel l'image doit être remplacée.
2.  Cliquez sur **Attributs**.
3.  Dans la page suivante, sélectionnez **Image**, puis cliquez sur **Modifier**. La page **Aperçu** s'ouvre sous forme de boîte de dialogue curseur.
4.  Cliquez sur **Ajouter**, puis remplacez l'URL d'image avec un nouvel URL.
5.  Cliquez sur **OK**. Vous voyez désormais l'aperçu de la nouvelle image et pouvez la définir comme image par défaut.

**[![cat3](./media/cat3.png)](./media/cat3.png)Remarque :** après l'association d'une image de catégorie, vous devez publier le canal et exécuter la Tâche du canal pour garantir que les modifications sont publiées dans la base de données du canal.

## <a name="setting-up-images-to-appear-in-offline-mode-for-mpos"></a>Paramétrage des images à afficher dans le mode hors connexion pour MPOS
MPOS peut s'exécuter en mode en ligne (lorsque MPOS est connecté au serveur Retail) ou en mode hors connexion (lorsqu'il n'existe aucun serveur Retail ni connexions réseau, et si les transactions sont stockées dans une base de données hors connexion locale). Lorsque MPOS fonctionne en mode hors ligne, il ne peut pas afficher les images du serveur d'images externe à partir du serveur Retail, car la connexion avec le serveur Retail est perdue. Toutefois, vous pouvez toujours paramétrer des images afin qu'elles soient affichées lorsque MPOS fonctionne en mode hors ligne.

### <a name="set-up-product-images-to-appear-in-offline-mode-for-mpos"></a>Paramétrer des images de produits à afficher dans le mode hors connexion pour MPOS

Les images de produits qui doivent être utilisées en mode hors connexion peuvent être paramétrées en téléchargeant l'image physique requise dans l'image du produit de base.

1.  Cliquez sur **Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits**.
2.  Sélectionnez le produit pour lequel définir l'image hors connexion.
3.  Cliquez sur **Modifier**, puis cliquez sur la flèche située dans le coin droit pour afficher le volet droit.
4.  Dans l'organisateur **Image du produit**, cliquez sur **Modifier l'image**, puis téléchargez l'image physique à utiliser pour le produit sélectionné en mode hors ligne.
5.  Sauvegardez et fermez la page.
6.  Alors que MPOS est en mode en ligne, exécutez la tâche de catalogue dans HQ, assurez-vous que les données sont envoyées au moins une fois à la base de données hors ligne.
7.  Mettez MPOS en mode hors ligne. Vous devez voir l'image que vous avez téléchargée pour le produit spécifique dans HQ. [![offline1](./media/offline1.png)](./media/offline1.png)

 

### <a name="set-up-catalog-category-employee-and-customer-images-to-appear-in-offline-mode-for-mpos"></a>Paramétrer des images de catalogue, de catégorie, d'employé et de client à afficher en mode hors connexion pour MPOS

Les images de catalogue, de catégorie, d'employé, et de client qui doivent être utilisées en mode hors connexion peuvent être paramétrées en ajoutant le lien de destination de l'image nécessaire à la galerie et en paramétrant l'image comme image par défaut pour l'entité sélectionnée.

1.  Accédez au catalogues, puis dans le volet Actions, cliquez sur **Supports** &gt; **Images**.
2.  Suivez les étapes de la section « **Remplacer à partir de la page d'aperçu au niveau de l'entité** » pour ajouter l'URL d'image externe.
3.  Marquez cette image comme image par défaut pour le catalogue en activant la case à cocher en regard de l'image répertoriée dans la grille.
4.  Exécutez la tâche de catalogue. Cette image est désormais utilisée comme image hors connexion pour ce catalogue dans MPOS.
5.  Suivez un processus similaire pour d'autres entités, telles que Catégorie, Employé, et Client.

[![offline2](./media/offline2.png)](./media/offline2.png)    




