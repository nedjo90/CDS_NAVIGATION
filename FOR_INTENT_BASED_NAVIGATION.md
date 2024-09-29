Ressources:
https://www.linkedin.com/pulse/cross-app-navigation-navigate-from-one-fiori-app-another-tiwari-kinge/


⚠️ La navigation ne fonctionne qu'une fois l'application déployée, elle n'est pas prise en charge dans l'aperçu via Eclipse ou BAS.

### Configuration des annotations :

- **semanticObject** : Le nom sémantique attribué à l'application cible.
- **semanticObjectAction** : L'action que l'on souhaite effectuer sur l'objet sémantique (par exemple, _display_, _create_, _manage_).
- **value** : Le paramètre que l'on souhaite transmettre lors de l'appel de l'application.

Exemple:

```C
@UI:{

	lineItem: [{

		semanticObject: 'SalesOrder',

		semanticObjectAction: 'display',

		type: #WITH_INTENT_BASED_NAVIGATION,

		value: 'SalesOrder' 
		// Correspond au salesOrder ci-dessous 
		// a ne pas confondre avec le semanticObject

	}]
}

SalesOrder;
```


Pour trouver le **semanticObject**, suivez ces étapes :

1. Accédez à la [Fiori Apps Library](https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#/home).
2. Recherchez l'application souhaitée (par exemple, _VA03_).
3. Ouvrez l'onglet **Implementation Information** pour obtenir le nom sémantique.

<img src="./images/Pasted image 20240929180407.png">

Dans la section **Configuration**, vous trouverez trois colonnes importantes :

1. **Semantic Object** : Correspond à l'annotation `semanticObject`.
    - Exemple : `SalesOrder`
2. **Semantic Action** : Correspond à l'annotation `semanticObjectAction`.
    - Exemple : `display`
3. **Parameter-Value** : Correspond à l'annotation `value`.
    - Exemple : Il s'agit du type de valeur que vous pouvez passer en paramètre. Voici quelques exemples de valeurs :
        - `(sap-ach=SD-SLS)`
        - `(CommodityOrderRequestDocument=>VBAK-VBELN)`
        - `(ConfigurationObject=>VBAK-VBELN)`
        - `(sap-ach=FIN-FSCM-CMM-DOT)`
        - `(DynproOKCode=ENT2=>DYNP_OKCODE)`
        - `(DynproNoFirstScreen=1=>DYNP_NO1ST)`
        - `(SalesOrder=>VBAK-VBELN)`

<img src="./images/Pasted image 20240929180304.png">

=> exemple  [VA03](https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#/detail/Apps('VA03')/S28OP)








