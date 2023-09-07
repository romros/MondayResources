# Workspace de Fundació .cat en Monday.com

## Descripció General

Aquest workspace serveix com a centre d'emmagatzematge per a dades i informació que són globals i referencials per a tots els projectes de la Fundació .cat.

## Taulells Globals

### Informació Compartida

#### Proveidors

Dins de la carpeta "Informació Compartida", trobareu un taulell dedicat als proveidors. Aquest taulell està organitzat en diferents grups segons la funció del proveidor, com ara Desenvolupadors, Disseny Gràfic, etc. En aquest taulell, es poden trobar els següents camps:

- Proveidor
- Contacte del Proveidor
- Correu Electrònic
- Àrea (Desenvolupament, Disseny Gràfic, etc.)
- Valoració (1 a 5 estrelles)
- Telèfon
- Notes

#### Categories Conceptes Pressupostaris

Aquest taulell conté les diferents categories que s'utilitzen per segmentar dades en A3ERP per fer un seguiment efectiu dels pressupostos.

# Plantilla Genèrica de workspace de Fundació .cat

Aquesta plantilla està dissenyada per a espais de treball que gestionen un o més projectes o subprojectes. Alguns exemples de casos d'ús poden ser:

- Gestió de múltiples projectes dins d'una "galàxia".
- Gestió de diferents àrees de negoci com a projectes independents.
- Gestió de l'àrea de comunicació amb diverses campanyes.
- Gestió de l'àrea de Sistemes amb múltiples subprojectes interns.

Si només estàs gestionant un projecte, aquesta plantilla també pot ser utilitzada eficaçment.

## Estructura de Carpetes

La plantilla està dividida en diferents carpetes en funció de l'àrea de treball. Per exemple:

## Carpeta Pressupostos

Aquesta carpeta conté taulells per a gestionar:

- Pressupostos de compra del projecte
- Factures de compra del projecte

### Taulell: Pressupostos de compra

En aquest taulell es gestiona els diferents pressupostos de compra del projecte. La idea és que quan es demana un pressupost, es crea un element en aquest taulell. I des d'aquest mateix taulell, es pot fer un seguiment de l'estat del pressupost, així com de la seva aprovació o rebutjament. Els camps que component aquesta taulell són:

Vull explicar el taulell de pressupostos del projecte. en aquest taulell es decriu el pressupost complert d'un projecte.
M'agradaria que quedes molt clar que es un taulell on hi ha camps calculats i camps que ha de actualitzar el responsable del projecte.
També m'agradaria que quedes molt clar que està vinculat al taulell de factures del rpojecte. A més a me´s el taulell gestiona tant el pressupost d'ingresoss com el de despeses.

Estructura del Taulell

Grups
El taulell està organitzat en grups que representen els diferents projectes. Cada grup conté un conjunt d'elements que són els pressupostos associats a aquest projecte en particular.

Elements
Cada element del taulell representa un item MENSUAL del pressupost. Es important veure que si tenim una factura mensual, en el pressupost aquest item apareixerà 12 vegades, una per cada mes. Això ens permetrà fer un seguiment de la desviació del pressupost en funció del temps. En aquest punt hi havien dues alternatives. o bé un item era un concepte i es feien subelements per mes,
o bé es simplificada l'estructura i cada element pertany a un mes. La segona opció és la que s'ha escollit perquè és més senzilla i més fàcil de mantenir. A més a més, aquesta estructura ens permetrà fer un seguiment de la desviació del pressupost en funció del temps en els diferents dashboards de seguiment.

Si es necessita agrupar per conceptes, per tal de veure els subtotals, per exemple el pressupost en lloguer d'espais informatics de tot el projecte, només caldrà usar el "Filtre" del tauell per filtrar per concepte i podrrem veure facilment els subtotals per aquests grup.

Sub-elements
Actualment, els elements en aquest taulell no contenen sub-elements.

Camps del taulell
Els camps que composen aquest taulell són de dos tipus, els normals o manuals que s'han de completar manualment i els calculats que es calculen automàticament.
Els camps que s'han de completar manualment són:

