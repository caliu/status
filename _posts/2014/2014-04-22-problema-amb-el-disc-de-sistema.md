---

title: Problema amb el disc de sistema
layout: default

---

Aquest matí, cap a quarts de 12 he actualitzat els paquets pendents que afecten a les màquines virtuals i he reiniciat el servidor.
La sorpresa ha estat que la màquina virtual que serveix la web de Caliu no arrencava i no hi havia forma que el disc de rescat trobés el sistema.
Després d'investigar una mica he forçat un `e2fsck` al disc de sistema per corregir els problemes que feien que no arrenqués correctament.

Com ha passat això? Bé doncs, resulta que el disc de sistema no està particionat sinó que conté directament el sistema de fitxers,
és a dir, `/dev/vdb` és `/` directament, sense cap taula de particions.
Això que em va semblar una optimització que permetria fer crèixer en calent el disc sense reiniciar la màquina virtual resulta ser una molt mala idea:
el disc de rescat no sap trobar aquesta partició i no ofereix la possibilitat de muntar-la.
El procés de *boot* de la màquina virtual la munta però tampoc li acaba d'agradar i no ha estat capaç d'executar-hi el `e2fsck` automàticament.
Quan investigava què passava, pensava que el disc de sistema estava amb LVM i no entenia per què no el detectava.
Fins que he recordat que el logwatch envia cada dia un informe d'ocupació del disc i aleshores he mirat quins eren els dispositius reals que munta el sistema.
Un cop vist que el dispositiu del sistema era `/dev/vdb`, ha estat immediat forçar-hi una comprovació i han començat a sortir errors pendents de corregir.
La resta ja la sabeu... El servidor torna a funcionar.

/alexm
