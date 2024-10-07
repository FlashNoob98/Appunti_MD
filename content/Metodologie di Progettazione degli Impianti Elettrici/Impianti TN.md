Nel caso di impianti TN è presente un unico collegamento a terra in cabina mediante una resistenza $R_N$, viene distribuito il neutro come conduttore di protezione (conduttore PEN, sistema TN-C) o eventualmente un conduttore di protezione separato (sistema TN-S).

In questo caso si considera la resistenza del conduttore di fase e protezione per calcolare la corrente di guasto. In caso di contatto la persona è in parallelo alla maglia di guasto a bassa impedenza con una sua resistenza serie $R_B$ e $R_{EB}$, l'impedenza dell'anello di guasto è data dalla serie dell'impedenza del conduttore di fase e quello di protezione.
Calcolando l'equivalente di Thevenin tra il punto di contatto e la terra, in assenza di contatto la resistenza $R_N$ non è attraversata da corrente, dunque
$$
U_{eq} = U_{0} \frac{\dot{Z}_{p}}{\dot{Z}_{p}+\dot{Z}_{f}}
$$
mentre l'impedenza equivalente:
$$
\dot{Z}_{eq} = R_{N} + \frac{\dot{Z}_{p}\dot{Z}_{f}}{\dot{Z}_{p}+\dot{Z}_{f}}
$$
Una prima approssimazione prevede che la $U_{eq}$ è data dal partitore dei due conduttori, prossima alla tensione a vuoto, si potrebbe ridurre soltanto riducendo il modulo di $\dot{Z}_{p}$ aumentandone la sezione, per valori tecnicamente inaccettabili, anche le correnti di guasto sarebbero poi inaccettabili.