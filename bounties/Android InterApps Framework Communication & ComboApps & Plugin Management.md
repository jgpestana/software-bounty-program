![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")

# Android InterApps Coomunication & Addons Development & ComboApps integration

## Introduction

Android powers hundreds of millions of mobile devices in more than 190 countries around the world. It's the largest installed base of any mobile platform and growing fast—every day another million users power up their Android devices for the first time and start looking for apps, games, and other digital content.
En noviembre de 2015 se pudieron observar 1.8 million apps, con más del 80% del mercado mobile en sus manos, Android es la plataforma perfecta para poder desarrollar el ecosistema Fermat y permitir que el universo de aplicaciones Android puedan interactuar y consumir los servicios que nuestro ecosistema brinda.

## Scope

### Bounty scope

#### Android InterApps Framework Communication & ComboApps & Plugin Management.

#### Android InterApps Framework Communication:

Es un framework de desarrollo e intercomunicación de aplicaciones por fuera de las fronteras del ecosistema de Fermat, Se debe crear la posibilidad de establecer conexion con incontables clientes a la vez, los cuales se registrarán a Fermat por medio de un token, se creará un canal para la comunicación entre Fermat y dichos clientes externos que corren en procesos distintos, permitiendo consumir los servicios de los plugins modules de Fermat.
Las implementaciones a realizar serán las siguientes:

* ##### Refactor y mejora del framework de desarrollo de los Module y su comunicación con los componentes GUI, AbstractModule, Interfaces, Estructura de clases, todos estos elementos deben estar preparados para ser serializados y compartidos entre aplicaciones externas del ecosistema de Fermat.
        * CryptoWalletModule has to be improve, En este plugin hay que realizar todos estos cambios
        * CryptoWallet has to be improve, Esta es la interfaz la cual sirve de Proxy entre el core y los componentes GUI.
        * IntraWalletUserIdentityManager has to be improve, El module de la wallet comsume servicios de dicho plugin por lo cual este tambien debe ser mejorado con todas las clases en su haber.
        * IntraWalletUserManager (actor plugin) has to be improve, El module de la wallet comsume servicios de dicho plugin por lo cual este tambien debe ser mejorado con todas las clases en su haber.
        * IntraWalletUserModule has to be improve, Mejoras en el module del actor para poder serializar los objetos finales que pueden transmitirse a traves de la interApps communication.
        * IntraWalletUserIdentityModule has to be improve, Mejoras en el module del actor para poder serializar los objetos finales que pueden transmitirse a traves de la interApps communication. 
        
* Fermat Structure
        * WalletManager & SubAppManager have to be removed, AppManager creation and implementation.
        * Wallet runtime & SubApp runtime have to be removed, AppRuntime creation and implementation.
      

* Mejoras a nivel del Android core:
        * Creación de paquete y clases para la conexión entre apps externas con Fermat.
        * Creación de Servicio de intercomunicación
        * Implementación del Binder Framework
        * Conexión con Fermat segura, autentificación, token.

* Creación del entorno y división del primer proceso de Fermat en android OS

* ##### Framework de comunicación de aplicaciónes externas.
        * Paquetes y clases necesarias para conectarse con Fermat las cuales se encontrarán en un repositorio de maven y cualquier aplicación externa las podrá descargar.
        * Clase base de comunicación Cliente.
        * Api en Maven.

* Apis de plataformas en Maven
        * Se subiran todas las apis de plataforma a Maven para su fácil distribución entra aplicaciones externas.

*  Correr la propia bitcoin wallet por fuera del ecosistema Fermat como si fuera una aplicación externa.
        * Siendo la primera aplicación de ejemplo.
        
        
#### ComboApps implementation:
    
    * Crear una layer para las ComboApps.
    * Actualizar el Wallet
    * Mejorar el Android core para soportar las aplicaciones con multiples modules.
    * Crear la Actividad que permita dicho concepto.
    * Mejorar el AppConnectionManager para soportar varios modules.
    * Crear clase base de fragmentos multi modules
    * Crear la primera ComboApp que consuma el module de la identity y de la community

#### Plugin Managment improvements:
    
 * Creación de addons que brinden:
 
        * NetworkState
        * Tipo de red
        * Estado de la bateria
        * Locación
        * Estado del dispositivo (sleep,encendido)
        * Estado de la aplicación (background, foreground)
        
* Command Processor Pattern for system services:
        Se debe crear un framework de registro de servicios del sistema el cual los plugins puedan registrarse y escuchar eventos propios del sistema en el cual estan siendo ejecutados, como el estado de la bateria, estado de la conexión, tipo de red, entre otros.       
        * Este diseño debe implementarse en el core de Fermat que sirve de Broker para los plugins.

#### The following diagram describes the Android OS view of  InterApps Communications:

  ![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/Infographies/software%20arquitecture/software_arquitecture.png
 "Fermat Logo")

  
  ## Timeline

Based on current workload and resouces available, the delivery date of this bounty will be **April 30th**.

## Evaluation

To be considered success this bounty must pass the following tests:
  * Aplicación de muestra corriendo la bitcoin wallet por fuera de Fermat conectandose con la propia plataforma, autentificandose y pasando los tokens de seguridad.
  * ComboApp Corriendo dentro de Fermat consumiendo los modules de la identity y community
  * Plugin mejorado con los nuevos servicios que brinda el sistema para detectar estado.
