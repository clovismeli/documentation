# Mantika Migration

## Cambios para Andy
- [[Tools]]. Unicos por campaña
- Deeplink Landing. Deeplink "Landing de Items" que no te pida nada. 
- **Multiples segmentos**. Si matamos los segmentos perdemos el **"[[traking]]"**. O tenes un dynamic content que nos diga el [[batch_id]]. "No existe la experimentacion en campaigns". Hay que ver si creas una campaign multi segment en el front que no se rompa y no se pisen los campos (ej [[groups_api_key]]) ni segmentos ni experiments. Ver si se puede "hacer lo del batch_id con dynamic content". Ver si se puede meterle un dynamic content en el name del segmentation_config y hacer pasar ese campo por [[template engine]].
- Hay que mantener [[groups_filters]] y [[groups_api_key]], que estan a nivel del segment, por fuera de los experimentos.


### Preguntas
- Que son los trakings que se generan a partir de los segmentos?
- Que son y para que se usan los campos:
	* groups_api_key
	* groups_filters
