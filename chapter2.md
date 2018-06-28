Nagysebességű valós idejű marker-alapú horgonypont leképezési és illesztési módszertan {#nagyseb}
======================================================================================

TODO: rövid bevezető a fejezethez

Motiváció
---------

TODO: milyen feladatot szeretnénk megoldani? (kevés függőség, egyszerűség, gyorsaság, skálázhatóság a markerek száma szerint, spatial mapping, egyszer végigolvasás, egymagos működés, ...)

Korábbi eredmények, létező megoldások
-------------------------------------

TODO: Releváns kutatások és eredmények (nagyon) rövid összefoglalója
TODO: Releváns létező marker tracking implementációk (Vuforia, ARTK5, ARToolkit, stb.)
TODO: Közös jellemzők és hiányosságok - amennyiben van ilyen.

Alapvetések
-----------

TODO: Kör->ellipszis, alapvetően on-line de rétegzett felépítés milyensége (lásd angol github bevezető pl), 
TODO: alapfogalmak formális bevezetése
TODO: fasttrack algoritmus-osztály bevezetése (2D felismeréshez)
TODO: vázolni, hogy a továbbiakban ezek mentén kialakítunk néhány algoritmus példányt

Kedzeti marker tervek és elképzelések variációi
-----------------------------------------------

TODO: színes markerek 4-es osztással v1 (üres középpel), v2 (nem-üres középpel)
TODO: gradiens-sávos markerek
TODO: Szürke-sávos markerek
TODO: Kutatási irányt befolyásoló tényezők, fő irányt meghatározó okok (pl. nyomtathatóság, kamerák képességei stb.)

Homarea-k, és felismerésük
--------------------------

TODO: alapötlet
TODO: homarea definíciója
TODO: homarea paraméterei és jellemzői
TODO: felismerő algoritmus megadása
TODO: Finomítási lehetőségek és opcionális javátási variációk
TODO: Blur esetén látható "ördögszarv" - definíció, kezelési mód, stb.
TODO: CSAK EMLÍTVE MERT MÁSIK FEJEZET: exponenciális és lineáris függvény közelítési módszer
TODO: implementáció és példaprogram

HoParser 1D markerek és felismerésük
------------------------------------

TODO: 1D markerek és marker-középpontok definíciója
TODO: Alapötlet: Kapcsolat a fordítással, nyelvek parzolásával - verem használat lehetősége
TODO: 1D marker paraméterei és jellemzői (bnf-szerű leírás)
TODO: felismerő algoritmus megadása
TODO: Finomítási lehetőségek és opcionális javátási variációk
TODO: Blur esetén tapasztalható túl apró homarea területek (mikrosávok) - definíció, kezelési mód stb.
TODO: Alacsony kontrasztból fakadó homarea-egyesülési hibák (sávszám-csökkentés és kontraszt növelés a markerben)
TODO: Belső és külső középpont definíciója (belső kör két széle között vs. marker két széle)
TODO: Projekció általi középpont torzulás javításának lehetősége a belső és külső középpont arányai alapján
TODO: Algoritmus féloldalasságának előnyei és hátrányai (balról-jobbra parzol, ezért jobbról sokkal érzéketlenebb a hibákra, hiányzó fehér területre stb.)

MCParser 2D markerek és felismerésük
------------------------------------

TODO: A kör-projekciók vertikálisan képezhető középvonalának tulajdonsága
TODO: Alapötlet: 2D marker középpont meghatározás
TODO: 2D marker paraméterei és jellemzői (bnf-szerű leírás)
TODO: Sáv-szám hibák javítása
TODO: 

Paraméterezések és a felfedezett felismerési hibák
--------------------------------------------------

TODO: Algoritmus-paraméterek táblázatos leírása
TODO: Ezt esetleg inkább fejezetenként???
TODO: motion blur probléma hatásai, gyors recover...

Információ kódolási lehetőségek és azok megbízhatósága
------------------------------------------------------

TODO: Sávok száma?
TODO: Színek használata 1 (szürke-sávosból színsávos eset)
TODO: Színek használata 2 (színes markerek esete)
TODO: Hybrid-kód (pl. QR kóddal)
TODO: Geometriai pozíción alapuló kódolás
TODO: Hybrid 

Algoritmus variációk 1
----------------------

TODO: QR-pozícionáláshoz való átalakítás és paraméterezés
TODO: itt meg lehet említeni, hogy 3D közelítés is adható 3 pontból.. lásd később...

Algoritmus variációk 2
----------------------

TODO: Homogén színekkel történő felismerés előnyei és hátrányai a tapasztalatok fényében

LightGun - egy lehetséges használati eset
-----------------------------------------

TODO: 

3D póz-közelítések
------------------

TODO: motiváció
TODO: pnp, p3p, p2p, p4p, stb.
TODO: egyéb módszerek rövid összefoglalója és igényei
TODO: "körös módszer" - lásd paper-ek között...



...TODO...
