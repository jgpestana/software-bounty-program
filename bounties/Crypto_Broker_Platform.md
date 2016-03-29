![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")

# Crypto Broker Platform


## Introduction

In this platform the actors involved are the crypto brokers and his customers (crypto customers). A crypto broker is a person or small organization whose business logic is to buy and sell crypto or fiat money in his local market, obtaining his profits from the difference in the buying/selling price. We can also distinguish two common crypto brokers levels, those acting as crypto brokers wholesalers and those who deal with final customers. The key goal of this platform is to facilitate most of the routine tasks to run the business and even provide the necessary functionalities always avoid the loss of money in every transaction.

The Fermat book chapters related to this bounty can be found here:[Chapter 16 - Fermat Book](https://github.com/Fermat-ORG/fermat-book/blob/master/book-chapter-16.asciidoc), [Chapter 17 - Fermat Book](https://github.com/Fermat-ORG/fermat-book/blob/master/book-chapter-17.asciidoc)


## Scope

### CBP Platform

La plataforma contara con las siguientes caracteristicas, apoyandose , cada una de ellas tiene una serie de Crterios de Aceptacion asi como componentes involucrados:

#### Creacion de identidades para Crypto Brokers

Criterios de Aceptacion:
- Se debe poder crear una broker identity
- Se debe poder editar la informacion de una broker identity
- Se debe poder publicar y despublicar una broker identity en la red Fermat

Componentes Involucrados:
- Crypto Broker Identity Subapp
- Crypto Broker Identity Plugin

#### Creacion de identidades para Crypto Customer

Criterios de Aceptacion:
- Se debe poder crear una Customer identity
- Se debe poder editar la informacion de una customer identity

Componentes Involucrados:
- Crypto Customer Identity Subapp
- Crypto Customer Identity Plugin

#### Configuracion Previa (Wizard) de la Broker Reference Wallet

Criterios de Aceptacion:
- Asociar una identidad a la Wallet
- Asociar al menos dos wallets a la Broker Wallet para definir las monedas que estas manejan como mercancia
  - Estas wallets pueden ser: Cash Money Wallet, Bank Money Wallet o Bitcoin Wallet
  - En el caso de la Bank wallet se debe seleccionar la cuenta bancaria a utilizar
- Seleccionar las wallets a donde van a ir dirigidas las ganancias de los diferentes pares de mercancia que un broker puede negociar
- Seleccionar proveedores de tasas de cambio para los diferentes pares de mercancia que un broker puede negociar
- Configurar el spread y si va a realizar restock automatico al momento de recibir un pago

Componentes Involucrados:
- Crypto Broker Reference Wallet
- Crypto Broker Wallet Plugin
- Matching Engine Plugin

#### Configuracion Previa (Wizard) de la Customer Reference Wallet

Criterios de Aceptacion:
- Asociar una identidad a la Wallet
- Asociar una Bitcoin Wallet para que pueda pagar con Bitcoin
- Seleccionar proveedores de tasas de cambio para los diferentes pares de mercancia que un customer desee comprar
- Agregar y Eliminar una Locacion donde recibirá la mercancia que desee comprar
- Agregar y Eliminar una Cuenta Bancaria donde recibirá la mercancia que desee comprar

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Customer Broker Purchase Negotiation Plugin

#### Configurar la Broker Wallet

Criterios de Aceptacion:
- Agregar y Eliminar una locacion
- Agregar y Eliminar una cuenta bancaria
- Agregar Mercancia (Hacer Restock) a la Broker wallet
- Retirar Mercancia (Hacer Destock) en la Broker wallet
- Actualizar el Spread y el Restock automatico

Componentes Involucrados:
- Crypto Broker Reference Wallet
- Crypto Broker Wallet Plugin
- Customer Broker Sale Negotiation Plugin

#### Configurar la Customer Wallet

Criterios de Aceptacion:
- Agregar y Eliminar una locacion
- Agregar y Eliminar una cuenta bancaria
- Agregar y Eliminar un Proveedor de Tasas de Cambio

Componentes Involucrados:
- Crypto Broker Reference Wallet
- Crypto Broker Wallet Plugin
- Customer Broker Sale Negotiation Plugin

#### Conectar un Crypto Customer con un Crypto Broker

Criterios de Aceptacion:
- Visualizar Customers conectados en la red Fermat
- Visualizar Brokers disponibles (visibles) en la red Fermat
- Un Customer puede enviar una solicitud de conexion a un Broker
- Un Broker debe recibir una notifiacion de conexion por parte de un Customer
- Un Broker puede aceptar la solicitud de conexion de un Customer
- Un Customer debe recibir la notificacion de que el broker aceptó la Solicitud

Componentes Involucrados:
- Crypto Broker Community Subapp
- Crypto Customer Community Subapp
- Customer Actor Network Service
- Broker Actor Network Service

#### Obtener cotizaciones de un Broker

Se muestra en la Customer Wallet una lista con las diferentes mercancias que ofrecen los brokers con los que esta conectado un customer
- Por cada item de la lista se debe mostrar una sublista con las diferentes cotizaciones que ofrece el broker para la mercancia que esta vendiendo
- Esta cotizacion puede ser el precio del mercado o el precio de la ultima venta
- Estas cotizaciones se actualizan una vez al dia

Criterios de Aceptacion:
- Se debe visualizar la lista de brokers y sus mercancias con sus cotizaciones

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Broker Actor Plugin
- Customer Actor Plugin
- Crypto Broker Wallet
- Broker Actor Network Service
- Customer Actor Network Service

#### Permitir a un Crypto Customer iniciar una nueva Negociacion

Criterios de Aceptacion:
- Se muestra una nueva negociacion en el tab de Negociaciones Abiertas en la seccion Wating for Broker
- Se muestra en el dispositivo del broker una nueva negociacion en el tab de Negociaciones Abiertas en la seccion Waiting for You
- Se mostrara una notifiacion android en el dispositivo del otro actor indicando que se recibio una nueva negociacion

Como Probar:
- Al seleccionar un item de la lista de brokers y sus cotizaciones se mostrará la pantalla para iniciar una negociacion
- Se Podrá seleccionar y cambiar el valor de los siguientes items:
  - Mercancia para pagar
  - Tasa de cambio para pagar
  - Cantidad a comprar
  - Cantidad a pagar
- Al modificar la tasa de cambio se recalcula la cantidad a pagar
- Al modificar la cantidad a comprar se recalcula la cantidad a pagar y viceversa
- Enviar la negociacion al Broker
- La nueva negociacion a de aparecer en el tab de Negociaciones Abiertas de la Customer Wallet
- El Broker ha de recibir la nueva negociacion en el home de la Broker Wallet y recibir una notificacion android
- Se debe crea un nuevo registro en los plugins de Customer Broker Pruchase Negotiatiation y Customer Broker Sale Negotiatiation con la negociacion iniciada

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker New Negotiation Transaction Plugin
- Negotiation Transmision Network Service
- Customer Broker Purchase Negotiation Plugin
- Customer Broker Sale Negotiation Plugin

#### Actualizar una negociacion

Criterios de Aceptacion:
- Al ser editado un item de la lista, este cambiara a un color Verde
- Al pulsar el boton Send la negociacion se mostrara en el tab de Negociaciones Abiertas
  - En la Customer Reference Wallet se Mostrara con el estado Sending to Broker y Wating for Broker
  - En la Broker Reference Wallet se Mostrara con el estado Sending to Customer y Wating for Customer
- Se mostrara una notifiacion android en el dispositivo del otro actor indicando que se actualizo una negocaicion

Como Probar:
- El Crypto Broker puede editar los siguientes items:
  - Cantidad a vender
  - Tasa de cambio
  - Cantidad a recibir
  - Modo de pago (Puede ser Cash on Hand, Cash Delivery, Bank o Crypto)
  - Locacion donde recibir el pago si seleccionó Cash On Hand o Cash Delivery
  - Cuenta bancaria donde recibir el pago si seleccionó Bank
  - Fecha y Hora de pago
  - Fecha y hora de entrega
- El Crypto Customer puede editar los siguientes items:
  - Cantidad a Comprar
  - Tasa de cambio
  - Cantidad a Pagar
  - Modo de Entrega (Puede ser Cash on Hand, Cash Delivery, Bank o Crypto)
  - Locacion donde recibir la mercancia si seleccionó Cash On Hand o Cash Delivery
  - Cuenta Bancaria donde recibir la mercancia si seleccionó Bank
  - Fecha y Hora de pago
  - Fecha y hora de entrega
- El broker puede visualizar el precio sugerido por la plataforma y el precio del mercado
- El customer y el broker pueden agregar una nota en la negociacion. Esto es tecto libre
- Las cantidades a comprar/vender asi como recibir/pagar se recalculan automaticamente
- Si el broker o el customer modifica la negociacion, esta a de aparecer en tab de Negociaciones Abiertas de sus wallets, ser recibida por su contraparte en su tab de Negociaciones Abiertas y recibir una notifiacion android indicando que la negociacion se modificó
- Se debe registrar en los plugins de Customer Broker Pruchase Negotiatiation y Customer Broker Sale Negotiatiation el cambio del estado

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker Update Negotiation Transaction Plugin
- Negotiation Transmision Network Service
- Customer Broker Purchase Negotiation Plugin
- Customer Broker Sale Negotiation Plugin

#### Cancelar una negociacion

Criterios de Aceptacion:
- La negociacion no se muestra en el tab de Negociones Abiertas de la Crypto Customer Reference Wallet y la Broker Reference Wallet
- La negociacion se muestra ahora en la pantalla de Contract History de ambas wallets
- En el detalle de esa negociacion cancelada se puede ver el motido de la cancelacion

Como Probar:
- Se debe mostrar un dialogo que permita al Customer o al Broker indicar la razon de la cancelacion
- La negociacion debe desaparacer del tab de Negociaciones Abiertas en la wallet del actor que realizo la cancelacion
- Se debe registrar en los plugins Customer Broker Pruchase Negotiatiation y Customer Broker Sale Negotiatiation el cambio del estado
- La negociacion actualizada dese ser recibida por la contraparte y debe desaparecer del tab de Negociaciones Abiertas de su wallet y recibir una notificacion android indicando que se cancelo la negociacion
- La negociacion Cancelada debe aparecer en la pantalla de Contract History de ambas wallets

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker Update Negotiation Transaction Plugin
- Negotiation Transmision Network Service
- Customer Broker Purchase Negotiation Plugin
- Customer Broker Sale Negotiation Plugin

#### Cerrar una Negociacion y crear un Contrato de la misma

Criterios de aceptacion:
- La negociacion no se muestra en el tab de Negociones Abiertas de la Crypto Customer Reference Wallet y la Broker Reference Wallet
- El contrato se muestra en el tab de Contratos Abertos de la Crypto Customer Reference Wallet y la Broker Reference Wallet
- Se debe mostrar una notificacion android indicando que se a creado un nuevo contrato en el dispositivos de ambos actores

Como Probar:
- Cuando el broker o el customer acepte todos los cambios de una negociacion, esta es enviada a su contraparte 
- La negociacion se cierra, desapareciendo del tab de Negociaciones Abiertas y apareciendo un nuevo elemento en el tab de Contratos Abiertos, indicando que se creo un nuevo contrato ademas de recibir una notifiacion android
- La contraparte recibe la negociacion y la cierra quitandola del tab de Negociaciones Abiertas y apareciendo un nuevo elemento en el tab de Contratos Abiertos, indicando que se creo un nuevo contrato ademas de recibir una notifiacion android

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker Close Negotiation Transaction Plugin
- Open Contract Business Transaction Plugin
- Customer Broker Purchase Negotiation Plugin
- Customer Broker Sale Negotiation Plugin
- Customer Broker Purchase Contract Plugin
- Customer Broker Sale Contract Plugin
- Negotiation Transmision Network Service
- Transaction Transmision Network Service
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Procesar un contrato de Pago Offline y Mercancia Offline

La palabra *Offline* se refiere a que la moneda se maneja en una Cash Wallet o Bank Wallet

Criterios de Aceptacion:
- Se puede visualizar el detalle del contrato con los 4 items:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- Se puede acceder al detalle de la negociacion asociada al contrato
- Se muestra el contrato en el tab de Contratos Abiertos en ambas Reference Wallets
- Al actulizar el contrato se muestra una notificacion y se muestra el contrato en la seccion adecuada del tab
  - Si el estado es Pending Payment o Confirm Merchandise se muestra en la seccion de esperando por el customer
  - Si el estado es Confirm Payment o Pending Merchandise se muestra en la seccion de esperando por el broker
- Se muestra una notifiacion android en el dispositivo de la contraparte cuando el customer o el broker actualice el contrato
- Cuando el Broker confirma el pago:
  - Debe aparecer aumentada la cantidad de mercancia en la Broker Wallet 
  - Se debe mostrar un credito en la Cash wallet o la Bank wallet. Esto depende del modo de pago seleccionado en la negociacion
- Cuando el broker indique que envió la mercancia, debe aparecer disminuida la cantidad de mercancia en la Broker Wallet

Como Probar:
- El Crypto Cuistomer accede a la pantalla de Open Contract Details desde el tab de Contratos Abiertos de su Customer Reference Wallet
- En la pantalla de Open Contract Details el Crypto Customer indica que envió al Crypto Broker que realizó el pago de una mercancia Offline
- El Crypto Broker recibe la actulizacion del contrato indicando que se realizó el pago 
- En la pantalla de Open Contract Details el Crypto Broker envia al customer la confirmacion del pago
- Se realiza automaticamente un credito a la Broker Wallet y a la Cash Wallet o Bank Wallet dependiendo del modo de pago seleccionado en la negociacion
- El Crypto Customer recibe la actulizacion del contrato indicando que el Crypto Broker confirmó el pago Offline
- En la pantalla de Open Contract Details el Crypto Broker indica que envió al Crypto Customer la mercancia Offline
- Se realiza automaticamente un debito a la Broker Wallet sobre la mercancia enviada
- El Crypto Customer recibe la actulizacion del contrato indicando que el Crypto Broker realizó el envio de la mercancia Offline
- En la pantalla de Open Contract Details el Crypto Customer envia al Crypto Broker la confirmacion de recepcion de la mercancia

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plugin
- Broker Ack Offline Payment Business Transaction Plugin
- Broker Submit Offline Merchandise Business Transaction Plugin
- Customer Ack Offline Merchandise Business Transaction Plugin
- Customer Broker Sale Contract Plugin
- Customer Broker Purchase Contract Plugin
- Transaction Transmision Network Service
- Plataforma CSH y Plataforma BNK
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Procesar un contrato de Pago Online y Mercancia Offline

La palabra *Online* se refiere a que la moneda cuyo envio y recepcion se maneja de forma automatica desde Fermat, no hace falta intervencion del usuario para realizar el envio y confirmar la recepcion. Actualmente la moneda soportada es el Bitcoin por medio de una Bitcoin Wallet 

Criterios de Aceptacion:
- Se puede visualizar el detalle del contrato con los 4 items:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- Se puede acceder al detalle de la negociacion asociada al contrato
- Se muestra el contrato en el tab de Contratos Abiertos en ambas Reference Wallets
- Al actulizar el contrato se muestra una notificacion y se muestra el contrato en la seccion adecuada del tab
  - Si el estado es Pending Payment o Confirm Merchandise se muestra en la seccion de esperando por el customer
  - Si el estado es Confirm Payment o Pending Merchandise se muestra en la seccion de esperando por el broker
- Se muestra una notifiacion android en el dispositivo de la contraparte cuando el customer o el broker actualice el contrato
- Cuando el Broker confirma el pago:
  - Debe aparecer aumentada la cantidad de mercancia en la Broker Wallet 
  - Se debe mostrar un credito en su Bitcoin Wallet
- Cuando el broker indique que envió la mercancia, debe aparecer disminuida la cantidad de mercancia en la Broker Wallet

Como Probar:
- El Crypto Customer accede a la pantalla de Open Contract Details desde el tab de Contratos Abiertos de su Customer Reference Wallet
- Indica que desea enviar la mercancia Online al Crypto Broker
- Se realiza automaticamente un debito a la Bitcoin Wallet del Customer
- El Crypto Broker recibe la actualizacion del contrato indicando que se realizó el pago
- La plataforma CBP haciendo uso de la plataforma CCP monitorea la recepcion del pago y envia al Customer el contrato actualizado con la confirmacion del pago
- Se realiza automaticamente un credito a la Bitcoin Wallet y a la Broker Wallet
- En la pantalla de Open Contract Details el Crypto Broker indica que envió al Crypto Customer la mercancia Offline
- Se realiza automaticamente un debito a la Broker Wallet sobre la mercancia enviada
- El Crypto Customer recibe la actulizacion del contrato indicando que el Crypto Broker realizó el envio de la mercancia Offline
- En la pantalla de Open Contract Details el Crypto Customer envia al Crypto Broker la confirmacion de recepcion de la mercancia

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plugin
- Broker Ack Offline Payment Business Transaction Plugin
- Broker Submit Offline Merchandise Business Transaction Plugin
- Customer Ack Offline Merchandise Business Transaction Plugin
- Customer Broker Sale Contract Plugin
- Customer Broker Purchase Contract Plugin
- Transaction Transmision Network Service
- Plataforma CSH, Plataforma BNK y Plataforma CCP
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Procesar un contrato de Pago Offline y Mercancia Online

Criterios de Aceptacion:
- Se puede visualizar el detalle del contrato con los 4 items:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- Se puede acceder al detalle de la negociacion asociada al contrato
- Se muestra el contrato en el tab de Contratos Abiertos en ambas Reference Wallets
- Al actulizar el contrato se muestra una notificacion y se muestra el contrato en la seccion adecuada del tab
  - Si el estado es Pending Payment o Confirm Merchandise se muestra en la seccion de esperando por el customer
  - Si el estado es Confirm Payment o Pending Merchandise se muestra en la seccion de esperando por el broker
- Se muestra una notifiacion android en el dispositivo de la contraparte cuando el customer o el broker actualice el contrato
- Cuando el Broker confirma el pago:
  - Debe aparecer aumentada la cantidad de mercancia en la Broker Wallet 
  - Se debe mostrar un credito en su Bitcoin Wallet
- Cuando el broker indique que envió la mercancia, debe aparecer disminuida la cantidad de mercancia en la Broker Wallet

Como Probar:
- El Crypto Cuistomer accede a la pantalla de Open Contract Details desde el tab de Contratos Abiertos de su Customer Reference Wallet
- Indica que envió el pago de una mercancia Offline al Crypto Broker
- El Crypto Broker recibe la actulizacion del contrato indicando que se realizó el pago 
- En la pantalla de Open Contract Details el Crypto Broker envia al Customer la confirmacion del pago
- Se realiza automaticamente un credito a la Broker Wallet y a la Cash Wallet o Bank Wallet dependiendo del modo de pago seleccionado en la negociacion
- El Crypto Customer recibe la actulizacion del contrato indicando que el Crypto Broker confirmó el pago Offline
- En la pantalla de Open Contract Details el Crypto Broker indica que desea enviar la mercancia Online al Crypto Customer
- El Crypto Customer recibe la actulizacion del contrato indicando que se realizó envió la mercancia 
- Se realiza automaticamente un debito a la Broker Wallet y la Bitcoin Wallet del Broker
- La plataforma CBP haciendo uso de la plataforma CCP monitorea la recepcion de la mercancia y envia al Broker el contrato actualizado con la confirmacion de recepcion de la mercancia en el dispositivo del Customer
- Se realiza automaticamente un credito a la Bitcoin Wallet del Customer

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plugin
- Broker Ack Offline Payment Business Transaction Plugin
- Broker Submit Offline Merchandise Business Transaction Plugin
- Customer Ack Offline Merchandise Business Transaction Plugin
- Customer Broker Sale Contract Plugin
- Customer Broker Purchase Contract Plugin
- Transaction Transmision Network Service
- Plataforma CSH, Plataforma BNK y Plataforma CCP
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Cerrar Contrato

Criterios de Aceptacion:
- El contrato no se muestra en el tab de Contratos Abiertos de la Customer Reference Wallet y la Broker Reference Wallet
- Se recibe una notificacion android de que el Contrato se a Completado
- El contrato se muestra en la pantalla de Contract History de ambas Reference Wallets con estado completado
- El detalle del contrato muestra informacion de la misma

Como probar:
- Cuando se confirme el envio de la mercancia por parte del customer automaticamente el sistema cierra el contrato colocandolo como completado
- Este ya no se muestra en el en el tab de Contratos Abiertos y recibe una notificacion android de que el Contrato se a Completado
- El contrato aparece completado podra ser visible en la pantalla de COntract History de cada Reference Wallet
- Al seleccionar el contrato en esa pantalla se accedera al detalle donde se mostrara la siguiente informacion
  - Cantidad Comprada o Vendida
  - Precio
  - Forma de Pago
  - Fecha de completacion del contrato
  - Acceso al detalle de la negociacion asociada

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Close Contract Business Transaction Plugin
- Customer Broker Sale Contract Plugin
- Customer Broker Purchase Contract Plugin
- Transaction Transmision Network Service
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Extraccion de ganancias

Criterios de Aceptacion
- Visualizar las ganancias en la pantalla de Earnings en la Broker Reference Wallet: Diario, Semanal, Mensual y Anual
- Visualizar el credito de las ganancias obtenidas durante el proceso de matching en las wallets de Cash, Bank o Bitcoin, dependiendo de los pares de mercancia seleccionados y las wallets asociadas a esos pares

Componentes Involucrados:
- Crypto Broker Reference Wallet
- Matching Engine Middleware Plugin
- Crypto Broker Wallet Plugin
- Plataforma CSH, BNK y CCP


### Related Projects To Develop

Para el desarrollo de la funcionalidad con la que contará la plataforma CBP es necesaria la creacion de varios Side Projects los cuales se especifican a continuacion indicando el alcance de los mismos:

#### CSH Platform

Esta plataforma permite la administracion de dinero FIAT (Dolar, Bolivar, Peso Argentino, Euro, etc) que se tiene en efectivo, y permite a un Crypto Broker vender mercancia recibiendo el pago dinero en efectivo

Alcance:
- Configurar la wallet asociando una moneda a ella
- Hacer creditos
- Hacer debitos
- Editar transacciones de credito o debito que esten en proceso
- Cancelar transacciones de credito o debito mientras esten en proceso 
- Llevar el balance book y available del dinero en efectivo
- Mostrar el historial de transacciones hechas a la wallet
- Mostrar detalles de cada transaccion

Criterios de Aceptacion:
- En el wizard inicial, se puede configurar una moneda para llevar el balance del dinero en cash
- Se muestran los balances Available y Book de la wallet (mostrando el book solo cuando los balances sean distintos)
- Realizar una transaccion de Credito
- Editar la informacion de la transaccion de Credito mientras este en proceso
- Cancelar la transaccion de Credito mientras este en proceso
- Realizar una transaccion de Debito
- Editar la informacion de la transaccion de Debito mientras este en proceso
- Cancelar la transaccion de Debito mientras este en proceso
- Ver la informacion de cualquier transaccion realizada

#### BNK Platform

Esta plataforma permite la administracion de dinero FIAT (Dolar, Bolivar, Peso Argentino, Euro, etc) que se tiene almacenada en un banco, y permite a un Crypto Broker vender mercancia recibiendo el pago dinero a travez de deposito o transferencia bancaria.

Alcance:
- Configurar la wallet indicando nombre de un banco
- Agregar cuentas bancarias en diferentes monedas
- Hacer creditos a las cuentas bancarias
- Hacer debitos a las cuentas bancarias
- Editar transacciones de credito o debito que esten en proceso
- Cancelar transacciones de credito o debito mientras esten en proceso 
- Llevar el balance book y available del dinero en cada cuenta bancaria
- Mostrar el historial de transacciones hechas sobre cada cuenta
- Mostrar detalles de cada transaccion
- No va a estar conectada a la API de ningun banco, eso solo para uso administrativo

Criterios de Aceptacion:
- En el wizard inicial, se puede ingresar un texto que represente el nombre de un banco
- Se puede agregar una o mas cuentas bancarias y cada una puede tener asociada una moneda diferente
- Se muestran los balances Availabe y Book de cada cuenta (mostrando el book solo cuando los balances sean distintos)
- Mostrar historial de transacciones.
- Realizar una transaccion de Credito en cualquiera de las cuentas
- Editar la informacion de la transaccion de Credito mientras este en proceso
- Cancelar la transaccion de Credito mientras este en proceso
- Realizar una transaccion de Debito en cualquiera de las cuentas
- Editar la informacion de la transaccion de Debito mientras este en proceso
- Cancelar la transaccion de Debito mientras este en proceso
- Ver la informacion de cualquier transaccion realizada

#### CER Super Layer

Esta super capa se creo con la finalidad de poder ofrecer a las diferentes plataformas que lo requieran proveedores de tasas de cambio. En el caso de la plataforma CBP se usa para que el Crypto Broker y el Crypto Customer tengan un precio de referencia con el cual comprar y vender

Alcance:
- Contiene providers de exchangeRates para monedas fiat y crypto
- Retorna una lista de todos los Providers que contiene el CER
- Filtra providers segun su public key
- Filtra Providers segun un par de monedas dado
- De cada provider se obtiene 
  - Una lista de pares de monedas soportadas
  - El exchangeRate actual
  - El exchangeRate para una fecha dada (de ser soportado por el provider)
  - ExchangeRates diarios para un rango de fechas (de ser soportado por el provider)
  - Una lista de todos los exchangeRates alguna vez solicitados al plugin
- Providers inicialmente soportados:
  - Bitcoin Venezuela (Monedas soportadas: Bitcoin, Litecoin, Dolar Americano, Euro, Bolivar, Peso Argentino)
  - Bitfinex (Monedas soportadas: Bitcoin, Litecoin, Ethereum, Dolar Americano)
  - Bter (Monedas soportadas: Bitcoin, Litecoin, Ethereum, Yuan, Dolar Americano)
  - Dolar Today (Dolar Americano, Bolivares)
  - El Cronista (Dolar Americano, Peso Argentino)
  - La Nacion (Dolar Americano, Peso Argentino)
  - European Central Bank (Dolar Australiano, Real Brasileño, Libra Esterlina, Dolar Canadiense, Yuan, Euro, Yen, Peso Mexicano, Dolar Neozelandes, Franco Suizo, Dolar Americano)
  - Yahoo (Todos las monedas FIAT)

Criterios de Aceptacion:
 - Implementacion de la funcionalidad e integracion de la capa CER con la plataforma CBP


### Current Development in Progress

Para el inicio de este proyecto se cuenta con la implementacion de la plataforma CCP que permite el envio y recepcion de bitcoins a traves de red Fermat. Utilizaremos las funcionaldades y componentes desarrollados para manejar negociaciones donde se desee comprar o vender Bitcoins


### Evaluation

Para considerar este bounty exitoso se debe cumplir los Criterios de Aceptacion de los flujos expuestos anteriormente.

### Distribution 

Cada caracteristica expuesta mas arriba tiene un porcentaje que representa parte del bounty. A continuacion se indican dichos porcentajes:

|Features                                                      | % | 
|--------------------------------------------------------------|:----:|
|Creacion de identidades para Crypto Brokers                   | 2% |
|Creacion de identidades para Crypto Customer                  | 2% |
|Configuracion Previa (Wizard) de la Broker Reference Wallet   | 3% |
|Configuracion Previa (Wizard) de la Customer Reference Wallet | 3% |
|Configurar la Broker Wallet                                   | 3% |
|Configurar la Customer Wallet                                 | 3% |
|Conectar un Crypto Customer con un Crypto Broker              | 6% |
|Obtener cotizaciones de un Broker                             | 6% |
|Permitir a un Crypto Customer iniciar una nueva Negociacion   | 8% |
|Actualizar una negociacion                                    | 8% |
|Cancelar una negociacion                                      | 4% |
|Cerrar una Negociacion y crear un Contrato                    | 7% |
|Procesar un contrato de Pago Offline y Mercancia Offline      | 7% |
|Procesar un contrato de Pago Online y Mercancia Offline       | 7% |
|Procesar un contrato de Pago Offline y Mercancia Online       | 7% |
|Cerrar Contrato                                               | 4% |
|Extraccion de ganancias                                       | 6% |
|CSH Platform                                                  | 5% |
|BNK Platform                                                  | 5% |
|CER Super Layer                                               | 4% |
|**Total**                                                    | **100%** |