- Concepte: Descripció del concepte del pressupost. Per exemple: "Lloguer de l'espai informàtic". Si hi han conceptes repetits en diferents mesos, es recomana fer servir el mateix concepte per tal de poder fer un seguiment més fàcil.
- Categories Conceptes Pressupostaris: Indica la categoria a la qual pertany la factura, utilitzant els codis de A3ERP. Aquests codis es poden trobar en el workspace de "Fundació .cat".
- Tipus: Despesa o Ingrés
- Data: Els pressuposots es segmenten per mesos. Per tant, cada element del taulell representa un mes del pressupost. En aquest camp s'ha d'indicar el mes al qual pertany el pressupost. Donat que farem servir el camp data es recomana posar el primer dia del mes on es vol que aparegui el pressupost. Per exemple, si volem que el pressupost aparegui al mes de gener de 2023, posarem 01/01/2023.
- Pressupost: El pressupost en € per aquest concepte i mes. Es important recalcar que el pressupost sempre es un nombre positiu. A efectes de compatbilitat hi ha altres camps automàtics que tindran en compte si es un tipus despesa o compra per tal de fer els càlculs correctament i convertir la xifra en positiva o negativa. L'usuari només ha d'indicar el pressupost en € en positiu.
- Factures: connectat al taulell de factures. Un cop pagada la factura es pot actualitzar aquest camp, amb una o mes factures que s'han pagat sobre aquest concepte de pressupost.
- Import a mà: Aquest camp només s'ha d'usar en els casos que no disposem d'una facrtura i s'hagi d'imputar un cost executat de despesa o ingrés. Quan disposem de facrtura (que es el cas recomanat) aquest camp no s'ha d'usar i restarà buit.
- Notes: Indicar consideracions especials d'aquest concepte, com per exemple "no hi ha factura. Es paga desde sistemes i ho gestionen conjuntament amb altres projectes.".

Camps automatitats:

- Estat factura: Camp que reflecteix l'estat de la facturea en el taulell de factures. Aquest camp es calcula automàticament i no es pot modificar manualment.
- Import de la factura: Camp que reflecteix el cost de la factua en el taulell de factures. És el cost de la factura sense IVA.

A continuació et poso altres camps automàtics. Si us plau, En aquest cas et poso la formula i descriu de la millor forma possible el camp i per a que l'usem per exemple en el dashboard de seguiment de pressuposots. També descriu que ens indiquen per aquest camps els totals del taulell

- Pressup despesa: : IF({Tipus}="Despesa", {Pressupost}, 0)
- Pressup. Ingrés: IF({Tipus}="Ingrés", {Pressupost}, 0)
- Ingrés: IF({Tipus}="Ingrés", {Import factura}+{Import a mà},0)
- Despesa: IF({Tipus}="Despesa", {Import factura}+{Import a mà},0)
- Ingrés - Pres.: IF({Tipus}="Despesa", if( {Data} < TODAY(), 0, {Despesa}-{Pressupost}), 0)
- Desviació actual despesa : IF({Tipus}="Despesa", IF(DAYS({Data},TODAY()) < 0, {Despesa}-{Pressupost}, 0), 0)
- Per gastar: IF({Tipus}="Despesa", {Pressupost}-{Despesa}, 0)
- Per ingressar: IF({Tipus}="Ingrés", {Pressupost}-{Ingrés}, 0)
- Pressupost comptable: IF({Tipus} = "Despesa", -1 \* {Pressupost}, {Pressupost})
- Real comptable: IF({Tipus} = "Despesa", -1 \* {Despesa}, {Ingrés})
- Desviació comptable: IF({Tipus} = "Ingrés", {Ingrés},-1\*{Despesa}) -{Pressupost comptable}

- camps que fem servir en el dahsnoard:

Despesa pressupostada total: Pressupost de despesa
Despesa pressup. fins avui: Despesa pressup. fins avui amb filtre fins avui
Despesa pressupostada restant final any: Despesa pressup. fins final any
Despesa real: Despesa
Desviació de despesa actual: Desviació actual de despesa
Pressupost despesa per projecte: Pressupost despesa apilada per projecte (grup)
Gastat en factures per projecte: Despesa apilada per projecte (grup)
Desviació despesa per projecte: desviacio actual de despesa apilada per projecte (grup)
Pressupost despesa vs real per mesos: Area on eix de x és data per mes, dos eixos de Y: Pressup. despesa i despesa
Pressupost despesa vs real acumulat: idem anterior pero acumulat

Usat : Pressup. despesa , despesa, desviació actual de despesa.
