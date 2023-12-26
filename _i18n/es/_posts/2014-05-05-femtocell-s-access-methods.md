---
layout: post
title:  Los métodos de acceso a las femtoceldas
date:   2014-05-08 05:00:00
description: Las femtoceldas pueden operar básicamente de tres modos diferentes acceso abierto, acceso cerrado y una combinación de los anteriores denominado acceso híbrido, a continuación se explican cada uno de los modelos de acceso
tags: 4G femtoceldas LTE QoS
categories: Networks Innovation
thumbnail: assets/img/TICs/metodos-acceso-femtoceldas/1.png
---
**Las femtoceldas son estaciones base de baja potencia y bajo costo** que proveen servicios celulares a nivel residencial, ofrecen una cobertura de aproximadamente $$10 m$$ [1]. Se integra con el operador móvil mediante una **conexión de banda ancha**, típicamente ADSL. En General, la femtocelda hace que el tráfico del sistema celular proveniente del hogar, se desvíe por la conexión de banda ancha, liberando el consumo de recursos de la macrocelda.

El 3GPP ha introducido el concepto de Closed Subscriber Group (CSG), que en esencia identifica a un grupo de suscriptores que tienen **permiso de acceso a una o varias celdas**. Las femtoceldas pueden operar básicamente de tres modos diferentes: **acceso abierto, acceso cerrado y una combinación de los anteriores denominado acceso híbrido** [2] y [3], a continuación se explican cada uno de los modelos de acceso:

- **Acceso abierto**: En este caso, el UE puede tener acceso a la femtocelda sin ningún tipo de restricción, esto se aprecia en la Figura #1 donde el UE2 tiene acceso sin restricción a la femtocelda en el edificio.
- **Acceso cerrado**: El administrador de la femtocelda define los únicos usuarios (CSG) que pueden tener acceso a la red. Para este modo, se exceptúan las llamadas de emergencia.
- **Acceso híbrido**: En este tipo de acceso, una cantidad limitada de recursos es asignada para permitir acceso a usuarios que no forman parte del CSG.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/metodos-acceso-femtoceldas/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Ejemplo de diversos métodos de acceso a femto-celdas [2]: acceso abierto, acceso cerrado y acceso híbrido.
</div>

Figura #1 es un ejemplo de los diversos tipos de acceso a la femtoceldas definidos por el 3GPP. **El acceso cerrado brinda los servicios contratados a los usuarios que forman parte del CSG**, brindando cierto nivel de seguridad y privacidad en el acceso a la femtocelda,además, que todos los recursos de la femtocelda están a disposición del usuario garantizando la QoS (en cierta medida). Sin embargo, los que no forman parte de este grupo de suscriptores no pueden tener acceso a la red, excepto para llamadas de emergencia. Este tipo de acceso genera más interferencia ya que los móviles cercanos tratan de conectarse a una femtocelda, pero el método de acceso los bloquea, por lo que se genera una gran cantidad de señalización implícita en dicha área.

Por otro lado, **el acceso abierto presenta una buena ventaja para el proveedor de servicios ya que parte del tráfico se desvía por las femtoceldas, liberando en buena medida, la carga de la macrocelda**. Sin embargo, este tipo de implementación provee un incremento en el handover, debido a que un UE que se desplaza por una localidad donde hay diversas femtoceldas implementadas, realizará traspasos en cada femtocelda donde encuentre mejor calidad de la señal, incrementando así el tráfico de señalización. Desde esta perspectiva **el método híbrido puede presentar ciertas ventajas, pero los recursos compartidos por cada femtocelda deben ser administrados con mucho cuidado** con la finalidad de no degradar la calidad de servicio de los usuarios de la femtocelda.

## References

1. D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.
2. Assen, Golaup;Mona, Mustapha;Leo, Boonchin Patanapogpibul, Femtocell Access Control Strategy in UMTS and LTE, 2009.
3. G, de la Roche;A, Valcarce;D, Lopez-Perez;Jie, Zhang, Access control Mechanisms for Femtocells, 2010.
4. [http://www.femtoforum.org/](http://www.femtoforum.org)
5. [http://www.3gpp.org/](http://www.3gpp.org/)