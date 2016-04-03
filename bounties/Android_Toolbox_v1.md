![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")

# Android toolbox  V1 (The first bounty for DEVELOPERS AND GRAPHIC DESIGNERS!!!!)

## Introduction

Fermat is a complex application that rus on its own development framework, its found a layer above the operating system, on this first stage we are developing on android, therefore, we must create the bases in order to make easier and faster the creation of applications in our platform.

We must develop the components, views, utilities and optimizers in order to reach a superior abstraction level, stopping to think of views as code but as components already pre-designed, starting with the lowest level of the framework and going higher until reaching the components already pre-made for use.

## Scope

### Current developments in progress

Currently, the toolbox has basic things to develop in fermat, we have to expand it more with:

## General Purpose

* TextBox
* EditText
* Button
* CheckButton
* BottomSlider
* NavigationView
* Tabs
* Expandable header

### Lists

* Expandable Lists
* RecyclerView

## Dialogs

* Yes / No
* TutorialDialog
* Dialog Welcome Screen / Help Screen
* FermatDialog (Dialog with fermat basics for custom development)

## Adapters
* Recycler adapter
* Expandable adapter

### Graphics

* Dona
* Badge (circle with notification number)
* RoundedView
* Picture in Circle

## Workers
* BitmapWorker
* ExecutorWorker

## Transformation effect
* CircleTransformation

## Inflater
* ViewInflater V1

### Bounty scope

#### Toolbox version V1

The following components, views, widgets, optimizers, utilities and upgrades will be developed (we must organize them by levels, i will do it on my document and then i will place it here):

---
| Artifact  | Description  | Idea  | Type of view  |
|:----:|:----:|:----:|:----:|
|ChatView	| already pre-assembled fragment with chat list, bubbles, adapter, holders.|	Luis |	fragmento |
|notificationes	| notifications template and possibility of custom notifications through a  painter |	furszy |	view |
|CoinUnitsPicker |	selector of the different units of currency, for example: bitcoin (mili, micro, satoshis, etc) |	furszy |	dialog, popup, fragment |
|CurrencySelectorDialog |	selector of fiat/crypto currency  |	Luis |	dialog, popup, fragment |
|SettingsView |	view design for the settings of any fermat application, we must create the whole infraestructure in order to build this in a scalable way and easy to expand with different components |	furszy	| Component |
|FermatAdapter 2.0 |	upgrade the fermat adapter to make adding row types easier, for example footers, headers, etc. |	nelsonalfo |	Adapter|
|fermatViewHolder 2.0 |	Upgrade the view holder with everything new adapter has in order to store the views build|	furszy|	ViewHolder|
|SendForm |	desarrollar un formulario de envió básico para todas las plataformas|	furszy|	view|
|FermatLoadingView |	una view de loading con estilo de fermat |	furszy|	view|
|FermatSearchView |	SearchView en el toolbar con collapse y expand	|furszy/no se quien la pidió |	view |
|ImageSlider |	un slider con imágenes optimizado para android (Esto es por ejemplo se puede usar en un header con noticias o alguna información a presentar) |	furszy |	
|basic menu in drawer with header picture V2 |	el navigation view, todo estandarizado |	furszy |	improve|
|top toolbar expandible menu |	menú expanpandible desde el toolbar |	furszy |	view |
|animación entre pantallas |	La posibilidad de agregar un efecto al pasar de pantalla en pantalla en una FermatApp |	nelson |	animation|
|Grafico de barras para el header (como el de CBP) |	Hacer el gráfico de barras de cbp para todo fermat |	nelson |	Componente|
|Grafico lineal para el header (como el de CBP) |	Hacer el gráfico lineal de cbp para todo fermat |	nelson |	Componente|
|SimpleSpinnerView with material design |	Un spinner para crear facilmente con material design	| furszy |	Componente|
|FermatFlipAnimation |	Animación especifica para rotar una tarjeta para cualquier container |	furszy |	Animation|
|FermatFlipCard |	Un container el cual pueda rotarse y tenga de ambos lados información diferente para el usuario |	furszy |	Componente |
|fermatCryptoCurrencieExchange widget |	un widget para el inicio de android con el valor del bitcoin proporcionado por plugins de Fermat |	furszy	| widget |
|TransactionsFragment |	ventana de transacciones con valores básicos como lo son: el sender, destination, amount, date, description	| furszy |	 componente|
|contactsFragment |	ventana de contactos con valores básicos como lo son: el nombre, la imagen.	|furszy | componente|
|FermatProgressBar |	una barra de progreso que se pueda actualizar facilmente desde las notificaciones |	acostarodrigo | view |
|WalletSelectorDialog |	un selector de wallets dentro de fermat, con el cual se va a poder realizar alguna acción al clickearla |	furszy | view|
|Mnemonic dialog/screen |una pantalla/vista la cual sirva para exportar la clave mnemonic de la wallet |	acostarodrigo | view|
|Tabs v2 |Mejorar los tabs actuales para que soporten el agregado de customView (por ejemplo notificaciones)|  nelson | improvement|
|UnitConversor |Conversor de unidades para la api de android, dp-sp-px|  furszy | Utility|
|Multi selector Spinner | Un Spinner con la posibilidad de selección doble como el selector de un bingo|  acostarodrigo | View|
|AvtivityBackButtonNotification | Mejora del framework para que avise a los fragmentos a la hora de realizar un back button o entrar en reposo en celular|  furszy | FermatAndroidFramework|
|ShareCompatFunctionality | Funcionalidad para poder compartir fotos,textos,videos,archivos con otras aplicaciones desde Fermat|  furszy | FermatAndroidFramework|
|AbstractDesktopFragment | Un fragmento base y optimizado para la creación de desktop screens| furszy| android-api|
|ShapesLibrary |libreria con varios tipos de figuras desarrolladas en codigo| furszy| library|
|AbstractViewPager | ViewPager generico que facilita su utilización en android | furszy| android-api|
|Apps Stack | vista de tipo stack con el diseño que posee android | furszy| library|
|Android-core structure to support Apps stack | mejoras en el core de android para que pueda soportar el stack de aplicaciones desarrollado | furszy| android-core|
|RecentsActivity | actividad que corre en paralelo a Fermat con el stack de aplicaciones abiertas, conectado a traves del router previamente creado en esta lista | furszy| android-core|
|Broadcaster V2 | Mejora al broadcaster para que permita enviar objetos, los cuales pueden ser broadcasteados dentro o fuera de Fermat | furszy| Improve|
|FermatProgressBar multi color cancelable | una progress bar la cual puede ser cancelada con varios colores | Luis| view|
|CardGridLayout | Un fragmento armado para poder visualizar en tarjetas los rows indicados por el usuario (Ej: el de communities)|  furszy | fragment|
|RouterLauncherReceiver| Se trata de un receiver que actua como router para lanzar los diferentes tipos de pantalla que se encuentran en Fermat |  furszy | FermatAndroidFramework|
|Apps connection V1 | Se trata de armar las bases para que Fermat pueda ser proveedora de servicios a otras aplicaciones en su versión 1 (Para que esto se pueda implementar en necesario hacer cambios en el core de Fermat)  |  furszy | FermatAndroidFramework|


---

***Once approved, each element will have a better description in the documentation***
     

## Timeline

Based on current workload and resouces available, the delivery date of this bounty will be **March 15th**.

## Evaluation

To be considered success this bounty must pass the following tests:

* All of the components have to been created and finished.

* La evaluación que se realizará será en base a lo aportado, sean diseñadores gráficos o desarrolladores. Se realizará un calculo matematico para determinar cuanto a sido el aporte de la persona para completar el bounty en base a la cantidad de componentes realizados con exito.
* El dueño de la idea , como ya lo fuí explicando a cada uno que quiso aportar, tendrá la prioridad del desarrollo del componente ante el responsable de llevar a cabo este bounty , si el dueño de la idea se encuentra ocupado a la hora de su creación y hay otra persona libre, el organizador del bounty puede determinar la importancia del componente y si es necesario, entregarselo a la segunda persona para su desarrollo, ganando así los tokens del mismo.


## Distribution


---

### Graphic Design

| Github Username | # Elements | U$S |
|:----:|:----:|:----:|
|arnaldos|5|**$1219,51**
|m471c4|3|**$731,70**
|emmysm|1|**$243,90**
|Ivonne|1|**$243,90**

---

### CoinDiggers

| Github Username  | # Elements | U$S |
|:----:|:----:|:----:|
|Exilum|3|**$553,24**
|nattyco|1|**$184,41**
|Clelia|9|**$1659,73**
|furszy|28|**$5163,59**

---



