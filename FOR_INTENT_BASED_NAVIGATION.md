Ressources:
https://www.linkedin.com/pulse/cross-app-navigation-navigate-from-one-fiori-app-another-tiwari-kinge/


⚠️ La navigation ne fonctionne qu'une fois l'application deployé, ne fonctionne ni dans le preview avec eclipse ni dans BAS


Configuration des annotations:

-> semanticObject: le nom semantic donné à l'app cherché
-> semanticObjectAction: L'opération que l'on soihaite faire l'objet semantique (display, create, manage, ...)
-> Value: le paramètre que l'on souhaite passer à l'appel de l'application

Exemple:

```C
@UI:{

lineItem: [{

semanticObject: 'SalesOrder',

semanticObjectAction: 'display',

type: #WITH_INTENT_BASED_NAVIGATION,

value: 'SalesOrder'

}]
}

SalesOrder;
```


Pour le semantic object, on va la chercher dans :
1. [Fiori apps library](https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#/home)   
2. Chercher l'app voulu example va03
3. IMPLEMENTATION INFORMATION (onglet)
4. Configuration => 3 colonnes :
	1. Semantic Object => annotation = `semanticObject` 
		1. exemple: SalesOrder
	2. Semantic Action => annotation = `semanticObjectAction` 
		1. exemple : display
	3. Parameter-Value => annotation = `value` 
		1. exemple correspond au type de valeur que nous pouvons passer en paramètre (voir exemple ci-dessus) : (sap-ach=SD-SLS)& (CommodityOrderRequestDocument=>VBAK-VBELN)& (ConfigurationObject=>VBAK-VBELN)& (sap-ach=FIN-FSCM-CMM-DOT)& (DynproOKCode=ENT2=>DYNP_OKCODE)& (DynproNoFirstScreen=1=>DYNP_NO1ST)& (SalesOrder=>VBAK-VBELN)
=> exemple  [VA03](https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#/detail/Apps('VA03')/S28OP)
![[Pasted image 20240929180407.png]]
![[Pasted image 20240929180304.png]]

