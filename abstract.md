Kivonat {.unnumbered}
=======

A dolgozat témája egy új megközelítésű, egyszerű és gyors, elsősorban 2D marker felismerésre és követésre szolgáló valós-idejű algoritmus-család kísérleti kidolgozása, illetve kezdeti elemzése. Már nagy számban léteznek olyan algoritmusok, amelyek egy kamera mozgókép alapján követnek adott pontokat, de ezek mind az elvárásainktól eltérő kialakításuak voltak. A korábbi megoldások zöme jellemzően nagy-méretű függőségekkel és komplex algoritmusokkal dolgozik. Ezzel szemben mi olyan megoldásokat keresünk, amelyek minimális, vagy semmilyen függőséggel sem rendelkeznek a bonyolult matematikai keretrendszerekhez és optimalizált, de egyszerű és célszerű algoritmusokat használnak a korábbi bonyolult iteratív képfelismerési módszerekkel szemben. Fontos továbbá, hogy a korábbi eljárásokkal ellentétben azt is célul tűzzük ki, hogy az algoritmusok sebessége és tárigénye jól skálázódjon a markerek számának képen látható megnövekedésével. Sok algoritmus akár 3D póz-meghatározásra is képes, de a feldolgozási sebesség általában a legjobb esetben is lineárisan romlik a gyakorlatban a markerek számának növekedésével, ami sok alkalmazáshoz nem megfelelő.

A kapott módszerek és eljárások használhatósága a következő területeken várható:

* 2D markerek (akár tömeges) feismerése és követése
* 3D póz-meghatározás, több markerből építhető kompozit 3D markerrel
* Egyedi QR-alapú 3D-póz meghatározás
* Beltéri környezet-leképezés és navigáció markerekkel (spatial mapping)

A dolgozattal célunk továbbá, hogy a megadott új algoritmus-családhoz konkrét példányokat is rendeljünk, amelyek optimalizációs vonzatai különálló fejezetben láthatók. Ennek megfelelően a dokumentum alapvetően két részből áll - az algoritmuscsalád és példányok bemutatásából, illetve ezek részletes megvalósítási és optimalizációs elemzéséből.

Abstract {.unnumbered}
========

The main topic described in this thesis document is an experimental development of a new simple and fast algorithm-family primarily useful for real-time 2D marker recognition and tracking and its prelimenary analysis. Algorithms that track points-of-interests in camera frames are available in good quantity and variety, however all those algorithms have certain disabilities or problems according to our requirements. Most of the earlier solutions rely on large APIs with complex algorithms and dependencies. In contrast to that, we are searching solutions to be implemented with minimal-to-nothing dependencies and use algorithms made of simple building blocks instead of complicated iterative computer vision approaches. Alongside this we set up an important goal for our algorithms being space- and time-scalable with respect to the number of markers seen (and tracked) on the picture frames. Many good algorithms are there to even get 3D pose estimates, but the processing speed usually degrades linearly with the increase of the number of markers in the best case - which is not good-enough for many application areas.

The resulting methods and processes can be of interest for:

* (Possibly high-quantity) tracking and recognition of 2D markers
* 3D pose estimation using composite 2D markers
* Unique QR-code based 3D pose estimation
* Indoor spatial mapping and navigation

Our goal for this document also includes the definition of some specific algorithm instances with their implementation and code-optimization techniques described separately in a designated chapter. For this purpose the document is structured as two parts: first the definition of the algorithm family and instances, then the optimization methods and description of profiling for realtime performance.
