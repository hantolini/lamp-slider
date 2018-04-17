# Javascript: Control de intensidad de una fuente luminosa
Control tipo "circular slider" para una fuente de luz dimerizable. Con boton "ON / OFF" que permite apagar y encender de forma instantanea.

El objetivo del programa es presentar un control deslizable curvo en el navegador del dispositivo con el que se desea controlar la fuente de luz.

El control deslizable maneja la intensidad de la fuente, entre el 0% y el 100%. Además se agrega un boton al costado, para controlar el encendido y apagado instantaneo.

Los archivos necesarios para ejectuar el script (el código en sí mismo, la página HTML que lo ejecuta, y la librería de jQuery) se almacenan en el filesystem del controlador, y se sirven al dispositivo con el que se desea controlar la fuente de luz.

La lógica del control es la siguiente:

* Cuando el cliente se conecta al dispositivo con un browser (mobile o PC) para controlarlo, se le manda una página HTML que contiene el control deslizable y el boton.
* Cuando la página termina de cargar, se lee via AJAX el estado actual de la fuente de luz (apagada / encendida / valor de intensidad) y se actualiza el estado de los controles.

* La página en el dispositivo del cliente responde a dos eventos:
    * un cambio en la psición de la barra del control deslizable
    * un cambio en el estado del boton

* Si el deslizable cambió su posición, el nuevo valor se envía al microcontrolador para que lo almacene y cambie el estado de la fuente.
* Si el botón es pulsado, se envía al controlador un cambio de estado de la fuente, para que lo almacene y ejecute el cambio.

