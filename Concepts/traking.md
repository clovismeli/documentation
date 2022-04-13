# Traking
#### [Generacion en Notif Sender](https://github.com/mercadolibre/fury_growth-notification-sender/blob/e3df2698e4506b3a5fa5dd12592217ef2844aae1/cmd/api/usecases/services/payload/builder/notification.go#L568)

En los PayloadBuilders de [[NotifSender]] y [[Figari]], se genera el campaign_id y el batch_id, eso se mete en el trak (dentro del event_data) de sent que se genera cuando envias una comm (y tambien se genera en todos los tracks consecuentes de open dismiss etc).

Hay unos dashboards que hizo el equipo de Insights que levanta la data de la tabla de traks y genera los resumentes de las comms que se enviaron a traves de Hermes. En ellos tenes por ejemplo cuantos envios tuvo una comm, cuantos opens, cuantas compras. etc.
Y como dividimos las audiencias con su respectivo grupo de control, podemos medir la performance **(lift)** de las mismas.
Por ejemplo si el objetivo de la comm es que compres, podemos ver cuantas compras tuvieron los que recibieron la notificacion y se les mostro en el decive vs su grupo de conrtol.

En Hermes (comm manager) tenemos forma de segmentar y experimentar dentro de cada segmento, eso se hace con los segmentos y experimentos de la comm. El campaign_id se genera con el nombre de la comm y el batch_id se genera con el nombre del segmento + el nombre del experimento. (ej, en Mantika tenemos los segmentos de Credits y No Credits, y cada segmento tiene sus grupos (experimentos): CG, Bucket, Fijo. Entonces hoy en Mantika se puede medir el performance del segmento no credits y cada uno de sus grupos (experimentos)).

### Cambios nuevos
Con los nuevos cambios, estamos borrando los segmentos, y generando suno solo **default** que no hace distincion por credit o no credit, solo se esta mostrando diferente wording si tiene o no credito. 

