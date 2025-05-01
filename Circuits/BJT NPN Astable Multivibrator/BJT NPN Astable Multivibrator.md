## Circuit
![[schematic.jpeg]]

This is an example of an [[Multivibrator#Astable|astable multivibrator]] implemented using two NPN transistor set up as Common Emitter Amplifier.
## Operation 

In each state, one transistor is switched on and the other is switched off. Accordingly, one fully charged capacitor discharges slowly and, at the same time, the other empty capacitor quickly charges thus restoring its charge. The first capacitor acts as a time-setting capacitor and the second prepares to play this role in the next state. The circuit operation is based on the fact that the forward-biased base-emitter junction of the switched-on bipolar transistor can provide a path for the capacitor restoration.
#### State 1 ($Q_1$ is switched on, $Q_2$ is switched off)
![[schematic-state1.jpeg]]
![[Q1-outputAndBase.jpg]]

In the beginning, the capacitor $C_1$ is fully charged (in the previous State 2) to the power supply voltage $V$. $Q_1$ is _on_ and connects the left-hand positive plate of $C_1$ to ground. As its right-hand negative plate is connected to $Q_2$ base, a maximum negative voltage (-$V$) is applied to $Q_2$ base that keeps $Q_2$ firmly _off_. $C_1$ begins discharging via the high-value base resistor $R_2$, so that the voltage of its right-hand plate (and at the base of $Q_2$) is rising from below ground (-$V$) toward +$V$. As $Q_2$ base-emitter junction is reverse-biased, it does not conduct, so all the current from $R_2$ goes into $C_1$. Simultaneously, $C_2$ that is fully discharged and even slightly charged to 0.6 V (in the previous State 2) quickly charges via the low-value collector resistor $R_4$ and $Q_1$ forward-biased base-emitter junction (because $R_4$ is less than $R_2$, $C_2$ charges faster than $C_1$). Thus $C_2$ restores its charge and prepares for the next State $C_2$ when it will act as a time-setting capacitor. $Q_1$ is firmly saturated in the beginning by the "forcing" $C_2$ charging current added to $R_3$ current. In the end, only $R_3$ provides the needed input base current. The resistance $R_3$ is chosen small enough to keep $Q_1$ (not deeply) saturated after $C_2$ is fully charged.

When the voltage of $C_1$ right-hand plate ($Q_2$ base voltage) becomes positive and reaches 0.6 V, $Q_2$ base-emitter junction begins diverting a part of $R_2$ charging current. $Q_2$ begins conducting and this starts the avalanche-like positive feedback process as follows. $Q_2$ collector voltage begins falling; this change transfers through the fully charged $C_2$ to $Q_1$ base and $Q_1$ begins cutting off. Its collector voltage begins rising; this change transfers back through the almost empty $C_1$ to $Q_2$ base and makes $Q_2$ conduct more thus sustaining the initial input impact on $Q_2$ base. Thus the initial input change circulates along the feedback loop and grows in an avalanche-like manner until finally $Q_1$ switches off and $Q_2$ switches on. The forward-biased $Q_2$ base-emitter junction fixes the voltage of $C_1$ right-hand plate at 0.6 V and does not allow it to continue rising toward +$V$.
#### State 2 ($Q_1$ is switched off, Q2 is switched on)

![[schematic-state2.jpeg]]
Now, the capacitor $C_2$ is fully charged (in the previous State 1) to the power supply voltage $V$ with the polarity shown in Figure 1. $Q_2$ is _on_ and connects the right-hand positive plate of $C_2$ to ground. As its left-hand negative plate is connected to $Q_1$ base, a maximum negative voltage (-$V$) is applied to $Q_1$ base that keeps $Q_1$ firmly _off_. $C_2$ begins discharging (reverse charging) via the high-value base resistor $R_3$, so that the voltage of its left-hand plate (and at the base of $Q_1$) is rising from below ground (-$V$) toward +$V$. Simultaneously, $C_1$ that is fully discharged and even slightly charged to 0.6 V (in the previous State 1) quickly charges via the low-value collector resistor $R_1$ and $Q_2$ forward-biased base-emitter junction (because $R_1$ is less than $R_3$, $C_1$ charges faster than $C_2$). Thus $C_1$ restores its charge and prepares for the next State 1 when it will act again as a time-setting capacitor...and so on... (the next explanations are a mirror copy of the second part of State 1).
## Multivibrator frequency

The duration of state 1 (low output) will be related to the time constant $R_2C_1$ as it depends on the charging of $C_1$, and the duration of state 2 (high output) will be related to the time constant $R_3C_2$ as it depends on the charging of $C_2$. Because they do not need to be the same, an asymmetric duty cycle can be achieved.

The voltage on a capacitor with non-zero initial charge is: 

$$\Large V_{cap}(t) = [(V_{init} - V_{charging}) \cdot e^{-t/RC}] + V_{charging}$$

Looking at $C_2$, just before $Q_2$ turns on, the left terminal of $C_2$ is at the base-emitter voltage of $Q_1$ ($V_{BE-Q1}$) and the right terminal is at $V_{CC}$. The voltage across $C_2$ is $V_{CC}$ minus $V_{BE-Q1}$.  The moment after $Q_2$ turns on, the right terminal of $C_2$ is now at approximately 0 V which drives the left terminal of $C_2$ to  $-(V_{CC} - V_{BE-Q1})$. From this instant in time, the left terminal of $C_2$ must be charged back up to $V_{BE-Q1}$. How long this takes is half our multivibrator switching time (the other half comes from $C_1$).
In the charging capacitor equation above, substituting:

$\large V_{cap}(t) = V_{BE-Q1}$
$\large V_{init} = V_{BE-Q1} - V_{CC}$
$\large V_{charging} = V_{CC}$

results in:

$$\Large V_{BE-Q1}(t) = [(V_{BE-Q1} - 2V_{CC}) \cdot e^{-t/RC}] + V_{CC}$$

solving for $t$ results in:

$$\Large t = -RC \cdot \ln(\cfrac{V_{BE-Q1} - V_{CC}}{V_{BE-Q1} - 2V_{CC}})$$

If the supply voltage $\large V_{CC}$ is much greater that the base emitter voltage of $\large Q_1$ ($\large V_{CC} >> V_{BE-Q1}$), the equation can be simplified to:

$$\Large t = -RC \cdot \ln(\cfrac{1}{2}) = RC \cdot \ln(2)$$

The period of each _half_ of the multivibrator is therefore given by $\large t = RC \cdot \ln(2)$.

The total period of oscillation is given by:

$$\Large T = t_1 + t_2 = \ln(2) \cdot (R_2C_1 + R_3C_2)$$
$$\Large f = \cfrac{1}{T} = \cfrac{1}{\ln(2) \cdot (R_2C_1 + R_3C_2)}$$

If $\large R_2 = R_3$ and $\large C_1 = C_2$, the equation can be simplified to:

$$\Large f = \cfrac{1}{T} = \cfrac{1}{\ln(2) \cdot 2RC$}$$
## Initial power-up

When the circuit is first powered up, neither transistor will be switched on. However, this means that at this stage they will both have high base voltages and therefore a tendency to switch on, and inevitable slight asymmetries will mean that one of the transistors is first to switch on. This will quickly put the circuit into one of the above states, and oscillation will ensue. In practice, oscillation always occurs for practical values of _R_ and _C_.

However, if the circuit is temporarily held with both bases high, for longer than it takes for both capacitors to charge fully, then the circuit will remain in this stable state, with both bases at 0.60 V, both collectors at 0 V, and both capacitors charged backwards to −0.60 V. This can occur at startup without external intervention, if _R_ and _C_ are both very small.
## Design consideration

To approach the needed square waveform, the collector resistors have to be low in resistance. The base resistors have to be low enough to make the transistors saturate in the end of the restoration ($\large R_B < β.R_C$)
#### Protection components

If the supply voltage $V$ is greater that the base-emitter breakdown voltage $V_{BE}$, protection diode should be connected in series with either the base or the emitter to protect the transistor and prevent the diode from charging through ground.
![[schematic-protection-diode 1.jpeg]]

Base voltage $V_B$ without protection diode and a supply voltage $V$ of 18 V; the negative $-V$ spike is clamped to $-V_{BE}$ as the capacitor $C_1$ is rapidly charged through the $BE$ junction.
![[BE-junctionBreakdown.jpg]]
## Images 

The circuit output voltage on the collector of collector of $Q_1$ and $Q_2$.
![[outputs.jpg]]

The base voltage of transistors $Q_1$ and $Q_2$.
![[TransistorBases.jpg]]
#### Sources
- https://en.wikipedia.org/wiki/Multivibrator