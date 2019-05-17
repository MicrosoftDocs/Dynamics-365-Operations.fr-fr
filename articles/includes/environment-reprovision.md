Lors de la copie d'une base de données entre des environnements, vous devez exécuter l'outil de remise en service de l'environnement avant que la base de données copiée soit complètement fonctionnelle pour vous assurer que tous les composants de Retail sont à jour.

> [!IMPORTANT]
> Nous vous recommandons d'exécuter cette procédure, que vous utilisiez des composants Retail ou non, car la fonctionnalité Retail est incluse dans tous les environnements. 

Avant de continuer, vous devez vous assurer que les conditions préalables suivantes sont remplies :
1. Si vous mettez à niveau la version de juillet 2017 (également appelée 7.2) 7.2.11792.56024, appliquez les correctifs X++ d'application suivants dans l'environnement de destination avant de procéder à la mise à niveau des données dans cet environnement. Cela empêchera que différentes erreurs se produisent lors de la mise à niveau des données :

    - KB 4036156 - Mise à niveau de version mineure de Retail - « La souche de numéros de la variante n'est pas définie. » Ce package de correctif inclut également les articles KB 4035399 et KB 4035751. Notez que vous devez disposer au minimum de Platform Update 9 pour utiliser ce package. Si vous n'en êtes pas certain, installez les derniers fichiers binaires.
    
2. Si vous mettez à niveau depuis Microsoft Dynamics AX 2012, installez les correctifs X++ d'application suivants dans l'environnement de destination avant de procéder à la mise à niveau des données :
    - KB 4033183 - Échec de la mise à niveau de Dynamics AX 2012 R2 ou Dynamics AX 2012 R3 pré-CU8 avec Objet introuvable pour dbo.RETAILTILLLAYOUTZONE.
    - KB 4040692 - Échec de la mise à niveau de Dynamics AX 2012 R3 vers Microsoft Dynamics 365 for Operations 7.2 sur l'index en double RetailSalesLine sur SalesLineIdx.
    - KB 4035490 - Problème de performances avec le script de mise à niveau du champ MainAccount de GeneralJournalAccountEntry.


Procédez comme suit pour exécuter l'outil de remise en service de l'environnement.

1. Dans la bibliothèque d'actifs partagés, sélectionnez **Package logiciel déployable**.
2. Téléchargez de l'outil de remise en service de l'environnement.
3. Dans la bibliothèque d'actifs de votre projet, sélectionnez **Package logiciel déployable**.
4. Sélectionnez **Nouveau** pour créer un package.
5. Entrez un nom et une description du package. Vous pouvez utiliser **Outil de remise en service de l'environnement** comme nom du package.
6. Chargez le package que vous avez téléchargé précédemment.
7. Sur la page **Détails de l'environnement** de votre environnement cible, sélectionnez **Mettre à jour** > **Appliquer les mises à jour**.
8. Sélectionnez l'outil de remise en service de l'environnement téléchargé plus tôt, puis sélectionnez **Appliquer** pour appliquer le package.
9. Surveillez la progression du déploiement du package. 

Pour plus d'informations sur l'application d'un package déployable, voir [Appliquer un package déployable](../deployment/create-apply-deployable-package.md). Pour plus d'informations sur l'application manuellement d'un package déployable, voir [Installer un package déployable](../deployment/install-deployable-package.md).
