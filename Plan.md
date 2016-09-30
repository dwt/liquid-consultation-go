Erste Abbildung von Go Zügen auf Voterunner
* Voterunner bildet eine Entscheidung als ‚Thema‘ auf eine URL ab. Bei jeder Entscheidung kann jeder Teilnehmer nur eine Stimme, in form eines Kommentars, abgeben.
* Jeder Go-Zug kann auf eine URL abgebildet werden, in der die Diskussion und die Abstimmung stattfindet.
* Man kann für einen Zug stimmen, oder einen neuen Zug vorschlagen.
* Im Kommentar kann man erklären wieso dieser Zug gut ist.
* Mit der Zustimmung für einen Zug kann man kommentieren welcher Aspekt von der Begründung betont werden soll
* Jeder kann nur seinen eigenen Kommentar ändern
* Erhaltung der Fähigkeit von ConGo dass man erst selbst einen Zug auswählen muss, bevor man sieht was andere gewählt haben.

Zu testen:
* Funktioniert es nur an einer Stelle pro zur seinen Kommentar mit seiner Stimme zusammen abgeben zu können?
* Benötigt es eine Funktion an mehreren Stellen kommentieren zu können - ohne das kommentierte Argument damit zu unterstützen? Wenn ja, wie viel Besser ist das?
* Funktioniert die Darstellung von Voterunner als Baum Thread-Baum, braucht es zusätzliche Intelligenz um bestimmte Bäume / Sub-Bäume per default einzuklappen?

Weitere Integrationsschritte für Voterunner:
* Wie lässt sich die Information über Delegationsgewichte am besten zwischen Zügen/ Spielen übertragen?
* Wie kann man Delegationen am besten als Informationsmittel nutzen um über das Spiel zu lernen / davon Begeistert zu werden?
* Wie kann man die Erfahrung die ein Spieler hat, nutzen um seine Diskussionsbeiträge besser sichtbar zu machen? Wie gut funktioniert das?
* Ist es möglich aus zurückliegenden Kommentaren Zügen / Spielen einen Spiel-Rang (Kyu/ Dan) zu berechnen?
* Kann man Zug-Vorschläge zwischen Zügen portieren, wenn Sie immer noch relevant sind? Lässt sich die Diskussion zu diesem Zug mit übertragen? Wie lässt sie sich aktualisieren / auf Aktualität überprüfen?
* Wie lässt sich die Diskussion der Züge am besten auf dem Spielbrett visualisieren? Wie viele Unterstützer hat ein Zug, wie will man aus dem Zug profitieren, wie viele Punkte erwartet man sich daraus, welcher Gefahr möchte man begegnen, …
* Wie lassen sich Zugfolgen am besten unterstützen? Kann das Spiel beschleunigt werden, indem man über ganze Zugfolgen abstimmt? Wenn die Gegenseite die gleiche Zugfolge abgestimmt hat, kann z.B. ein Fast-Forward erfolgen, bis zum nächsten Zug der unterschiedlich ist.
* Lassen sich Einflussgebiete / Sichere Punkte, der Leben / Tod-Status von Gruppen visualisieren?
* Wie lässt sich die Diskussion über Einflussgebiete oder Züge in bestimmten Bereichen des Spielbrettes visualisieren?
* Lässt sich quantifizieren wie sich die eigene Spielstärke durch die Teilnahme / während der Teilnahme an LCG Spielen verändert?

Entwicklung der API um zwischen Taktgeber (z.B. ConGo) und Abstimmungswerkzeug (z.B. Voterunner)

Problem: Bisher sind eigentlich alle Abstimmungswerkzeuge integriert entwickelt. D.h. man erhält eine Oberfläche über die man Probleme zur Abstimmung stellen kann und ein integriertes Abstimmungs-Werkzeug. Das hat den Nachteil, das es sehr schwer ist verschiedene Abstimmungs-Methoden zu integrieren und zu Vergleichen - in der Regel hat man als Anwender hier keine oder nur sehr beschränkte Auswahlmöglichkeiten und muss für Experimente regelmäßig dass ganze Tool austauschen. (Siehe z.B. Doodle)

Ziel: Einfache Integration von Abstimmungswerkzeugen in beliebige Taktgeber.

Definitionen: Als Taktgeber bezeichne ich hier Werkzeuge die Probleme Stellen und bestimmen wann die Abstimmung darüber ausgewertet wird. Als Abstimmungswerkzeuge bezeichne ich Werkzeuge die Abstimmungsalgorithmen implementieren.

Offen Fragen:
* Wie und wo ist in dieser Aufteilung ein Diskurssystem einzubauen?
    * Auf der Taktgeber-Seite bedeutet das man die Informationen aus dem Abstimmungswerkzeug nicht / schlecht verwenden kann um den Diskurs anzuzeigen.
    * Auf der Abstimmungs-Seite, bedeutet das es nicht / schwer möglich ist den Diskurs zu behalten wenn man das Abstimmungswerkzeug auswechselt
* Wie sieht die 

Was wird durch die API ermöglicht?
* Austausch / Kombination verschiedener Abstimmungswerkzeuge für eine Entscheidung. Vorstellbar ist von mehreren Vorschlägen zuerst mit einem System wie ‚Bag of Lemmons‘ / Veto die besonders schlechten Vorschläge auszusortieren. (Beispiel: Eine Gruppe von Freunden will sich auf einen Film einigen: Einer der Teilnehmer will definitiv keinen Horrorfilm ansehen und kann dies mit einem Veto ganz zu Anfang aussortieren. Danach kann mit einem anderen System z.B. Ranked Voting der Film gefunden werden der die größte Zustimmung von allen Teilnehmern hat.
* Ausprobieren von verschiedenen Abstimmungsmethoden ohne große Kosten/ Aufwand (Auswahl eines anderen Tools, Neue Accounts, mitnehmen aller Teilnehmer, …)
* Einfache Entwicklung von Abstimmungs-Werkzeugen, die mit Erfüllung der API viel weniger Komplex sein können und in viele Taktgeber Werkzeuge integriert werden können.

Weitere Abstimmungswerkzeuge die Entwickelt werden können:
* Bag of Lemons / Veto: Schnelles Ausschließen von inakzeptablen Optionen. Wichtig ist hier, dass man ein Veto nicht leichtfertig aussprechen soll - es soll nur verwendet werden wenn man eine Option absolut unterstützt werden können.
