Al fine di permettere il [[Controllo digitale|controllo]] di un [[Dinamica dei convertitori elettrici|convertitore]] può essere utile calcolare la funzione di trasferimento di un sistema.
Si suppone il sistema a regime o comunque quasi-stazionario, quindi 
$\vec{X}_{0}=\vec{0}$, un generico sistema dinamico viene così rappresentato nel dominio di Laplace:
$$
\left\{
\begin{aligned}
\frac{d}{dt}\delta \vec{x} = s\delta \vec{x} &=A_{s}\delta \vec{x} + B_{s}\delta d\\
\vec{y} &= C\delta \vec{x}
\end{aligned}
\right.
$$
dove in questo caso $\delta d$ è il singolo ingresso del sistema, $\vec{y}$ il vettore delle uscite.
Sviluppando la prima:
$$
\left( s\hat{I} -A_{s}\right)\delta \vec{x} = B_{s}\delta d \Rightarrow \delta \vec{x} = (B_{s}\cdot \delta d)(s\hat{I}-A_{s})^{-1}
$$
se $\delta y$ è uno scalare si può ricavare una relazione ingresso-uscita:
$$
\frac{\delta y}{\delta d} = C\left[(s\hat{I}-A_{s})^{-1}\cdot B_{s}\right]
$$
Quella appena ricavata viene definita funzione di trasferimento $F(s)$ del sistema.

## FdT dei convertitori
Per i convertitori DC-DC è possibile utilizzare una formula generale, variando opportunamente i parametri:
$$
\frac{\delta v_{C}}{\delta d} = G_{d 0} \frac{1-\frac{s}{\omega_{z}}}{1 + \frac{s}{Q\omega_{0}} + \frac{s^2}{\omega_{0}^2}}
$$
con:


<center>

|            |        $G_{d0}$        |     $\omega_{z}$      |       $\omega_{0}$        |             $Q$              |
| :--------: | :--------------------: | :-------------------: | :-----------------------: | :--------------------------: |
|   Boost    |  $\frac{V_{C}}{1-D}$   | $\frac{R(1-D)^2}{L}$  | $\frac{1-D}{\sqrt{ LC }}$ | $(1-D)R\sqrt{ \frac{C}{L} }$ |
|    Buck    |    $\frac{V_c}{D}$     |       $\infty$        |          $1/LC$           |   $R\sqrt{ \frac{C}{L} }$    |
| Buck-Boost | $\frac{V_{C}}{D(1-D)}$ | $\frac{(1-D)^2R}{DL}$ | $\frac{1-D}{\sqrt{ RC }}$ | $(1-D)R\sqrt{ \frac{C}{L} }$ |
</center>
