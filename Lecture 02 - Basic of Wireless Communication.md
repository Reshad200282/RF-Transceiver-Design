Lecture 02 - Basic of Wireless Communication - II
<img width="1199" height="570" alt="image" src="https://github.com/user-attachments/assets/4bab5172-c74a-4a9a-ae4e-828c64b29e7f" />

\section*{Why Inductors Are Low-Q Components at RF}

Inductors are not inherently low-Q devices, but at radio frequencies their losses increase rapidly and parasitic effects dominate, causing the effective Q to drop significantly.

\subsection*{Quality Factor of an Inductor}
The quality factor of an inductor is defined as:
\[
Q = \frac{\omega L}{R_{\text{loss}}}
\]
where $\omega$ is the angular frequency, $L$ is the inductance, and $R_{\text{loss}}$ represents the total effective resistance.

At RF, $R_{\text{loss}}$ increases faster than $\omega L$, resulting in a reduced Q.

\subsection*{Reasons for Low Q at RF}

\subsubsection*{Skin Effect}
At high frequencies, current flows only near the surface of the conductor:
\begin{itemize}
\item Reduced effective cross-sectional area
\item Increased AC resistance
\item Higher resistive loss
\end{itemize}

\subsubsection*{Proximity Effect}
Magnetic fields from adjacent turns cause non-uniform current distribution:
\begin{itemize}
\item Current crowding
\item Increased resistive loss
\item Further reduction in Q
\end{itemize}

\subsubsection*{Parasitic Capacitance and Self-Resonance}
Inductors exhibit parasitic capacitance due to:
\begin{itemize}
\item Turn-to-turn capacitance
\item Pad and package capacitance
\end{itemize}

This leads to a self-resonant frequency (SRF). Near SRF, the Q drops sharply, and above SRF the inductor behaves capacitively.

\subsubsection*{Core Losses}
Magnetic cores introduce:
\begin{itemize}
\item Eddy current losses
\item Hysteresis losses
\item Reduced permeability at high frequency
\end{itemize}

Therefore, RF inductors are typically air-core.

\subsubsection*{Radiation Losses}
At RF, inductors may radiate electromagnetic energy:
\begin{itemize}
\item Stored energy is lost as radiation
\item Effective loss increases
\item Q decreases
\end{itemize}

\subsection*{Comparison with Capacitors}
Capacitors generally have higher Q at RF because they:
\begin{itemize}
\item Do not use wound conductors
\item Exhibit lower parasitic resistance
\item Can achieve very high Q (e.g., NP0/C0G, mica)
\end{itemize}

\subsection*{Typical Q Values}
\begin{itemize}
\item Audio inductors: $Q \approx 100\text{--}1000$
\item RF inductors: $Q \approx 10\text{--}100$
\item Microwave inductors: $Q < 20$
\end{itemize}

\subsection*{RF Design Guidelines}
\begin{itemize}
\item Use the smallest inductance possible
\item Operate well below SRF
\item Prefer air-core or planar inductors
\item Use distributed elements at high frequencies
\end{itemize}
