Általános és alátámasztott erőforrás-igény predikció
====================================================

TODO: Rövid bevezető a fejezethez: optimalizációk és profilozás

Célkitűzések
------------

TODO

Implementációs nyelv megválasztása
----------------------------------

TODO: Miért C++11: Move szemantika, template-ek, értékalapú programozás, low-level lehetőségek, járulékos költség nélküli absztrakciók, template nyelvi lehetőségek

Fast-track algoritmusok hatékonysága
------------------------------------

TODO: Általános keretek a számításokhoz

Algoritmikus optimalizációk
---------------------------

TODO: Az algoritmusaink futását befolyásoló tényezők és azok empirikus vizsgálata (pl. általában: pixelek száma vs. Homer-ből kieső kék pontok száma vs. 1D markerek száma vs. 2D marker szám arányok!)
TODO: pontosságtartó optimalizációk (pl. fastforwardlist - csak említve, mert később külön van!)
TODO: pontosságot, vagy működést módosító optimalizációk (pl. egyszerűbb kezelése az ördögszarv jelenségeknek, vagy minden második sor, és sorokban minden második pixel kezelése, esetleg kisebb felbontás használata)

Cél-architektúrák sajátosságai
------------------------------

TODO: A célrendszerek - x86 low-end rendszerek, beágyazott ARM rendszerek, Hololens és más AR headset-ek - architekturális sajátosságai
TODO: Instruction és data cache optimalitás szükségessége: ábra arról, hogy ez mennyire számít, melyik réteg elérése mennyire lassít + ábra arról, hogy 
TODO: Adaptív órajelen működő eszközök problémái a profilozásban (nem gyorsul fel a proci!)

Fast-track algoritmusok többszálú párhuzamosítási módjai
--------------------------------------------------------

TODO: scanline-onkénti feldolgozhatóság több szálon
TODO: Vigyázni: az algoritmus online-sága vs. párhuzamosítottsága egymás ellen képes hatni!
TODO: Adatcsatorna (pipeline) párhuzamosítási lehetőségek
TODO: "NUMA" - Non-Uniform-Memory-Access
TODO: Lock-free megoldások fajtái és alkalmazhatósága

Egyéb párhuzamosítási lehetőségek
---------------------------------

TODO: Egyedi HW 1: Saját cél-FPGA, vagy hardver lehetősége esetén érdekes műveletek
TODO: Egyedi HW 2: Scanline-processzorok használata (masszív párhuzamosság?)
TODO: GPU gyorsítás lehetőségei?
TODO: SIMD, vagy MMX gyorsítási lehetőségek
TODO: Kimérhető instruction level parallelism optimalizációs lehetőségek

Egyedi előre láncolt lista típus
--------------------------------

TODO: motiváció
TODO: megoldás módja
TODO: indexelés típusbiztos de no-cost absztrakciója


Algoritmusok implementációinak optimalizációs lépései
-----------------------------------------------------

TODO: Homer
TODO: HoParser
TODO: MCParser
TODO: instruction cache optimalizálás a forró kódrészlethez
TODO: Időmérő pontok
TODO: CImg használatából fakadó lassúság kiküszöbölése
TODO: Kamera frame-rate probléma felderítése és megoldása
TODO: kcachegrind profilozás
TODO: perf elemzések
TODO: branch prediction heurisztikák
TODO: csak-integer számítások használatának jelentősége
TODO: inline függvények, NOINLINE függvények
TODO: költséges műveletek elhagyása, vagy cseréje (div helyett más, megfelelő értékek használata, hogy shift lehessen stb.)

TODO
----

TODO: egyéb pontok - itt át kell gondolni ezt még
